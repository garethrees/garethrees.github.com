---
layout: post
title: Ordered FAQ Section in Rails
meta: Some Ruby on Rails code to manage an FAQ page with sections.
---

# {{ page.title }}

Lets say you want an FAQ page with sections and orderable FAQs belonging to each section:

    <!-- About Section -->
    <h1>About</h1>

    <!-- First FAQ in About -->
    <h2>What are you about?</h2>
    <p>Blah blah blah</p>

    <!-- Second FAQ in About -->
    <h2>Who are you?</h2>
    <p>I am me</p>

    <!-- Payment Section -->
    <h1>Payment</h1>

    <!-- First FAQ in Payment -->
    <h2>How much do you cost?</h2>
    <p>£££</p>

    <!-- Second FAQ in Payment -->
    <h2>When will you bill me?</h2>
    <p>Today</p>

Here's the model:

    class Faq < ActiveRecord::Base

      SECTIONS = %w(About Payment Terms)

      validates_presence_of :title, :body, :section

      before_create :set_default_position

      named_scope :ordered, :order => 'faqs.position ASC'

      def increment_position
        # Find all the FAQs for the section
        faqs = Faq.ordered.find_all_by_section(section)

        # Only increment if current FAQ is not the only FAQ or the last FAQ
        unless faqs.size == 1 || faqs.last == self        
          # find where the current FAQ is in the array
          current_position = faqs.index(self)
          # find the next FAQ in the array (to get its position)
          next_faq = faqs.at(current_position + 1)
          # save the current_position temporarily
          next_faq_position = next_faq.position
          # set the next_faq's position to the current_position
          next_faq.update_attribute(:position, position)
          # set the current FAQ's position to the next_faq's position before the 
          # swap
          self.update_attribute(:position, next_faq_position)
        end
      end

      private

      # Sets position to 1 if it is the first FAQ of a section
      # Sets position +1 greater than the position of the last FAQ in a section
      def set_default_position
        faqs = Faq.ordered.find_all_by_section(section)
        if faqs.any?
          self.position = faqs.last.position + 1
        else
          self.position = 1
        end
      end

    end

When you create an FAQ you need to supply the `title` and `body` of the FAQ, and the `section` it will appear in.

    @faq = Faq.new(:title   => 'Who are you?'
                   :body    => 'I am me',
                   :section => 'About')

Before saving, the FAQ will be assigned a `position`. If its the first in a section, the position will be `1`, otherwise it will be the position of the last FAQ in the section + 1.

    @faq.save
    @faq.position
    # => 1

    @faq = Faq.new(:title   => 'What are you about?'
                   :body    => 'Blah blah blah',
                   :section => 'About')
    @faq.save
    @faq.position
    # => 2

What if we want to make the last FAQ we created the first in the section?

    @faq = Faq.find_by_title('Who are you?')
    @faq.increment_position

    Faq.ordered.find_all_by_section('About').each { |f| puts f.title }
    # => What are you about?
    # => Who are you?

You can hook this up to a new controller action to allow an admin to click an icon to move the FAQ down the pile.

    def increment_position
      @faq = Faq.find(params[:id])

      respond_to do |format|
        if @faq.increment_position
          flash[:confirmation] = 'FAQ was successfully reordered'
          format.html { redirect_to admin_faqs_path }
        else
          flash[:notice] = 'Could not update the increment_position of this FAQ'
          format.html { redirect_to admin_faqs_path }
        end
      end
    end

<!-- TODO: Animated GIF of updating -->

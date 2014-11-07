---
layout: post
title: Use Rails Helpers for Complex View Components
---

# {{ page.title }}

Rails helpers are a great way to remove complexity from your templates.

During an upgrade of Micro's [Group Giving](http://www.worldvisionmicro.org/groups) interface we needed a progress checkbox list to illustrate whether the group owner has completed all the tasks to complete the group creation.

!["Progress checkboxes"](/images/posts/micro-group-giving-checklist.jpg "Progress checkboxes")

    def group_creation_checklist(group)
      content = content_tag :h3, "Checklist"

      content += content_tag :ul, :class => "group_creation_checklist" do
        css_class = group.new_record? ? "incomplete" : "complete"
        list = group_creation_checklist_item('Created Group', css_class)

        css_class = if group.about.present? && group.goal.present? && group.location.present?
                      "complete"
                    else
                      "incomplete"
                    end
        list += group_creation_checklist_item('Described Group', css_class)

        css_class = group.group_image.present? ? "complete" : "incomplete"
        list += group_creation_checklist_item('Added Photo', css_class)
      end

      content += content_tag :ul, :class => "group_creation_checklist" do
        if group.current_fundraiser
          css_class = group.current_fundraiser.loans.size >= 1 ? "complete" : "incomplete"
        else
          css_class = "incomplete"
        end

        list = group_creation_checklist_item('Reserved Entrepreneur', css_class)

        css_class = group.donations.size >= 1 ? "complete" : "incomplete"
        list += group_creation_checklist_item('Made My First Donation', css_class)
    

        css_class = 'incomplete'
        list += group_creation_checklist_item('Invited Members', css_class)
      end

      content += content_tag :div, '', :class => 'clearing'
    end

    def group_creation_checklist_item(text, css_class)
      content_tag :li, :class => css_class { text }
    end



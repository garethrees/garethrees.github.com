---
layout: post
title: Book Notes – The Design of Everyday Things
---

# {{ page.title }}

<!--
Some in-progress notes of [Community Building on The Web](http://amzn.eu/bLMM60u).

Seems really good so far, if you keep the following in mind:

- Some of the terminology is old, like "cyberspace" and "hubbub"
- Tool examples are outdated

Most of the important ideas seem reasonably relavent today though.

![Book cover of Community Building on The Web](/images/posts/community-building-on-the-web.jpg)
-->

## Preface

**Lessons from DOET**

- **It's not your fault:** If a user is having trouble interacting with something, the design is at fault.
- **Design Principles:** _never criticise_ something _unless_ you can _offer a solution_.
  - **Conceptual Models:**
    - Good design is an act of communication between designer and and user.
    - Conceptual models are how a user maps the interface of the tool to how they understand it should be used.
    - The device must explain itself.
  - **Feedback:** Always important to show the effect of an action.
  - **Constraints:**
    - Make something easy to use by making it impossible to do otherwise.
    - When instructions need to be added to something it is badly designed.
  - **Affordances:** Appropriate actions are perceptible and inappropriate ones invisible.
- **The power of observation:** Learn to observe so that you become aware when there are difficulties using a product.

Appropriate, human-centred design requires that all the considerations be addressed from the very beginning.

Technology changes rapidly; **people change slowly**.

Much of our everyday knowledge resides in the world, not in the head. We infer meaning from the information available.

## Chapter 1: The Psychology of Everyday Things

Why do we put up with the frustrations of everyday objects? _Probably because people don't perceive there's a better way._

Well-designed objects are easy to interpret and understand. They contain visible clues to their operation. Poorly designed things provide limited clues, or sometimes false clues.

There's paragraph where Norman talks about problems with doors. This could well be intentional though, to slow people down before they push open a door in to someone on the other side.

<dfn id="def-natural-signals">Natural signals</dfn>: design elements naturally interpreted without any need to be conscious of them. The use of _natural signals_ is called <dfn id="def-natural-design">natural design</dfn>.

Problems with the new telephone system example:

- Poor instructions (no _conceptual model_)
- Failure to relate new functions to similarly named functions that people already know about (false _conceptual model_)
- Lack of visibility of the operation of the system - buttons have no labels (no _natural mappings_)
- Arbitrary actions (poor _affordances_)
- No visible outcome of the operation (_feedback_)

### Affordances

<dfn id="def-affordances">Affordances</dfn> are the perceived and actual properties of how the thing could possibly used (e.g. a chair "affords" sitting).

The user knows what to do just by looking – no picture, label, or instruction is required.

When simple things need pictures, labels, or instructions, the design has failed. – _what is "simple" though?_

<dfn id="def-causality">Causality</dfn>: cause/effect - Something that happens right after an action appears to be caused by that action.

### Conceptual Models

<dfn id="def-conceptual-model">Conceptual model</dfn>: a mental simulation of how to operate a device, based on your _perception_ of how it should be operated.

Clues come from affordances, constraints and mappings. All together form a conceptual model.

Scissors example:

- Affordance: fingers go in finger holes
- Constraint: size of holes is similar to size of fingers
- Mapping: fingers go in holes and operate the blades

**The fundamental principles of designing for people:** good conceptual model + make things visible.

A good conceptual model allows us to predict the effects of our actions. Without, we can't fully appreciate why a thing works, what effects to expect, or what to do if things go wrong.

For everyday things, conceptual models don't need to be very complex. No need to understand the underlying physics or chemistry – just the relationship between controls and the outcomes.

- <dfn id="def-design-model">Design Model</dfn>: The designer's conceptual model.
- <dfn id="def-users-model">User's Model:</dfn> Mental model developed through interaction with the system.
- <dfn id="def-system-image">System Image:</dfn> Physical structure of the object (including documentation, instructions and labels). The visible part of a device.

All communication takes place through the _system image_.

Designers might try to simplify the conceptual model with the intention of making the item easier to understand, but with the wrong conceptual model, it can be impossible to operate the item correctly (fridge/freezer example).

<dfn id="def-mental-model">Mental Model</dfn>: The models people have of themsleves, others, the environment, and the things with which they interact. People form mental models through _experience_, _training_ and _instruction_. The mental model of a device is formed largely by _interpreting_ the perceived actions and its visible structure.

When the system image is incoherent or inappropriate the user cannot easily use the device.

### Make Things Visible

<dfn id="def-visibility">Visibility</dfn>: The mapping between intended actions and actual operations. Lack of visibility makes many computer-controlled devices difficult to operate. Excess of visibility can also make devices intimidating.

Car vs Phone example.

**Car:**

- Things are visible.
- Good mappings, natural relationships between controls and things controlled.
- Single controls have single functions.
- Good feedback.
- The system is understandable.
- Relationships between user's intentions, the required actions, and the results are sensible, non-arbitrary, and meaningful.

**Phone:**

- No visible structure.
- Mappings are arbitrary.
- No relationship between the actions the user must perform and the results to be accomplished.
- Controls have multiple functions.
- Isn't good feedback.
- The system is not understandable.
- Relationships between user's intentions, the required actions, and the results are completely arbitrary.

Whenever the possible number of actions exceeds the number of controls, it's likely there will be some difficulty. Labelling becomes difficult or impossible. _Functions become invisible_.
When the number of controls equals the number of functions, each control can be specialised and labeled. _The possible functions are visible_.

Visibility acts as a good reminder of what can be done, and allows the control to specify how the action is to be performed.

The good relationship between the placement of the control and what it does makes it easy to find the appropriate control for the task. As a result, there is _little to remember_.

### The Principle of Mapping

<dfn id="def-mapping">Mapping</dfn>: The relationship between two things. What you want to do vs what appears to be possible. One button to do two things? What is the mapping? How is a first-time user to know?

<dfn id="def-natural-mapping">Natural Mapping</dfn>: Taking advantage of physical analogies and cultural standards, leading to immediate understanding.
  - Spacial: Move control up to go up
  - Cultural: Rising level = more
  - Biological: Loudness; brightness
  - Additive dimensions: add more to show incremental increases
  - Substitutive dimensions: substitute one value for another to make a change
  - Principles of perception: e.g. groupings of controls similar to controlled object

Mapping problems are one of the fundamental causes of difficulties.

A device is easy to use when there is _visibility_ to the set of possible actions, where the controls and displays exploit _natural mappings_.

### The Principle of Feedback

<dfn id="def-feedback">Feedback</dfn>: Sending back to the user information about what action has been done, and what result has been accomplished.

* <dfn id="def-tactile-feedback">Tactile Feedback</dfn>: the _feel_ of an interface.
* <dfn id="def-auditory-feedback">Auditory Feedback</dfn>: using sound – e.g. an alarm or the _sidetone_ in telephones for the user to regulate how loud they speak

### The Paradox of Technology

<dfn id="def-paradox-of-technology">The paradox of technology</dfn>: added functionality generally comes with the price of added complexity.

Technology development follows a U-shaped curve of complexity (High → Low → High). See the three stages of life in [Selling the Invisible](/2017/01/03/book-notes-selling-the-invisible/).

Whenever the number of functions exceeds the number of controls, the design becomes arbitrary, unnatural and complicated.




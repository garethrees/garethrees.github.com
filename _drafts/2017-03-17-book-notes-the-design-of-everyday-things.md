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
- <dfn id="def-users-model">User's Model</dfn>: Mental model developed through interaction with the system.
- <dfn id="def-system-image">System Image</dfn>: Physical structure of the object (including documentation, instructions and labels). The visible part of a device.

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

## Chapter 2: The Psychology of Everyday Actions

### Falsely Blaming Yourself

People often blame themselves if they make an error in a task that _seems_ easy.

When a system is poorly designed (e.g. makes use of arbitrary actions) and a user makes a mistake, they perceive it to be their fault, rather than a fault of the design.

Designers should make errors as cost-free as possible.

* Assume all errors _will_ occur
* Minimise the chance of each error
* Minimise the cost of an error
* Errors should be easy to detect
* Effects should be reversible if possible

### People as Explanatory Creatures

We base our conceptual and mental models on whatever knowledge we have; real or imaginary; naive or sophisticated.

Mental models are often constructed from fragmentary evidence but with a poor understanding of what is happening, and with a kind of naive psychology that postulates causes, mechanisms and relationships even where there are none.

Everyone forms theories (mental models) to explain what they have observed. In the absence of external information, people are free to let their imaginations run free as long as the mental models they develop account for the facts as they perceive them.

### Blaming the Wrong Cause

People tend to assign a _causal relation_ whenever two things occur in succession.

<dfn id="def-causal-relationship">Causal relationship</dfn>: The relationship between an action causing a result.

<dfn id="def-attribution">Attribution (Blame)</dfn>: A _perceived_ causal relationship between the thing being blamed and a result.

The word _perceived_ is critical: The causal relationship may not have to _actually exist_; just that the person _thinks_ it exists. Blame or credit can be assessed almost independently of reality when there is poor design in a system.

### Learned & Taught Helplessness

<dfn id="def-learned-helplessness">Learned Helplessness</dfn>: When people fail at a task (often repeatedly) and as a result, conclude that the task cannot be done by them.

<dfn id="def-taught-helplessness">Taught Helplessness</dfn>: When complexity keeps increasing and is assumed that a user knows the conventions of what came before. Once you fall behind it is hard to catch up.

### The Nature of Human Thought and Explanation

How do highly skilled, trained people make mistakes?

Sometimes the design of the Thing is poor (e.g. "The light didn't monitor the valve, only the electrical signal to the valve"). In this case a problem was past experience with a leaky valve, so it was easy to ignore a genuine problem.

Sometimes whole system failures go unnoticed until a big problem happens (e.g. change of procurement missed o-rings).

### The Seven Stages of Action

* Start with a goal of what you want to get done
* Then do something to the world
* Finally, you check to see that your goal was achieved


<dfn id="def-execution">Execution</dfn>: Doing something to achieve a goal

<dfn id="def-evaluation">Evaluation</dfn>: Checking that what you did achieved your goal

<dfn id="def-goal">Goal</dfn>: Something to be achieved. Goals may be imprecisely specified.

<dfn id="def-intention">Intention</dfn>: A specific action taken to get to the goal.

<dfn id="def-action-sequence">Action Sequence</dfn>: The physical actions that need to be performed to fulfil the intention.

Note that goals may be satisfied by any number of intentions or action sequences.

* **Goal**
* **Execution:**
  * Intention to act
  * Sequence of actions
  * Execution of the action sequence
* **Evaluation:**
  * Perceiving the state of the world
  * Interpreting the perception
  * Evaluation of interpretations

The stages are not discrete entities – most behaviour does not require going through all stages in sequence, and most goals will not be satisfied by single actions.

For many everyday tasks, goals and intentions are not well specified.

<dfn id="def-opportunistic-actions">Opportunistic Actions</dfn>: Where behaviour takes advantage of the circumstances. Less precise and certain than specified goals and intentions, but result in less mental effort.

<dfn id="def-gulf-of-execution">The Gulf of Execution</dfn>: The difference between the intentions and the allowable actions.

<dfn id="def-gulf-of-evaluation">The Gulf of Evaluation</dfn>: The effort required to interpret the sate of the system and to determine how well the intentions have been met.

The seven-stage structure can be a valuable design aid as it provides a basic checklist of questions to ask to ensure that the Gulfs of Execution and Evaluation are bridged.

**Good Design**: Visibility, a good Conceptual Model, good Mappings and Feedback

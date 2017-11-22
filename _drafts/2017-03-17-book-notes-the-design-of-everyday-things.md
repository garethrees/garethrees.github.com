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

Usability is not often thought about during the purchasing process – often the purchaser is not even the end user.

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

**If a design depends on labels, it may be faulty**. Natural mappings reduce memory burden, and therefore the need for labels. Aim for the design to carry all the information required.

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

## Chapter 3: Knowledge in the Head and in the World

Not all knowledge required for precise behaviour has to be in the head.

Precise behaviour can emerge from imprecise knowledge for for reasons:

* <dfn id="def-information-in-the-world">Information is in the world</dfn>: e.g. a "pull" sign on a door. Behaviour is determined by combining information in memory with that in the world.
* <dfn id="def-precision-not-required">Great precision is not required</dfn>: "Good enough" is often perfectly acceptable.
* <dfn id="def-natural-constraints">Natural constraints are present</dfn>: The world restricts the allowed behaviour.
* <dfn id="def-cultural-constraints">Cultural constraints are present</dfn>: Artificial conventions that govern acceptable social behaviour.

<dfn id="def-constraint">Constraints</dfn>: Natural and artificial constraints reduce the alternatives when choosing a sequence of actions.

Behaviour is determined by the combination of internal knowledge and external information and constraints.

Gaining the advantages of knowledge in the world means losing the advantages of knowledge in the head.

### Information is in the World

Whenever information needed to do a task is readily available in the world, the need for us to learn it diminishes. <em>– Help users by putting knowledge in "the world".</em>

There is a tradeoff between speed and quality of performance and mental effort.

<dfn id="def-knowledge-of">Knowledge of</dfn>: declarative knowledge; facts and rules; easy to write down and teach.

<dfn id="def-knowledge-how">Knowledge how</dfn>: procedural knowledge; largely subconscious; difficult to write down and teach; best taught through demonstration and learned through practice.

Knowledge in the world is available only if you are not somewhere else, or if the world has changed, the knowledge is gone.

### Great Precision is Not Required

Normally people do not need precise memory information. We store only partial descriptions of the things to be remembered – e.g. we can distinguish coins but not the details of the faces.

Descriptions need discriminate only among the choices in front of me, but what works for one purpose may not for another.

### The Power of Constraints

In the poem example, as long as the constraints are known, the choice of word can be completely determined. <em>– the illusion of choice.</em>

Constraints reduce the amount that must be learned to a reasonable quantity.

### The Structure of Memory

Retrieval of the past differs from the retrieval of the just present.

<dfn id="def-short-term-memory">Short Term Memory</dfn> (<abbr title="Short Term Memory">STM</abbr>): low capacity (5 +/- 2); fast retrieval; fragile; Increase capacity by chunking.

<dfn id="def-long-term-memory">Long Term Memory</dfn> (<abbr title="Long Term Memory">LTM</abbr>): high capacity; slow retrieval.

<dfn id="def-memory-for-arbitrary-things">Memory for arbitrary things</dfn>: Simple remembering of what is to be done without reliance on why or internal structure. Don't know what to do when something goes wrong (unless solution memorised). Difficult to learn; fast recall; poor debugging.

<dfn id="def-memory-for-meaningful-relationships">Memory for meaningful relationships</dfn>: remembered by meaningful relationships of things already known. Easier to remember, even if you don't understand.

<dfn id="def-memory-through-explanation">Memory through explanation</dfn>: Material is not remembered; derived from _understanding_. Not ideal for tasks that need to be done rapidly or smoothly. Can derive appropriate behaviour for new situations.

### Reminding

* <dfn id="def-rehearsal">Rehearsal</dfn>: Count on it coming to mind because the thing is important enough.
* Transfer the burden to the outside world.
* Put the burden on the thing itself.

Two aspects to a reminder – a good reminder has both:

1. <dfn id="def-reminder-signal">Signal</dfn>: An alert that there is something that should be remembered.
2. <dfn id="def-reminder-message">Message</dfn>: The message of what is to be remembered.

## Chapter 4: Knowing What to Do

The difficulty of dealing with novel situations is directly related to the number of possibilities.

Information in the head: either we heave dealt with something similar in the past and transfer old knowledge to the new object, or we obtain instruction.

Information in the world: use information in the world if the design has presented us with information that can be interpreted.

_Natural constraints_ and _affordances_ lets a user determine the proper course of action, even in novel situations.

### Constraints

<dfn id="def-physical-constraints">Physical Constraints</dfn>: rely on properties of the physical world; no special training necessary. Desired actions can be made obvious. More useful if they are easy to see and interpret, otherwise they prevent the wrong action from succeeding only after it has been tried.

<dfn id="semantic-constraints">Semantic Constraints</dfn>: rely on the meaning of the situation to control the possible actions. Use our knowledge of the situation and the world,

<dfn id="def-cultural-constraints">Cultural Constraints</dfn>: rely on accepted cultural conventions. Each culture has a set of of allowable actions for social situations. Guidelines for cultural behaviour are represented in the mind by <dfn id="def-cultural-constraints-schemas">schemas</dfn> – knowledge structures that contain the general rules and information necessary for interpreting situations and for guiding behaviour.

<dfn id="def-logical-constraints">Logical Constraints</dfn>: Logical relationship between spatial or functional layout of components and the things that they affect or are affected by.

### Controls

<dfn id="def-grouping-problem">Grouping Problem</dfn>: How to determine which control goes with which function.

**Controls that cause trouble should not be located where they can be operated by accident.**

Set the controls for one set of functions apart from the controls that control other functions.

Can also use different types of switches – ideally by <dfn id="def-shape-coding">shape coding</dfn>: make the switch look like the thing that is being controlled.

<dfn id="def-mapping-problem">Mapping Problem</dfn>: How to determine which control affects which thing to be controlled.

Arrange controls in a similar way to the things that they are controlling (e.g. cooker knobs).

### Feedback

* Decide which parts signify the state of the object.
* What things change?
* What changed since the previous state?
* Where should we be watching or listening to to determine any change?

**The important things to watch should be visible and clearly marked.**

#### Sound for Visibility

> Real, natural sound is as essential as visual information because **sound tells us about things we can't see**.

Sound can confirm you've interacted with a control, or that a thing is operating as expected – or indeed, that something is wrong.

Sound can also be annoying and distracting – careful use necessary.

Difficult to keep private.

## Chapter 5: To Err is to Human

People make errors routinely.

Two fundamental categories:

1. <dfn id="def-slips">Slips</dfn>: Incorrect performance of an action intended to satisfy a goal.
2. <dfn id="def-mistakes">Mistakes</dfn>: An incorrect intention or action sequence for the intended goal.

Sometimes we generalise too rapidly, classifying a new situation as similar to an old one when there are significant discrepancies.

People can consciously attend to only one primary thing at a time. We can do more than one thing at a time only if most of the actions are done automatically, subconsciously or with little or no need for conscious attention.

### Types of Slips

<dfn id="def-capture-error">Capture Error</dfn>: When a frequently done activity suddenly takes charge instead of the one intended.

<dfn id="def-description-error">Description Error</dfn>: Performing the correct action on the wrong object. Occur most frequently when the wrong and right objects are physically near each other.

<dfn id="def-data-driven-error">Data-driven Error</dfn>: Automatic actions triggered by the arrival of sensory data. Can sometimes intrude in to an ongoing action sequence causing behaviour that was not intended.

<dfn id="def-associative-activation-error">Associative Activation Error</dfn>: Actions mistakenly triggered by internal thoughts and associations.

<dfn id="def-loss-of-activation-error">Loss-of-activation Error</dfn>: Simply forgetting to do something. The intent was there, but the activation never happened.

<dfn id="def-mode-error">Mode Error</dfn>: When devices have different modes of operation, and the action appropriate for one mode has different meanings in other modes. Especially likely when the equipment does not make the mode visible.

Slips are relatively _easy to detect_ because there is a clear _discrepancy between goal and result_, but can only take place if there is _feedback_.

### Design Lessons from the Study of Slips

Actions can be specified at many different levels

1. <dfn id="def-high-level-specification">High-level specification</dfn>: The most global description.
2. <dfn id="def-low-level-specification">Low-level specification</dfn>: The sub-actions that make up the high-level specification.

Problems of level commonly thwart the correction of error.

Error correction seems to start at the lowest possible level and slowly works its way higher.

**Prevent slips before they occur**
**Detect and correct when they do occur**

When you build an error-tolerant mechanism, people come to rely on it, so it must be reliable.

Often people tend to rely on remembered experiences rather than more systematic analysis.

### Some Models of Human Thought

Even though people always make mistakes, we still believe that thought is rational, logical and orderly. Much of _law_ is based on the concept of rational thought and behaviour.

Much of problem solving and decision making is about remembering previous experience that can serve as a guide to the present.

### The Structure of Tasks

<dfn id="def-wide-and-deep-tasks">Wide and Deep Structures</dfn>: Characterised by a vast, spreading network of possibilities; the number of choices increases exponentially.

<dfn id="def-shallow-tasks">Shallow Structures</dfn>: Many alternative actions, but each is simple; few decisions to make after the single top-level action.

<dfn id="def-narrow-tasks">Narrow Structures</dfn>: Only a small number of alternatives; any task that involves a sequence of activities where the action to be done at any point is determined by its place in the sequence is a narrow structure.

### Explaining Away Errors

Mistakes can take a very long time to be discovered. It is a lot easier to determine what is obvious after it has happened.

### Designing for Error

Error is often thought of as something to be avoided or something done by unskilled or unmotivated people, but everyone makes errors. Designers make the mistake of not taking error in to account.

1. Understand the causes of error and **design to minimise those causes**.
2. **Make it possible to reverse actions** – to undo them – or make it **harder to do what cannot be reversed**.
3. Make it **easier to discover the errors** that do occur, and make them **easier to correct**.
4. **Change the attitude toward errors**. Think of an object's user as attempting to do a task, getting there by imperfect approximations. Don't think od the user as making errors; **think of the actions as approximations of what is desired**.

Normal behaviour isn't always accurate.

### How to Deal with Errors.

Warning signals are usually not the answer. Most are ignored because they tell the operator something that is already known. When a real emergency happens, all the warning signals go off at once. Each competes with each other to be heard, preventing the person from concentrating on the problem.

Built in warning features are bypassed for several reasons:

* they can go off in error, interrupting normal behaviour
* they often conflict, and become distracting enough to hamper performance
* they are often inconvenient

Warnings and safety signals must be used with care and intelligence, taking in to account the tradeoffs for the people affected.

<dfn id="def-forcing-functions">Forcing Functions</dfn>: a form of physical constraint to prevent the next action if the previous action fails.

<dfn id="def-interlock">Interlock</dfn>: forces operations to take place in proper sequence.

<dfn id="def-lockin">Lockin</dfn>: keeps an operation active, preventing someone from prematurely stopping it.

<dfn id="def-lockout">Lockout</dfn>: prevents an event from occurring.

Must consider whether the cost will result in people disabling the forcing function.

Forcing functions are almost always a nuisance in normal usage. The designer must minimuse the nuisance value while retaining the safety, forcing function mechanism to guard against the occasional tragedy.

### A Design Philosophy

The designer shouldn't think of a simple dichotomy between errors and correct behaviour; rather, the entire interaction should be treated as a cooperative endeavour between person and machine, one in which misconceptions can arise on either side.

* Put the desired knowledge in the world
* Use the power of natural and artificial constraints
* Narrow the gulfs of execution and evaluation

## Chapter 6: The Design Challenge

Much good design evolves. The design is tested, problem areas are discovered and modified, and then it is continually retested and remodified until time, energy and resources run out.

The severe constraints of existing practice prevent change, even where the change would be an improvement.

Once a satisfactory product has been achieved, further change may be counterproductive, especially if the product is successful. You have to know when to stop.

### Why Designers Go Astray

* The reward structure of the design community tends to put aesthetics first.
* Designers are not typical users; they become so expert in using the object that they cannot believe that anyone else might have problems.
* They must please their clients, and the clients may not be the users.

A major part of the design process ought to be the study of just how the objects being designed are to be used.

Designers often become expert with the _device_ they are designing. Users are often expert at the _task_ they are trying to perform with the device.

### The Complexity of the Design Process

> Design is the successive application of constraints until only a unique product is left.



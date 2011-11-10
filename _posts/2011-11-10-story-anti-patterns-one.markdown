---
date: 2011-11-10 12:00 PM
title: Story Anti-Patterns 1
layout: post
author: Matt Van Horn
---

This is the first in a series, where I describe some common mistakes made when trying to run an agile team.

# Anti-Pattern 1 - Visual design isn't the whole story.

## Example 1 - _the team is using Pivotal Tracker as a to-do list_ 
### Typical Story

* Add styling to product page.

In teams that have stories like this, there are probably a few others that look like:

* Clicking on product title directs user to to product page
* Product page shows detailed description and product specs
* User clicks buy now button on product page
    

## Example 2 - _all the business value attached to the wrong thing for the wrong role_
### Typical Story
As the designer  
I want a well-designed product page  
In order to encourage purchases  

Here, the team is trying to find the value, but they are looking in the wrong place for it.
This is an example of thinking about "what do I want the user to do?" instead of "what does the user want to do?"

### Forces leading to the use of this anti-pattern:

* The team is using Pivotal Tracker (or their equivalent tool) to track to-do items, instead of tracking the stakeholder conversations it was meant for.
* The visual designers are not working on the same team as the software developers (stovepiping).
* UI design and graphic asset production is being done in a big-design-up-front fashion.
* The user is lacking representation in the agile process
* The development team feels pressured to put points on the board.

### Problems caused by this anti-pattern:

When this pattern becomes common, you wind up with an application that spends most of its time not ready for deployment.
If the demo gets rescheduled two weeks earlier, there's a good chance you won't be able to show many features in a complete state.
Punchlists that need to be completed in order to deploy is the opposite of agile practice.


Another issue this pattern leads to is programmers waiting on designers, or vice versa. Again - not very agile. This fosters
an us-vs-them mentality that is inimical to getting things done.

Lastly, when software development is iterating, but UI design and/or production is handled as a page-at-a-time waterfall,
the mismatch leads to gross inefficiencies in how the look & feel gets implemented - bloated CSS, endless tweaking of styles, etc.

## Solutions:

* Use story templates that enforce business value consideration
* Use iterative development in ui design as well as programming
* Designers and developers work together on the same stories until they are done.

### Using better story templates

Story templates need to show three important things:

* Business **value**
* The **role** that benefits from the value
* The **feature** necessary to provide the value

The above story could become:

In order to _**more easily make a purchase decision**_  
_**the customer**_  
wants to see _**a well-designed product details page**_  

Given an existing product named "Foo"  
When the customer visits the product page for "Foo"  
Then the customer should see the product details for "Foo"  
And the page should be styled according to the current design specifications for the product page  

Notice that there are no implementation details exposed in the story or scenario. This prevents brittle tests.
The feature is written from a user's point of view, and doesn't concern itself with what the developers consider details,
or what the designers mean by well-designed.

If what is meant by "product details" changes, this is a change in requirements that will correctly force a change in
the implementation of the step. However, the feature itself does not need to change, since it is value-driven and focused on the
user's needs. Ideally, what is meant by product details should be centralized, and changed only in one place to update all
the features that rely on it.

The last step could be implemented using matchers for such ui requirements as:
All headlines should be blue, and all body copy should be 16px high. This then becomes a reusable step that can
help catch look & feel flaws on other pages, as well.

It can be argued that tests for this sort of thing are excessive, since look and feel changes so often, and maintaining these
tests creates a lot of overhead. I think that perhaps the overhead would encourage more consideration of changes, since the actual
cost of doing them correctly becomes exposed. The alternative is to not care whether the look and feel is correct - if you do care,
there is work to be done to ensure correctness, whether it is automated or (like most teams) manually reviewed by designers working
over the shoulders of developers, nearly doubling the overhead costs.

### Iterative UI design

There's not enough space or time to go into a full discussion of agile UI development here. I wish there were more resources
online, but unfortunately there is not a lot written on the topic. Briefly, though, UI development should follow many of
the same principles as software development. The UI design can and should be developed in an organic, iterative fashion.
Stories should be deployed as they are completed - in this system you'll never hear "the story is done, but we can't deploy it until
the UI is finished."

### No More Us-And-Them

The UI design team should be an integral part of the development team, and should pair with software engineers to deliver stories. The
pairs can work on establishing what UI elements are needed for a given story, and can add chores to create the actual assets, while using
placeholders in development. Programmer-Designer pairs can go from paper wireframes to HTML prototype to working application code, together.
The agile principle of YAGNI will be critical to making this system work. Design development can also benefit from DRY thinking.


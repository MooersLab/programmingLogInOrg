# Programming Log Template in Org-mode

## Problem addressed

Programming tasks that cannot be completed in a single setting are complicated enough that there needs to be a written record of the decisions made.
Such large projects also need space for planning.
Planning often involves generating lists and tables.
Org-mode provides excellent support for generating these features, which is why I chose this format.
I use org-mode for my writing log for this reason, while I use LaTeX for manuscripts originating from my lab.


## Inspiration for the writing log

This document follows the spirit of the [writing log](https://github.com/MooersLab/writingLogTemplateInOrg) for recording the thinking that goes behind a manuscript.
In this scenario, the more planning that goes into the writing log, the easier it is to write the manuscript.
The manuscript becomes a side effect of the work done in the writing log.

I anticipate that using a programming log will reduce confusion, resistance, and friction when starting the day's work.
This is especially true when re-engaging with a programming project that was previously suspended due to more urgent priorities interfering with its completion.
This programming log, much like the writing log, can help accelerate the rebooting of suspended projects.

I had previously included notes on program development in my writing log file.
At that time, I was not treating programming projects as standalone projects with their own project numbers and dedicated directories in my home directory.
However, I have recently come to realize that software projects can have a life of their own, quite independent of the manuscript.
Eventually, the manuscript project comes to an end by being published, but the life of a software package can continue for many years, if it proves to be a popular and useful package for other people or for your own work.
Maintaining a programming log helps you focus on the software and treat it with more respect by providing a dedicated platform for recording accomplishments and thoughts.
Sometimes, popular software can be updated and contribute to additional publications in the future.

## Scope

This programming log was written from the perspective of somebody who does solo programming.
There may be some blind spots when it comes to collaborative programming.
Please let me know what I am missing, and I can update the template.

The integration of this approach with team programming may not be readily obvious.
At a minimum, you can keep track of your contributions and decisions in meetings to do your part as a team player.


## Software engineering features

This template incorporates several key concepts from the software engineering literature:

1. **Architecture Decision Records (ADRs)**: ADRs document significant decisions affecting the structure and characteristics of the solution, including the context, decision, and consequences.

2. **Software Requirements Specification sections**: The template includes both functional and non-functional requirements, with functional requirements outlining the software's specific functionality and structured in testable format.

3. **Daily logging practice**: Following the guidance that you should maintain insight into your work on a daily or hourly basis and update every time you have a new idea or insight.

4. **Decision traceability**: A decision log shifts conversations from "I think we decided…" to "The log says we decided…", putting everyone on the same page with objective facts.

## Writing log carryovers

### Explanations
Each section of the programming log has a few sentences that describe the purpose of that section and how to use it.
These can be deleted or commented out if you wish.

The early sections of the writing log were used to identify the target audience, the scope of the paper, whether your group is the right group to write such a paper, potential titles, and potential journals.
These early sections provide space and guidance for doing this preliminary work before beginning the manuscript.
Likewise, similar activities are included in the planning of a software project, and these early sections serve that purpose.
You can always delete those sections or comment them out.

### The "Daily Log" section

This section is the heart of the programming log.
It is the section you will make the most additions to.
It will wind up being the bulk of the document.

This section is like a diary.
It involves daily entries in which one describes their decisions and accomplishments.
This is where I also include meeting notes and correspondence with collaborators.
In my view, this is the heart of the document and the part you will use most frequently.

### To-dos section
The *to-dos* are listed below this section, and the *could-be-done* items are listed in a so-called *Grasscatcher list* section beyond the *to-dos*.
These *could be done* items can be valuable, but they can clutter the to-do list if they're not essential to completing the task at hand.
These features are just slightly out of scope, but could be useful in future projects.
The Grasscatcher list provides a place to store these so that they can get out of your brain and free up your four or five neural threads that you have available for cognitive work to get the important stuff done.

### TODO List

This section is for the storage of TODO items that can be picked up by org agenda.
You can customize org-agenda to examine this log file for TODO items.
You can also assign priorities to the TODO items and sort the list by priority.

### Grasscatcher List

Yes, that grasscatcher--the bag attached to a lawn mower that catches the clipped grass.
The *Grasscatcher* section preserves the spirit of your writing log's *Future Additions and Tangents* section, providing a place for ideas that are not essential but worth preserving.
Without this grass-catcher list, these *could-be-done* items all too often appear on the to-do list, diluting its sense of urgency and inhibiting prioritization.
The term **grasscatcher list** comes from Charles Hobbs, the author of the book *Time Power*, which describes a principled and disciplined approach to time management.
This book provides excellent guidance on setting priorities.

## Limitations

This document is not in pure Org.
It depends on several LaTeX packages.
You may have to install these if you do not have a full installation of LaTeX.


### Status

Very alpha.

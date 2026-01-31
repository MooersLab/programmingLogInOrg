# Programming Log Template in Org-mode

![Version](https://img.shields.io/static/v1?label=writing-time-spent-heatmap&message=0.1&color=brightcolor)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Made with Org-mode](https://img.shields.io/badge/Made%20with-Org--mode-blue.svg)](https://orgmode.org/)
[![Emacs](https://img.shields.io/badge/Emacs-27.1+-purple.svg)](https://www.gnu.org/software/emacs/)

A structured template for documenting the thinking, decisions, and progress behind programming projects that span multiple sessions.

## Table of Contents

- [Problem Addressed](#problem-addressed)
- [Features](#features)
- [Inspiration](#inspiration)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Template Structure](#template-structure)
- [Configuration](#configuration)
- [Exporting to PDF](#exporting-to-pdf)
- [Testing Your Setup](#testing-your-setup)
- [Software Engineering Features](#software-engineering-features)
- [Writing Log Carryovers](#writing-log-carryovers)
- [Customization](#customization)
- [Contributing](#contributing)
- [Related Projects](#related-projects)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Problem Addressed

Programming tasks that cannot be completed in a single setting are complicated enough that there needs to be a written record of the decisions made.
Such large projects also need space for planning.
Planning often involves generating lists and tables.
Org-mode provides excellent support for generating these features, which is why I chose this format.
I use org-mode for my writing log for this reason, while I use LaTeX for manuscripts originating from my lab.

## Features

- **Structured daily logging**: Track progress, decisions, and insights on an hourly or daily basis
- **Architecture Decision Records (ADRs)**: Document significant architectural choices with context and consequences
- **Requirements tracking**: Capture both functional and non-functional requirements in a testable format
- **TODO management**: Integration with org-agenda for task tracking and prioritization
- **Grasscatcher list**: Preserve ideas that are not essential but worth keeping for future consideration
- **PDF export**: Generate professional documentation via LaTeX export
- **Version control friendly**: Plain text format works seamlessly with Git

## Inspiration

This document follows the spirit of the [writing log](https://github.com/MooersLab/writingLogTemplateInOrg) for recording the thinking that goes behind a manuscript.
In this scenario, the more planning that goes into the writing log, the easier it is to write the manuscript.
The manuscript becomes a side effect of the work done in the writing log.

I anticipate that using a programming log will reduce confusion, resistance, and friction when starting the day's work.
This is especially true when re-engaging with a programming project that was previously suspended because more urgent priorities interfered with its completion.
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

## Prerequisites

Before using this template, ensure you have the following installed:

### Required

- **Emacs** (version 27.1 or later recommended)
- **Org-mode** (version 9.0 or later, included with Emacs 27+)

### Optional (for PDF Export)

- **TeX Live** (full installation recommended) or **MacTeX** (for macOS)
- The following LaTeX packages (included in most full TeX distributions):
  - `geometry`
  - `hyperref`
  - `booktabs`
  - `minted` (requires Python and Pygments)
  - `fancyhdr`

### Checking Your Installation

To verify your Emacs and Org-mode versions, run the following in Emacs:

```
M-x emacs-version RET
M-x org-version RET
```

## Installation

### Method 1: Clone the Repository

```bash
# Clone the repository
git clone https://github.com/MooersLab/prologTemplate.git

# Navigate to the directory
cd prologTemplate

# Copy the template to your project directory
cp prologTemplate.org /path/to/your/project/
```

### Method 2: Direct Download

1. Navigate to the repository on GitHub
2. Click on `prologTemplate.org`
3. Click the "Raw" button
4. Save the file to your desired location using `Ctrl+S` (or `Cmd+S` on macOS)

### Method 3: Using curl or wget

```bash
# Using curl
curl -O https://raw.githubusercontent.com/MooersLab/prologTemplate/main/prologTemplate.org

# Using wget
wget https://raw.githubusercontent.com/MooersLab/prologTemplate/main/prologTemplate.org
```

### Post-Installation Setup

1. Rename the file to match your project:
   ```bash
   mv prologTemplate.org myproject-log.org
   ```

2. Open the file in Emacs and customize the header information (title, author, etc.)

3. (Optional) Add the log file to your org-agenda-files for TODO tracking:
   ```elisp
   ;; Add to your init.el or .emacs
   (add-to-list 'org-agenda-files "/path/to/your/project/myproject-log.org")
   ```

## Usage

### Getting Started

1. **Open the template** in Emacs:
   ```
   C-x C-f /path/to/your/myproject-log.org RET
   ```

2. **Customize the metadata** at the top of the file:
   - Update `#+TITLE:` with your project name
   - Update `#+AUTHOR:` with your name
   - Adjust any LaTeX header settings as needed

3. **Begin your first daily entry**:
   - Navigate to the "Daily Log" section
   - Add a new date heading using `M-RET` for a new heading
   - Record your goals, progress, and decisions

### Daily Workflow

A typical daily workflow involves:

1. **Start of session**: Review the previous entry and TODO list
2. **Planning**: Note your goals for the current session
3. **During work**: Record decisions, problems encountered, and solutions
4. **End of session**: Summarize accomplishments and update TODOs

### Keyboard Shortcuts

Here are essential Org-mode commands for working with the log:

| Keybinding | Action |
|------------|--------|
| `TAB` | Cycle visibility of current heading |
| `S-TAB` | Cycle visibility of entire document |
| `M-RET` | Insert new heading at same level |
| `M-S-RET` | Insert new TODO heading |
| `C-c C-t` | Cycle TODO state |
| `C-c C-s` | Schedule a TODO item |
| `C-c C-d` | Add deadline to TODO item |
| `C-c a` | Open org-agenda |
| `C-c C-e` | Open export dispatcher |

### Adding a Daily Entry

```org
** <2025-01-31 Fri>
*** Goals for today
- [ ] Implement feature X
- [ ] Fix bug in module Y
- [ ] Review pull request #42

*** Progress
Started work on feature X. Encountered an issue with...

*** Decisions made
Decided to use approach A instead of B because...

*** Notes
Remember to update the documentation before merging.
```

### Recording an Architecture Decision

```org
** ADR-001: Choice of Database
*** Status
Accepted

*** Context
We need to store user data with complex relationships...

*** Decision
We will use PostgreSQL because...

*** Consequences
- Positive: Strong ACID compliance, excellent query performance
- Negative: Requires additional setup compared to SQLite
```

## Template Structure

The template is organized into the following major sections:

| Section | Purpose |
|---------|---------|
| **Metadata** | Document title, author, LaTeX configuration |
| **Introduction** | Project overview and objectives |
| **Requirements** | Functional and non-functional requirements |
| **Architecture Decisions** | ADRs documenting significant choices |
| **Daily Log** | Chronological record of progress and decisions |
| **TODO List** | Active tasks integrated with org-agenda |
| **Grasscatcher List** | Ideas for future consideration |
| **References** | Links to documentation, papers, and resources |

## Configuration

### Emacs Configuration

Add the following to your `init.el` or `.emacs` file to optimize the template usage:

```elisp
;; Enable org-mode for .org files
(require 'org)

;; Set up org-agenda to include your programming logs
(setq org-agenda-files '("~/projects/" "~/org/"))

;; Configure TODO keywords
(setq org-todo-keywords
      '((sequence "TODO(t)" "IN-PROGRESS(i)" "WAITING(w)" "|" "DONE(d)" "CANCELLED(c)")))

;; Enable logging of state changes
(setq org-log-done 'time)
(setq org-log-into-drawer t)

;; Configure org-babel for code execution (optional)
(org-babel-do-load-languages
 'org-babel-load-languages
 '((emacs-lisp . t)
   (python . t)
   (shell . t)))
```

### LaTeX Export Configuration

For PDF export with the minted package (syntax highlighting), add:

```elisp
;; Enable minted for code highlighting in LaTeX export
(setq org-latex-listings 'minted)
(setq org-latex-minted-options
      '(("frame" "lines")
        ("fontsize" "\\scriptsize")
        ("linenos" "")))

;; Required for minted: use shell-escape
(setq org-latex-pdf-process
      '("pdflatex -shell-escape -interaction nonstopmode -output-directory %o %f"
        "pdflatex -shell-escape -interaction nonstopmode -output-directory %o %f"
        "pdflatex -shell-escape -interaction nonstopmode -output-directory %o %f"))
```

## Exporting to PDF

### Basic Export

1. Open your programming log in Emacs
2. Press `C-c C-e` to open the export dispatcher
3. Press `l` for LaTeX export options
4. Press `p` to export directly to PDF

### Export Commands

| Keybinding | Result |
|------------|--------|
| `C-c C-e l p` | Export to PDF via LaTeX |
| `C-c C-e l l` | Export to LaTeX file only |
| `C-c C-e l o` | Export to PDF and open |
| `C-c C-e h h` | Export to HTML |

### Troubleshooting Export Issues

If PDF export fails, check the `*Org PDF LaTeX Output*` buffer for error messages. Common issues include:

1. **Missing LaTeX packages**: Install the required packages via your TeX distribution
2. **Minted errors**: Ensure Python and Pygments are installed (`pip install Pygments`)
3. **Special characters**: Escape special LaTeX characters in your text

## Testing Your Setup

Follow these steps to verify your installation is working correctly:

### Test 1: Basic Org-mode Functionality

1. Open the template file in Emacs
2. Press `TAB` on any heading to cycle visibility
3. Press `S-TAB` to cycle through global visibility states

**Expected result**: Headings should expand and collapse smoothly.

### Test 2: TODO Functionality

1. Navigate to the TODO List section
2. Add a new TODO item: `M-S-RET` then type "Test TODO item"
3. Cycle the TODO state: `C-c C-t`

**Expected result**: The item should cycle through TODO states.

### Test 3: Org-agenda Integration

1. Ensure the file is in your `org-agenda-files`
2. Open the agenda: `C-c a t`

**Expected result**: TODO items from the log should appear in the agenda view.

### Test 4: LaTeX Export (Optional)

1. Press `C-c C-e l p` to export to PDF
2. Check the output directory for the generated PDF

**Expected result**: A formatted PDF document should be generated.

### Test 5: Code Block Execution (Optional)

1. Add a simple code block:
   ```org
   #+BEGIN_SRC emacs-lisp
   (message "Hello from org-babel!")
   #+END_SRC
   ```
2. Place cursor in the block and press `C-c C-c`

**Expected result**: "Hello from org-babel!" should appear in the minibuffer.

## Software Engineering Features

This template incorporates several key concepts from the software engineering literature:

1. **Architecture Decision Records (ADRs)**: ADRs document significant decisions affecting the structure and characteristics of the solution, including the context, decision, and consequences.

2. **Software Requirements Specification sections**: The template includes both functional and non-functional requirements, with functional requirements outlining the software's specific functionality and structured in a testable format.

3. **Daily logging practice**: Following the guidance that you should maintain insight into your work on a daily or hourly basis and update every time you have a new idea or insight.

4. **Decision traceability**: A decision log shifts conversations from "I think we decided…" to "The log says we decided…", putting everyone on the same page with objective facts.

## Writing Log Carryovers

### Explanations

Each section of the programming log has a few sentences that describe the purpose of that section and how to use it.
These can be deleted or commented out if you wish.

The early sections of the writing log were used to identify the target audience, the paper's scope, whether your group is the right group to write it, potential titles, and potential journals.
These early sections provide space and guidance for doing this preliminary work before beginning the manuscript.
Likewise, similar activities are included in the planning of a software project, and these early sections serve that purpose.
You can always delete those sections or comment them out.

### The "Daily Log" Section

This section is the heart of the programming log.
It is the section you will make the most additions to.
It will wind up being the bulk of the document.

This section is like a diary.
It involves daily entries in which one describes their decisions and accomplishments.
This is where I also include meeting notes and correspondence with collaborators.
In my view, this is the heart of the document and the part you will use most frequently.

### To-dos Section

The *to-dos* are listed below this section, and the *could-be-done* items are listed in a so-called *Grasscatcher list* section beyond the *to-dos*.
These *could be done* items can be valuable, but they can clutter the to-do list if they are not essential to completing the task at hand.
These features are just slightly out of scope, but could be useful in future projects.
The Grasscatcher list provides a place to store these so that they can get out of your brain and free up your four or five neural threads that you have available for cognitive work to get the important stuff done.

### TODO List

This section is for storing TODO items that can be picked up by org-agenda.
You can customize org-agenda to examine this log file for TODO items.
You can also assign priorities to the TODO items and sort the list by priority.

### Grasscatcher List

Yes, that grasscatcher—the bag attached to a lawn mower that catches the clipped grass.
The *Grasscatcher* section preserves the spirit of your writing log's *Future Additions and Tangents* section, providing a place for ideas that are not essential but worth preserving.
Without this grass-catcher list, these *could-be-done* items all too often appear on the to-do list, diluting its sense of urgency and inhibiting prioritization.
The term **grasscatcher list** comes from Charles Hobbs, the author of the book *Time Power*, which describes a principled and disciplined approach to time management.
This book provides excellent guidance on setting priorities.

## Customization

### Adding Custom Sections

To add a new section to the template:

1. Navigate to the appropriate location in the document
2. Create a new heading at the desired level (`*` for top-level, `**` for sub-section)
3. Add explanatory text describing the section's purpose (optional)

### Modifying LaTeX Export Settings

The template includes LaTeX header configurations that can be customized:

```org
#+LaTeX_HEADER: \usepackage[margin=0.5in]{geometry}
```

Common modifications include:
- Adjusting page margins
- Changing fonts
- Adding custom packages
- Modifying header/footer content

### Creating a Personal Snippet

If you use yasnippet, create a snippet for daily entries:

```snippet
# -*- mode: snippet -*-
# name: daily-log-entry
# key: dlog
# --
** <`(format-time-string "%Y-%m-%d %a")`>
*** Goals for today
- [ ] $1

*** Progress
$2

*** Decisions made
$3

*** Notes
$0
```

## Contributing

Contributions are welcome! Here is how you can help:

### Reporting Issues

1. Check if the issue already exists in the [Issues](https://github.com/MooersLab/prologTemplate/issues) section
2. If not, create a new issue with:
   - A clear, descriptive title
   - Steps to reproduce the problem
   - Expected vs. actual behavior
   - Your Emacs and Org-mode versions

### Suggesting Enhancements

1. Open an issue describing your suggestion
2. Explain why this enhancement would be useful
3. Provide examples if applicable

### Submitting Pull Requests

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Commit with clear messages (`git commit -m 'Add amazing feature'`)
5. Push to your branch (`git push origin feature/amazing-feature`)
6. Open a Pull Request

### Code Style

- Follow existing formatting conventions in the template
- Include explanatory comments for new sections
- Test LaTeX export before submitting

## Related Projects

- [writingLogTemplateInOrg](https://github.com/MooersLab/writingLogTemplateInOrg) - The original writing log template that inspired this project
- [org-mode](https://orgmode.org/) - The powerful Emacs major mode for keeping notes, maintaining TODO lists, and project planning
- [org-roam](https://www.orgroam.com/) - A plain-text personal knowledge management system

## Limitations

This document is not in pure Org.
It depends on several LaTeX packages.
You may need to install these if you do not have a full texlive installation.

### Status

Very alpha.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- The Org-mode community for creating such a powerful tool
- Dr. Charles Hobbs for the "grasscatcher" concept from *Time Power*.
- Contributors to the software engineering literature on ADRs and requirements documentation

---

## Frequently Asked Questions

### Q: Can I use this template with other editors?

A: While the template is designed for Emacs and Org-mode, the underlying `.org` file format is plain text and can be edited with any text editor. However, you will lose Org-mode-specific features like TODO management and agenda integration.

### Q: How do I handle multiple projects?

A: Create a separate programming log file for each project. You can configure org-agenda to aggregate TODOs from multiple log files by adding all project directories to `org-agenda-files`.

### Q: Can I use this for team projects?

A: Yes, though the template was designed with solo programming in mind. For team projects, consider keeping individual logs and using Git to track changes. You may also want to add sections for meeting notes and team decisions.

### Q: How often should I update the log?

A: Update at least once per work session. Many practitioners find it helpful to add brief notes whenever they make a significant decision or encounter an interesting problem.



## Update history

|Version      | Changes                                                                                                                                   | Date              |
|:-----------|:------------------------------------------------------------------------------------------------------------------------------------------|:--------------------|
| Version 0.1 |  Initi commit.                                                                                           | 2026 January 31    |


## Funding
- NIH: R01 CA242845, R01 AI088011
- NIH: P30 CA225520 (PI: R. Mannel); P30GM145423 (PI: A. West)


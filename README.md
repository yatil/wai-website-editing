# Editing the new WAI website ***(DRAFT)***

This page is a quick and rough introduction on how to make changes in the new WAI website.

## Where are the new templates used?
There new templates and approaches are used primarily for public facing pages of our websites. Mostly EO deliverables, certain staff pages and the top-level initial WG pages (that usually don’t change that often) are affected by the change.

## When do I have to change my pages?
The simple answer is “never,” the new layout is not a requirement for any pages or internal tools as outlined above. However, the goal is to provide templates for you so you can leverage at least the general look and feel of the new page.

## What is the approach to reviewing edits?
To enable a certain level of checking before changes are published, there are multiple levels of manual review that _can_ be used. People with write privileges on the main GitHub repository (=staff) can skip those steps.

## How do I edit content on the WAI website?
You go to the repository on GitHub and make the changes to the appropriate files. The repository will be linked from the footer of each page[^1](#myfootnote1).
* **Simple Resources** usually only have a few `.md` files in the root directory. You can use GitHub to make changes directly.
* **Complicated Resources** are resources that consist of multiple pages that are in a common sub-navigation. The perspectives videos or the tutorials are good examples of those complicated resources.
	You will find a directory with `_` (underscore) signs in those repositories (the `_external` directory is not of interest). The content files are inside of this directory.

## What is the file format of the content files?
There are two ways to write content:
1. **Markdown**, a simplified way to write HTML. There is a 1:1 conversation from HTML to Markdown and back available.
2. **HTML**.

In any case, the file starts with a header area in YAML format:

~~~yaml
---
title: "The Business Case for Accessibility"
order: 1
permalink: /business-case/
---
~~~

In this example, the header has some metadata about the title, the order in the resource list on the left side and the permalink, the destination in the site.

After the second `---` (three dashes) you can use any combination of Markdown and HTML you like[^2](#myfootnote2).

**Note:** The file has to start with three dashes. Otherwise the rendering won’t work.
**Note:** There are some special codes for using expand/collapse sections, boxes, and tables of contents. A full reference to these codes will be provided ASAP.

## How do I preview my changes?
Once you commit your changes to the (default) `master` branch, the page is automatically rendered on GitHub pages. Every repository has a link to the GitHub pages version on the “Code“ tab.

## How do I publish my changes?
Once you are OK with your changes in the preview, you merge the changes into the `publish` branch. The `publish` branch will be protected in a way that only allows staff to make those merges.

Currently, while in development, we have to manually pull the changes into the main `wai-website` repository and then render the site locally and upload the changes through CVS. The aim is to automate most, if not all, of those steps. However, I’m unsure how to bridge the gap between GitHub and CVS and I have to check back with the systeam.

---

<a name="myfootnote1">[^1]</a>:	Maybe we can even link to the correct document directly, but I have to see if that is an option.

<a name="myfootnote2">[^2]</a>:	Markdown Tables, for example, are not as easy to use as HTML tables are. On the other hand, not having to remember to add `<p>` elements makes it easier to edit files.

---
title: Quick Start Guide
layout: home
nav_order: 1
---

# Quick Start Guide for the OOPP

Here, we outline the whole OOPP digital-publication process, start to finish, in really rough simple terms  so that the more detailed documentation that follows will make more sense.

## 1. Getting Started

What are your goals for using the OOPP?

- Are you interested in:
	- full opacity control for a large amount of sensitive material, along with all of the systematic processes that make managing that sensitive material easier?
	- managing some sensitive material that needs full or partial opacity control but is embedded in a mostly-traditional narrative?
- What is your current writing process? Do you use:
	- a linear editor like MS Word or Google docs?
	- a specialized writing platform like Scrivener or DevonThink to organize your writing?

## 2. Prepping your photos and text

1. Divide your text into chapters, sections and subsections into separate text files and name them properly. *Example:* Chapter 1, section 1, subsection 3, would be in a text-only file named `1_1_3.md`.
1. Redact and name photos properly. *Example:* a fully-visible photo of a patient named Patient S in chapter 1 might be called `Chapter1_PSmith.jpg`. You would then use a photo editor to partially and fully redact sensitive content in that photo, naming the resulting files `Chapter1_PSmith_partial.jpg` and `Chapter1_PSmith_full.jpg`.

## 3. Creating and prepping your GitHub account

*If you're comfortable with GitHub already,* this will go quickly. Follow the steps in our Github-basics page to make a copy of our example site and customize a few things for your digital publication.

*If you're not comfortable with GitHub*, our Github basics page provides an overview of how your site will work, plus step-by-step details for each of the 5 steps here. Focus on Steps 3a and 3b in your first read through so that you can set up your Github account and use it to work with files.

1. Create a new Github account, where the username is the name people will search for to find your digital publication. For instance, our sample publication is titled "The Tuberculosis Specimen", so the username is "tuberculosisspecimen"
	2. The "free" option will mean people can see, but not edit, the files that run your web site.
1. Make a copy of our template repository at Visit [`https://github.com/OpaquePublisher/template`](https://github.com/OpaquePublisher/template)
1. Create a new `_config.yml` file using our "Configuration File Generator" at [https://OpaquePublisher.github.io/MakeConfigFile/](https://OpaquePublisher.github.io/MakeConfigFile/)
1. Go to "Settings" for your new repository and choose the "Pages" option to tell Github that your new repository should be set up as a public website

## 3. Upload your prepared text files into your GitHub account

1. Upload the chapter/section/subsection files into the `narrative` folder.
1. Upload your images into the `assets/img` folder.

Github limits you to 100 files at a time and 10MB of content at a time. You may have to upload files in batches.
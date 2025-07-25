---
title: File Naming
layout: default
nav_order: 1
parent: Prepping Your Text and Photos
---

# File Naming

In order to more easily keep track of the numerous photographs and text files in a digital publication, it is essential to have a system for standardizing file names. 

## Text Files

### Narrative Files

Each chapter, section, and subsection ***must*** be named using a 3-number naming convention that the OOPP uses to create an orderly table of contents, the previous/next links in the digital publication, and the index of terms.

```
1_3_4.md
```

1. the first number corresponds to a chapter number.
1. the second number indicates a section within that chapter.
1. the third number indicates a subsection within a section of a chapter.

These "narrative" files have "header" information--metadata that controls how the table of contents generates and how the chapter is listed in the publication index.

```
---
layout: section
title: "Medicine's Visual Cultures"
chapter: "1"
section: "1"
subsection: "2"
indexterms: "Visual Culture;Foucault, Michel;Clinical Gaze"
---
```

The body copy of the section follows the last set of three hyphens `---`, with a blank line between the last set of hyphens and the beginning of that section's text.

### Chapter/Section Header Files

Each section and subsection also has a stand-in file, usually using the number zero `0`, to allow you to explicitly provide chapter and section titles and abstracts.


```
1_0_0.md
```

This is a header file for Chapter 1 that contains the title of the chapter and a short description of the chapter for use generating a chapter-by-chapter and section-by-section table of contents. The first file in each chapter additionally uses a different layout type (`chapterhead`) so that each main-chapter page has a fully generated table of contents for that chapter only.

```
---
layout: chapterhead
title:
sectiontitle: "Tuberculosis' Visual Culture"
chapter: "1"
section: "0"
subsection: "0"
info: "This chapter examines medical visual culture in the context of the sanatorium movement. Thinking about the limitations of Michel Foucault's notions of the clinical gaze, this chapter argues for an expanded understanding of medicine's visual practices."
---
```

These chapter and section "lead" files do not need content below the last set of three hyphens.
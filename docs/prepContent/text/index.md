---
title: Content Editing 
layout: default
nav_order: 2
parent: Prepping Your Text and Photos
---

The move from Scrivener to markdown (.md) involves some amount of alteration of the markdown files exported. This is because Scrivener exports to markdown, but not the kind of Yet Another Markup Language (.yaml) formatted markdown. The goal of this formatting is to create a serviceable file in Microsoft Word (.docx) and a markdown file that can be made to work for the dissertation platform with minimal intervention.

To prep a file for export, the Scrivener draft needs to first be marked up with placeholder sequences for the definitions and image files. For images with no opacity, the following format was used:

    +=+[filename]-=-4[filename]#=#2

And for images with opacity filtering required, the following format was used:

    +=+[filename]-=-1[filename]#=#1

    +=+[filename]-=-2[filename]#=#2

    +=+[filename]-=-3[filename]#=#3

Here are some examples from the first chapter (1.2.2). For an image with no filtering:

    +=+TubSanConf\_1926\_0003-=-4TubSanConf\_1926\_0003#=#2

For an image with opacity filtering:

    +=+TubSanConf\_1926\_0002-=-1TubSanConf\_1926\_0002#=#1

    +=+TubSanConf\_1926\_0002-=-2TubSanConf\_1926\_0002#=#2

    +=+TubSanConf\_1926\_0002-=-3TubSanConf\_1926\_0002#=#3

These uniform sequences are made to make find and replace functions work fluidly across the dissertation. This can be done programmatically using a python script, or by doing batch find and replace functions in a code editor like bbEdit. Here is the protocol for finding and replacing the placeholder sequences:

For non-{#c4-3}opaque{#end} images:

    Find: \+=\+ Replace with: <img id="

    Find -=-4 Replace with: " src="{{ site.baseurl }}/assets/img/

For {#c4-3}opaque{#end} images:

    Find: \+=\+ Replace with: <img id="

    Find: -=-1 Replace with: " class="opaque" src="{{ site.baseurl }}/assets/img/

    Find: -=-2 Replace with: " class="transparent" src="{{ site.baseurl }}/assets/img/

    Find: -=-3 Replace with: " class="partially-opaque" src="{{ site.baseurl }}/assets/img/

    Find: #=#1 Replace with: \_full.jpg">

    Find: #=#2 Replace with: .jpg">

    Find: #=#3 Replace with: \_partial.jpg">

By replacing each of these placeholder sequences, the code above reads as follows. For non-{#c4-3}opaque{#end} images:

    <img id="TubSanConf\_1926\_0003" src="{{ site.baseurl }}/assets/img/TubSanConf\_1926\_0003.jpg">

For {#c4-3}opaque{#end} images:

    <img id="TubSanConf\_1926\_0002" class="opaque" src="{{ site.baseurl }}/assets/img/TubSanConf\_1926\_0002\_full.jpg">

    <img id="TubSanConf\_1926\_0002" class="transparent" src="{{ site.baseurl }}/assets/img/TubSanConf\_1926\_0002.jpg">

    <img id="TubSanConf\_1926\_0002" class="partially-opaque" src="{{ site.baseurl }}/assets/img/TubSanConf\_1926\_0002\_partial.jpg">

The same search and replace workflow is used for the mouseover, but on a slightly more granular scale. While I entered the images as I wrote, I created the definitions and the text {#c4-3}opacity{#end} after the polished draft for the dissertation committee was complete, as a step in parallel with the ethics audit (4.3.5). As I read over the chapter, I flagged important terms using the following find and replace structure:

    {#c[chapternumber]-[definitionnumber]}[definition]{#end}

I broke this into chapter-by-chapter definitions, because the definitions would become too many to keep in my head at any one moment. The definition number allowed me to replace the whole placeholder with a specific, written version which could then be uniform across the chapter or dissertation.

For an example from chapter one (1.4.1):

    I address this to think about how the careful framing, and the detail in exposure, would imply a kind of {#c1-25}consent{#end}, at least from the doctor. Inviting a photographer into the space, having them set up their equipment, and posing for the image all require a kind of acceptance that this work will be done. These are not doctors caught in the act unaware. Very rarely do they return the glace to the camera (fig. 15).

{#c1-25}consent{#end}

The find and replace, for this example, reads as follows:

    Find: {#c1-25} Replace with: Consent {#c1-25} <span data-tooltip aria-haspopup="true" class="has-tip" data-disable-hover="false" tabindex="1" title="I use consent in relation to the idea of informed consent: that a patient would be first cognizant of the what is done to them, for them, or through them, and that they would have the ability to say 'no' at any point during research."><b> 

    Find: {#end} Replace with: </b></span>

The final sentence in the markdown file reads as follows:

    I address this to think about how the careful framing, and the detail in exposure, would imply a kind of <span data-tooltip aria-haspopup="true" class="has-tip" data-disable-hover="false" tabindex="1" title="I use consent in relation to the idea of informed consent: that a patient would be first cognizant of the what is done to them, for them, or through them, and that they would have the ability to say 'no' at any point during research."><b>consent</b></span>, at least from the doctor. Inviting a photographer into the space, having them set up their equipment, and posing for the image all require a kind of acceptance that this work will be done. These are not doctors caught in the act unaware. Very rarely do they return the glace to the camera (fig. 15).

I have included the entire replace function in the next section (X.2.4).

The opacity text span classes (X.2.1) also function with this replace function. I use the following placeholder for the partial-opacity span class:

    {#par}[content]{#span}

And this for full opacity:

    {#op}[content}{#span}

These are replaced using the following replace protocol:

    Find: {#op} Replace with: <span class="partial-lines”>

    Find: {#par} Replace with: <span class="opaque-lines”>

    Find: {#span} Replace with: </span>

Here is an example from chapter 1 (1.3.4):

    {#par}{#op}13 year old Polish lad who was suffering from tuberculosis,{#span}{#span}

Which reads like this in the final markdown file:

    <span class="partial-lines"><span class="opaque-lines">13 year old Polish lad who was suffering from tuberculosis,</span></span> 

The last process that is required for the creation of the markdown files is the header. This has to be entered manually. The header is the first text in any of the markdown files, and reads as follows:

    ---

    layout: #this defines how the page will be created when the site is built.

    title:

    identifier: #this corresponds with the actual identifier for each section

    chapter: #this is used for the autogenerated table of contents

    section: #this is used for the autogenerated table of contents

    subsection: #this is used for the autogenerated table of contents

    chapterdisplay: #this is used for the autogenerated table of contents

    sectiondisplay: #this is used for the autogenerated table of contents

    subsectiondisplay: #this is used for the autogenerated table of contents

    ---

Here is an example from chapter 1 (1.3.4):

    ---

    layout: section

    title: "Teaching Hygiene"

    identifier: 1.3.4

    chapter: 1

    section: 3

    subsection: 4

    chapterdisplay: 1

    sectiondisplay: 3

    subsectiondisplay: 4

    ---
    
## The following is the code used for the mouseover functionality.[^fn1]

To add mouseover, this is the code used, which is written directly into the markdown file:

    <span data-tooltip aria-haspopup="true" class="has-tip" data-disable-hover="false" tabindex="1" title=“[content]“><b>[defined-term]</b></span>

Here is an example of the code from the first chapter (<a href="{{ site.baseurl }}/narrative/1_3_4">1.3.4</a>):

    <span data-tooltip aria-haspopup="true" class="has-tip" data-disable-hover="false" tabindex="1" title="The open air approach to treating tuberculosis focused on the constant flow of fresh air. It was often paired with the rest cure."><b>open air</b></span>

<div class="style-divider">
 	<div class="line"></div>
</div>

[^fn1]: This code was developed by Kalani Craig.
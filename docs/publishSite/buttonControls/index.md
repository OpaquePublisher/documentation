---
title: Understanding the Transparency Button Controls
layout: default
nav_order: 1
parent: Publishing Your Site
---

The following is the code used for <span data-tooltip aria-haspopup="true" class="has-tip" data-disable-hover="false" tabindex="1" data-title="Opacity is a rights-based philosophical framework that assumes humans have a right to not be known in knowledge systems."><b>opacity</b></span> functionality.[^fn1] It is also described in chapter four (<a href="{{ site.baseurl }}/narrative/4_3_3">4.3.3</a>).

This is the code for the buttons:

     <div class="toggle-buttons">

        <button id="opaqueBtn" class="toggle-button">Opaque</button>

        <button id="transparentBtn" class="toggle-button">Transparent</button>

        <button id="partiallyOpaqueBtn" class="toggle-button">Partially Opaque</button></div>

This is the code for images, each level is defined and uses a uniquely generated image:

        <img id=“[filename]” class="opaque" src="{{ site.baseurl }}/assets/items/[filename]_opaque.jpg" style="max-width:60%;height:auto;">

        <img id="[filename]" class="transparent" src="{{ site.baseurl }}/assets/items/[filename].jpg" style="max-width:60%;height:auto;">

        <img id="[filename]" class="partially-opaque" src="{{ site.baseurl }}/assets/items/[filename]_partial.jpg" style="max-width:60%;height:auto;">

The following code is used for the text <span data-tooltip aria-haspopup="true" class="has-tip" data-disable-hover="false" tabindex="1" data-title="Opacity is a rights-based philosophical framework that assumes humans have a right to not be known in knowledge systems."><b>opacity</b></span> functions. For partial lines: 

    <span class="partial-lines”>[content]</span>

For fully <span data-tooltip aria-haspopup="true" class="has-tip" data-disable-hover="false" tabindex="1" data-title="Opacity is a rights-based philosophical framework that assumes humans have a right to not be known in knowledge systems."><b>opaque</b></span> text:

    <span class="opaque-lines”>[content]</span>

The fully <span data-tooltip aria-haspopup="true" class="has-tip" data-disable-hover="false" tabindex="1" data-title="Opacity is a rights-based philosophical framework that assumes humans have a right to not be known in knowledge systems."><b>opaque</b></span> lines will always be crossed out with partial lines, so using the fully <span data-tooltip aria-haspopup="true" class="has-tip" data-disable-hover="false" tabindex="1" data-title="Opacity is a rights-based philosophical framework that assumes humans have a right to not be known in knowledge systems."><b>opaque</b></span> function will usually have the partial lines span class nested inside:

    <span class="partial-lines"><span class="opaque-lines”>[content]</span></span>

<div class="style-divider">
 	<div class="line"></div>
</div>

[^fn1]: This code was developed by Kalani Craig.


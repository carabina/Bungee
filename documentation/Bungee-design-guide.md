# Bungee Design Guide

This document demonstrates how to use some of Bungee's more interesting features, such as its chromatic layers, vertical forms, and stylistic alternates.


## Family structure

Bungee contains several different font sets that allow access to the chromatic layers and vertical forms. 

The basic *Bungee* family includes Regular and Hairline weights, as well as three composite layerings: Inline, Outline, and Shade.

*Bungee Layers* contains each layer in a separate font, which all share the same metrics. These fonts can be used in combination to create chromatic text by using layered textboxes in a website or advanced design app.

*Bungee Layers Rotated* implements Bungee’s vertical forms by default, with all characters rotated 90° counterclockwise. These fonts can be set in a textbox rotated 90° clockwise to simulate vertical type, and have a limited character set.

*Bungee Color* contains experiments with the various color font formats out there, including SVG, COLR/CPAL and sbix. None of these formats are widely supported (yet!), so your milage may vary. These fonts are built with Jens Kutilek’s <a href="https://github.com/fontfont/RoboChrome">RoboChrome</a>.


## Using chromatic layers

### Desktop apps

No design apps have native support for chromatic layers.

1. In one text box, set a line of matching text for each layer.

[]

2. Using the *Bungee Layers* font, style each line, starting with the backmost layer (Shade) and ending with the frontmost (Inline).

[]

3. Add colors to each line.

[]

4. When you are finished, select all of the text, and set the leading/linespacing to 0.

[]

4. To edit the text, do a find and replace, or increase the leading.

[]

Instead of zeroing out the leading, you can also set each layer in a separate text block, and manage their arrangement in the z axis.

[]

### On the web

Bungee.js has a bit of javascript that will duplicate text in overlaid <div>s, giving the appearance of layered text without cluttering your markup.

<script type="text/javascript" src="bungee.js">
<div id="bungee">Layered text!</div>

Warning: This solution requires loading multiple fonts, which will increase bandwidth usage and download times. 

When only single letters or small bits of text are required, an alternative approach is to use a SVG with alternate text.

<img src="images/layeredText.svg" alt="Layered text" />

### Color font formats

[screenshot of color font used on desktop machine]

The *Bungee Color* family contains experimental fonts in the various color font formats out there, including SVG (Adobe/Mozilla), COLR/CPAL (Microsoft) and sbix (Apple). 

These fonts were built with Jens Kutilek’s <a href="https://github.com/fontfont/RoboChrome">RoboChrome</a>.


## Using vertical text

Bungee’s vertical features are implemented via three OpenType features:

* *vert*: Vertical Forms.

Replace default horizontal forms with glyphs drawn for vertical setting. These glyphs are monowidth in appearance, and their widths are adjusted to foster better vertical alignment. The hyphen and other basic punctuation are rotated 90°.

[]

* *vpal*: Vertical Positioning and Layout.

Reset the vertical sidebearings and advance heights for the glyphs. This feature enables Bungee to have proportional vertical spacing, with shorter glyphs occupying less vertical space than taller ones.

[]

* *vkrn*: Vertical Kerning.

Adjust the vertical spacing of individual glyph pairs so that they are more evenly spaced.

[]

### Apps that support vertical text 

Several professional design applications have separate vertical text tools, which will implement all of the necessary OpenType features and provide a nice interface for setting vertical text.

Desktop apps that natively support vertical text include:

* Adobe Photoshop
* Adobe Illustrator
* Apple TextEdit

### Apps that do not support vertical text

In apps that do not have native vertical text tools, the *Bungee Layers Rotated* family allows you to simulate vertical type. 

These fonts have Bungee’s vertical forms, spacing, and kerning baked in to the default forms, and all characters are rotated 90° counterclockwise. 

1. Set the text. 

[Image from InDesign]

2. Change the font to *Bungee Layers Rotated*.

[Image from InDesign]

3. Rotate the text block 90° counterclockwise. 

[Image from InDesign]

Voilà! Pseudo-vertical text.

Apps that do not support vertical text include:

* Google Docs
* Microsoft Word
* Apple Pages
* Adobe InDesign


### On the web

The proper way to implement vertical text is via the CSS **writing-mode** selector.

<style type="text/css">
	.vertical {
			writing-mode: vertical-rl;
			-webkit-writing-mode: vertical-rl;
			-moz-writing-mode: vertical-rl;
</style>

<div class="vertical">Vertical Text!</div>


## Stylistic alternates

As a display font, Bungee is intended for small bits of, sometimes even single words.

* Stylistic Set 01: Round Forms.

Replace diagonal forms of A, M, N, W, X, and Y with deco-inspired alternates with round shapes and vertical sides. 

Each of these letters can also be implemented separately using the following stylistic sets:
	
	* Stylistic Set 05: Round A.
	* Stylistic Set 06: Round M.
	* Stylistic Set 07: Round N.
	* Stylistic Set 08: Round W.
	* Stylistic Set 09: Round X.
	* Stylistic Set 10: Round Y.
	
* Stylistic Set 02: Serifless I.

Replace wide, serifed I with an unserifed alternate. This is a very narrow character that may result in less-than-ideal vertical setting.

For all you Hawaiians out there, I drew a special serifless vertical II ligature. Let me know if you actually find a way to use it!

* Stylistic Set 03: Round E.
	
Replace forms of E with an decorative alternate with a rounded left side.
	
* Stylistic Set 04: Alternate Ampersand.

Replace the default ‘ET’ ampersand with an alternate that resembles a stylized ‘E’ with a vertical stroke.
	
* Stylistic Set 12: Small Quotes.

Replace the curly apostrophe and matching left quote with smaller, less obtrusive versions.

* Stylistic Set 18: John Downer Recommendations.

Signpainter John Downer recommends against vertical type that includes problematic characters like I, M, and W, which are unusually narrow or wide. This feature disables those characters.

* Stylistic Set 20: Vertical forms.

Activate Bungee’s vertical forms (identical to the *vert* feature). These forms are better accessed through the vertical text features described above, but this stylistic set can be handy when such tools are not available, or when monowidth letters are required in a non-vertical setting.

[Image of vertical forms used in horizontal cameo letters]


## Other OpenType features

In addition to its stylistic alternates, Bungee also contains several OpenType Stylistic Sets for easy access to certain characters or alternate forms.

* Stylistic Set 11: Sequential IJ.

Deactivate the ligated form of the Ĳ glyph.

* Stylistic Set 13: Indexes.

Replace directional arrows with pointing hands.

* Stylistic Set 14: Alternate Indexes.

Replace directional arrows and pointing hands with alternate hands where the pointer and thumb are shown.

* Stylistic Set 15: Outline Indexes.

Replace filled indexes with outlined versions.

* Stylistic Set 19: Primes.

Replace straight single and double quote with angled minute and second glyphs.


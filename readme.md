CSS DAY 2017: Useful links and some notes

## Rachel Nabors: Alice in Web Animations API Land
* https://spiritapp.io/
* https://codepen.io/rachelnabors/

## ppk: Constraint validation and form validation
Form validation is the oldest trick in the JS book. At first, it was the only thing that browsers could do.

Validation timing:
* onsubmit: when the user submits the form: far too late.
* onkeypress: whenever the user changes part of the value: too soon, too many times
* onblur:  when the user leaves a form field: sweet spot

* https://medium.com/samsung-internet-dev/native-form-validation-part-1-bf8e35099f1d
* https://medium.com/samsung-internet-dev/native-form-validation-part-2-552c78f563b
* https://medium.com/samsung-internet-dev/native-form-validation-part-3-8e643e1dd06
* https://www.quirksmode.org/blog/archives/2008/04/delegating_the.html

## Philip Walton: Polyfills & Houdini
Polyfills turn code the browser doesn't understand into code the browser does understand. CSS that the browser doesn't understand doesn't make it to the CSSOM.
* https://www.smashingmagazine.com/2016/03/houdini-maybe-the-most-exciting-development-in-css-youve-never-heard-of/

## CSS Reset
What would we do if we could rewrite CSS? What could we have done differently?
* Bert: A more detailed spec: what do we mean with line-break, justify, etc? The specs now are pretty precise so they are implemented the same everywhere, but this wasn't always the case, obviously.
* Håkon: actually, we made it too specific. We should've left out collapsing margin, first line/letter pseudo elements. We could've taken out some features.
* Bert: make reading documents easier. Put in stuff like collapsing lists, pop-ups.
* Håkon: Implement card elements/Apple's hypercard. Move away from the scrolled web. A page-based view, no scrollbars.
* Bert: pretty happy with the formal CSS syntax. The original idea was even simpler. Make the syntax readable for non-programmers (no curly braces). Avoid nesting. CSS should be as easy to write HTML.
* Håkon: should preprocessors have been a part since the beginning?
* Bert: nope. Preprocessors are wonderful, but they are a separate process. Not everyone needs them, so it doesn't really make sense to put them in the language. It's also great people can choose their own program, like Sass or Less, there is more choice.
* Håkon: I was against border-radius. It's too 1970s, and we've moved on from that. But a lot of people wanted it, and they got it. It's just visual fluff, but that is exactly what designers want.
* Håkon: the spec was done without any testing documents. That was a mistake. See: https://en.wikipedia.org/wiki/Acid2. The community developed the tests, but maybe we should've done more.
* Bert: we didn't think of testing much. We also could've done more with courses and tutorials. Make the spec more understood.
* Håkon: what about Grid? Is that something that should've been a fundamental part?
* Bert: yes. We actually did think about that: frames. For Grid, a document is a whole (as it should). We wanted to show the documents as quickly as possible (progressive rendering). We wanted to show a document line by line, because the internet was a lot slower back then. For Bert and Håkon, documents are structures, which wasn't always clear for implementors/users.
* Bert: what I don't like about JS is it interferes with your browser, and allows it to do things that I may not want or expect. Both of us had a document background, not an application background. We have document-based features (hyphenation, etc), and user interface features. We could've made separate languages: one for documents, one for user interfaces.

## Rachel Andrew: What I discovered about layout via CSS Grid
While learning Grid and going through the spec, Rachel learned a huge amount about how CSS works. The more she dug into the specs, she realized there's a whole world of stuff she knew existed, but didn't really know how they exactly worked. So here are the things she learned while learning Grid. When learning Grid, you can't tune out other things, the spec is touched by a lot of different things, like CSS display, writing modes..

- CSS display
Outer display: relationship with parents
Inner display: formatting context

Blockification

Inlinification

You can override display: table-cell with Grid, so you don't always need feature queries! So two sets of code are not needed.
* https://rachelandrew.co.uk/css/cheatsheets/grid-fallbacks
* https://rachelandrew.co.uk/archives/2017/03/16/subgrid-moved-to-level-2-of-the-css-grid-specification/

Display: contents =/= subgrid.
* https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout

Don't change Grid code, change writing mode! From left and right to start and end.

* https://rachelandrew.co.uk/archives/2017/06/01/breaking-out-with-css-grid-explained/

Names lines create a named area, which in turn can be used as named lines.

If something odd happens, try using longhand. If that doesn't work, ask people. The spec is not always perfect and could be written more clearly.

## Mark Boulton: Designing grids
There are no rules, there are just good (and bad) decisions.
* https://en.wikipedia.org/wiki/David_Carson_(graphic_designer)

Why design a grid in the first place? They provide order and connectedness. It aids in usability and comprehension. Where should what go?

Content informs the layout, not the other way around. The whole point of a grid is to connect space.

Grids can be iterated upon: it's not design once, then you're done.

Compound: two grids in the same space, overlaid. You can use on or the other, or a combination of the two.

Typesetting: do it until it feels right.

Hanging punctuation: https://css-tricks.com/almanac/properties/h/hanging-punctuation/

## Jen Simmons: Writing modes
Direction needs to be defined in the HTML element, not the CSS!

`<html lang="en-US" dir="rtl">`

* https://developer.mozilla.org/nl/docs/Web/HTML/Element/bdo
* https://developer.mozilla.org/nl/docs/Web/HTML/Element/bdi
* https://www.chenhuijing.com/zh-type/
* http://labs.jensimmons.com/2016/workshop/
* https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Logical_Properties

Alignment: Block (vertical)

Justify: Inline (horizontal)

## Tab Atkins: Houdini & the Future
* http://blogs.perficient.com/perficientdigital/2016/08/03/houdini-a-new-development-in-css/

## Chris Coyier: Four Properties
* https://developer.mozilla.org/en-US/docs/Web/CSS/shape-outside
* https://rachelandrew.co.uk/archives/2016/03/16/css-exclusions-and-grid-layout/

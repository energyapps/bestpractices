#Energy's Best Practices for Programing maps, charts, and timelines

The contents of this repository are released under a [Creative Commons CC BY 3.0 License](http://creativecommons.org/licenses/by/3.0/deed.en_US).

**Note:** If you're building a map or chart for energy.gov

 * You have reviewed the Best Practices (below) and reviewed the map template (if applicable).

## Naming things

Naming things (variables, files, classes, etc.) consistently and intuitively is one of the hardest problems in computer science. To make it easier, follow these conventions:

* Always proceed from more general to more specific. For example, ``widget-skinny`` is better than ``skinny-widget``.
* Strive for parallelism. If you have a `begin()` function, then have an `end()` function (not `stop()` or `done()`).
* Group related names with common prefixes, e.g. `search_query` and `search_address`.
* Prefer more specific terms to more vague ones. If it's an address call it `address`, not `location`.
* When a function operates on a variable, their naming should be consistent. If working with `updates` then `process_updates()`, don't `process_changes()`. 
* Maintain naming conventions between iterables and their iterators: `for update in updates`, not `for record in updates`.

<table>
  <tr><th>Prefer...</th><th>to...</th></tr>
  <tr><td>create</td><td>insert, add, new</td></tr>
  <tr><td>update</td><td>change, edit</td></tr>
  <tr><td>delete</td><td>remove, purge</td></tr>
  <tr><td>setup</td><td>init</td></tr>
  <tr><td>make</td><td>build, generate</td></tr>
  <tr><td>wrapper</td><td>wrap</td></tr>
  <tr><td>render</td><td>draw</td></tr>
</table>  

(Note: sometimes these words don't mean the same thing, but when they do, prefer the former.)

## HTML & CSS

* Element IDs and class names should always be ``lowercase-with-dashes``.
* Make sure to use a Reset CSS, such as [Meyerweb](http://meyerweb.com/eric/tools/css/reset/).
* Coming Soon: Info about CSS template and font information for energy.gov
* Coming Soon: When possible adhere to the energy.gov style guide (link coming.)
* Coming Soon: Information about 508 compliance.

## Javascript

### General

* Use 4-spaces for indentation (because it's easier to be consistent with Python than it is to switch your editor back and forth).
* Javascript variables names should always be ``lowercase_with_underscores``.
* Static variables and configuration parameters should be in ``TITLECASE_WITH_UNDERSCORES``.
* Named functions should look like this ``var camelCase = function() {}``.
* All global variables should be defined at the top of the file.
* All variables should be constrained to the current scope with ``var``.
* Declare only a single variable on one line.
* End all statements with a semicolon.
* Use spaces after opening and before closing braces and brackets in array and object definitions, i.e. ``{ foo: [ 1, 2, 3 ] }`` not ``{foo:[1,2,3]}``.
* Do not use spaces after opening or before closing parentheses, i.e. ``if (foo == true) {`` and not ``if ( foo == true ) {``. 
* When accessing properties of a data structure (such as one retrieved using ``getJSON``) prefer bracket syntax (``data["property"]``) to attribute syntax (``data.property``).
* Very frequent property references should be cached, i.e. ``var array_length = array.length;``.
* Use ``===`` rather than ``==``. ([Why?](http://www.impressivewebs.com/why-use-triple-equals-javascipt/))
* **Use single-quotes for strings.**

### Libraries

For consistency, prefer the following libraries to others that perform the same tasks:

 * [Jquery](http://jquery.com/) for DOM manipulation (default on all Energy.gov page).
 * [Timeline JS](http://timeline.knightlab.com/) for timelines (soon to be integrated in Drupal).
 * [Leaflet JS](http://leafletjs.com/reference.html) for mapping
 * [Mapbox JS](https://www.mapbox.com/mapbox.js/) for mapping
 * [Highcharts JS](http://www.highcharts.com/) for charts and graphs
 * [D3 JS](http://d3js.org/) for SVG and canvas advanced charts
 * [Dragdealer JS](http://code.ovidiu.ch/dragdealer/) for dragable b
 ars
 * [Underscore JS ](http://documentcloud.github.io/underscore/) for functional programming (where Underscore and jQuery overlap, i.e. each(), prefer Underscore).
 * [Enquire JS ](http://wicky.nillia.ms/enquire.js/) for responsive javascript.

DOE note: all libraries must be approved priort use on energy.gov

### jQuery-specific

* jQuery references that are used more than once should be cached. Prefix these references with ``$``, i.e. ``var $electris = $("#electris");``.
* Whenever possible constrain jQuery DOM lookups within the scope of a cached element. For example, ``$electris.find(".candidate")`` is preferable to ``$(".candidate")``.
* Always use [on](http://api.jquery.com/on/), never [bind](http://api.jquery.com/bind/), [delegate](http://api.jquery.com/delegate/) or [live](http://api.jquery.com/live/). ``on`` should also be preferred to "verb events", such as [click](http://api.jquery.com/click/).

## git

At this time we have no recorded best practices for using git.

## More to come

Much more heavy lifting needs to be done here:

* Map template using mapbox JS, timeline, and highchart template.
* Directions for creating maps using Energy.gov's drupal interface.
* Code review process.
* Other helpful code snippets.
* Posting of CSS style guidelines for maps.
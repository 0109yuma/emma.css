# Emma.css { Emmet-like utility classes }

A collection of [CSS utility classes](emma.css) for rapid front-end development.

## Example

``` html
<article class="u-cf u-ml-xl u-p-lg">
  <img class="u-d-b u-fl-l u-w-a u-mr-md u-bdw-2 u-bds-s u-bdc-orange u-bdrs-3" src="" alt="">
  <div class="u-d-b u-fl-l">
    <h1 class="u-m-0 u-ff-t">Title</h1>
    <p class="u-wow-bw u-wfsm-a">Description</p>
    <a class="u-d-ib u-fz-sm u-lh-xs" href="#">Read more</a>
  </div>
</article>
```

utility class name | declaration
--- | ---
`.u-cf` (clearfix) | [micro clearfix hack](http://nicolasgallagher.com/micro-clearfix-hack/)
`.u-ml-xl` (extra large) | margin-left: 4.0rem;
`.u-p-lg` (large) | padding: 2.0rem;
`.u-d-b` | display: block;
`.u-fl-l` | float: left;
`.u-w-a` | width: auto;
`.u-mr-md` (medium) | margin-right: 1.0rem;
`.u-bdw-2` | border-width: 2px;
`.u-bds-s` | border-style: solid;
`.u-bdc-orange` | border-color: orange;
`.u-bdrs-3` | border-radius: 3px;
`.u-m-0` | margin: 0;
`.u-ff-t` | font-family: "Times New Roman", Times, Baskerville, Georgia, serif;
`.u-wow-bw` | word-wrap: break-word;
`.u-wfsm-a` | -webkit-font-smoothing: antialiased;
`.u-d-ib` | display: inline-block;
`.u-fz-sm` (small) | font-size: small;
`.u-lh-xs` (extra small) | line-height: 1.2;

See also: [emma.css](emma.css) (all utility classes)

## Getting Started

### Basic

SCSS:
``` scss
@import "path/to/emma.scss";
```
CSS output:
``` css
.u-pos-s { position: static !important; }
.u-pos-a { position: absolute !important; }
.u-pos-r { position: relative !important; }
(snip)
```

### Change prefix of utility classes

Default prefix: `u-`  
You can change prefix of utility classes by `$emma-prefix` variable:

``` scss
$emma-prefix: "foo-"; // Change prefix
@import "path/to/emma.scss";
```
CSS output:
``` css
.foo-pos-s { position: static !important; }
.foo-pos-a { position: absolute !important; }
.foo-pos-r { position: relative !important; }
(snip)
```

If you need to remove prefix:

``` scss
$emma-prefix: ""; // Remove prefix
@import "path/to/emma.scss";
```
CSS output:
``` css
.pos-s { position: static !important; }
.pos-a { position: absolute !important; }
.pos-r { position: relative !important; }
(snip)
```

### Remove !important decralations

You can remove `!important` decralations by `$emma-important` variable:

``` scss
$emma-important: false; // Remove !important decralations
@import "path/to/emma.scss";
```
CSS output:
``` css
.u-pos-s { position: static; }
.u-pos-a { position: absolute; }
.u-pos-r { position: relative; }
(snip)
```

### Select available snippets

You can select available snippets by `$emma-available-snippet-list` variable:

``` scss
$emma-available-snippet-list: (
  tt-u, ff-a, wfsm-a, cf,
);
@import "path/to/emma.scss";
```
CSS output:
``` css
.u-tt-u { text-transform: uppercase !important; }
.u-ff-a { font-family: Arial, "Helvetica Neue", Helvetica, sans-serif !important; }
.u-wfsm-a { -webkit-font-smoothing: antialiased !important; }
.u-cf:before, .u-cf:after { content: " "; display: table; }
.u-cf:after { clear: both; }
```

### Change default sizes or colors

You can change default sizes or colors by variables:

``` scss
$emma-padding-md: 20px;     // default: 1.0rem
$emma-color-black: #111111; // default: black
@import "path/to/emma.scss";
```

If you need to change [nicer color palette](http://clrs.cc/):

``` scss
$emma-alternative-colors: true;
@import "path/to/emma.scss";
```

### Define custom snippets

You can define custom snippets by `emma` mixin:

``` scss
@import "path/to/emma.scss";
@include emma(foo-bar, color, #369); // Single declaration
@include emma(baz) {                 // Multiple declaration
  font-size: 2.1em !important;
  line-height: 1.618;
}
```
CSS output:
``` css
(snip)
.u-foo-bar { color: #369 !important; }
.u-baz { font-size: 2.1em !important; line-height: 1.618; }
```

## Inspired by

* [emmetio/emmet](https://github.com/emmetio/emmet)
* [suitcss/suit](https://github.com/suitcss/suit)
* [jxnblk/basscss](https://github.com/jxnblk/basscss)
* [t32k/wisteria](https://github.com/t32k/wisteria)
* [hail2u/node-edjo](https://github.com/hail2u/node-edjo)

## License

Released under the [MIT license](http://ruedap.mit-license.org/2015).

## Author

<a href="https://github.com/ruedap"><img src="https://dl.dropboxusercontent.com/u/281168/images/github-ruedap-avatar-1500x1500.png" alt="ruedap" title="ruedap" width="100" height="100"></a>

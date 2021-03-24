# face-expression
To recognize the facial expression 
<!DOCTYPE html>
<html>
<head><meta charset="utf-8" />

<title>face_exp</title>

<script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>



<style type="text/css">
    /*!
*
* Twitter Bootstrap
*
*/
/*!
 * Bootstrap v3.3.7 (http://getbootstrap.com)
 * Copyright 2011-2016 Twitter, Inc.
 * Licensed under MIT (https://github.com/twbs/bootstrap/blob/master/LICENSE)
 */
/*! normalize.css v3.0.3 | MIT License | github.com/necolas/normalize.css */
html {
  font-family: sans-serif;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
}
body {
  margin: 0;
}
article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
main,
menu,
nav,
section,
summary {
  display: block;
}
audio,
canvas,
progress,
video {
  display: inline-block;
  vertical-align: baseline;
}
audio:not([controls]) {
  display: none;
  height: 0;
}
[hidden],
template {
  display: none;
}
a {
  background-color: transparent;
}
a:active,
a:hover {
  outline: 0;
}
abbr[title] {
  border-bottom: 1px dotted;
}
b,
strong {
  font-weight: bold;
}
dfn {
  font-style: italic;
}
h1 {
  font-size: 2em;
  margin: 0.67em 0;
}
mark {
  background: #ff0;
  color: #000;
}
small {
  font-size: 80%;
}
sub,
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}
sup {
  top: -0.5em;
}
sub {
  bottom: -0.25em;
}
img {
  border: 0;
}
svg:not(:root) {
  overflow: hidden;
}
figure {
  margin: 1em 40px;
}
hr {
  box-sizing: content-box;
  height: 0;
}
pre {
  overflow: auto;
}
code,
kbd,
pre,
samp {
  font-family: monospace, monospace;
  font-size: 1em;
}
button,
input,
optgroup,
select,
textarea {
  color: inherit;
  font: inherit;
  margin: 0;
}
button {
  overflow: visible;
}
button,
select {
  text-transform: none;
}
button,
html input[type="button"],
input[type="reset"],
input[type="submit"] {
  -webkit-appearance: button;
  cursor: pointer;
}
button[disabled],
html input[disabled] {
  cursor: default;
}
button::-moz-focus-inner,
input::-moz-focus-inner {
  border: 0;
  padding: 0;
}
input {
  line-height: normal;
}
input[type="checkbox"],
input[type="radio"] {
  box-sizing: border-box;
  padding: 0;
}
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: textfield;
  box-sizing: content-box;
}
input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}
fieldset {
  border: 1px solid #c0c0c0;
  margin: 0 2px;
  padding: 0.35em 0.625em 0.75em;
}
legend {
  border: 0;
  padding: 0;
}
textarea {
  overflow: auto;
}
optgroup {
  font-weight: bold;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
td,
th {
  padding: 0;
}
/*! Source: https://github.com/h5bp/html5-boilerplate/blob/master/src/css/main.css */
@media print {
  *,
  *:before,
  *:after {
    background: transparent !important;
    box-shadow: none !important;
    text-shadow: none !important;
  }
  a,
  a:visited {
    text-decoration: underline;
  }
  a[href]:after {
    content: " (" attr(href) ")";
  }
  abbr[title]:after {
    content: " (" attr(title) ")";
  }
  a[href^="#"]:after,
  a[href^="javascript:"]:after {
    content: "";
  }
  pre,
  blockquote {
    border: 1px solid #999;
    page-break-inside: avoid;
  }
  thead {
    display: table-header-group;
  }
  tr,
  img {
    page-break-inside: avoid;
  }
  img {
    max-width: 100% !important;
  }
  p,
  h2,
  h3 {
    orphans: 3;
    widows: 3;
  }
  h2,
  h3 {
    page-break-after: avoid;
  }
  .navbar {
    display: none;
  }
  .btn > .caret,
  .dropup > .btn > .caret {
    border-top-color: #000 !important;
  }
  .label {
    border: 1px solid #000;
  }
  .table {
    border-collapse: collapse !important;
  }
  .table td,
  .table th {
    background-color: #fff !important;
  }
  .table-bordered th,
  .table-bordered td {
    border: 1px solid #ddd !important;
  }
}
@font-face {
  font-family: 'Glyphicons Halflings';
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot');
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot?#iefix') format('embedded-opentype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff2') format('woff2'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff') format('woff'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.ttf') format('truetype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.svg#glyphicons_halflingsregular') format('svg');
}
.glyphicon {
  position: relative;
  top: 1px;
  display: inline-block;
  font-family: 'Glyphicons Halflings';
  font-style: normal;
  font-weight: normal;
  line-height: 1;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.glyphicon-asterisk:before {
  content: "\002a";
}
.glyphicon-plus:before {
  content: "\002b";
}
.glyphicon-euro:before,
.glyphicon-eur:before {
  content: "\20ac";
}
.glyphicon-minus:before {
  content: "\2212";
}
.glyphicon-cloud:before {
  content: "\2601";
}
.glyphicon-envelope:before {
  content: "\2709";
}
.glyphicon-pencil:before {
  content: "\270f";
}
.glyphicon-glass:before {
  content: "\e001";
}
.glyphicon-music:before {
  content: "\e002";
}
.glyphicon-search:before {
  content: "\e003";
}
.glyphicon-heart:before {
  content: "\e005";
}
.glyphicon-star:before {
  content: "\e006";
}
.glyphicon-star-empty:before {
  content: "\e007";
}
.glyphicon-user:before {
  content: "\e008";
}
.glyphicon-film:before {
  content: "\e009";
}
.glyphicon-th-large:before {
  content: "\e010";
}
.glyphicon-th:before {
  content: "\e011";
}
.glyphicon-th-list:before {
  content: "\e012";
}
.glyphicon-ok:before {
  content: "\e013";
}
.glyphicon-remove:before {
  content: "\e014";
}
.glyphicon-zoom-in:before {
  content: "\e015";
}
.glyphicon-zoom-out:before {
  content: "\e016";
}
.glyphicon-off:before {
  content: "\e017";
}
.glyphicon-signal:before {
  content: "\e018";
}
.glyphicon-cog:before {
  content: "\e019";
}
.glyphicon-trash:before {
  content: "\e020";
}
.glyphicon-home:before {
  content: "\e021";
}
.glyphicon-file:before {
  content: "\e022";
}
.glyphicon-time:before {
  content: "\e023";
}
.glyphicon-road:before {
  content: "\e024";
}
.glyphicon-download-alt:before {
  content: "\e025";
}
.glyphicon-download:before {
  content: "\e026";
}
.glyphicon-upload:before {
  content: "\e027";
}
.glyphicon-inbox:before {
  content: "\e028";
}
.glyphicon-play-circle:before {
  content: "\e029";
}
.glyphicon-repeat:before {
  content: "\e030";
}
.glyphicon-refresh:before {
  content: "\e031";
}
.glyphicon-list-alt:before {
  content: "\e032";
}
.glyphicon-lock:before {
  content: "\e033";
}
.glyphicon-flag:before {
  content: "\e034";
}
.glyphicon-headphones:before {
  content: "\e035";
}
.glyphicon-volume-off:before {
  content: "\e036";
}
.glyphicon-volume-down:before {
  content: "\e037";
}
.glyphicon-volume-up:before {
  content: "\e038";
}
.glyphicon-qrcode:before {
  content: "\e039";
}
.glyphicon-barcode:before {
  content: "\e040";
}
.glyphicon-tag:before {
  content: "\e041";
}
.glyphicon-tags:before {
  content: "\e042";
}
.glyphicon-book:before {
  content: "\e043";
}
.glyphicon-bookmark:before {
  content: "\e044";
}
.glyphicon-print:before {
  content: "\e045";
}
.glyphicon-camera:before {
  content: "\e046";
}
.glyphicon-font:before {
  content: "\e047";
}
.glyphicon-bold:before {
  content: "\e048";
}
.glyphicon-italic:before {
  content: "\e049";
}
.glyphicon-text-height:before {
  content: "\e050";
}
.glyphicon-text-width:before {
  content: "\e051";
}
.glyphicon-align-left:before {
  content: "\e052";
}
.glyphicon-align-center:before {
  content: "\e053";
}
.glyphicon-align-right:before {
  content: "\e054";
}
.glyphicon-align-justify:before {
  content: "\e055";
}
.glyphicon-list:before {
  content: "\e056";
}
.glyphicon-indent-left:before {
  content: "\e057";
}
.glyphicon-indent-right:before {
  content: "\e058";
}
.glyphicon-facetime-video:before {
  content: "\e059";
}
.glyphicon-picture:before {
  content: "\e060";
}
.glyphicon-map-marker:before {
  content: "\e062";
}
.glyphicon-adjust:before {
  content: "\e063";
}
.glyphicon-tint:before {
  content: "\e064";
}
.glyphicon-edit:before {
  content: "\e065";
}
.glyphicon-share:before {
  content: "\e066";
}
.glyphicon-check:before {
  content: "\e067";
}
.glyphicon-move:before {
  content: "\e068";
}
.glyphicon-step-backward:before {
  content: "\e069";
}
.glyphicon-fast-backward:before {
  content: "\e070";
}
.glyphicon-backward:before {
  content: "\e071";
}
.glyphicon-play:before {
  content: "\e072";
}
.glyphicon-pause:before {
  content: "\e073";
}
.glyphicon-stop:before {
  content: "\e074";
}
.glyphicon-forward:before {
  content: "\e075";
}
.glyphicon-fast-forward:before {
  content: "\e076";
}
.glyphicon-step-forward:before {
  content: "\e077";
}
.glyphicon-eject:before {
  content: "\e078";
}
.glyphicon-chevron-left:before {
  content: "\e079";
}
.glyphicon-chevron-right:before {
  content: "\e080";
}
.glyphicon-plus-sign:before {
  content: "\e081";
}
.glyphicon-minus-sign:before {
  content: "\e082";
}
.glyphicon-remove-sign:before {
  content: "\e083";
}
.glyphicon-ok-sign:before {
  content: "\e084";
}
.glyphicon-question-sign:before {
  content: "\e085";
}
.glyphicon-info-sign:before {
  content: "\e086";
}
.glyphicon-screenshot:before {
  content: "\e087";
}
.glyphicon-remove-circle:before {
  content: "\e088";
}
.glyphicon-ok-circle:before {
  content: "\e089";
}
.glyphicon-ban-circle:before {
  content: "\e090";
}
.glyphicon-arrow-left:before {
  content: "\e091";
}
.glyphicon-arrow-right:before {
  content: "\e092";
}
.glyphicon-arrow-up:before {
  content: "\e093";
}
.glyphicon-arrow-down:before {
  content: "\e094";
}
.glyphicon-share-alt:before {
  content: "\e095";
}
.glyphicon-resize-full:before {
  content: "\e096";
}
.glyphicon-resize-small:before {
  content: "\e097";
}
.glyphicon-exclamation-sign:before {
  content: "\e101";
}
.glyphicon-gift:before {
  content: "\e102";
}
.glyphicon-leaf:before {
  content: "\e103";
}
.glyphicon-fire:before {
  content: "\e104";
}
.glyphicon-eye-open:before {
  content: "\e105";
}
.glyphicon-eye-close:before {
  content: "\e106";
}
.glyphicon-warning-sign:before {
  content: "\e107";
}
.glyphicon-plane:before {
  content: "\e108";
}
.glyphicon-calendar:before {
  content: "\e109";
}
.glyphicon-random:before {
  content: "\e110";
}
.glyphicon-comment:before {
  content: "\e111";
}
.glyphicon-magnet:before {
  content: "\e112";
}
.glyphicon-chevron-up:before {
  content: "\e113";
}
.glyphicon-chevron-down:before {
  content: "\e114";
}
.glyphicon-retweet:before {
  content: "\e115";
}
.glyphicon-shopping-cart:before {
  content: "\e116";
}
.glyphicon-folder-close:before {
  content: "\e117";
}
.glyphicon-folder-open:before {
  content: "\e118";
}
.glyphicon-resize-vertical:before {
  content: "\e119";
}
.glyphicon-resize-horizontal:before {
  content: "\e120";
}
.glyphicon-hdd:before {
  content: "\e121";
}
.glyphicon-bullhorn:before {
  content: "\e122";
}
.glyphicon-bell:before {
  content: "\e123";
}
.glyphicon-certificate:before {
  content: "\e124";
}
.glyphicon-thumbs-up:before {
  content: "\e125";
}
.glyphicon-thumbs-down:before {
  content: "\e126";
}
.glyphicon-hand-right:before {
  content: "\e127";
}
.glyphicon-hand-left:before {
  content: "\e128";
}
.glyphicon-hand-up:before {
  content: "\e129";
}
.glyphicon-hand-down:before {
  content: "\e130";
}
.glyphicon-circle-arrow-right:before {
  content: "\e131";
}
.glyphicon-circle-arrow-left:before {
  content: "\e132";
}
.glyphicon-circle-arrow-up:before {
  content: "\e133";
}
.glyphicon-circle-arrow-down:before {
  content: "\e134";
}
.glyphicon-globe:before {
  content: "\e135";
}
.glyphicon-wrench:before {
  content: "\e136";
}
.glyphicon-tasks:before {
  content: "\e137";
}
.glyphicon-filter:before {
  content: "\e138";
}
.glyphicon-briefcase:before {
  content: "\e139";
}
.glyphicon-fullscreen:before {
  content: "\e140";
}
.glyphicon-dashboard:before {
  content: "\e141";
}
.glyphicon-paperclip:before {
  content: "\e142";
}
.glyphicon-heart-empty:before {
  content: "\e143";
}
.glyphicon-link:before {
  content: "\e144";
}
.glyphicon-phone:before {
  content: "\e145";
}
.glyphicon-pushpin:before {
  content: "\e146";
}
.glyphicon-usd:before {
  content: "\e148";
}
.glyphicon-gbp:before {
  content: "\e149";
}
.glyphicon-sort:before {
  content: "\e150";
}
.glyphicon-sort-by-alphabet:before {
  content: "\e151";
}
.glyphicon-sort-by-alphabet-alt:before {
  content: "\e152";
}
.glyphicon-sort-by-order:before {
  content: "\e153";
}
.glyphicon-sort-by-order-alt:before {
  content: "\e154";
}
.glyphicon-sort-by-attributes:before {
  content: "\e155";
}
.glyphicon-sort-by-attributes-alt:before {
  content: "\e156";
}
.glyphicon-unchecked:before {
  content: "\e157";
}
.glyphicon-expand:before {
  content: "\e158";
}
.glyphicon-collapse-down:before {
  content: "\e159";
}
.glyphicon-collapse-up:before {
  content: "\e160";
}
.glyphicon-log-in:before {
  content: "\e161";
}
.glyphicon-flash:before {
  content: "\e162";
}
.glyphicon-log-out:before {
  content: "\e163";
}
.glyphicon-new-window:before {
  content: "\e164";
}
.glyphicon-record:before {
  content: "\e165";
}
.glyphicon-save:before {
  content: "\e166";
}
.glyphicon-open:before {
  content: "\e167";
}
.glyphicon-saved:before {
  content: "\e168";
}
.glyphicon-import:before {
  content: "\e169";
}
.glyphicon-export:before {
  content: "\e170";
}
.glyphicon-send:before {
  content: "\e171";
}
.glyphicon-floppy-disk:before {
  content: "\e172";
}
.glyphicon-floppy-saved:before {
  content: "\e173";
}
.glyphicon-floppy-remove:before {
  content: "\e174";
}
.glyphicon-floppy-save:before {
  content: "\e175";
}
.glyphicon-floppy-open:before {
  content: "\e176";
}
.glyphicon-credit-card:before {
  content: "\e177";
}
.glyphicon-transfer:before {
  content: "\e178";
}
.glyphicon-cutlery:before {
  content: "\e179";
}
.glyphicon-header:before {
  content: "\e180";
}
.glyphicon-compressed:before {
  content: "\e181";
}
.glyphicon-earphone:before {
  content: "\e182";
}
.glyphicon-phone-alt:before {
  content: "\e183";
}
.glyphicon-tower:before {
  content: "\e184";
}
.glyphicon-stats:before {
  content: "\e185";
}
.glyphicon-sd-video:before {
  content: "\e186";
}
.glyphicon-hd-video:before {
  content: "\e187";
}
.glyphicon-subtitles:before {
  content: "\e188";
}
.glyphicon-sound-stereo:before {
  content: "\e189";
}
.glyphicon-sound-dolby:before {
  content: "\e190";
}
.glyphicon-sound-5-1:before {
  content: "\e191";
}
.glyphicon-sound-6-1:before {
  content: "\e192";
}
.glyphicon-sound-7-1:before {
  content: "\e193";
}
.glyphicon-copyright-mark:before {
  content: "\e194";
}
.glyphicon-registration-mark:before {
  content: "\e195";
}
.glyphicon-cloud-download:before {
  content: "\e197";
}
.glyphicon-cloud-upload:before {
  content: "\e198";
}
.glyphicon-tree-conifer:before {
  content: "\e199";
}
.glyphicon-tree-deciduous:before {
  content: "\e200";
}
.glyphicon-cd:before {
  content: "\e201";
}
.glyphicon-save-file:before {
  content: "\e202";
}
.glyphicon-open-file:before {
  content: "\e203";
}
.glyphicon-level-up:before {
  content: "\e204";
}
.glyphicon-copy:before {
  content: "\e205";
}
.glyphicon-paste:before {
  content: "\e206";
}
.glyphicon-alert:before {
  content: "\e209";
}
.glyphicon-equalizer:before {
  content: "\e210";
}
.glyphicon-king:before {
  content: "\e211";
}
.glyphicon-queen:before {
  content: "\e212";
}
.glyphicon-pawn:before {
  content: "\e213";
}
.glyphicon-bishop:before {
  content: "\e214";
}
.glyphicon-knight:before {
  content: "\e215";
}
.glyphicon-baby-formula:before {
  content: "\e216";
}
.glyphicon-tent:before {
  content: "\26fa";
}
.glyphicon-blackboard:before {
  content: "\e218";
}
.glyphicon-bed:before {
  content: "\e219";
}
.glyphicon-apple:before {
  content: "\f8ff";
}
.glyphicon-erase:before {
  content: "\e221";
}
.glyphicon-hourglass:before {
  content: "\231b";
}
.glyphicon-lamp:before {
  content: "\e223";
}
.glyphicon-duplicate:before {
  content: "\e224";
}
.glyphicon-piggy-bank:before {
  content: "\e225";
}
.glyphicon-scissors:before {
  content: "\e226";
}
.glyphicon-bitcoin:before {
  content: "\e227";
}
.glyphicon-btc:before {
  content: "\e227";
}
.glyphicon-xbt:before {
  content: "\e227";
}
.glyphicon-yen:before {
  content: "\00a5";
}
.glyphicon-jpy:before {
  content: "\00a5";
}
.glyphicon-ruble:before {
  content: "\20bd";
}
.glyphicon-rub:before {
  content: "\20bd";
}
.glyphicon-scale:before {
  content: "\e230";
}
.glyphicon-ice-lolly:before {
  content: "\e231";
}
.glyphicon-ice-lolly-tasted:before {
  content: "\e232";
}
.glyphicon-education:before {
  content: "\e233";
}
.glyphicon-option-horizontal:before {
  content: "\e234";
}
.glyphicon-option-vertical:before {
  content: "\e235";
}
.glyphicon-menu-hamburger:before {
  content: "\e236";
}
.glyphicon-modal-window:before {
  content: "\e237";
}
.glyphicon-oil:before {
  content: "\e238";
}
.glyphicon-grain:before {
  content: "\e239";
}
.glyphicon-sunglasses:before {
  content: "\e240";
}
.glyphicon-text-size:before {
  content: "\e241";
}
.glyphicon-text-color:before {
  content: "\e242";
}
.glyphicon-text-background:before {
  content: "\e243";
}
.glyphicon-object-align-top:before {
  content: "\e244";
}
.glyphicon-object-align-bottom:before {
  content: "\e245";
}
.glyphicon-object-align-horizontal:before {
  content: "\e246";
}
.glyphicon-object-align-left:before {
  content: "\e247";
}
.glyphicon-object-align-vertical:before {
  content: "\e248";
}
.glyphicon-object-align-right:before {
  content: "\e249";
}
.glyphicon-triangle-right:before {
  content: "\e250";
}
.glyphicon-triangle-left:before {
  content: "\e251";
}
.glyphicon-triangle-bottom:before {
  content: "\e252";
}
.glyphicon-triangle-top:before {
  content: "\e253";
}
.glyphicon-console:before {
  content: "\e254";
}
.glyphicon-superscript:before {
  content: "\e255";
}
.glyphicon-subscript:before {
  content: "\e256";
}
.glyphicon-menu-left:before {
  content: "\e257";
}
.glyphicon-menu-right:before {
  content: "\e258";
}
.glyphicon-menu-down:before {
  content: "\e259";
}
.glyphicon-menu-up:before {
  content: "\e260";
}
* {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
*:before,
*:after {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
html {
  font-size: 10px;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}
body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 13px;
  line-height: 1.42857143;
  color: #000;
  background-color: #fff;
}
input,
button,
select,
textarea {
  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
}
a {
  color: #337ab7;
  text-decoration: none;
}
a:hover,
a:focus {
  color: #23527c;
  text-decoration: underline;
}
a:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
figure {
  margin: 0;
}
img {
  vertical-align: middle;
}
.img-responsive,
.thumbnail > img,
.thumbnail a > img,
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  display: block;
  max-width: 100%;
  height: auto;
}
.img-rounded {
  border-radius: 3px;
}
.img-thumbnail {
  padding: 4px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: all 0.2s ease-in-out;
  -o-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  display: inline-block;
  max-width: 100%;
  height: auto;
}
.img-circle {
  border-radius: 50%;
}
hr {
  margin-top: 18px;
  margin-bottom: 18px;
  border: 0;
  border-top: 1px solid #eeeeee;
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
[role="button"] {
  cursor: pointer;
}
h1,
h2,
h3,
h4,
h5,
h6,
.h1,
.h2,
.h3,
.h4,
.h5,
.h6 {
  font-family: inherit;
  font-weight: 500;
  line-height: 1.1;
  color: inherit;
}
h1 small,
h2 small,
h3 small,
h4 small,
h5 small,
h6 small,
.h1 small,
.h2 small,
.h3 small,
.h4 small,
.h5 small,
.h6 small,
h1 .small,
h2 .small,
h3 .small,
h4 .small,
h5 .small,
h6 .small,
.h1 .small,
.h2 .small,
.h3 .small,
.h4 .small,
.h5 .small,
.h6 .small {
  font-weight: normal;
  line-height: 1;
  color: #777777;
}
h1,
.h1,
h2,
.h2,
h3,
.h3 {
  margin-top: 18px;
  margin-bottom: 9px;
}
h1 small,
.h1 small,
h2 small,
.h2 small,
h3 small,
.h3 small,
h1 .small,
.h1 .small,
h2 .small,
.h2 .small,
h3 .small,
.h3 .small {
  font-size: 65%;
}
h4,
.h4,
h5,
.h5,
h6,
.h6 {
  margin-top: 9px;
  margin-bottom: 9px;
}
h4 small,
.h4 small,
h5 small,
.h5 small,
h6 small,
.h6 small,
h4 .small,
.h4 .small,
h5 .small,
.h5 .small,
h6 .small,
.h6 .small {
  font-size: 75%;
}
h1,
.h1 {
  font-size: 33px;
}
h2,
.h2 {
  font-size: 27px;
}
h3,
.h3 {
  font-size: 23px;
}
h4,
.h4 {
  font-size: 17px;
}
h5,
.h5 {
  font-size: 13px;
}
h6,
.h6 {
  font-size: 12px;
}
p {
  margin: 0 0 9px;
}
.lead {
  margin-bottom: 18px;
  font-size: 14px;
  font-weight: 300;
  line-height: 1.4;
}
@media (min-width: 768px) {
  .lead {
    font-size: 19.5px;
  }
}
small,
.small {
  font-size: 92%;
}
mark,
.mark {
  background-color: #fcf8e3;
  padding: .2em;
}
.text-left {
  text-align: left;
}
.text-right {
  text-align: right;
}
.text-center {
  text-align: center;
}
.text-justify {
  text-align: justify;
}
.text-nowrap {
  white-space: nowrap;
}
.text-lowercase {
  text-transform: lowercase;
}
.text-uppercase {
  text-transform: uppercase;
}
.text-capitalize {
  text-transform: capitalize;
}
.text-muted {
  color: #777777;
}
.text-primary {
  color: #337ab7;
}
a.text-primary:hover,
a.text-primary:focus {
  color: #286090;
}
.text-success {
  color: #3c763d;
}
a.text-success:hover,
a.text-success:focus {
  color: #2b542c;
}
.text-info {
  color: #31708f;
}
a.text-info:hover,
a.text-info:focus {
  color: #245269;
}
.text-warning {
  color: #8a6d3b;
}
a.text-warning:hover,
a.text-warning:focus {
  color: #66512c;
}
.text-danger {
  color: #a94442;
}
a.text-danger:hover,
a.text-danger:focus {
  color: #843534;
}
.bg-primary {
  color: #fff;
  background-color: #337ab7;
}
a.bg-primary:hover,
a.bg-primary:focus {
  background-color: #286090;
}
.bg-success {
  background-color: #dff0d8;
}
a.bg-success:hover,
a.bg-success:focus {
  background-color: #c1e2b3;
}
.bg-info {
  background-color: #d9edf7;
}
a.bg-info:hover,
a.bg-info:focus {
  background-color: #afd9ee;
}
.bg-warning {
  background-color: #fcf8e3;
}
a.bg-warning:hover,
a.bg-warning:focus {
  background-color: #f7ecb5;
}
.bg-danger {
  background-color: #f2dede;
}
a.bg-danger:hover,
a.bg-danger:focus {
  background-color: #e4b9b9;
}
.page-header {
  padding-bottom: 8px;
  margin: 36px 0 18px;
  border-bottom: 1px solid #eeeeee;
}
ul,
ol {
  margin-top: 0;
  margin-bottom: 9px;
}
ul ul,
ol ul,
ul ol,
ol ol {
  margin-bottom: 0;
}
.list-unstyled {
  padding-left: 0;
  list-style: none;
}
.list-inline {
  padding-left: 0;
  list-style: none;
  margin-left: -5px;
}
.list-inline > li {
  display: inline-block;
  padding-left: 5px;
  padding-right: 5px;
}
dl {
  margin-top: 0;
  margin-bottom: 18px;
}
dt,
dd {
  line-height: 1.42857143;
}
dt {
  font-weight: bold;
}
dd {
  margin-left: 0;
}
@media (min-width: 541px) {
  .dl-horizontal dt {
    float: left;
    width: 160px;
    clear: left;
    text-align: right;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
  .dl-horizontal dd {
    margin-left: 180px;
  }
}
abbr[title],
abbr[data-original-title] {
  cursor: help;
  border-bottom: 1px dotted #777777;
}
.initialism {
  font-size: 90%;
  text-transform: uppercase;
}
blockquote {
  padding: 9px 18px;
  margin: 0 0 18px;
  font-size: inherit;
  border-left: 5px solid #eeeeee;
}
blockquote p:last-child,
blockquote ul:last-child,
blockquote ol:last-child {
  margin-bottom: 0;
}
blockquote footer,
blockquote small,
blockquote .small {
  display: block;
  font-size: 80%;
  line-height: 1.42857143;
  color: #777777;
}
blockquote footer:before,
blockquote small:before,
blockquote .small:before {
  content: '\2014 \00A0';
}
.blockquote-reverse,
blockquote.pull-right {
  padding-right: 15px;
  padding-left: 0;
  border-right: 5px solid #eeeeee;
  border-left: 0;
  text-align: right;
}
.blockquote-reverse footer:before,
blockquote.pull-right footer:before,
.blockquote-reverse small:before,
blockquote.pull-right small:before,
.blockquote-reverse .small:before,
blockquote.pull-right .small:before {
  content: '';
}
.blockquote-reverse footer:after,
blockquote.pull-right footer:after,
.blockquote-reverse small:after,
blockquote.pull-right small:after,
.blockquote-reverse .small:after,
blockquote.pull-right .small:after {
  content: '\00A0 \2014';
}
address {
  margin-bottom: 18px;
  font-style: normal;
  line-height: 1.42857143;
}
code,
kbd,
pre,
samp {
  font-family: monospace;
}
code {
  padding: 2px 4px;
  font-size: 90%;
  color: #c7254e;
  background-color: #f9f2f4;
  border-radius: 2px;
}
kbd {
  padding: 2px 4px;
  font-size: 90%;
  color: #888;
  background-color: transparent;
  border-radius: 1px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
}
kbd kbd {
  padding: 0;
  font-size: 100%;
  font-weight: bold;
  box-shadow: none;
}
pre {
  display: block;
  padding: 8.5px;
  margin: 0 0 9px;
  font-size: 12px;
  line-height: 1.42857143;
  word-break: break-all;
  word-wrap: break-word;
  color: #333333;
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 2px;
}
pre code {
  padding: 0;
  font-size: inherit;
  color: inherit;
  white-space: pre-wrap;
  background-color: transparent;
  border-radius: 0;
}
.pre-scrollable {
  max-height: 340px;
  overflow-y: scroll;
}
.container {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
@media (min-width: 768px) {
  .container {
    width: 768px;
  }
}
@media (min-width: 992px) {
  .container {
    width: 940px;
  }
}
@media (min-width: 1200px) {
  .container {
    width: 1140px;
  }
}
.container-fluid {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
.row {
  margin-left: 0px;
  margin-right: 0px;
}
.col-xs-1, .col-sm-1, .col-md-1, .col-lg-1, .col-xs-2, .col-sm-2, .col-md-2, .col-lg-2, .col-xs-3, .col-sm-3, .col-md-3, .col-lg-3, .col-xs-4, .col-sm-4, .col-md-4, .col-lg-4, .col-xs-5, .col-sm-5, .col-md-5, .col-lg-5, .col-xs-6, .col-sm-6, .col-md-6, .col-lg-6, .col-xs-7, .col-sm-7, .col-md-7, .col-lg-7, .col-xs-8, .col-sm-8, .col-md-8, .col-lg-8, .col-xs-9, .col-sm-9, .col-md-9, .col-lg-9, .col-xs-10, .col-sm-10, .col-md-10, .col-lg-10, .col-xs-11, .col-sm-11, .col-md-11, .col-lg-11, .col-xs-12, .col-sm-12, .col-md-12, .col-lg-12 {
  position: relative;
  min-height: 1px;
  padding-left: 0px;
  padding-right: 0px;
}
.col-xs-1, .col-xs-2, .col-xs-3, .col-xs-4, .col-xs-5, .col-xs-6, .col-xs-7, .col-xs-8, .col-xs-9, .col-xs-10, .col-xs-11, .col-xs-12 {
  float: left;
}
.col-xs-12 {
  width: 100%;
}
.col-xs-11 {
  width: 91.66666667%;
}
.col-xs-10 {
  width: 83.33333333%;
}
.col-xs-9 {
  width: 75%;
}
.col-xs-8 {
  width: 66.66666667%;
}
.col-xs-7 {
  width: 58.33333333%;
}
.col-xs-6 {
  width: 50%;
}
.col-xs-5 {
  width: 41.66666667%;
}
.col-xs-4 {
  width: 33.33333333%;
}
.col-xs-3 {
  width: 25%;
}
.col-xs-2 {
  width: 16.66666667%;
}
.col-xs-1 {
  width: 8.33333333%;
}
.col-xs-pull-12 {
  right: 100%;
}
.col-xs-pull-11 {
  right: 91.66666667%;
}
.col-xs-pull-10 {
  right: 83.33333333%;
}
.col-xs-pull-9 {
  right: 75%;
}
.col-xs-pull-8 {
  right: 66.66666667%;
}
.col-xs-pull-7 {
  right: 58.33333333%;
}
.col-xs-pull-6 {
  right: 50%;
}
.col-xs-pull-5 {
  right: 41.66666667%;
}
.col-xs-pull-4 {
  right: 33.33333333%;
}
.col-xs-pull-3 {
  right: 25%;
}
.col-xs-pull-2 {
  right: 16.66666667%;
}
.col-xs-pull-1 {
  right: 8.33333333%;
}
.col-xs-pull-0 {
  right: auto;
}
.col-xs-push-12 {
  left: 100%;
}
.col-xs-push-11 {
  left: 91.66666667%;
}
.col-xs-push-10 {
  left: 83.33333333%;
}
.col-xs-push-9 {
  left: 75%;
}
.col-xs-push-8 {
  left: 66.66666667%;
}
.col-xs-push-7 {
  left: 58.33333333%;
}
.col-xs-push-6 {
  left: 50%;
}
.col-xs-push-5 {
  left: 41.66666667%;
}
.col-xs-push-4 {
  left: 33.33333333%;
}
.col-xs-push-3 {
  left: 25%;
}
.col-xs-push-2 {
  left: 16.66666667%;
}
.col-xs-push-1 {
  left: 8.33333333%;
}
.col-xs-push-0 {
  left: auto;
}
.col-xs-offset-12 {
  margin-left: 100%;
}
.col-xs-offset-11 {
  margin-left: 91.66666667%;
}
.col-xs-offset-10 {
  margin-left: 83.33333333%;
}
.col-xs-offset-9 {
  margin-left: 75%;
}
.col-xs-offset-8 {
  margin-left: 66.66666667%;
}
.col-xs-offset-7 {
  margin-left: 58.33333333%;
}
.col-xs-offset-6 {
  margin-left: 50%;
}
.col-xs-offset-5 {
  margin-left: 41.66666667%;
}
.col-xs-offset-4 {
  margin-left: 33.33333333%;
}
.col-xs-offset-3 {
  margin-left: 25%;
}
.col-xs-offset-2 {
  margin-left: 16.66666667%;
}
.col-xs-offset-1 {
  margin-left: 8.33333333%;
}
.col-xs-offset-0 {
  margin-left: 0%;
}
@media (min-width: 768px) {
  .col-sm-1, .col-sm-2, .col-sm-3, .col-sm-4, .col-sm-5, .col-sm-6, .col-sm-7, .col-sm-8, .col-sm-9, .col-sm-10, .col-sm-11, .col-sm-12 {
    float: left;
  }
  .col-sm-12 {
    width: 100%;
  }
  .col-sm-11 {
    width: 91.66666667%;
  }
  .col-sm-10 {
    width: 83.33333333%;
  }
  .col-sm-9 {
    width: 75%;
  }
  .col-sm-8 {
    width: 66.66666667%;
  }
  .col-sm-7 {
    width: 58.33333333%;
  }
  .col-sm-6 {
    width: 50%;
  }
  .col-sm-5 {
    width: 41.66666667%;
  }
  .col-sm-4 {
    width: 33.33333333%;
  }
  .col-sm-3 {
    width: 25%;
  }
  .col-sm-2 {
    width: 16.66666667%;
  }
  .col-sm-1 {
    width: 8.33333333%;
  }
  .col-sm-pull-12 {
    right: 100%;
  }
  .col-sm-pull-11 {
    right: 91.66666667%;
  }
  .col-sm-pull-10 {
    right: 83.33333333%;
  }
  .col-sm-pull-9 {
    right: 75%;
  }
  .col-sm-pull-8 {
    right: 66.66666667%;
  }
  .col-sm-pull-7 {
    right: 58.33333333%;
  }
  .col-sm-pull-6 {
    right: 50%;
  }
  .col-sm-pull-5 {
    right: 41.66666667%;
  }
  .col-sm-pull-4 {
    right: 33.33333333%;
  }
  .col-sm-pull-3 {
    right: 25%;
  }
  .col-sm-pull-2 {
    right: 16.66666667%;
  }
  .col-sm-pull-1 {
    right: 8.33333333%;
  }
  .col-sm-pull-0 {
    right: auto;
  }
  .col-sm-push-12 {
    left: 100%;
  }
  .col-sm-push-11 {
    left: 91.66666667%;
  }
  .col-sm-push-10 {
    left: 83.33333333%;
  }
  .col-sm-push-9 {
    left: 75%;
  }
  .col-sm-push-8 {
    left: 66.66666667%;
  }
  .col-sm-push-7 {
    left: 58.33333333%;
  }
  .col-sm-push-6 {
    left: 50%;
  }
  .col-sm-push-5 {
    left: 41.66666667%;
  }
  .col-sm-push-4 {
    left: 33.33333333%;
  }
  .col-sm-push-3 {
    left: 25%;
  }
  .col-sm-push-2 {
    left: 16.66666667%;
  }
  .col-sm-push-1 {
    left: 8.33333333%;
  }
  .col-sm-push-0 {
    left: auto;
  }
  .col-sm-offset-12 {
    margin-left: 100%;
  }
  .col-sm-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-sm-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-sm-offset-9 {
    margin-left: 75%;
  }
  .col-sm-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-sm-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-sm-offset-6 {
    margin-left: 50%;
  }
  .col-sm-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-sm-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-sm-offset-3 {
    margin-left: 25%;
  }
  .col-sm-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-sm-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-sm-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 992px) {
  .col-md-1, .col-md-2, .col-md-3, .col-md-4, .col-md-5, .col-md-6, .col-md-7, .col-md-8, .col-md-9, .col-md-10, .col-md-11, .col-md-12 {
    float: left;
  }
  .col-md-12 {
    width: 100%;
  }
  .col-md-11 {
    width: 91.66666667%;
  }
  .col-md-10 {
    width: 83.33333333%;
  }
  .col-md-9 {
    width: 75%;
  }
  .col-md-8 {
    width: 66.66666667%;
  }
  .col-md-7 {
    width: 58.33333333%;
  }
  .col-md-6 {
    width: 50%;
  }
  .col-md-5 {
    width: 41.66666667%;
  }
  .col-md-4 {
    width: 33.33333333%;
  }
  .col-md-3 {
    width: 25%;
  }
  .col-md-2 {
    width: 16.66666667%;
  }
  .col-md-1 {
    width: 8.33333333%;
  }
  .col-md-pull-12 {
    right: 100%;
  }
  .col-md-pull-11 {
    right: 91.66666667%;
  }
  .col-md-pull-10 {
    right: 83.33333333%;
  }
  .col-md-pull-9 {
    right: 75%;
  }
  .col-md-pull-8 {
    right: 66.66666667%;
  }
  .col-md-pull-7 {
    right: 58.33333333%;
  }
  .col-md-pull-6 {
    right: 50%;
  }
  .col-md-pull-5 {
    right: 41.66666667%;
  }
  .col-md-pull-4 {
    right: 33.33333333%;
  }
  .col-md-pull-3 {
    right: 25%;
  }
  .col-md-pull-2 {
    right: 16.66666667%;
  }
  .col-md-pull-1 {
    right: 8.33333333%;
  }
  .col-md-pull-0 {
    right: auto;
  }
  .col-md-push-12 {
    left: 100%;
  }
  .col-md-push-11 {
    left: 91.66666667%;
  }
  .col-md-push-10 {
    left: 83.33333333%;
  }
  .col-md-push-9 {
    left: 75%;
  }
  .col-md-push-8 {
    left: 66.66666667%;
  }
  .col-md-push-7 {
    left: 58.33333333%;
  }
  .col-md-push-6 {
    left: 50%;
  }
  .col-md-push-5 {
    left: 41.66666667%;
  }
  .col-md-push-4 {
    left: 33.33333333%;
  }
  .col-md-push-3 {
    left: 25%;
  }
  .col-md-push-2 {
    left: 16.66666667%;
  }
  .col-md-push-1 {
    left: 8.33333333%;
  }
  .col-md-push-0 {
    left: auto;
  }
  .col-md-offset-12 {
    margin-left: 100%;
  }
  .col-md-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-md-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-md-offset-9 {
    margin-left: 75%;
  }
  .col-md-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-md-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-md-offset-6 {
    margin-left: 50%;
  }
  .col-md-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-md-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-md-offset-3 {
    margin-left: 25%;
  }
  .col-md-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-md-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-md-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 1200px) {
  .col-lg-1, .col-lg-2, .col-lg-3, .col-lg-4, .col-lg-5, .col-lg-6, .col-lg-7, .col-lg-8, .col-lg-9, .col-lg-10, .col-lg-11, .col-lg-12 {
    float: left;
  }
  .col-lg-12 {
    width: 100%;
  }
  .col-lg-11 {
    width: 91.66666667%;
  }
  .col-lg-10 {
    width: 83.33333333%;
  }
  .col-lg-9 {
    width: 75%;
  }
  .col-lg-8 {
    width: 66.66666667%;
  }
  .col-lg-7 {
    width: 58.33333333%;
  }
  .col-lg-6 {
    width: 50%;
  }
  .col-lg-5 {
    width: 41.66666667%;
  }
  .col-lg-4 {
    width: 33.33333333%;
  }
  .col-lg-3 {
    width: 25%;
  }
  .col-lg-2 {
    width: 16.66666667%;
  }
  .col-lg-1 {
    width: 8.33333333%;
  }
  .col-lg-pull-12 {
    right: 100%;
  }
  .col-lg-pull-11 {
    right: 91.66666667%;
  }
  .col-lg-pull-10 {
    right: 83.33333333%;
  }
  .col-lg-pull-9 {
    right: 75%;
  }
  .col-lg-pull-8 {
    right: 66.66666667%;
  }
  .col-lg-pull-7 {
    right: 58.33333333%;
  }
  .col-lg-pull-6 {
    right: 50%;
  }
  .col-lg-pull-5 {
    right: 41.66666667%;
  }
  .col-lg-pull-4 {
    right: 33.33333333%;
  }
  .col-lg-pull-3 {
    right: 25%;
  }
  .col-lg-pull-2 {
    right: 16.66666667%;
  }
  .col-lg-pull-1 {
    right: 8.33333333%;
  }
  .col-lg-pull-0 {
    right: auto;
  }
  .col-lg-push-12 {
    left: 100%;
  }
  .col-lg-push-11 {
    left: 91.66666667%;
  }
  .col-lg-push-10 {
    left: 83.33333333%;
  }
  .col-lg-push-9 {
    left: 75%;
  }
  .col-lg-push-8 {
    left: 66.66666667%;
  }
  .col-lg-push-7 {
    left: 58.33333333%;
  }
  .col-lg-push-6 {
    left: 50%;
  }
  .col-lg-push-5 {
    left: 41.66666667%;
  }
  .col-lg-push-4 {
    left: 33.33333333%;
  }
  .col-lg-push-3 {
    left: 25%;
  }
  .col-lg-push-2 {
    left: 16.66666667%;
  }
  .col-lg-push-1 {
    left: 8.33333333%;
  }
  .col-lg-push-0 {
    left: auto;
  }
  .col-lg-offset-12 {
    margin-left: 100%;
  }
  .col-lg-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-lg-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-lg-offset-9 {
    margin-left: 75%;
  }
  .col-lg-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-lg-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-lg-offset-6 {
    margin-left: 50%;
  }
  .col-lg-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-lg-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-lg-offset-3 {
    margin-left: 25%;
  }
  .col-lg-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-lg-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-lg-offset-0 {
    margin-left: 0%;
  }
}
table {
  background-color: transparent;
}
caption {
  padding-top: 8px;
  padding-bottom: 8px;
  color: #777777;
  text-align: left;
}
th {
  text-align: left;
}
.table {
  width: 100%;
  max-width: 100%;
  margin-bottom: 18px;
}
.table > thead > tr > th,
.table > tbody > tr > th,
.table > tfoot > tr > th,
.table > thead > tr > td,
.table > tbody > tr > td,
.table > tfoot > tr > td {
  padding: 8px;
  line-height: 1.42857143;
  vertical-align: top;
  border-top: 1px solid #ddd;
}
.table > thead > tr > th {
  vertical-align: bottom;
  border-bottom: 2px solid #ddd;
}
.table > caption + thead > tr:first-child > th,
.table > colgroup + thead > tr:first-child > th,
.table > thead:first-child > tr:first-child > th,
.table > caption + thead > tr:first-child > td,
.table > colgroup + thead > tr:first-child > td,
.table > thead:first-child > tr:first-child > td {
  border-top: 0;
}
.table > tbody + tbody {
  border-top: 2px solid #ddd;
}
.table .table {
  background-color: #fff;
}
.table-condensed > thead > tr > th,
.table-condensed > tbody > tr > th,
.table-condensed > tfoot > tr > th,
.table-condensed > thead > tr > td,
.table-condensed > tbody > tr > td,
.table-condensed > tfoot > tr > td {
  padding: 5px;
}
.table-bordered {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > tbody > tr > th,
.table-bordered > tfoot > tr > th,
.table-bordered > thead > tr > td,
.table-bordered > tbody > tr > td,
.table-bordered > tfoot > tr > td {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > thead > tr > td {
  border-bottom-width: 2px;
}
.table-striped > tbody > tr:nth-of-type(odd) {
  background-color: #f9f9f9;
}
.table-hover > tbody > tr:hover {
  background-color: #f5f5f5;
}
table col[class*="col-"] {
  position: static;
  float: none;
  display: table-column;
}
table td[class*="col-"],
table th[class*="col-"] {
  position: static;
  float: none;
  display: table-cell;
}
.table > thead > tr > td.active,
.table > tbody > tr > td.active,
.table > tfoot > tr > td.active,
.table > thead > tr > th.active,
.table > tbody > tr > th.active,
.table > tfoot > tr > th.active,
.table > thead > tr.active > td,
.table > tbody > tr.active > td,
.table > tfoot > tr.active > td,
.table > thead > tr.active > th,
.table > tbody > tr.active > th,
.table > tfoot > tr.active > th {
  background-color: #f5f5f5;
}
.table-hover > tbody > tr > td.active:hover,
.table-hover > tbody > tr > th.active:hover,
.table-hover > tbody > tr.active:hover > td,
.table-hover > tbody > tr:hover > .active,
.table-hover > tbody > tr.active:hover > th {
  background-color: #e8e8e8;
}
.table > thead > tr > td.success,
.table > tbody > tr > td.success,
.table > tfoot > tr > td.success,
.table > thead > tr > th.success,
.table > tbody > tr > th.success,
.table > tfoot > tr > th.success,
.table > thead > tr.success > td,
.table > tbody > tr.success > td,
.table > tfoot > tr.success > td,
.table > thead > tr.success > th,
.table > tbody > tr.success > th,
.table > tfoot > tr.success > th {
  background-color: #dff0d8;
}
.table-hover > tbody > tr > td.success:hover,
.table-hover > tbody > tr > th.success:hover,
.table-hover > tbody > tr.success:hover > td,
.table-hover > tbody > tr:hover > .success,
.table-hover > tbody > tr.success:hover > th {
  background-color: #d0e9c6;
}
.table > thead > tr > td.info,
.table > tbody > tr > td.info,
.table > tfoot > tr > td.info,
.table > thead > tr > th.info,
.table > tbody > tr > th.info,
.table > tfoot > tr > th.info,
.table > thead > tr.info > td,
.table > tbody > tr.info > td,
.table > tfoot > tr.info > td,
.table > thead > tr.info > th,
.table > tbody > tr.info > th,
.table > tfoot > tr.info > th {
  background-color: #d9edf7;
}
.table-hover > tbody > tr > td.info:hover,
.table-hover > tbody > tr > th.info:hover,
.table-hover > tbody > tr.info:hover > td,
.table-hover > tbody > tr:hover > .info,
.table-hover > tbody > tr.info:hover > th {
  background-color: #c4e3f3;
}
.table > thead > tr > td.warning,
.table > tbody > tr > td.warning,
.table > tfoot > tr > td.warning,
.table > thead > tr > th.warning,
.table > tbody > tr > th.warning,
.table > tfoot > tr > th.warning,
.table > thead > tr.warning > td,
.table > tbody > tr.warning > td,
.table > tfoot > tr.warning > td,
.table > thead > tr.warning > th,
.table > tbody > tr.warning > th,
.table > tfoot > tr.warning > th {
  background-color: #fcf8e3;
}
.table-hover > tbody > tr > td.warning:hover,
.table-hover > tbody > tr > th.warning:hover,
.table-hover > tbody > tr.warning:hover > td,
.table-hover > tbody > tr:hover > .warning,
.table-hover > tbody > tr.warning:hover > th {
  background-color: #faf2cc;
}
.table > thead > tr > td.danger,
.table > tbody > tr > td.danger,
.table > tfoot > tr > td.danger,
.table > thead > tr > th.danger,
.table > tbody > tr > th.danger,
.table > tfoot > tr > th.danger,
.table > thead > tr.danger > td,
.table > tbody > tr.danger > td,
.table > tfoot > tr.danger > td,
.table > thead > tr.danger > th,
.table > tbody > tr.danger > th,
.table > tfoot > tr.danger > th {
  background-color: #f2dede;
}
.table-hover > tbody > tr > td.danger:hover,
.table-hover > tbody > tr > th.danger:hover,
.table-hover > tbody > tr.danger:hover > td,
.table-hover > tbody > tr:hover > .danger,
.table-hover > tbody > tr.danger:hover > th {
  background-color: #ebcccc;
}
.table-responsive {
  overflow-x: auto;
  min-height: 0.01%;
}
@media screen and (max-width: 767px) {
  .table-responsive {
    width: 100%;
    margin-bottom: 13.5px;
    overflow-y: hidden;
    -ms-overflow-style: -ms-autohiding-scrollbar;
    border: 1px solid #ddd;
  }
  .table-responsive > .table {
    margin-bottom: 0;
  }
  .table-responsive > .table > thead > tr > th,
  .table-responsive > .table > tbody > tr > th,
  .table-responsive > .table > tfoot > tr > th,
  .table-responsive > .table > thead > tr > td,
  .table-responsive > .table > tbody > tr > td,
  .table-responsive > .table > tfoot > tr > td {
    white-space: nowrap;
  }
  .table-responsive > .table-bordered {
    border: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:first-child,
  .table-responsive > .table-bordered > tbody > tr > th:first-child,
  .table-responsive > .table-bordered > tfoot > tr > th:first-child,
  .table-responsive > .table-bordered > thead > tr > td:first-child,
  .table-responsive > .table-bordered > tbody > tr > td:first-child,
  .table-responsive > .table-bordered > tfoot > tr > td:first-child {
    border-left: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:last-child,
  .table-responsive > .table-bordered > tbody > tr > th:last-child,
  .table-responsive > .table-bordered > tfoot > tr > th:last-child,
  .table-responsive > .table-bordered > thead > tr > td:last-child,
  .table-responsive > .table-bordered > tbody > tr > td:last-child,
  .table-responsive > .table-bordered > tfoot > tr > td:last-child {
    border-right: 0;
  }
  .table-responsive > .table-bordered > tbody > tr:last-child > th,
  .table-responsive > .table-bordered > tfoot > tr:last-child > th,
  .table-responsive > .table-bordered > tbody > tr:last-child > td,
  .table-responsive > .table-bordered > tfoot > tr:last-child > td {
    border-bottom: 0;
  }
}
fieldset {
  padding: 0;
  margin: 0;
  border: 0;
  min-width: 0;
}
legend {
  display: block;
  width: 100%;
  padding: 0;
  margin-bottom: 18px;
  font-size: 19.5px;
  line-height: inherit;
  color: #333333;
  border: 0;
  border-bottom: 1px solid #e5e5e5;
}
label {
  display: inline-block;
  max-width: 100%;
  margin-bottom: 5px;
  font-weight: bold;
}
input[type="search"] {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
input[type="radio"],
input[type="checkbox"] {
  margin: 4px 0 0;
  margin-top: 1px \9;
  line-height: normal;
}
input[type="file"] {
  display: block;
}
input[type="range"] {
  display: block;
  width: 100%;
}
select[multiple],
select[size] {
  height: auto;
}
input[type="file"]:focus,
input[type="radio"]:focus,
input[type="checkbox"]:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
output {
  display: block;
  padding-top: 7px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
}
.form-control {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
}
.form-control:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.form-control::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.form-control:-ms-input-placeholder {
  color: #999;
}
.form-control::-webkit-input-placeholder {
  color: #999;
}
.form-control::-ms-expand {
  border: 0;
  background-color: transparent;
}
.form-control[disabled],
.form-control[readonly],
fieldset[disabled] .form-control {
  background-color: #eeeeee;
  opacity: 1;
}
.form-control[disabled],
fieldset[disabled] .form-control {
  cursor: not-allowed;
}
textarea.form-control {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: none;
}
@media screen and (-webkit-min-device-pixel-ratio: 0) {
  input[type="date"].form-control,
  input[type="time"].form-control,
  input[type="datetime-local"].form-control,
  input[type="month"].form-control {
    line-height: 32px;
  }
  input[type="date"].input-sm,
  input[type="time"].input-sm,
  input[type="datetime-local"].input-sm,
  input[type="month"].input-sm,
  .input-group-sm input[type="date"],
  .input-group-sm input[type="time"],
  .input-group-sm input[type="datetime-local"],
  .input-group-sm input[type="month"] {
    line-height: 30px;
  }
  input[type="date"].input-lg,
  input[type="time"].input-lg,
  input[type="datetime-local"].input-lg,
  input[type="month"].input-lg,
  .input-group-lg input[type="date"],
  .input-group-lg input[type="time"],
  .input-group-lg input[type="datetime-local"],
  .input-group-lg input[type="month"] {
    line-height: 45px;
  }
}
.form-group {
  margin-bottom: 15px;
}
.radio,
.checkbox {
  position: relative;
  display: block;
  margin-top: 10px;
  margin-bottom: 10px;
}
.radio label,
.checkbox label {
  min-height: 18px;
  padding-left: 20px;
  margin-bottom: 0;
  font-weight: normal;
  cursor: pointer;
}
.radio input[type="radio"],
.radio-inline input[type="radio"],
.checkbox input[type="checkbox"],
.checkbox-inline input[type="checkbox"] {
  position: absolute;
  margin-left: -20px;
  margin-top: 4px \9;
}
.radio + .radio,
.checkbox + .checkbox {
  margin-top: -5px;
}
.radio-inline,
.checkbox-inline {
  position: relative;
  display: inline-block;
  padding-left: 20px;
  margin-bottom: 0;
  vertical-align: middle;
  font-weight: normal;
  cursor: pointer;
}
.radio-inline + .radio-inline,
.checkbox-inline + .checkbox-inline {
  margin-top: 0;
  margin-left: 10px;
}
input[type="radio"][disabled],
input[type="checkbox"][disabled],
input[type="radio"].disabled,
input[type="checkbox"].disabled,
fieldset[disabled] input[type="radio"],
fieldset[disabled] input[type="checkbox"] {
  cursor: not-allowed;
}
.radio-inline.disabled,
.checkbox-inline.disabled,
fieldset[disabled] .radio-inline,
fieldset[disabled] .checkbox-inline {
  cursor: not-allowed;
}
.radio.disabled label,
.checkbox.disabled label,
fieldset[disabled] .radio label,
fieldset[disabled] .checkbox label {
  cursor: not-allowed;
}
.form-control-static {
  padding-top: 7px;
  padding-bottom: 7px;
  margin-bottom: 0;
  min-height: 31px;
}
.form-control-static.input-lg,
.form-control-static.input-sm {
  padding-left: 0;
  padding-right: 0;
}
.input-sm {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-sm {
  height: 30px;
  line-height: 30px;
}
textarea.input-sm,
select[multiple].input-sm {
  height: auto;
}
.form-group-sm .form-control {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.form-group-sm select.form-control {
  height: 30px;
  line-height: 30px;
}
.form-group-sm textarea.form-control,
.form-group-sm select[multiple].form-control {
  height: auto;
}
.form-group-sm .form-control-static {
  height: 30px;
  min-height: 30px;
  padding: 6px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.input-lg {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-lg {
  height: 45px;
  line-height: 45px;
}
textarea.input-lg,
select[multiple].input-lg {
  height: auto;
}
.form-group-lg .form-control {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.form-group-lg select.form-control {
  height: 45px;
  line-height: 45px;
}
.form-group-lg textarea.form-control,
.form-group-lg select[multiple].form-control {
  height: auto;
}
.form-group-lg .form-control-static {
  height: 45px;
  min-height: 35px;
  padding: 11px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.has-feedback {
  position: relative;
}
.has-feedback .form-control {
  padding-right: 40px;
}
.form-control-feedback {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 2;
  display: block;
  width: 32px;
  height: 32px;
  line-height: 32px;
  text-align: center;
  pointer-events: none;
}
.input-lg + .form-control-feedback,
.input-group-lg + .form-control-feedback,
.form-group-lg .form-control + .form-control-feedback {
  width: 45px;
  height: 45px;
  line-height: 45px;
}
.input-sm + .form-control-feedback,
.input-group-sm + .form-control-feedback,
.form-group-sm .form-control + .form-control-feedback {
  width: 30px;
  height: 30px;
  line-height: 30px;
}
.has-success .help-block,
.has-success .control-label,
.has-success .radio,
.has-success .checkbox,
.has-success .radio-inline,
.has-success .checkbox-inline,
.has-success.radio label,
.has-success.checkbox label,
.has-success.radio-inline label,
.has-success.checkbox-inline label {
  color: #3c763d;
}
.has-success .form-control {
  border-color: #3c763d;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-success .form-control:focus {
  border-color: #2b542c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
}
.has-success .input-group-addon {
  color: #3c763d;
  border-color: #3c763d;
  background-color: #dff0d8;
}
.has-success .form-control-feedback {
  color: #3c763d;
}
.has-warning .help-block,
.has-warning .control-label,
.has-warning .radio,
.has-warning .checkbox,
.has-warning .radio-inline,
.has-warning .checkbox-inline,
.has-warning.radio label,
.has-warning.checkbox label,
.has-warning.radio-inline label,
.has-warning.checkbox-inline label {
  color: #8a6d3b;
}
.has-warning .form-control {
  border-color: #8a6d3b;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-warning .form-control:focus {
  border-color: #66512c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
}
.has-warning .input-group-addon {
  color: #8a6d3b;
  border-color: #8a6d3b;
  background-color: #fcf8e3;
}
.has-warning .form-control-feedback {
  color: #8a6d3b;
}
.has-error .help-block,
.has-error .control-label,
.has-error .radio,
.has-error .checkbox,
.has-error .radio-inline,
.has-error .checkbox-inline,
.has-error.radio label,
.has-error.checkbox label,
.has-error.radio-inline label,
.has-error.checkbox-inline label {
  color: #a94442;
}
.has-error .form-control {
  border-color: #a94442;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-error .form-control:focus {
  border-color: #843534;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
}
.has-error .input-group-addon {
  color: #a94442;
  border-color: #a94442;
  background-color: #f2dede;
}
.has-error .form-control-feedback {
  color: #a94442;
}
.has-feedback label ~ .form-control-feedback {
  top: 23px;
}
.has-feedback label.sr-only ~ .form-control-feedback {
  top: 0;
}
.help-block {
  display: block;
  margin-top: 5px;
  margin-bottom: 10px;
  color: #404040;
}
@media (min-width: 768px) {
  .form-inline .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .form-inline .form-control-static {
    display: inline-block;
  }
  .form-inline .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .form-inline .input-group .input-group-addon,
  .form-inline .input-group .input-group-btn,
  .form-inline .input-group .form-control {
    width: auto;
  }
  .form-inline .input-group > .form-control {
    width: 100%;
  }
  .form-inline .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio,
  .form-inline .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio label,
  .form-inline .checkbox label {
    padding-left: 0;
  }
  .form-inline .radio input[type="radio"],
  .form-inline .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .form-inline .has-feedback .form-control-feedback {
    top: 0;
  }
}
.form-horizontal .radio,
.form-horizontal .checkbox,
.form-horizontal .radio-inline,
.form-horizontal .checkbox-inline {
  margin-top: 0;
  margin-bottom: 0;
  padding-top: 7px;
}
.form-horizontal .radio,
.form-horizontal .checkbox {
  min-height: 25px;
}
.form-horizontal .form-group {
  margin-left: 0px;
  margin-right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .control-label {
    text-align: right;
    margin-bottom: 0;
    padding-top: 7px;
  }
}
.form-horizontal .has-feedback .form-control-feedback {
  right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .form-group-lg .control-label {
    padding-top: 11px;
    font-size: 17px;
  }
}
@media (min-width: 768px) {
  .form-horizontal .form-group-sm .control-label {
    padding-top: 6px;
    font-size: 12px;
  }
}
.btn {
  display: inline-block;
  margin-bottom: 0;
  font-weight: normal;
  text-align: center;
  vertical-align: middle;
  touch-action: manipulation;
  cursor: pointer;
  background-image: none;
  border: 1px solid transparent;
  white-space: nowrap;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  border-radius: 2px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.btn:focus,
.btn:active:focus,
.btn.active:focus,
.btn.focus,
.btn:active.focus,
.btn.active.focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
.btn:hover,
.btn:focus,
.btn.focus {
  color: #333;
  text-decoration: none;
}
.btn:active,
.btn.active {
  outline: 0;
  background-image: none;
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn.disabled,
.btn[disabled],
fieldset[disabled] .btn {
  cursor: not-allowed;
  opacity: 0.65;
  filter: alpha(opacity=65);
  -webkit-box-shadow: none;
  box-shadow: none;
}
a.btn.disabled,
fieldset[disabled] a.btn {
  pointer-events: none;
}
.btn-default {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.btn-default:focus,
.btn-default.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.btn-default:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active:hover,
.btn-default.active:hover,
.open > .dropdown-toggle.btn-default:hover,
.btn-default:active:focus,
.btn-default.active:focus,
.open > .dropdown-toggle.btn-default:focus,
.btn-default:active.focus,
.btn-default.active.focus,
.open > .dropdown-toggle.btn-default.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  background-image: none;
}
.btn-default.disabled:hover,
.btn-default[disabled]:hover,
fieldset[disabled] .btn-default:hover,
.btn-default.disabled:focus,
.btn-default[disabled]:focus,
fieldset[disabled] .btn-default:focus,
.btn-default.disabled.focus,
.btn-default[disabled].focus,
fieldset[disabled] .btn-default.focus {
  background-color: #fff;
  border-color: #ccc;
}
.btn-default .badge {
  color: #fff;
  background-color: #333;
}
.btn-primary {
  color: #fff;
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary:focus,
.btn-primary.focus {
  color: #fff;
  background-color: #286090;
  border-color: #122b40;
}
.btn-primary:hover {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active:hover,
.btn-primary.active:hover,
.open > .dropdown-toggle.btn-primary:hover,
.btn-primary:active:focus,
.btn-primary.active:focus,
.open > .dropdown-toggle.btn-primary:focus,
.btn-primary:active.focus,
.btn-primary.active.focus,
.open > .dropdown-toggle.btn-primary.focus {
  color: #fff;
  background-color: #204d74;
  border-color: #122b40;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  background-image: none;
}
.btn-primary.disabled:hover,
.btn-primary[disabled]:hover,
fieldset[disabled] .btn-primary:hover,
.btn-primary.disabled:focus,
.btn-primary[disabled]:focus,
fieldset[disabled] .btn-primary:focus,
.btn-primary.disabled.focus,
.btn-primary[disabled].focus,
fieldset[disabled] .btn-primary.focus {
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary .badge {
  color: #337ab7;
  background-color: #fff;
}
.btn-success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success:focus,
.btn-success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.btn-success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active:hover,
.btn-success.active:hover,
.open > .dropdown-toggle.btn-success:hover,
.btn-success:active:focus,
.btn-success.active:focus,
.open > .dropdown-toggle.btn-success:focus,
.btn-success:active.focus,
.btn-success.active.focus,
.open > .dropdown-toggle.btn-success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  background-image: none;
}
.btn-success.disabled:hover,
.btn-success[disabled]:hover,
fieldset[disabled] .btn-success:hover,
.btn-success.disabled:focus,
.btn-success[disabled]:focus,
fieldset[disabled] .btn-success:focus,
.btn-success.disabled.focus,
.btn-success[disabled].focus,
fieldset[disabled] .btn-success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.btn-info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info:focus,
.btn-info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.btn-info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active:hover,
.btn-info.active:hover,
.open > .dropdown-toggle.btn-info:hover,
.btn-info:active:focus,
.btn-info.active:focus,
.open > .dropdown-toggle.btn-info:focus,
.btn-info:active.focus,
.btn-info.active.focus,
.open > .dropdown-toggle.btn-info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  background-image: none;
}
.btn-info.disabled:hover,
.btn-info[disabled]:hover,
fieldset[disabled] .btn-info:hover,
.btn-info.disabled:focus,
.btn-info[disabled]:focus,
fieldset[disabled] .btn-info:focus,
.btn-info.disabled.focus,
.btn-info[disabled].focus,
fieldset[disabled] .btn-info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.btn-warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning:focus,
.btn-warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.btn-warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active:hover,
.btn-warning.active:hover,
.open > .dropdown-toggle.btn-warning:hover,
.btn-warning:active:focus,
.btn-warning.active:focus,
.open > .dropdown-toggle.btn-warning:focus,
.btn-warning:active.focus,
.btn-warning.active.focus,
.open > .dropdown-toggle.btn-warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  background-image: none;
}
.btn-warning.disabled:hover,
.btn-warning[disabled]:hover,
fieldset[disabled] .btn-warning:hover,
.btn-warning.disabled:focus,
.btn-warning[disabled]:focus,
fieldset[disabled] .btn-warning:focus,
.btn-warning.disabled.focus,
.btn-warning[disabled].focus,
fieldset[disabled] .btn-warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.btn-danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger:focus,
.btn-danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.btn-danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active:hover,
.btn-danger.active:hover,
.open > .dropdown-toggle.btn-danger:hover,
.btn-danger:active:focus,
.btn-danger.active:focus,
.open > .dropdown-toggle.btn-danger:focus,
.btn-danger:active.focus,
.btn-danger.active.focus,
.open > .dropdown-toggle.btn-danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  background-image: none;
}
.btn-danger.disabled:hover,
.btn-danger[disabled]:hover,
fieldset[disabled] .btn-danger:hover,
.btn-danger.disabled:focus,
.btn-danger[disabled]:focus,
fieldset[disabled] .btn-danger:focus,
.btn-danger.disabled.focus,
.btn-danger[disabled].focus,
fieldset[disabled] .btn-danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger .badge {
  color: #d9534f;
  background-color: #fff;
}
.btn-link {
  color: #337ab7;
  font-weight: normal;
  border-radius: 0;
}
.btn-link,
.btn-link:active,
.btn-link.active,
.btn-link[disabled],
fieldset[disabled] .btn-link {
  background-color: transparent;
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn-link,
.btn-link:hover,
.btn-link:focus,
.btn-link:active {
  border-color: transparent;
}
.btn-link:hover,
.btn-link:focus {
  color: #23527c;
  text-decoration: underline;
  background-color: transparent;
}
.btn-link[disabled]:hover,
fieldset[disabled] .btn-link:hover,
.btn-link[disabled]:focus,
fieldset[disabled] .btn-link:focus {
  color: #777777;
  text-decoration: none;
}
.btn-lg,
.btn-group-lg > .btn {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.btn-sm,
.btn-group-sm > .btn {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-xs,
.btn-group-xs > .btn {
  padding: 1px 5px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-block {
  display: block;
  width: 100%;
}
.btn-block + .btn-block {
  margin-top: 5px;
}
input[type="submit"].btn-block,
input[type="reset"].btn-block,
input[type="button"].btn-block {
  width: 100%;
}
.fade {
  opacity: 0;
  -webkit-transition: opacity 0.15s linear;
  -o-transition: opacity 0.15s linear;
  transition: opacity 0.15s linear;
}
.fade.in {
  opacity: 1;
}
.collapse {
  display: none;
}
.collapse.in {
  display: block;
}
tr.collapse.in {
  display: table-row;
}
tbody.collapse.in {
  display: table-row-group;
}
.collapsing {
  position: relative;
  height: 0;
  overflow: hidden;
  -webkit-transition-property: height, visibility;
  transition-property: height, visibility;
  -webkit-transition-duration: 0.35s;
  transition-duration: 0.35s;
  -webkit-transition-timing-function: ease;
  transition-timing-function: ease;
}
.caret {
  display: inline-block;
  width: 0;
  height: 0;
  margin-left: 2px;
  vertical-align: middle;
  border-top: 4px dashed;
  border-top: 4px solid \9;
  border-right: 4px solid transparent;
  border-left: 4px solid transparent;
}
.dropup,
.dropdown {
  position: relative;
}
.dropdown-toggle:focus {
  outline: 0;
}
.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  z-index: 1000;
  display: none;
  float: left;
  min-width: 160px;
  padding: 5px 0;
  margin: 2px 0 0;
  list-style: none;
  font-size: 13px;
  text-align: left;
  background-color: #fff;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.15);
  border-radius: 2px;
  -webkit-box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  background-clip: padding-box;
}
.dropdown-menu.pull-right {
  right: 0;
  left: auto;
}
.dropdown-menu .divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.dropdown-menu > li > a {
  display: block;
  padding: 3px 20px;
  clear: both;
  font-weight: normal;
  line-height: 1.42857143;
  color: #333333;
  white-space: nowrap;
}
.dropdown-menu > li > a:hover,
.dropdown-menu > li > a:focus {
  text-decoration: none;
  color: #262626;
  background-color: #f5f5f5;
}
.dropdown-menu > .active > a,
.dropdown-menu > .active > a:hover,
.dropdown-menu > .active > a:focus {
  color: #fff;
  text-decoration: none;
  outline: 0;
  background-color: #337ab7;
}
.dropdown-menu > .disabled > a,
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  color: #777777;
}
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  text-decoration: none;
  background-color: transparent;
  background-image: none;
  filter: progid:DXImageTransform.Microsoft.gradient(enabled = false);
  cursor: not-allowed;
}
.open > .dropdown-menu {
  display: block;
}
.open > a {
  outline: 0;
}
.dropdown-menu-right {
  left: auto;
  right: 0;
}
.dropdown-menu-left {
  left: 0;
  right: auto;
}
.dropdown-header {
  display: block;
  padding: 3px 20px;
  font-size: 12px;
  line-height: 1.42857143;
  color: #777777;
  white-space: nowrap;
}
.dropdown-backdrop {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  top: 0;
  z-index: 990;
}
.pull-right > .dropdown-menu {
  right: 0;
  left: auto;
}
.dropup .caret,
.navbar-fixed-bottom .dropdown .caret {
  border-top: 0;
  border-bottom: 4px dashed;
  border-bottom: 4px solid \9;
  content: "";
}
.dropup .dropdown-menu,
.navbar-fixed-bottom .dropdown .dropdown-menu {
  top: auto;
  bottom: 100%;
  margin-bottom: 2px;
}
@media (min-width: 541px) {
  .navbar-right .dropdown-menu {
    left: auto;
    right: 0;
  }
  .navbar-right .dropdown-menu-left {
    left: 0;
    right: auto;
  }
}
.btn-group,
.btn-group-vertical {
  position: relative;
  display: inline-block;
  vertical-align: middle;
}
.btn-group > .btn,
.btn-group-vertical > .btn {
  position: relative;
  float: left;
}
.btn-group > .btn:hover,
.btn-group-vertical > .btn:hover,
.btn-group > .btn:focus,
.btn-group-vertical > .btn:focus,
.btn-group > .btn:active,
.btn-group-vertical > .btn:active,
.btn-group > .btn.active,
.btn-group-vertical > .btn.active {
  z-index: 2;
}
.btn-group .btn + .btn,
.btn-group .btn + .btn-group,
.btn-group .btn-group + .btn,
.btn-group .btn-group + .btn-group {
  margin-left: -1px;
}
.btn-toolbar {
  margin-left: -5px;
}
.btn-toolbar .btn,
.btn-toolbar .btn-group,
.btn-toolbar .input-group {
  float: left;
}
.btn-toolbar > .btn,
.btn-toolbar > .btn-group,
.btn-toolbar > .input-group {
  margin-left: 5px;
}
.btn-group > .btn:not(:first-child):not(:last-child):not(.dropdown-toggle) {
  border-radius: 0;
}
.btn-group > .btn:first-child {
  margin-left: 0;
}
.btn-group > .btn:first-child:not(:last-child):not(.dropdown-toggle) {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn:last-child:not(:first-child),
.btn-group > .dropdown-toggle:not(:first-child) {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group > .btn-group {
  float: left;
}
.btn-group > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group .dropdown-toggle:active,
.btn-group.open .dropdown-toggle {
  outline: 0;
}
.btn-group > .btn + .dropdown-toggle {
  padding-left: 8px;
  padding-right: 8px;
}
.btn-group > .btn-lg + .dropdown-toggle {
  padding-left: 12px;
  padding-right: 12px;
}
.btn-group.open .dropdown-toggle {
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn-group.open .dropdown-toggle.btn-link {
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn .caret {
  margin-left: 0;
}
.btn-lg .caret {
  border-width: 5px 5px 0;
  border-bottom-width: 0;
}
.dropup .btn-lg .caret {
  border-width: 0 5px 5px;
}
.btn-group-vertical > .btn,
.btn-group-vertical > .btn-group,
.btn-group-vertical > .btn-group > .btn {
  display: block;
  float: none;
  width: 100%;
  max-width: 100%;
}
.btn-group-vertical > .btn-group > .btn {
  float: none;
}
.btn-group-vertical > .btn + .btn,
.btn-group-vertical > .btn + .btn-group,
.btn-group-vertical > .btn-group + .btn,
.btn-group-vertical > .btn-group + .btn-group {
  margin-top: -1px;
  margin-left: 0;
}
.btn-group-vertical > .btn:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.btn-group-vertical > .btn:first-child:not(:last-child) {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn:last-child:not(:first-child) {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
.btn-group-vertical > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.btn-group-justified {
  display: table;
  width: 100%;
  table-layout: fixed;
  border-collapse: separate;
}
.btn-group-justified > .btn,
.btn-group-justified > .btn-group {
  float: none;
  display: table-cell;
  width: 1%;
}
.btn-group-justified > .btn-group .btn {
  width: 100%;
}
.btn-group-justified > .btn-group .dropdown-menu {
  left: auto;
}
[data-toggle="buttons"] > .btn input[type="radio"],
[data-toggle="buttons"] > .btn-group > .btn input[type="radio"],
[data-toggle="buttons"] > .btn input[type="checkbox"],
[data-toggle="buttons"] > .btn-group > .btn input[type="checkbox"] {
  position: absolute;
  clip: rect(0, 0, 0, 0);
  pointer-events: none;
}
.input-group {
  position: relative;
  display: table;
  border-collapse: separate;
}
.input-group[class*="col-"] {
  float: none;
  padding-left: 0;
  padding-right: 0;
}
.input-group .form-control {
  position: relative;
  z-index: 2;
  float: left;
  width: 100%;
  margin-bottom: 0;
}
.input-group .form-control:focus {
  z-index: 3;
}
.input-group-lg > .form-control,
.input-group-lg > .input-group-addon,
.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-group-lg > .form-control,
select.input-group-lg > .input-group-addon,
select.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  line-height: 45px;
}
textarea.input-group-lg > .form-control,
textarea.input-group-lg > .input-group-addon,
textarea.input-group-lg > .input-group-btn > .btn,
select[multiple].input-group-lg > .form-control,
select[multiple].input-group-lg > .input-group-addon,
select[multiple].input-group-lg > .input-group-btn > .btn {
  height: auto;
}
.input-group-sm > .form-control,
.input-group-sm > .input-group-addon,
.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-group-sm > .form-control,
select.input-group-sm > .input-group-addon,
select.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  line-height: 30px;
}
textarea.input-group-sm > .form-control,
textarea.input-group-sm > .input-group-addon,
textarea.input-group-sm > .input-group-btn > .btn,
select[multiple].input-group-sm > .form-control,
select[multiple].input-group-sm > .input-group-addon,
select[multiple].input-group-sm > .input-group-btn > .btn {
  height: auto;
}
.input-group-addon,
.input-group-btn,
.input-group .form-control {
  display: table-cell;
}
.input-group-addon:not(:first-child):not(:last-child),
.input-group-btn:not(:first-child):not(:last-child),
.input-group .form-control:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.input-group-addon,
.input-group-btn {
  width: 1%;
  white-space: nowrap;
  vertical-align: middle;
}
.input-group-addon {
  padding: 6px 12px;
  font-size: 13px;
  font-weight: normal;
  line-height: 1;
  color: #555555;
  text-align: center;
  background-color: #eeeeee;
  border: 1px solid #ccc;
  border-radius: 2px;
}
.input-group-addon.input-sm {
  padding: 5px 10px;
  font-size: 12px;
  border-radius: 1px;
}
.input-group-addon.input-lg {
  padding: 10px 16px;
  font-size: 17px;
  border-radius: 3px;
}
.input-group-addon input[type="radio"],
.input-group-addon input[type="checkbox"] {
  margin-top: 0;
}
.input-group .form-control:first-child,
.input-group-addon:first-child,
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group > .btn,
.input-group-btn:first-child > .dropdown-toggle,
.input-group-btn:last-child > .btn:not(:last-child):not(.dropdown-toggle),
.input-group-btn:last-child > .btn-group:not(:last-child) > .btn {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.input-group-addon:first-child {
  border-right: 0;
}
.input-group .form-control:last-child,
.input-group-addon:last-child,
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group > .btn,
.input-group-btn:last-child > .dropdown-toggle,
.input-group-btn:first-child > .btn:not(:first-child),
.input-group-btn:first-child > .btn-group:not(:first-child) > .btn {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.input-group-addon:last-child {
  border-left: 0;
}
.input-group-btn {
  position: relative;
  font-size: 0;
  white-space: nowrap;
}
.input-group-btn > .btn {
  position: relative;
}
.input-group-btn > .btn + .btn {
  margin-left: -1px;
}
.input-group-btn > .btn:hover,
.input-group-btn > .btn:focus,
.input-group-btn > .btn:active {
  z-index: 2;
}
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group {
  margin-right: -1px;
}
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group {
  z-index: 2;
  margin-left: -1px;
}
.nav {
  margin-bottom: 0;
  padding-left: 0;
  list-style: none;
}
.nav > li {
  position: relative;
  display: block;
}
.nav > li > a {
  position: relative;
  display: block;
  padding: 10px 15px;
}
.nav > li > a:hover,
.nav > li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.nav > li.disabled > a {
  color: #777777;
}
.nav > li.disabled > a:hover,
.nav > li.disabled > a:focus {
  color: #777777;
  text-decoration: none;
  background-color: transparent;
  cursor: not-allowed;
}
.nav .open > a,
.nav .open > a:hover,
.nav .open > a:focus {
  background-color: #eeeeee;
  border-color: #337ab7;
}
.nav .nav-divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.nav > li > a > img {
  max-width: none;
}
.nav-tabs {
  border-bottom: 1px solid #ddd;
}
.nav-tabs > li {
  float: left;
  margin-bottom: -1px;
}
.nav-tabs > li > a {
  margin-right: 2px;
  line-height: 1.42857143;
  border: 1px solid transparent;
  border-radius: 2px 2px 0 0;
}
.nav-tabs > li > a:hover {
  border-color: #eeeeee #eeeeee #ddd;
}
.nav-tabs > li.active > a,
.nav-tabs > li.active > a:hover,
.nav-tabs > li.active > a:focus {
  color: #555555;
  background-color: #fff;
  border: 1px solid #ddd;
  border-bottom-color: transparent;
  cursor: default;
}
.nav-tabs.nav-justified {
  width: 100%;
  border-bottom: 0;
}
.nav-tabs.nav-justified > li {
  float: none;
}
.nav-tabs.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-tabs.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-tabs.nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs.nav-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs.nav-justified > .active > a,
.nav-tabs.nav-justified > .active > a:hover,
.nav-tabs.nav-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs.nav-justified > .active > a,
  .nav-tabs.nav-justified > .active > a:hover,
  .nav-tabs.nav-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.nav-pills > li {
  float: left;
}
.nav-pills > li > a {
  border-radius: 2px;
}
.nav-pills > li + li {
  margin-left: 2px;
}
.nav-pills > li.active > a,
.nav-pills > li.active > a:hover,
.nav-pills > li.active > a:focus {
  color: #fff;
  background-color: #337ab7;
}
.nav-stacked > li {
  float: none;
}
.nav-stacked > li + li {
  margin-top: 2px;
  margin-left: 0;
}
.nav-justified {
  width: 100%;
}
.nav-justified > li {
  float: none;
}
.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs-justified {
  border-bottom: 0;
}
.nav-tabs-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs-justified > .active > a,
.nav-tabs-justified > .active > a:hover,
.nav-tabs-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs-justified > .active > a,
  .nav-tabs-justified > .active > a:hover,
  .nav-tabs-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.tab-content > .tab-pane {
  display: none;
}
.tab-content > .active {
  display: block;
}
.nav-tabs .dropdown-menu {
  margin-top: -1px;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar {
  position: relative;
  min-height: 30px;
  margin-bottom: 18px;
  border: 1px solid transparent;
}
@media (min-width: 541px) {
  .navbar {
    border-radius: 2px;
  }
}
@media (min-width: 541px) {
  .navbar-header {
    float: left;
  }
}
.navbar-collapse {
  overflow-x: visible;
  padding-right: 0px;
  padding-left: 0px;
  border-top: 1px solid transparent;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1);
  -webkit-overflow-scrolling: touch;
}
.navbar-collapse.in {
  overflow-y: auto;
}
@media (min-width: 541px) {
  .navbar-collapse {
    width: auto;
    border-top: 0;
    box-shadow: none;
  }
  .navbar-collapse.collapse {
    display: block !important;
    height: auto !important;
    padding-bottom: 0;
    overflow: visible !important;
  }
  .navbar-collapse.in {
    overflow-y: visible;
  }
  .navbar-fixed-top .navbar-collapse,
  .navbar-static-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    padding-left: 0;
    padding-right: 0;
  }
}
.navbar-fixed-top .navbar-collapse,
.navbar-fixed-bottom .navbar-collapse {
  max-height: 340px;
}
@media (max-device-width: 540px) and (orientation: landscape) {
  .navbar-fixed-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    max-height: 200px;
  }
}
.container > .navbar-header,
.container-fluid > .navbar-header,
.container > .navbar-collapse,
.container-fluid > .navbar-collapse {
  margin-right: 0px;
  margin-left: 0px;
}
@media (min-width: 541px) {
  .container > .navbar-header,
  .container-fluid > .navbar-header,
  .container > .navbar-collapse,
  .container-fluid > .navbar-collapse {
    margin-right: 0;
    margin-left: 0;
  }
}
.navbar-static-top {
  z-index: 1000;
  border-width: 0 0 1px;
}
@media (min-width: 541px) {
  .navbar-static-top {
    border-radius: 0;
  }
}
.navbar-fixed-top,
.navbar-fixed-bottom {
  position: fixed;
  right: 0;
  left: 0;
  z-index: 1030;
}
@media (min-width: 541px) {
  .navbar-fixed-top,
  .navbar-fixed-bottom {
    border-radius: 0;
  }
}
.navbar-fixed-top {
  top: 0;
  border-width: 0 0 1px;
}
.navbar-fixed-bottom {
  bottom: 0;
  margin-bottom: 0;
  border-width: 1px 0 0;
}
.navbar-brand {
  float: left;
  padding: 6px 0px;
  font-size: 17px;
  line-height: 18px;
  height: 30px;
}
.navbar-brand:hover,
.navbar-brand:focus {
  text-decoration: none;
}
.navbar-brand > img {
  display: block;
}
@media (min-width: 541px) {
  .navbar > .container .navbar-brand,
  .navbar > .container-fluid .navbar-brand {
    margin-left: 0px;
  }
}
.navbar-toggle {
  position: relative;
  float: right;
  margin-right: 0px;
  padding: 9px 10px;
  margin-top: -2px;
  margin-bottom: -2px;
  background-color: transparent;
  background-image: none;
  border: 1px solid transparent;
  border-radius: 2px;
}
.navbar-toggle:focus {
  outline: 0;
}
.navbar-toggle .icon-bar {
  display: block;
  width: 22px;
  height: 2px;
  border-radius: 1px;
}
.navbar-toggle .icon-bar + .icon-bar {
  margin-top: 4px;
}
@media (min-width: 541px) {
  .navbar-toggle {
    display: none;
  }
}
.navbar-nav {
  margin: 3px 0px;
}
.navbar-nav > li > a {
  padding-top: 10px;
  padding-bottom: 10px;
  line-height: 18px;
}
@media (max-width: 540px) {
  .navbar-nav .open .dropdown-menu {
    position: static;
    float: none;
    width: auto;
    margin-top: 0;
    background-color: transparent;
    border: 0;
    box-shadow: none;
  }
  .navbar-nav .open .dropdown-menu > li > a,
  .navbar-nav .open .dropdown-menu .dropdown-header {
    padding: 5px 15px 5px 25px;
  }
  .navbar-nav .open .dropdown-menu > li > a {
    line-height: 18px;
  }
  .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-nav .open .dropdown-menu > li > a:focus {
    background-image: none;
  }
}
@media (min-width: 541px) {
  .navbar-nav {
    float: left;
    margin: 0;
  }
  .navbar-nav > li {
    float: left;
  }
  .navbar-nav > li > a {
    padding-top: 6px;
    padding-bottom: 6px;
  }
}
.navbar-form {
  margin-left: 0px;
  margin-right: 0px;
  padding: 10px 0px;
  border-top: 1px solid transparent;
  border-bottom: 1px solid transparent;
  -webkit-box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  margin-top: -1px;
  margin-bottom: -1px;
}
@media (min-width: 768px) {
  .navbar-form .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .navbar-form .form-control-static {
    display: inline-block;
  }
  .navbar-form .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .navbar-form .input-group .input-group-addon,
  .navbar-form .input-group .input-group-btn,
  .navbar-form .input-group .form-control {
    width: auto;
  }
  .navbar-form .input-group > .form-control {
    width: 100%;
  }
  .navbar-form .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio,
  .navbar-form .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio label,
  .navbar-form .checkbox label {
    padding-left: 0;
  }
  .navbar-form .radio input[type="radio"],
  .navbar-form .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .navbar-form .has-feedback .form-control-feedback {
    top: 0;
  }
}
@media (max-width: 540px) {
  .navbar-form .form-group {
    margin-bottom: 5px;
  }
  .navbar-form .form-group:last-child {
    margin-bottom: 0;
  }
}
@media (min-width: 541px) {
  .navbar-form {
    width: auto;
    border: 0;
    margin-left: 0;
    margin-right: 0;
    padding-top: 0;
    padding-bottom: 0;
    -webkit-box-shadow: none;
    box-shadow: none;
  }
}
.navbar-nav > li > .dropdown-menu {
  margin-top: 0;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar-fixed-bottom .navbar-nav > li > .dropdown-menu {
  margin-bottom: 0;
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.navbar-btn {
  margin-top: -1px;
  margin-bottom: -1px;
}
.navbar-btn.btn-sm {
  margin-top: 0px;
  margin-bottom: 0px;
}
.navbar-btn.btn-xs {
  margin-top: 4px;
  margin-bottom: 4px;
}
.navbar-text {
  margin-top: 6px;
  margin-bottom: 6px;
}
@media (min-width: 541px) {
  .navbar-text {
    float: left;
    margin-left: 0px;
    margin-right: 0px;
  }
}
@media (min-width: 541px) {
  .navbar-left {
    float: left !important;
    float: left;
  }
  .navbar-right {
    float: right !important;
    float: right;
    margin-right: 0px;
  }
  .navbar-right ~ .navbar-right {
    margin-right: 0;
  }
}
.navbar-default {
  background-color: #f8f8f8;
  border-color: #e7e7e7;
}
.navbar-default .navbar-brand {
  color: #777;
}
.navbar-default .navbar-brand:hover,
.navbar-default .navbar-brand:focus {
  color: #5e5e5e;
  background-color: transparent;
}
.navbar-default .navbar-text {
  color: #777;
}
.navbar-default .navbar-nav > li > a {
  color: #777;
}
.navbar-default .navbar-nav > li > a:hover,
.navbar-default .navbar-nav > li > a:focus {
  color: #333;
  background-color: transparent;
}
.navbar-default .navbar-nav > .active > a,
.navbar-default .navbar-nav > .active > a:hover,
.navbar-default .navbar-nav > .active > a:focus {
  color: #555;
  background-color: #e7e7e7;
}
.navbar-default .navbar-nav > .disabled > a,
.navbar-default .navbar-nav > .disabled > a:hover,
.navbar-default .navbar-nav > .disabled > a:focus {
  color: #ccc;
  background-color: transparent;
}
.navbar-default .navbar-toggle {
  border-color: #ddd;
}
.navbar-default .navbar-toggle:hover,
.navbar-default .navbar-toggle:focus {
  background-color: #ddd;
}
.navbar-default .navbar-toggle .icon-bar {
  background-color: #888;
}
.navbar-default .navbar-collapse,
.navbar-default .navbar-form {
  border-color: #e7e7e7;
}
.navbar-default .navbar-nav > .open > a,
.navbar-default .navbar-nav > .open > a:hover,
.navbar-default .navbar-nav > .open > a:focus {
  background-color: #e7e7e7;
  color: #555;
}
@media (max-width: 540px) {
  .navbar-default .navbar-nav .open .dropdown-menu > li > a {
    color: #777;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #333;
    background-color: transparent;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #555;
    background-color: #e7e7e7;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #ccc;
    background-color: transparent;
  }
}
.navbar-default .navbar-link {
  color: #777;
}
.navbar-default .navbar-link:hover {
  color: #333;
}
.navbar-default .btn-link {
  color: #777;
}
.navbar-default .btn-link:hover,
.navbar-default .btn-link:focus {
  color: #333;
}
.navbar-default .btn-link[disabled]:hover,
fieldset[disabled] .navbar-default .btn-link:hover,
.navbar-default .btn-link[disabled]:focus,
fieldset[disabled] .navbar-default .btn-link:focus {
  color: #ccc;
}
.navbar-inverse {
  background-color: #222;
  border-color: #080808;
}
.navbar-inverse .navbar-brand {
  color: #9d9d9d;
}
.navbar-inverse .navbar-brand:hover,
.navbar-inverse .navbar-brand:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-text {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a:hover,
.navbar-inverse .navbar-nav > li > a:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-nav > .active > a,
.navbar-inverse .navbar-nav > .active > a:hover,
.navbar-inverse .navbar-nav > .active > a:focus {
  color: #fff;
  background-color: #080808;
}
.navbar-inverse .navbar-nav > .disabled > a,
.navbar-inverse .navbar-nav > .disabled > a:hover,
.navbar-inverse .navbar-nav > .disabled > a:focus {
  color: #444;
  background-color: transparent;
}
.navbar-inverse .navbar-toggle {
  border-color: #333;
}
.navbar-inverse .navbar-toggle:hover,
.navbar-inverse .navbar-toggle:focus {
  background-color: #333;
}
.navbar-inverse .navbar-toggle .icon-bar {
  background-color: #fff;
}
.navbar-inverse .navbar-collapse,
.navbar-inverse .navbar-form {
  border-color: #101010;
}
.navbar-inverse .navbar-nav > .open > a,
.navbar-inverse .navbar-nav > .open > a:hover,
.navbar-inverse .navbar-nav > .open > a:focus {
  background-color: #080808;
  color: #fff;
}
@media (max-width: 540px) {
  .navbar-inverse .navbar-nav .open .dropdown-menu > .dropdown-header {
    border-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu .divider {
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a {
    color: #9d9d9d;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #fff;
    background-color: transparent;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #fff;
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #444;
    background-color: transparent;
  }
}
.navbar-inverse .navbar-link {
  color: #9d9d9d;
}
.navbar-inverse .navbar-link:hover {
  color: #fff;
}
.navbar-inverse .btn-link {
  color: #9d9d9d;
}
.navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link:focus {
  color: #fff;
}
.navbar-inverse .btn-link[disabled]:hover,
fieldset[disabled] .navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link[disabled]:focus,
fieldset[disabled] .navbar-inverse .btn-link:focus {
  color: #444;
}
.breadcrumb {
  padding: 8px 15px;
  margin-bottom: 18px;
  list-style: none;
  background-color: #f5f5f5;
  border-radius: 2px;
}
.breadcrumb > li {
  display: inline-block;
}
.breadcrumb > li + li:before {
  content: "/\00a0";
  padding: 0 5px;
  color: #5e5e5e;
}
.breadcrumb > .active {
  color: #777777;
}
.pagination {
  display: inline-block;
  padding-left: 0;
  margin: 18px 0;
  border-radius: 2px;
}
.pagination > li {
  display: inline;
}
.pagination > li > a,
.pagination > li > span {
  position: relative;
  float: left;
  padding: 6px 12px;
  line-height: 1.42857143;
  text-decoration: none;
  color: #337ab7;
  background-color: #fff;
  border: 1px solid #ddd;
  margin-left: -1px;
}
.pagination > li:first-child > a,
.pagination > li:first-child > span {
  margin-left: 0;
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.pagination > li:last-child > a,
.pagination > li:last-child > span {
  border-bottom-right-radius: 2px;
  border-top-right-radius: 2px;
}
.pagination > li > a:hover,
.pagination > li > span:hover,
.pagination > li > a:focus,
.pagination > li > span:focus {
  z-index: 2;
  color: #23527c;
  background-color: #eeeeee;
  border-color: #ddd;
}
.pagination > .active > a,
.pagination > .active > span,
.pagination > .active > a:hover,
.pagination > .active > span:hover,
.pagination > .active > a:focus,
.pagination > .active > span:focus {
  z-index: 3;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
  cursor: default;
}
.pagination > .disabled > span,
.pagination > .disabled > span:hover,
.pagination > .disabled > span:focus,
.pagination > .disabled > a,
.pagination > .disabled > a:hover,
.pagination > .disabled > a:focus {
  color: #777777;
  background-color: #fff;
  border-color: #ddd;
  cursor: not-allowed;
}
.pagination-lg > li > a,
.pagination-lg > li > span {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.pagination-lg > li:first-child > a,
.pagination-lg > li:first-child > span {
  border-bottom-left-radius: 3px;
  border-top-left-radius: 3px;
}
.pagination-lg > li:last-child > a,
.pagination-lg > li:last-child > span {
  border-bottom-right-radius: 3px;
  border-top-right-radius: 3px;
}
.pagination-sm > li > a,
.pagination-sm > li > span {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.pagination-sm > li:first-child > a,
.pagination-sm > li:first-child > span {
  border-bottom-left-radius: 1px;
  border-top-left-radius: 1px;
}
.pagination-sm > li:last-child > a,
.pagination-sm > li:last-child > span {
  border-bottom-right-radius: 1px;
  border-top-right-radius: 1px;
}
.pager {
  padding-left: 0;
  margin: 18px 0;
  list-style: none;
  text-align: center;
}
.pager li {
  display: inline;
}
.pager li > a,
.pager li > span {
  display: inline-block;
  padding: 5px 14px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 15px;
}
.pager li > a:hover,
.pager li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.pager .next > a,
.pager .next > span {
  float: right;
}
.pager .previous > a,
.pager .previous > span {
  float: left;
}
.pager .disabled > a,
.pager .disabled > a:hover,
.pager .disabled > a:focus,
.pager .disabled > span {
  color: #777777;
  background-color: #fff;
  cursor: not-allowed;
}
.label {
  display: inline;
  padding: .2em .6em .3em;
  font-size: 75%;
  font-weight: bold;
  line-height: 1;
  color: #fff;
  text-align: center;
  white-space: nowrap;
  vertical-align: baseline;
  border-radius: .25em;
}
a.label:hover,
a.label:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.label:empty {
  display: none;
}
.btn .label {
  position: relative;
  top: -1px;
}
.label-default {
  background-color: #777777;
}
.label-default[href]:hover,
.label-default[href]:focus {
  background-color: #5e5e5e;
}
.label-primary {
  background-color: #337ab7;
}
.label-primary[href]:hover,
.label-primary[href]:focus {
  background-color: #286090;
}
.label-success {
  background-color: #5cb85c;
}
.label-success[href]:hover,
.label-success[href]:focus {
  background-color: #449d44;
}
.label-info {
  background-color: #5bc0de;
}
.label-info[href]:hover,
.label-info[href]:focus {
  background-color: #31b0d5;
}
.label-warning {
  background-color: #f0ad4e;
}
.label-warning[href]:hover,
.label-warning[href]:focus {
  background-color: #ec971f;
}
.label-danger {
  background-color: #d9534f;
}
.label-danger[href]:hover,
.label-danger[href]:focus {
  background-color: #c9302c;
}
.badge {
  display: inline-block;
  min-width: 10px;
  padding: 3px 7px;
  font-size: 12px;
  font-weight: bold;
  color: #fff;
  line-height: 1;
  vertical-align: middle;
  white-space: nowrap;
  text-align: center;
  background-color: #777777;
  border-radius: 10px;
}
.badge:empty {
  display: none;
}
.btn .badge {
  position: relative;
  top: -1px;
}
.btn-xs .badge,
.btn-group-xs > .btn .badge {
  top: 0;
  padding: 1px 5px;
}
a.badge:hover,
a.badge:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.list-group-item.active > .badge,
.nav-pills > .active > a > .badge {
  color: #337ab7;
  background-color: #fff;
}
.list-group-item > .badge {
  float: right;
}
.list-group-item > .badge + .badge {
  margin-right: 5px;
}
.nav-pills > li > a > .badge {
  margin-left: 3px;
}
.jumbotron {
  padding-top: 30px;
  padding-bottom: 30px;
  margin-bottom: 30px;
  color: inherit;
  background-color: #eeeeee;
}
.jumbotron h1,
.jumbotron .h1 {
  color: inherit;
}
.jumbotron p {
  margin-bottom: 15px;
  font-size: 20px;
  font-weight: 200;
}
.jumbotron > hr {
  border-top-color: #d5d5d5;
}
.container .jumbotron,
.container-fluid .jumbotron {
  border-radius: 3px;
  padding-left: 0px;
  padding-right: 0px;
}
.jumbotron .container {
  max-width: 100%;
}
@media screen and (min-width: 768px) {
  .jumbotron {
    padding-top: 48px;
    padding-bottom: 48px;
  }
  .container .jumbotron,
  .container-fluid .jumbotron {
    padding-left: 60px;
    padding-right: 60px;
  }
  .jumbotron h1,
  .jumbotron .h1 {
    font-size: 59px;
  }
}
.thumbnail {
  display: block;
  padding: 4px;
  margin-bottom: 18px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: border 0.2s ease-in-out;
  -o-transition: border 0.2s ease-in-out;
  transition: border 0.2s ease-in-out;
}
.thumbnail > img,
.thumbnail a > img {
  margin-left: auto;
  margin-right: auto;
}
a.thumbnail:hover,
a.thumbnail:focus,
a.thumbnail.active {
  border-color: #337ab7;
}
.thumbnail .caption {
  padding: 9px;
  color: #000;
}
.alert {
  padding: 15px;
  margin-bottom: 18px;
  border: 1px solid transparent;
  border-radius: 2px;
}
.alert h4 {
  margin-top: 0;
  color: inherit;
}
.alert .alert-link {
  font-weight: bold;
}
.alert > p,
.alert > ul {
  margin-bottom: 0;
}
.alert > p + p {
  margin-top: 5px;
}
.alert-dismissable,
.alert-dismissible {
  padding-right: 35px;
}
.alert-dismissable .close,
.alert-dismissible .close {
  position: relative;
  top: -2px;
  right: -21px;
  color: inherit;
}
.alert-success {
  background-color: #dff0d8;
  border-color: #d6e9c6;
  color: #3c763d;
}
.alert-success hr {
  border-top-color: #c9e2b3;
}
.alert-success .alert-link {
  color: #2b542c;
}
.alert-info {
  background-color: #d9edf7;
  border-color: #bce8f1;
  color: #31708f;
}
.alert-info hr {
  border-top-color: #a6e1ec;
}
.alert-info .alert-link {
  color: #245269;
}
.alert-warning {
  background-color: #fcf8e3;
  border-color: #faebcc;
  color: #8a6d3b;
}
.alert-warning hr {
  border-top-color: #f7e1b5;
}
.alert-warning .alert-link {
  color: #66512c;
}
.alert-danger {
  background-color: #f2dede;
  border-color: #ebccd1;
  color: #a94442;
}
.alert-danger hr {
  border-top-color: #e4b9c0;
}
.alert-danger .alert-link {
  color: #843534;
}
@-webkit-keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
@keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
.progress {
  overflow: hidden;
  height: 18px;
  margin-bottom: 18px;
  background-color: #f5f5f5;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
}
.progress-bar {
  float: left;
  width: 0%;
  height: 100%;
  font-size: 12px;
  line-height: 18px;
  color: #fff;
  text-align: center;
  background-color: #337ab7;
  -webkit-box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  -webkit-transition: width 0.6s ease;
  -o-transition: width 0.6s ease;
  transition: width 0.6s ease;
}
.progress-striped .progress-bar,
.progress-bar-striped {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-size: 40px 40px;
}
.progress.active .progress-bar,
.progress-bar.active {
  -webkit-animation: progress-bar-stripes 2s linear infinite;
  -o-animation: progress-bar-stripes 2s linear infinite;
  animation: progress-bar-stripes 2s linear infinite;
}
.progress-bar-success {
  background-color: #5cb85c;
}
.progress-striped .progress-bar-success {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-info {
  background-color: #5bc0de;
}
.progress-striped .progress-bar-info {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-warning {
  background-color: #f0ad4e;
}
.progress-striped .progress-bar-warning {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-danger {
  background-color: #d9534f;
}
.progress-striped .progress-bar-danger {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.media {
  margin-top: 15px;
}
.media:first-child {
  margin-top: 0;
}
.media,
.media-body {
  zoom: 1;
  overflow: hidden;
}
.media-body {
  width: 10000px;
}
.media-object {
  display: block;
}
.media-object.img-thumbnail {
  max-width: none;
}
.media-right,
.media > .pull-right {
  padding-left: 10px;
}
.media-left,
.media > .pull-left {
  padding-right: 10px;
}
.media-left,
.media-right,
.media-body {
  display: table-cell;
  vertical-align: top;
}
.media-middle {
  vertical-align: middle;
}
.media-bottom {
  vertical-align: bottom;
}
.media-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.media-list {
  padding-left: 0;
  list-style: none;
}
.list-group {
  margin-bottom: 20px;
  padding-left: 0;
}
.list-group-item {
  position: relative;
  display: block;
  padding: 10px 15px;
  margin-bottom: -1px;
  background-color: #fff;
  border: 1px solid #ddd;
}
.list-group-item:first-child {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
}
.list-group-item:last-child {
  margin-bottom: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
a.list-group-item,
button.list-group-item {
  color: #555;
}
a.list-group-item .list-group-item-heading,
button.list-group-item .list-group-item-heading {
  color: #333;
}
a.list-group-item:hover,
button.list-group-item:hover,
a.list-group-item:focus,
button.list-group-item:focus {
  text-decoration: none;
  color: #555;
  background-color: #f5f5f5;
}
button.list-group-item {
  width: 100%;
  text-align: left;
}
.list-group-item.disabled,
.list-group-item.disabled:hover,
.list-group-item.disabled:focus {
  background-color: #eeeeee;
  color: #777777;
  cursor: not-allowed;
}
.list-group-item.disabled .list-group-item-heading,
.list-group-item.disabled:hover .list-group-item-heading,
.list-group-item.disabled:focus .list-group-item-heading {
  color: inherit;
}
.list-group-item.disabled .list-group-item-text,
.list-group-item.disabled:hover .list-group-item-text,
.list-group-item.disabled:focus .list-group-item-text {
  color: #777777;
}
.list-group-item.active,
.list-group-item.active:hover,
.list-group-item.active:focus {
  z-index: 2;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.list-group-item.active .list-group-item-heading,
.list-group-item.active:hover .list-group-item-heading,
.list-group-item.active:focus .list-group-item-heading,
.list-group-item.active .list-group-item-heading > small,
.list-group-item.active:hover .list-group-item-heading > small,
.list-group-item.active:focus .list-group-item-heading > small,
.list-group-item.active .list-group-item-heading > .small,
.list-group-item.active:hover .list-group-item-heading > .small,
.list-group-item.active:focus .list-group-item-heading > .small {
  color: inherit;
}
.list-group-item.active .list-group-item-text,
.list-group-item.active:hover .list-group-item-text,
.list-group-item.active:focus .list-group-item-text {
  color: #c7ddef;
}
.list-group-item-success {
  color: #3c763d;
  background-color: #dff0d8;
}
a.list-group-item-success,
button.list-group-item-success {
  color: #3c763d;
}
a.list-group-item-success .list-group-item-heading,
button.list-group-item-success .list-group-item-heading {
  color: inherit;
}
a.list-group-item-success:hover,
button.list-group-item-success:hover,
a.list-group-item-success:focus,
button.list-group-item-success:focus {
  color: #3c763d;
  background-color: #d0e9c6;
}
a.list-group-item-success.active,
button.list-group-item-success.active,
a.list-group-item-success.active:hover,
button.list-group-item-success.active:hover,
a.list-group-item-success.active:focus,
button.list-group-item-success.active:focus {
  color: #fff;
  background-color: #3c763d;
  border-color: #3c763d;
}
.list-group-item-info {
  color: #31708f;
  background-color: #d9edf7;
}
a.list-group-item-info,
button.list-group-item-info {
  color: #31708f;
}
a.list-group-item-info .list-group-item-heading,
button.list-group-item-info .list-group-item-heading {
  color: inherit;
}
a.list-group-item-info:hover,
button.list-group-item-info:hover,
a.list-group-item-info:focus,
button.list-group-item-info:focus {
  color: #31708f;
  background-color: #c4e3f3;
}
a.list-group-item-info.active,
button.list-group-item-info.active,
a.list-group-item-info.active:hover,
button.list-group-item-info.active:hover,
a.list-group-item-info.active:focus,
button.list-group-item-info.active:focus {
  color: #fff;
  background-color: #31708f;
  border-color: #31708f;
}
.list-group-item-warning {
  color: #8a6d3b;
  background-color: #fcf8e3;
}
a.list-group-item-warning,
button.list-group-item-warning {
  color: #8a6d3b;
}
a.list-group-item-warning .list-group-item-heading,
button.list-group-item-warning .list-group-item-heading {
  color: inherit;
}
a.list-group-item-warning:hover,
button.list-group-item-warning:hover,
a.list-group-item-warning:focus,
button.list-group-item-warning:focus {
  color: #8a6d3b;
  background-color: #faf2cc;
}
a.list-group-item-warning.active,
button.list-group-item-warning.active,
a.list-group-item-warning.active:hover,
button.list-group-item-warning.active:hover,
a.list-group-item-warning.active:focus,
button.list-group-item-warning.active:focus {
  color: #fff;
  background-color: #8a6d3b;
  border-color: #8a6d3b;
}
.list-group-item-danger {
  color: #a94442;
  background-color: #f2dede;
}
a.list-group-item-danger,
button.list-group-item-danger {
  color: #a94442;
}
a.list-group-item-danger .list-group-item-heading,
button.list-group-item-danger .list-group-item-heading {
  color: inherit;
}
a.list-group-item-danger:hover,
button.list-group-item-danger:hover,
a.list-group-item-danger:focus,
button.list-group-item-danger:focus {
  color: #a94442;
  background-color: #ebcccc;
}
a.list-group-item-danger.active,
button.list-group-item-danger.active,
a.list-group-item-danger.active:hover,
button.list-group-item-danger.active:hover,
a.list-group-item-danger.active:focus,
button.list-group-item-danger.active:focus {
  color: #fff;
  background-color: #a94442;
  border-color: #a94442;
}
.list-group-item-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.list-group-item-text {
  margin-bottom: 0;
  line-height: 1.3;
}
.panel {
  margin-bottom: 18px;
  background-color: #fff;
  border: 1px solid transparent;
  border-radius: 2px;
  -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
}
.panel-body {
  padding: 15px;
}
.panel-heading {
  padding: 10px 15px;
  border-bottom: 1px solid transparent;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel-heading > .dropdown .dropdown-toggle {
  color: inherit;
}
.panel-title {
  margin-top: 0;
  margin-bottom: 0;
  font-size: 15px;
  color: inherit;
}
.panel-title > a,
.panel-title > small,
.panel-title > .small,
.panel-title > small > a,
.panel-title > .small > a {
  color: inherit;
}
.panel-footer {
  padding: 10px 15px;
  background-color: #f5f5f5;
  border-top: 1px solid #ddd;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .list-group,
.panel > .panel-collapse > .list-group {
  margin-bottom: 0;
}
.panel > .list-group .list-group-item,
.panel > .panel-collapse > .list-group .list-group-item {
  border-width: 1px 0;
  border-radius: 0;
}
.panel > .list-group:first-child .list-group-item:first-child,
.panel > .panel-collapse > .list-group:first-child .list-group-item:first-child {
  border-top: 0;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .list-group:last-child .list-group-item:last-child,
.panel > .panel-collapse > .list-group:last-child .list-group-item:last-child {
  border-bottom: 0;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .panel-heading + .panel-collapse > .list-group .list-group-item:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.panel-heading + .list-group .list-group-item:first-child {
  border-top-width: 0;
}
.list-group + .panel-footer {
  border-top-width: 0;
}
.panel > .table,
.panel > .table-responsive > .table,
.panel > .panel-collapse > .table {
  margin-bottom: 0;
}
.panel > .table caption,
.panel > .table-responsive > .table caption,
.panel > .panel-collapse > .table caption {
  padding-left: 15px;
  padding-right: 15px;
}
.panel > .table:first-child,
.panel > .table-responsive:first-child > .table:first-child {
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child {
  border-top-left-radius: 1px;
  border-top-right-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:first-child {
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:last-child {
  border-top-right-radius: 1px;
}
.panel > .table:last-child,
.panel > .table-responsive:last-child > .table:last-child {
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child {
  border-bottom-left-radius: 1px;
  border-bottom-right-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:first-child {
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:last-child {
  border-bottom-right-radius: 1px;
}
.panel > .panel-body + .table,
.panel > .panel-body + .table-responsive,
.panel > .table + .panel-body,
.panel > .table-responsive + .panel-body {
  border-top: 1px solid #ddd;
}
.panel > .table > tbody:first-child > tr:first-child th,
.panel > .table > tbody:first-child > tr:first-child td {
  border-top: 0;
}
.panel > .table-bordered,
.panel > .table-responsive > .table-bordered {
  border: 0;
}
.panel > .table-bordered > thead > tr > th:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:first-child,
.panel > .table-bordered > tbody > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:first-child,
.panel > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-bordered > thead > tr > td:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:first-child,
.panel > .table-bordered > tbody > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:first-child,
.panel > .table-bordered > tfoot > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:first-child {
  border-left: 0;
}
.panel > .table-bordered > thead > tr > th:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:last-child,
.panel > .table-bordered > tbody > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:last-child,
.panel > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-bordered > thead > tr > td:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:last-child,
.panel > .table-bordered > tbody > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:last-child,
.panel > .table-bordered > tfoot > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:last-child {
  border-right: 0;
}
.panel > .table-bordered > thead > tr:first-child > td,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > td,
.panel > .table-bordered > tbody > tr:first-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > td,
.panel > .table-bordered > thead > tr:first-child > th,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > th,
.panel > .table-bordered > tbody > tr:first-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > th {
  border-bottom: 0;
}
.panel > .table-bordered > tbody > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > td,
.panel > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-bordered > tbody > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > th,
.panel > .table-bordered > tfoot > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > th {
  border-bottom: 0;
}
.panel > .table-responsive {
  border: 0;
  margin-bottom: 0;
}
.panel-group {
  margin-bottom: 18px;
}
.panel-group .panel {
  margin-bottom: 0;
  border-radius: 2px;
}
.panel-group .panel + .panel {
  margin-top: 5px;
}
.panel-group .panel-heading {
  border-bottom: 0;
}
.panel-group .panel-heading + .panel-collapse > .panel-body,
.panel-group .panel-heading + .panel-collapse > .list-group {
  border-top: 1px solid #ddd;
}
.panel-group .panel-footer {
  border-top: 0;
}
.panel-group .panel-footer + .panel-collapse .panel-body {
  border-bottom: 1px solid #ddd;
}
.panel-default {
  border-color: #ddd;
}
.panel-default > .panel-heading {
  color: #333333;
  background-color: #f5f5f5;
  border-color: #ddd;
}
.panel-default > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ddd;
}
.panel-default > .panel-heading .badge {
  color: #f5f5f5;
  background-color: #333333;
}
.panel-default > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ddd;
}
.panel-primary {
  border-color: #337ab7;
}
.panel-primary > .panel-heading {
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.panel-primary > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #337ab7;
}
.panel-primary > .panel-heading .badge {
  color: #337ab7;
  background-color: #fff;
}
.panel-primary > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #337ab7;
}
.panel-success {
  border-color: #d6e9c6;
}
.panel-success > .panel-heading {
  color: #3c763d;
  background-color: #dff0d8;
  border-color: #d6e9c6;
}
.panel-success > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #d6e9c6;
}
.panel-success > .panel-heading .badge {
  color: #dff0d8;
  background-color: #3c763d;
}
.panel-success > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #d6e9c6;
}
.panel-info {
  border-color: #bce8f1;
}
.panel-info > .panel-heading {
  color: #31708f;
  background-color: #d9edf7;
  border-color: #bce8f1;
}
.panel-info > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #bce8f1;
}
.panel-info > .panel-heading .badge {
  color: #d9edf7;
  background-color: #31708f;
}
.panel-info > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #bce8f1;
}
.panel-warning {
  border-color: #faebcc;
}
.panel-warning > .panel-heading {
  color: #8a6d3b;
  background-color: #fcf8e3;
  border-color: #faebcc;
}
.panel-warning > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #faebcc;
}
.panel-warning > .panel-heading .badge {
  color: #fcf8e3;
  background-color: #8a6d3b;
}
.panel-warning > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #faebcc;
}
.panel-danger {
  border-color: #ebccd1;
}
.panel-danger > .panel-heading {
  color: #a94442;
  background-color: #f2dede;
  border-color: #ebccd1;
}
.panel-danger > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ebccd1;
}
.panel-danger > .panel-heading .badge {
  color: #f2dede;
  background-color: #a94442;
}
.panel-danger > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ebccd1;
}
.embed-responsive {
  position: relative;
  display: block;
  height: 0;
  padding: 0;
  overflow: hidden;
}
.embed-responsive .embed-responsive-item,
.embed-responsive iframe,
.embed-responsive embed,
.embed-responsive object,
.embed-responsive video {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  height: 100%;
  width: 100%;
  border: 0;
}
.embed-responsive-16by9 {
  padding-bottom: 56.25%;
}
.embed-responsive-4by3 {
  padding-bottom: 75%;
}
.well {
  min-height: 20px;
  padding: 19px;
  margin-bottom: 20px;
  background-color: #f5f5f5;
  border: 1px solid #e3e3e3;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
}
.well blockquote {
  border-color: #ddd;
  border-color: rgba(0, 0, 0, 0.15);
}
.well-lg {
  padding: 24px;
  border-radius: 3px;
}
.well-sm {
  padding: 9px;
  border-radius: 1px;
}
.close {
  float: right;
  font-size: 19.5px;
  font-weight: bold;
  line-height: 1;
  color: #000;
  text-shadow: 0 1px 0 #fff;
  opacity: 0.2;
  filter: alpha(opacity=20);
}
.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
  opacity: 0.5;
  filter: alpha(opacity=50);
}
button.close {
  padding: 0;
  cursor: pointer;
  background: transparent;
  border: 0;
  -webkit-appearance: none;
}
.modal-open {
  overflow: hidden;
}
.modal {
  display: none;
  overflow: hidden;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1050;
  -webkit-overflow-scrolling: touch;
  outline: 0;
}
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, -25%);
  -ms-transform: translate(0, -25%);
  -o-transform: translate(0, -25%);
  transform: translate(0, -25%);
  -webkit-transition: -webkit-transform 0.3s ease-out;
  -moz-transition: -moz-transform 0.3s ease-out;
  -o-transition: -o-transform 0.3s ease-out;
  transition: transform 0.3s ease-out;
}
.modal.in .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
.modal-open .modal {
  overflow-x: hidden;
  overflow-y: auto;
}
.modal-dialog {
  position: relative;
  width: auto;
  margin: 10px;
}
.modal-content {
  position: relative;
  background-color: #fff;
  border: 1px solid #999;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  background-clip: padding-box;
  outline: 0;
}
.modal-backdrop {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1040;
  background-color: #000;
}
.modal-backdrop.fade {
  opacity: 0;
  filter: alpha(opacity=0);
}
.modal-backdrop.in {
  opacity: 0.5;
  filter: alpha(opacity=50);
}
.modal-header {
  padding: 15px;
  border-bottom: 1px solid #e5e5e5;
}
.modal-header .close {
  margin-top: -2px;
}
.modal-title {
  margin: 0;
  line-height: 1.42857143;
}
.modal-body {
  position: relative;
  padding: 15px;
}
.modal-footer {
  padding: 15px;
  text-align: right;
  border-top: 1px solid #e5e5e5;
}
.modal-footer .btn + .btn {
  margin-left: 5px;
  margin-bottom: 0;
}
.modal-footer .btn-group .btn + .btn {
  margin-left: -1px;
}
.modal-footer .btn-block + .btn-block {
  margin-left: 0;
}
.modal-scrollbar-measure {
  position: absolute;
  top: -9999px;
  width: 50px;
  height: 50px;
  overflow: scroll;
}
@media (min-width: 768px) {
  .modal-dialog {
    width: 600px;
    margin: 30px auto;
  }
  .modal-content {
    -webkit-box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
  }
  .modal-sm {
    width: 300px;
  }
}
@media (min-width: 992px) {
  .modal-lg {
    width: 900px;
  }
}
.tooltip {
  position: absolute;
  z-index: 1070;
  display: block;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 12px;
  opacity: 0;
  filter: alpha(opacity=0);
}
.tooltip.in {
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.tooltip.top {
  margin-top: -3px;
  padding: 5px 0;
}
.tooltip.right {
  margin-left: 3px;
  padding: 0 5px;
}
.tooltip.bottom {
  margin-top: 3px;
  padding: 5px 0;
}
.tooltip.left {
  margin-left: -3px;
  padding: 0 5px;
}
.tooltip-inner {
  max-width: 200px;
  padding: 3px 8px;
  color: #fff;
  text-align: center;
  background-color: #000;
  border-radius: 2px;
}
.tooltip-arrow {
  position: absolute;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.tooltip.top .tooltip-arrow {
  bottom: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-left .tooltip-arrow {
  bottom: 0;
  right: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-right .tooltip-arrow {
  bottom: 0;
  left: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.right .tooltip-arrow {
  top: 50%;
  left: 0;
  margin-top: -5px;
  border-width: 5px 5px 5px 0;
  border-right-color: #000;
}
.tooltip.left .tooltip-arrow {
  top: 50%;
  right: 0;
  margin-top: -5px;
  border-width: 5px 0 5px 5px;
  border-left-color: #000;
}
.tooltip.bottom .tooltip-arrow {
  top: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-left .tooltip-arrow {
  top: 0;
  right: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-right .tooltip-arrow {
  top: 0;
  left: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.popover {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1060;
  display: none;
  max-width: 276px;
  padding: 1px;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 13px;
  background-color: #fff;
  background-clip: padding-box;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
}
.popover.top {
  margin-top: -10px;
}
.popover.right {
  margin-left: 10px;
}
.popover.bottom {
  margin-top: 10px;
}
.popover.left {
  margin-left: -10px;
}
.popover-title {
  margin: 0;
  padding: 8px 14px;
  font-size: 13px;
  background-color: #f7f7f7;
  border-bottom: 1px solid #ebebeb;
  border-radius: 2px 2px 0 0;
}
.popover-content {
  padding: 9px 14px;
}
.popover > .arrow,
.popover > .arrow:after {
  position: absolute;
  display: block;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.popover > .arrow {
  border-width: 11px;
}
.popover > .arrow:after {
  border-width: 10px;
  content: "";
}
.popover.top > .arrow {
  left: 50%;
  margin-left: -11px;
  border-bottom-width: 0;
  border-top-color: #999999;
  border-top-color: rgba(0, 0, 0, 0.25);
  bottom: -11px;
}
.popover.top > .arrow:after {
  content: " ";
  bottom: 1px;
  margin-left: -10px;
  border-bottom-width: 0;
  border-top-color: #fff;
}
.popover.right > .arrow {
  top: 50%;
  left: -11px;
  margin-top: -11px;
  border-left-width: 0;
  border-right-color: #999999;
  border-right-color: rgba(0, 0, 0, 0.25);
}
.popover.right > .arrow:after {
  content: " ";
  left: 1px;
  bottom: -10px;
  border-left-width: 0;
  border-right-color: #fff;
}
.popover.bottom > .arrow {
  left: 50%;
  margin-left: -11px;
  border-top-width: 0;
  border-bottom-color: #999999;
  border-bottom-color: rgba(0, 0, 0, 0.25);
  top: -11px;
}
.popover.bottom > .arrow:after {
  content: " ";
  top: 1px;
  margin-left: -10px;
  border-top-width: 0;
  border-bottom-color: #fff;
}
.popover.left > .arrow {
  top: 50%;
  right: -11px;
  margin-top: -11px;
  border-right-width: 0;
  border-left-color: #999999;
  border-left-color: rgba(0, 0, 0, 0.25);
}
.popover.left > .arrow:after {
  content: " ";
  right: 1px;
  border-right-width: 0;
  border-left-color: #fff;
  bottom: -10px;
}
.carousel {
  position: relative;
}
.carousel-inner {
  position: relative;
  overflow: hidden;
  width: 100%;
}
.carousel-inner > .item {
  display: none;
  position: relative;
  -webkit-transition: 0.6s ease-in-out left;
  -o-transition: 0.6s ease-in-out left;
  transition: 0.6s ease-in-out left;
}
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  line-height: 1;
}
@media all and (transform-3d), (-webkit-transform-3d) {
  .carousel-inner > .item {
    -webkit-transition: -webkit-transform 0.6s ease-in-out;
    -moz-transition: -moz-transform 0.6s ease-in-out;
    -o-transition: -o-transform 0.6s ease-in-out;
    transition: transform 0.6s ease-in-out;
    -webkit-backface-visibility: hidden;
    -moz-backface-visibility: hidden;
    backface-visibility: hidden;
    -webkit-perspective: 1000px;
    -moz-perspective: 1000px;
    perspective: 1000px;
  }
  .carousel-inner > .item.next,
  .carousel-inner > .item.active.right {
    -webkit-transform: translate3d(100%, 0, 0);
    transform: translate3d(100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.prev,
  .carousel-inner > .item.active.left {
    -webkit-transform: translate3d(-100%, 0, 0);
    transform: translate3d(-100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.next.left,
  .carousel-inner > .item.prev.right,
  .carousel-inner > .item.active {
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
    left: 0;
  }
}
.carousel-inner > .active,
.carousel-inner > .next,
.carousel-inner > .prev {
  display: block;
}
.carousel-inner > .active {
  left: 0;
}
.carousel-inner > .next,
.carousel-inner > .prev {
  position: absolute;
  top: 0;
  width: 100%;
}
.carousel-inner > .next {
  left: 100%;
}
.carousel-inner > .prev {
  left: -100%;
}
.carousel-inner > .next.left,
.carousel-inner > .prev.right {
  left: 0;
}
.carousel-inner > .active.left {
  left: -100%;
}
.carousel-inner > .active.right {
  left: 100%;
}
.carousel-control {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  width: 15%;
  opacity: 0.5;
  filter: alpha(opacity=50);
  font-size: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
  background-color: rgba(0, 0, 0, 0);
}
.carousel-control.left {
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#80000000', endColorstr='#00000000', GradientType=1);
}
.carousel-control.right {
  left: auto;
  right: 0;
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#00000000', endColorstr='#80000000', GradientType=1);
}
.carousel-control:hover,
.carousel-control:focus {
  outline: 0;
  color: #fff;
  text-decoration: none;
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.carousel-control .icon-prev,
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-left,
.carousel-control .glyphicon-chevron-right {
  position: absolute;
  top: 50%;
  margin-top: -10px;
  z-index: 5;
  display: inline-block;
}
.carousel-control .icon-prev,
.carousel-control .glyphicon-chevron-left {
  left: 50%;
  margin-left: -10px;
}
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-right {
  right: 50%;
  margin-right: -10px;
}
.carousel-control .icon-prev,
.carousel-control .icon-next {
  width: 20px;
  height: 20px;
  line-height: 1;
  font-family: serif;
}
.carousel-control .icon-prev:before {
  content: '\2039';
}
.carousel-control .icon-next:before {
  content: '\203a';
}
.carousel-indicators {
  position: absolute;
  bottom: 10px;
  left: 50%;
  z-index: 15;
  width: 60%;
  margin-left: -30%;
  padding-left: 0;
  list-style: none;
  text-align: center;
}
.carousel-indicators li {
  display: inline-block;
  width: 10px;
  height: 10px;
  margin: 1px;
  text-indent: -999px;
  border: 1px solid #fff;
  border-radius: 10px;
  cursor: pointer;
  background-color: #000 \9;
  background-color: rgba(0, 0, 0, 0);
}
.carousel-indicators .active {
  margin: 0;
  width: 12px;
  height: 12px;
  background-color: #fff;
}
.carousel-caption {
  position: absolute;
  left: 15%;
  right: 15%;
  bottom: 20px;
  z-index: 10;
  padding-top: 20px;
  padding-bottom: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
}
.carousel-caption .btn {
  text-shadow: none;
}
@media screen and (min-width: 768px) {
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-prev,
  .carousel-control .icon-next {
    width: 30px;
    height: 30px;
    margin-top: -10px;
    font-size: 30px;
  }
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .icon-prev {
    margin-left: -10px;
  }
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-next {
    margin-right: -10px;
  }
  .carousel-caption {
    left: 20%;
    right: 20%;
    padding-bottom: 30px;
  }
  .carousel-indicators {
    bottom: 20px;
  }
}
.clearfix:before,
.clearfix:after,
.dl-horizontal dd:before,
.dl-horizontal dd:after,
.container:before,
.container:after,
.container-fluid:before,
.container-fluid:after,
.row:before,
.row:after,
.form-horizontal .form-group:before,
.form-horizontal .form-group:after,
.btn-toolbar:before,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:before,
.btn-group-vertical > .btn-group:after,
.nav:before,
.nav:after,
.navbar:before,
.navbar:after,
.navbar-header:before,
.navbar-header:after,
.navbar-collapse:before,
.navbar-collapse:after,
.pager:before,
.pager:after,
.panel-body:before,
.panel-body:after,
.modal-header:before,
.modal-header:after,
.modal-footer:before,
.modal-footer:after,
.item_buttons:before,
.item_buttons:after {
  content: " ";
  display: table;
}
.clearfix:after,
.dl-horizontal dd:after,
.container:after,
.container-fluid:after,
.row:after,
.form-horizontal .form-group:after,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:after,
.nav:after,
.navbar:after,
.navbar-header:after,
.navbar-collapse:after,
.pager:after,
.panel-body:after,
.modal-header:after,
.modal-footer:after,
.item_buttons:after {
  clear: both;
}
.center-block {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.pull-right {
  float: right !important;
}
.pull-left {
  float: left !important;
}
.hide {
  display: none !important;
}
.show {
  display: block !important;
}
.invisible {
  visibility: hidden;
}
.text-hide {
  font: 0/0 a;
  color: transparent;
  text-shadow: none;
  background-color: transparent;
  border: 0;
}
.hidden {
  display: none !important;
}
.affix {
  position: fixed;
}
@-ms-viewport {
  width: device-width;
}
.visible-xs,
.visible-sm,
.visible-md,
.visible-lg {
  display: none !important;
}
.visible-xs-block,
.visible-xs-inline,
.visible-xs-inline-block,
.visible-sm-block,
.visible-sm-inline,
.visible-sm-inline-block,
.visible-md-block,
.visible-md-inline,
.visible-md-inline-block,
.visible-lg-block,
.visible-lg-inline,
.visible-lg-inline-block {
  display: none !important;
}
@media (max-width: 767px) {
  .visible-xs {
    display: block !important;
  }
  table.visible-xs {
    display: table !important;
  }
  tr.visible-xs {
    display: table-row !important;
  }
  th.visible-xs,
  td.visible-xs {
    display: table-cell !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-block {
    display: block !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline {
    display: inline !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm {
    display: block !important;
  }
  table.visible-sm {
    display: table !important;
  }
  tr.visible-sm {
    display: table-row !important;
  }
  th.visible-sm,
  td.visible-sm {
    display: table-cell !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-block {
    display: block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline {
    display: inline !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md {
    display: block !important;
  }
  table.visible-md {
    display: table !important;
  }
  tr.visible-md {
    display: table-row !important;
  }
  th.visible-md,
  td.visible-md {
    display: table-cell !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-block {
    display: block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline {
    display: inline !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg {
    display: block !important;
  }
  table.visible-lg {
    display: table !important;
  }
  tr.visible-lg {
    display: table-row !important;
  }
  th.visible-lg,
  td.visible-lg {
    display: table-cell !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-block {
    display: block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline {
    display: inline !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline-block {
    display: inline-block !important;
  }
}
@media (max-width: 767px) {
  .hidden-xs {
    display: none !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .hidden-sm {
    display: none !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .hidden-md {
    display: none !important;
  }
}
@media (min-width: 1200px) {
  .hidden-lg {
    display: none !important;
  }
}
.visible-print {
  display: none !important;
}
@media print {
  .visible-print {
    display: block !important;
  }
  table.visible-print {
    display: table !important;
  }
  tr.visible-print {
    display: table-row !important;
  }
  th.visible-print,
  td.visible-print {
    display: table-cell !important;
  }
}
.visible-print-block {
  display: none !important;
}
@media print {
  .visible-print-block {
    display: block !important;
  }
}
.visible-print-inline {
  display: none !important;
}
@media print {
  .visible-print-inline {
    display: inline !important;
  }
}
.visible-print-inline-block {
  display: none !important;
}
@media print {
  .visible-print-inline-block {
    display: inline-block !important;
  }
}
@media print {
  .hidden-print {
    display: none !important;
  }
}
/*!
*
* Font Awesome
*
*/
/*!
 *  Font Awesome 4.7.0 by @davegandy - http://fontawesome.io - @fontawesome
 *  License - http://fontawesome.io/license (Font: SIL OFL 1.1, CSS: MIT License)
 */
/* FONT PATH
 * -------------------------- */
@font-face {
  font-family: 'FontAwesome';
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?v=4.7.0');
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?#iefix&v=4.7.0') format('embedded-opentype'), url('../components/font-awesome/fonts/fontawesome-webfont.woff2?v=4.7.0') format('woff2'), url('../components/font-awesome/fonts/fontawesome-webfont.woff?v=4.7.0') format('woff'), url('../components/font-awesome/fonts/fontawesome-webfont.ttf?v=4.7.0') format('truetype'), url('../components/font-awesome/fonts/fontawesome-webfont.svg?v=4.7.0#fontawesomeregular') format('svg');
  font-weight: normal;
  font-style: normal;
}
.fa {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
/* makes the font 33% larger relative to the icon container */
.fa-lg {
  font-size: 1.33333333em;
  line-height: 0.75em;
  vertical-align: -15%;
}
.fa-2x {
  font-size: 2em;
}
.fa-3x {
  font-size: 3em;
}
.fa-4x {
  font-size: 4em;
}
.fa-5x {
  font-size: 5em;
}
.fa-fw {
  width: 1.28571429em;
  text-align: center;
}
.fa-ul {
  padding-left: 0;
  margin-left: 2.14285714em;
  list-style-type: none;
}
.fa-ul > li {
  position: relative;
}
.fa-li {
  position: absolute;
  left: -2.14285714em;
  width: 2.14285714em;
  top: 0.14285714em;
  text-align: center;
}
.fa-li.fa-lg {
  left: -1.85714286em;
}
.fa-border {
  padding: .2em .25em .15em;
  border: solid 0.08em #eee;
  border-radius: .1em;
}
.fa-pull-left {
  float: left;
}
.fa-pull-right {
  float: right;
}
.fa.fa-pull-left {
  margin-right: .3em;
}
.fa.fa-pull-right {
  margin-left: .3em;
}
/* Deprecated as of 4.4.0 */
.pull-right {
  float: right;
}
.pull-left {
  float: left;
}
.fa.pull-left {
  margin-right: .3em;
}
.fa.pull-right {
  margin-left: .3em;
}
.fa-spin {
  -webkit-animation: fa-spin 2s infinite linear;
  animation: fa-spin 2s infinite linear;
}
.fa-pulse {
  -webkit-animation: fa-spin 1s infinite steps(8);
  animation: fa-spin 1s infinite steps(8);
}
@-webkit-keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
@keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
.fa-rotate-90 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=1)";
  -webkit-transform: rotate(90deg);
  -ms-transform: rotate(90deg);
  transform: rotate(90deg);
}
.fa-rotate-180 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2)";
  -webkit-transform: rotate(180deg);
  -ms-transform: rotate(180deg);
  transform: rotate(180deg);
}
.fa-rotate-270 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=3)";
  -webkit-transform: rotate(270deg);
  -ms-transform: rotate(270deg);
  transform: rotate(270deg);
}
.fa-flip-horizontal {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=0, mirror=1)";
  -webkit-transform: scale(-1, 1);
  -ms-transform: scale(-1, 1);
  transform: scale(-1, 1);
}
.fa-flip-vertical {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2, mirror=1)";
  -webkit-transform: scale(1, -1);
  -ms-transform: scale(1, -1);
  transform: scale(1, -1);
}
:root .fa-rotate-90,
:root .fa-rotate-180,
:root .fa-rotate-270,
:root .fa-flip-horizontal,
:root .fa-flip-vertical {
  filter: none;
}
.fa-stack {
  position: relative;
  display: inline-block;
  width: 2em;
  height: 2em;
  line-height: 2em;
  vertical-align: middle;
}
.fa-stack-1x,
.fa-stack-2x {
  position: absolute;
  left: 0;
  width: 100%;
  text-align: center;
}
.fa-stack-1x {
  line-height: inherit;
}
.fa-stack-2x {
  font-size: 2em;
}
.fa-inverse {
  color: #fff;
}
/* Font Awesome uses the Unicode Private Use Area (PUA) to ensure screen
   readers do not read off random characters that represent icons */
.fa-glass:before {
  content: "\f000";
}
.fa-music:before {
  content: "\f001";
}
.fa-search:before {
  content: "\f002";
}
.fa-envelope-o:before {
  content: "\f003";
}
.fa-heart:before {
  content: "\f004";
}
.fa-star:before {
  content: "\f005";
}
.fa-star-o:before {
  content: "\f006";
}
.fa-user:before {
  content: "\f007";
}
.fa-film:before {
  content: "\f008";
}
.fa-th-large:before {
  content: "\f009";
}
.fa-th:before {
  content: "\f00a";
}
.fa-th-list:before {
  content: "\f00b";
}
.fa-check:before {
  content: "\f00c";
}
.fa-remove:before,
.fa-close:before,
.fa-times:before {
  content: "\f00d";
}
.fa-search-plus:before {
  content: "\f00e";
}
.fa-search-minus:before {
  content: "\f010";
}
.fa-power-off:before {
  content: "\f011";
}
.fa-signal:before {
  content: "\f012";
}
.fa-gear:before,
.fa-cog:before {
  content: "\f013";
}
.fa-trash-o:before {
  content: "\f014";
}
.fa-home:before {
  content: "\f015";
}
.fa-file-o:before {
  content: "\f016";
}
.fa-clock-o:before {
  content: "\f017";
}
.fa-road:before {
  content: "\f018";
}
.fa-download:before {
  content: "\f019";
}
.fa-arrow-circle-o-down:before {
  content: "\f01a";
}
.fa-arrow-circle-o-up:before {
  content: "\f01b";
}
.fa-inbox:before {
  content: "\f01c";
}
.fa-play-circle-o:before {
  content: "\f01d";
}
.fa-rotate-right:before,
.fa-repeat:before {
  content: "\f01e";
}
.fa-refresh:before {
  content: "\f021";
}
.fa-list-alt:before {
  content: "\f022";
}
.fa-lock:before {
  content: "\f023";
}
.fa-flag:before {
  content: "\f024";
}
.fa-headphones:before {
  content: "\f025";
}
.fa-volume-off:before {
  content: "\f026";
}
.fa-volume-down:before {
  content: "\f027";
}
.fa-volume-up:before {
  content: "\f028";
}
.fa-qrcode:before {
  content: "\f029";
}
.fa-barcode:before {
  content: "\f02a";
}
.fa-tag:before {
  content: "\f02b";
}
.fa-tags:before {
  content: "\f02c";
}
.fa-book:before {
  content: "\f02d";
}
.fa-bookmark:before {
  content: "\f02e";
}
.fa-print:before {
  content: "\f02f";
}
.fa-camera:before {
  content: "\f030";
}
.fa-font:before {
  content: "\f031";
}
.fa-bold:before {
  content: "\f032";
}
.fa-italic:before {
  content: "\f033";
}
.fa-text-height:before {
  content: "\f034";
}
.fa-text-width:before {
  content: "\f035";
}
.fa-align-left:before {
  content: "\f036";
}
.fa-align-center:before {
  content: "\f037";
}
.fa-align-right:before {
  content: "\f038";
}
.fa-align-justify:before {
  content: "\f039";
}
.fa-list:before {
  content: "\f03a";
}
.fa-dedent:before,
.fa-outdent:before {
  content: "\f03b";
}
.fa-indent:before {
  content: "\f03c";
}
.fa-video-camera:before {
  content: "\f03d";
}
.fa-photo:before,
.fa-image:before,
.fa-picture-o:before {
  content: "\f03e";
}
.fa-pencil:before {
  content: "\f040";
}
.fa-map-marker:before {
  content: "\f041";
}
.fa-adjust:before {
  content: "\f042";
}
.fa-tint:before {
  content: "\f043";
}
.fa-edit:before,
.fa-pencil-square-o:before {
  content: "\f044";
}
.fa-share-square-o:before {
  content: "\f045";
}
.fa-check-square-o:before {
  content: "\f046";
}
.fa-arrows:before {
  content: "\f047";
}
.fa-step-backward:before {
  content: "\f048";
}
.fa-fast-backward:before {
  content: "\f049";
}
.fa-backward:before {
  content: "\f04a";
}
.fa-play:before {
  content: "\f04b";
}
.fa-pause:before {
  content: "\f04c";
}
.fa-stop:before {
  content: "\f04d";
}
.fa-forward:before {
  content: "\f04e";
}
.fa-fast-forward:before {
  content: "\f050";
}
.fa-step-forward:before {
  content: "\f051";
}
.fa-eject:before {
  content: "\f052";
}
.fa-chevron-left:before {
  content: "\f053";
}
.fa-chevron-right:before {
  content: "\f054";
}
.fa-plus-circle:before {
  content: "\f055";
}
.fa-minus-circle:before {
  content: "\f056";
}
.fa-times-circle:before {
  content: "\f057";
}
.fa-check-circle:before {
  content: "\f058";
}
.fa-question-circle:before {
  content: "\f059";
}
.fa-info-circle:before {
  content: "\f05a";
}
.fa-crosshairs:before {
  content: "\f05b";
}
.fa-times-circle-o:before {
  content: "\f05c";
}
.fa-check-circle-o:before {
  content: "\f05d";
}
.fa-ban:before {
  content: "\f05e";
}
.fa-arrow-left:before {
  content: "\f060";
}
.fa-arrow-right:before {
  content: "\f061";
}
.fa-arrow-up:before {
  content: "\f062";
}
.fa-arrow-down:before {
  content: "\f063";
}
.fa-mail-forward:before,
.fa-share:before {
  content: "\f064";
}
.fa-expand:before {
  content: "\f065";
}
.fa-compress:before {
  content: "\f066";
}
.fa-plus:before {
  content: "\f067";
}
.fa-minus:before {
  content: "\f068";
}
.fa-asterisk:before {
  content: "\f069";
}
.fa-exclamation-circle:before {
  content: "\f06a";
}
.fa-gift:before {
  content: "\f06b";
}
.fa-leaf:before {
  content: "\f06c";
}
.fa-fire:before {
  content: "\f06d";
}
.fa-eye:before {
  content: "\f06e";
}
.fa-eye-slash:before {
  content: "\f070";
}
.fa-warning:before,
.fa-exclamation-triangle:before {
  content: "\f071";
}
.fa-plane:before {
  content: "\f072";
}
.fa-calendar:before {
  content: "\f073";
}
.fa-random:before {
  content: "\f074";
}
.fa-comment:before {
  content: "\f075";
}
.fa-magnet:before {
  content: "\f076";
}
.fa-chevron-up:before {
  content: "\f077";
}
.fa-chevron-down:before {
  content: "\f078";
}
.fa-retweet:before {
  content: "\f079";
}
.fa-shopping-cart:before {
  content: "\f07a";
}
.fa-folder:before {
  content: "\f07b";
}
.fa-folder-open:before {
  content: "\f07c";
}
.fa-arrows-v:before {
  content: "\f07d";
}
.fa-arrows-h:before {
  content: "\f07e";
}
.fa-bar-chart-o:before,
.fa-bar-chart:before {
  content: "\f080";
}
.fa-twitter-square:before {
  content: "\f081";
}
.fa-facebook-square:before {
  content: "\f082";
}
.fa-camera-retro:before {
  content: "\f083";
}
.fa-key:before {
  content: "\f084";
}
.fa-gears:before,
.fa-cogs:before {
  content: "\f085";
}
.fa-comments:before {
  content: "\f086";
}
.fa-thumbs-o-up:before {
  content: "\f087";
}
.fa-thumbs-o-down:before {
  content: "\f088";
}
.fa-star-half:before {
  content: "\f089";
}
.fa-heart-o:before {
  content: "\f08a";
}
.fa-sign-out:before {
  content: "\f08b";
}
.fa-linkedin-square:before {
  content: "\f08c";
}
.fa-thumb-tack:before {
  content: "\f08d";
}
.fa-external-link:before {
  content: "\f08e";
}
.fa-sign-in:before {
  content: "\f090";
}
.fa-trophy:before {
  content: "\f091";
}
.fa-github-square:before {
  content: "\f092";
}
.fa-upload:before {
  content: "\f093";
}
.fa-lemon-o:before {
  content: "\f094";
}
.fa-phone:before {
  content: "\f095";
}
.fa-square-o:before {
  content: "\f096";
}
.fa-bookmark-o:before {
  content: "\f097";
}
.fa-phone-square:before {
  content: "\f098";
}
.fa-twitter:before {
  content: "\f099";
}
.fa-facebook-f:before,
.fa-facebook:before {
  content: "\f09a";
}
.fa-github:before {
  content: "\f09b";
}
.fa-unlock:before {
  content: "\f09c";
}
.fa-credit-card:before {
  content: "\f09d";
}
.fa-feed:before,
.fa-rss:before {
  content: "\f09e";
}
.fa-hdd-o:before {
  content: "\f0a0";
}
.fa-bullhorn:before {
  content: "\f0a1";
}
.fa-bell:before {
  content: "\f0f3";
}
.fa-certificate:before {
  content: "\f0a3";
}
.fa-hand-o-right:before {
  content: "\f0a4";
}
.fa-hand-o-left:before {
  content: "\f0a5";
}
.fa-hand-o-up:before {
  content: "\f0a6";
}
.fa-hand-o-down:before {
  content: "\f0a7";
}
.fa-arrow-circle-left:before {
  content: "\f0a8";
}
.fa-arrow-circle-right:before {
  content: "\f0a9";
}
.fa-arrow-circle-up:before {
  content: "\f0aa";
}
.fa-arrow-circle-down:before {
  content: "\f0ab";
}
.fa-globe:before {
  content: "\f0ac";
}
.fa-wrench:before {
  content: "\f0ad";
}
.fa-tasks:before {
  content: "\f0ae";
}
.fa-filter:before {
  content: "\f0b0";
}
.fa-briefcase:before {
  content: "\f0b1";
}
.fa-arrows-alt:before {
  content: "\f0b2";
}
.fa-group:before,
.fa-users:before {
  content: "\f0c0";
}
.fa-chain:before,
.fa-link:before {
  content: "\f0c1";
}
.fa-cloud:before {
  content: "\f0c2";
}
.fa-flask:before {
  content: "\f0c3";
}
.fa-cut:before,
.fa-scissors:before {
  content: "\f0c4";
}
.fa-copy:before,
.fa-files-o:before {
  content: "\f0c5";
}
.fa-paperclip:before {
  content: "\f0c6";
}
.fa-save:before,
.fa-floppy-o:before {
  content: "\f0c7";
}
.fa-square:before {
  content: "\f0c8";
}
.fa-navicon:before,
.fa-reorder:before,
.fa-bars:before {
  content: "\f0c9";
}
.fa-list-ul:before {
  content: "\f0ca";
}
.fa-list-ol:before {
  content: "\f0cb";
}
.fa-strikethrough:before {
  content: "\f0cc";
}
.fa-underline:before {
  content: "\f0cd";
}
.fa-table:before {
  content: "\f0ce";
}
.fa-magic:before {
  content: "\f0d0";
}
.fa-truck:before {
  content: "\f0d1";
}
.fa-pinterest:before {
  content: "\f0d2";
}
.fa-pinterest-square:before {
  content: "\f0d3";
}
.fa-google-plus-square:before {
  content: "\f0d4";
}
.fa-google-plus:before {
  content: "\f0d5";
}
.fa-money:before {
  content: "\f0d6";
}
.fa-caret-down:before {
  content: "\f0d7";
}
.fa-caret-up:before {
  content: "\f0d8";
}
.fa-caret-left:before {
  content: "\f0d9";
}
.fa-caret-right:before {
  content: "\f0da";
}
.fa-columns:before {
  content: "\f0db";
}
.fa-unsorted:before,
.fa-sort:before {
  content: "\f0dc";
}
.fa-sort-down:before,
.fa-sort-desc:before {
  content: "\f0dd";
}
.fa-sort-up:before,
.fa-sort-asc:before {
  content: "\f0de";
}
.fa-envelope:before {
  content: "\f0e0";
}
.fa-linkedin:before {
  content: "\f0e1";
}
.fa-rotate-left:before,
.fa-undo:before {
  content: "\f0e2";
}
.fa-legal:before,
.fa-gavel:before {
  content: "\f0e3";
}
.fa-dashboard:before,
.fa-tachometer:before {
  content: "\f0e4";
}
.fa-comment-o:before {
  content: "\f0e5";
}
.fa-comments-o:before {
  content: "\f0e6";
}
.fa-flash:before,
.fa-bolt:before {
  content: "\f0e7";
}
.fa-sitemap:before {
  content: "\f0e8";
}
.fa-umbrella:before {
  content: "\f0e9";
}
.fa-paste:before,
.fa-clipboard:before {
  content: "\f0ea";
}
.fa-lightbulb-o:before {
  content: "\f0eb";
}
.fa-exchange:before {
  content: "\f0ec";
}
.fa-cloud-download:before {
  content: "\f0ed";
}
.fa-cloud-upload:before {
  content: "\f0ee";
}
.fa-user-md:before {
  content: "\f0f0";
}
.fa-stethoscope:before {
  content: "\f0f1";
}
.fa-suitcase:before {
  content: "\f0f2";
}
.fa-bell-o:before {
  content: "\f0a2";
}
.fa-coffee:before {
  content: "\f0f4";
}
.fa-cutlery:before {
  content: "\f0f5";
}
.fa-file-text-o:before {
  content: "\f0f6";
}
.fa-building-o:before {
  content: "\f0f7";
}
.fa-hospital-o:before {
  content: "\f0f8";
}
.fa-ambulance:before {
  content: "\f0f9";
}
.fa-medkit:before {
  content: "\f0fa";
}
.fa-fighter-jet:before {
  content: "\f0fb";
}
.fa-beer:before {
  content: "\f0fc";
}
.fa-h-square:before {
  content: "\f0fd";
}
.fa-plus-square:before {
  content: "\f0fe";
}
.fa-angle-double-left:before {
  content: "\f100";
}
.fa-angle-double-right:before {
  content: "\f101";
}
.fa-angle-double-up:before {
  content: "\f102";
}
.fa-angle-double-down:before {
  content: "\f103";
}
.fa-angle-left:before {
  content: "\f104";
}
.fa-angle-right:before {
  content: "\f105";
}
.fa-angle-up:before {
  content: "\f106";
}
.fa-angle-down:before {
  content: "\f107";
}
.fa-desktop:before {
  content: "\f108";
}
.fa-laptop:before {
  content: "\f109";
}
.fa-tablet:before {
  content: "\f10a";
}
.fa-mobile-phone:before,
.fa-mobile:before {
  content: "\f10b";
}
.fa-circle-o:before {
  content: "\f10c";
}
.fa-quote-left:before {
  content: "\f10d";
}
.fa-quote-right:before {
  content: "\f10e";
}
.fa-spinner:before {
  content: "\f110";
}
.fa-circle:before {
  content: "\f111";
}
.fa-mail-reply:before,
.fa-reply:before {
  content: "\f112";
}
.fa-github-alt:before {
  content: "\f113";
}
.fa-folder-o:before {
  content: "\f114";
}
.fa-folder-open-o:before {
  content: "\f115";
}
.fa-smile-o:before {
  content: "\f118";
}
.fa-frown-o:before {
  content: "\f119";
}
.fa-meh-o:before {
  content: "\f11a";
}
.fa-gamepad:before {
  content: "\f11b";
}
.fa-keyboard-o:before {
  content: "\f11c";
}
.fa-flag-o:before {
  content: "\f11d";
}
.fa-flag-checkered:before {
  content: "\f11e";
}
.fa-terminal:before {
  content: "\f120";
}
.fa-code:before {
  content: "\f121";
}
.fa-mail-reply-all:before,
.fa-reply-all:before {
  content: "\f122";
}
.fa-star-half-empty:before,
.fa-star-half-full:before,
.fa-star-half-o:before {
  content: "\f123";
}
.fa-location-arrow:before {
  content: "\f124";
}
.fa-crop:before {
  content: "\f125";
}
.fa-code-fork:before {
  content: "\f126";
}
.fa-unlink:before,
.fa-chain-broken:before {
  content: "\f127";
}
.fa-question:before {
  content: "\f128";
}
.fa-info:before {
  content: "\f129";
}
.fa-exclamation:before {
  content: "\f12a";
}
.fa-superscript:before {
  content: "\f12b";
}
.fa-subscript:before {
  content: "\f12c";
}
.fa-eraser:before {
  content: "\f12d";
}
.fa-puzzle-piece:before {
  content: "\f12e";
}
.fa-microphone:before {
  content: "\f130";
}
.fa-microphone-slash:before {
  content: "\f131";
}
.fa-shield:before {
  content: "\f132";
}
.fa-calendar-o:before {
  content: "\f133";
}
.fa-fire-extinguisher:before {
  content: "\f134";
}
.fa-rocket:before {
  content: "\f135";
}
.fa-maxcdn:before {
  content: "\f136";
}
.fa-chevron-circle-left:before {
  content: "\f137";
}
.fa-chevron-circle-right:before {
  content: "\f138";
}
.fa-chevron-circle-up:before {
  content: "\f139";
}
.fa-chevron-circle-down:before {
  content: "\f13a";
}
.fa-html5:before {
  content: "\f13b";
}
.fa-css3:before {
  content: "\f13c";
}
.fa-anchor:before {
  content: "\f13d";
}
.fa-unlock-alt:before {
  content: "\f13e";
}
.fa-bullseye:before {
  content: "\f140";
}
.fa-ellipsis-h:before {
  content: "\f141";
}
.fa-ellipsis-v:before {
  content: "\f142";
}
.fa-rss-square:before {
  content: "\f143";
}
.fa-play-circle:before {
  content: "\f144";
}
.fa-ticket:before {
  content: "\f145";
}
.fa-minus-square:before {
  content: "\f146";
}
.fa-minus-square-o:before {
  content: "\f147";
}
.fa-level-up:before {
  content: "\f148";
}
.fa-level-down:before {
  content: "\f149";
}
.fa-check-square:before {
  content: "\f14a";
}
.fa-pencil-square:before {
  content: "\f14b";
}
.fa-external-link-square:before {
  content: "\f14c";
}
.fa-share-square:before {
  content: "\f14d";
}
.fa-compass:before {
  content: "\f14e";
}
.fa-toggle-down:before,
.fa-caret-square-o-down:before {
  content: "\f150";
}
.fa-toggle-up:before,
.fa-caret-square-o-up:before {
  content: "\f151";
}
.fa-toggle-right:before,
.fa-caret-square-o-right:before {
  content: "\f152";
}
.fa-euro:before,
.fa-eur:before {
  content: "\f153";
}
.fa-gbp:before {
  content: "\f154";
}
.fa-dollar:before,
.fa-usd:before {
  content: "\f155";
}
.fa-rupee:before,
.fa-inr:before {
  content: "\f156";
}
.fa-cny:before,
.fa-rmb:before,
.fa-yen:before,
.fa-jpy:before {
  content: "\f157";
}
.fa-ruble:before,
.fa-rouble:before,
.fa-rub:before {
  content: "\f158";
}
.fa-won:before,
.fa-krw:before {
  content: "\f159";
}
.fa-bitcoin:before,
.fa-btc:before {
  content: "\f15a";
}
.fa-file:before {
  content: "\f15b";
}
.fa-file-text:before {
  content: "\f15c";
}
.fa-sort-alpha-asc:before {
  content: "\f15d";
}
.fa-sort-alpha-desc:before {
  content: "\f15e";
}
.fa-sort-amount-asc:before {
  content: "\f160";
}
.fa-sort-amount-desc:before {
  content: "\f161";
}
.fa-sort-numeric-asc:before {
  content: "\f162";
}
.fa-sort-numeric-desc:before {
  content: "\f163";
}
.fa-thumbs-up:before {
  content: "\f164";
}
.fa-thumbs-down:before {
  content: "\f165";
}
.fa-youtube-square:before {
  content: "\f166";
}
.fa-youtube:before {
  content: "\f167";
}
.fa-xing:before {
  content: "\f168";
}
.fa-xing-square:before {
  content: "\f169";
}
.fa-youtube-play:before {
  content: "\f16a";
}
.fa-dropbox:before {
  content: "\f16b";
}
.fa-stack-overflow:before {
  content: "\f16c";
}
.fa-instagram:before {
  content: "\f16d";
}
.fa-flickr:before {
  content: "\f16e";
}
.fa-adn:before {
  content: "\f170";
}
.fa-bitbucket:before {
  content: "\f171";
}
.fa-bitbucket-square:before {
  content: "\f172";
}
.fa-tumblr:before {
  content: "\f173";
}
.fa-tumblr-square:before {
  content: "\f174";
}
.fa-long-arrow-down:before {
  content: "\f175";
}
.fa-long-arrow-up:before {
  content: "\f176";
}
.fa-long-arrow-left:before {
  content: "\f177";
}
.fa-long-arrow-right:before {
  content: "\f178";
}
.fa-apple:before {
  content: "\f179";
}
.fa-windows:before {
  content: "\f17a";
}
.fa-android:before {
  content: "\f17b";
}
.fa-linux:before {
  content: "\f17c";
}
.fa-dribbble:before {
  content: "\f17d";
}
.fa-skype:before {
  content: "\f17e";
}
.fa-foursquare:before {
  content: "\f180";
}
.fa-trello:before {
  content: "\f181";
}
.fa-female:before {
  content: "\f182";
}
.fa-male:before {
  content: "\f183";
}
.fa-gittip:before,
.fa-gratipay:before {
  content: "\f184";
}
.fa-sun-o:before {
  content: "\f185";
}
.fa-moon-o:before {
  content: "\f186";
}
.fa-archive:before {
  content: "\f187";
}
.fa-bug:before {
  content: "\f188";
}
.fa-vk:before {
  content: "\f189";
}
.fa-weibo:before {
  content: "\f18a";
}
.fa-renren:before {
  content: "\f18b";
}
.fa-pagelines:before {
  content: "\f18c";
}
.fa-stack-exchange:before {
  content: "\f18d";
}
.fa-arrow-circle-o-right:before {
  content: "\f18e";
}
.fa-arrow-circle-o-left:before {
  content: "\f190";
}
.fa-toggle-left:before,
.fa-caret-square-o-left:before {
  content: "\f191";
}
.fa-dot-circle-o:before {
  content: "\f192";
}
.fa-wheelchair:before {
  content: "\f193";
}
.fa-vimeo-square:before {
  content: "\f194";
}
.fa-turkish-lira:before,
.fa-try:before {
  content: "\f195";
}
.fa-plus-square-o:before {
  content: "\f196";
}
.fa-space-shuttle:before {
  content: "\f197";
}
.fa-slack:before {
  content: "\f198";
}
.fa-envelope-square:before {
  content: "\f199";
}
.fa-wordpress:before {
  content: "\f19a";
}
.fa-openid:before {
  content: "\f19b";
}
.fa-institution:before,
.fa-bank:before,
.fa-university:before {
  content: "\f19c";
}
.fa-mortar-board:before,
.fa-graduation-cap:before {
  content: "\f19d";
}
.fa-yahoo:before {
  content: "\f19e";
}
.fa-google:before {
  content: "\f1a0";
}
.fa-reddit:before {
  content: "\f1a1";
}
.fa-reddit-square:before {
  content: "\f1a2";
}
.fa-stumbleupon-circle:before {
  content: "\f1a3";
}
.fa-stumbleupon:before {
  content: "\f1a4";
}
.fa-delicious:before {
  content: "\f1a5";
}
.fa-digg:before {
  content: "\f1a6";
}
.fa-pied-piper-pp:before {
  content: "\f1a7";
}
.fa-pied-piper-alt:before {
  content: "\f1a8";
}
.fa-drupal:before {
  content: "\f1a9";
}
.fa-joomla:before {
  content: "\f1aa";
}
.fa-language:before {
  content: "\f1ab";
}
.fa-fax:before {
  content: "\f1ac";
}
.fa-building:before {
  content: "\f1ad";
}
.fa-child:before {
  content: "\f1ae";
}
.fa-paw:before {
  content: "\f1b0";
}
.fa-spoon:before {
  content: "\f1b1";
}
.fa-cube:before {
  content: "\f1b2";
}
.fa-cubes:before {
  content: "\f1b3";
}
.fa-behance:before {
  content: "\f1b4";
}
.fa-behance-square:before {
  content: "\f1b5";
}
.fa-steam:before {
  content: "\f1b6";
}
.fa-steam-square:before {
  content: "\f1b7";
}
.fa-recycle:before {
  content: "\f1b8";
}
.fa-automobile:before,
.fa-car:before {
  content: "\f1b9";
}
.fa-cab:before,
.fa-taxi:before {
  content: "\f1ba";
}
.fa-tree:before {
  content: "\f1bb";
}
.fa-spotify:before {
  content: "\f1bc";
}
.fa-deviantart:before {
  content: "\f1bd";
}
.fa-soundcloud:before {
  content: "\f1be";
}
.fa-database:before {
  content: "\f1c0";
}
.fa-file-pdf-o:before {
  content: "\f1c1";
}
.fa-file-word-o:before {
  content: "\f1c2";
}
.fa-file-excel-o:before {
  content: "\f1c3";
}
.fa-file-powerpoint-o:before {
  content: "\f1c4";
}
.fa-file-photo-o:before,
.fa-file-picture-o:before,
.fa-file-image-o:before {
  content: "\f1c5";
}
.fa-file-zip-o:before,
.fa-file-archive-o:before {
  content: "\f1c6";
}
.fa-file-sound-o:before,
.fa-file-audio-o:before {
  content: "\f1c7";
}
.fa-file-movie-o:before,
.fa-file-video-o:before {
  content: "\f1c8";
}
.fa-file-code-o:before {
  content: "\f1c9";
}
.fa-vine:before {
  content: "\f1ca";
}
.fa-codepen:before {
  content: "\f1cb";
}
.fa-jsfiddle:before {
  content: "\f1cc";
}
.fa-life-bouy:before,
.fa-life-buoy:before,
.fa-life-saver:before,
.fa-support:before,
.fa-life-ring:before {
  content: "\f1cd";
}
.fa-circle-o-notch:before {
  content: "\f1ce";
}
.fa-ra:before,
.fa-resistance:before,
.fa-rebel:before {
  content: "\f1d0";
}
.fa-ge:before,
.fa-empire:before {
  content: "\f1d1";
}
.fa-git-square:before {
  content: "\f1d2";
}
.fa-git:before {
  content: "\f1d3";
}
.fa-y-combinator-square:before,
.fa-yc-square:before,
.fa-hacker-news:before {
  content: "\f1d4";
}
.fa-tencent-weibo:before {
  content: "\f1d5";
}
.fa-qq:before {
  content: "\f1d6";
}
.fa-wechat:before,
.fa-weixin:before {
  content: "\f1d7";
}
.fa-send:before,
.fa-paper-plane:before {
  content: "\f1d8";
}
.fa-send-o:before,
.fa-paper-plane-o:before {
  content: "\f1d9";
}
.fa-history:before {
  content: "\f1da";
}
.fa-circle-thin:before {
  content: "\f1db";
}
.fa-header:before {
  content: "\f1dc";
}
.fa-paragraph:before {
  content: "\f1dd";
}
.fa-sliders:before {
  content: "\f1de";
}
.fa-share-alt:before {
  content: "\f1e0";
}
.fa-share-alt-square:before {
  content: "\f1e1";
}
.fa-bomb:before {
  content: "\f1e2";
}
.fa-soccer-ball-o:before,
.fa-futbol-o:before {
  content: "\f1e3";
}
.fa-tty:before {
  content: "\f1e4";
}
.fa-binoculars:before {
  content: "\f1e5";
}
.fa-plug:before {
  content: "\f1e6";
}
.fa-slideshare:before {
  content: "\f1e7";
}
.fa-twitch:before {
  content: "\f1e8";
}
.fa-yelp:before {
  content: "\f1e9";
}
.fa-newspaper-o:before {
  content: "\f1ea";
}
.fa-wifi:before {
  content: "\f1eb";
}
.fa-calculator:before {
  content: "\f1ec";
}
.fa-paypal:before {
  content: "\f1ed";
}
.fa-google-wallet:before {
  content: "\f1ee";
}
.fa-cc-visa:before {
  content: "\f1f0";
}
.fa-cc-mastercard:before {
  content: "\f1f1";
}
.fa-cc-discover:before {
  content: "\f1f2";
}
.fa-cc-amex:before {
  content: "\f1f3";
}
.fa-cc-paypal:before {
  content: "\f1f4";
}
.fa-cc-stripe:before {
  content: "\f1f5";
}
.fa-bell-slash:before {
  content: "\f1f6";
}
.fa-bell-slash-o:before {
  content: "\f1f7";
}
.fa-trash:before {
  content: "\f1f8";
}
.fa-copyright:before {
  content: "\f1f9";
}
.fa-at:before {
  content: "\f1fa";
}
.fa-eyedropper:before {
  content: "\f1fb";
}
.fa-paint-brush:before {
  content: "\f1fc";
}
.fa-birthday-cake:before {
  content: "\f1fd";
}
.fa-area-chart:before {
  content: "\f1fe";
}
.fa-pie-chart:before {
  content: "\f200";
}
.fa-line-chart:before {
  content: "\f201";
}
.fa-lastfm:before {
  content: "\f202";
}
.fa-lastfm-square:before {
  content: "\f203";
}
.fa-toggle-off:before {
  content: "\f204";
}
.fa-toggle-on:before {
  content: "\f205";
}
.fa-bicycle:before {
  content: "\f206";
}
.fa-bus:before {
  content: "\f207";
}
.fa-ioxhost:before {
  content: "\f208";
}
.fa-angellist:before {
  content: "\f209";
}
.fa-cc:before {
  content: "\f20a";
}
.fa-shekel:before,
.fa-sheqel:before,
.fa-ils:before {
  content: "\f20b";
}
.fa-meanpath:before {
  content: "\f20c";
}
.fa-buysellads:before {
  content: "\f20d";
}
.fa-connectdevelop:before {
  content: "\f20e";
}
.fa-dashcube:before {
  content: "\f210";
}
.fa-forumbee:before {
  content: "\f211";
}
.fa-leanpub:before {
  content: "\f212";
}
.fa-sellsy:before {
  content: "\f213";
}
.fa-shirtsinbulk:before {
  content: "\f214";
}
.fa-simplybuilt:before {
  content: "\f215";
}
.fa-skyatlas:before {
  content: "\f216";
}
.fa-cart-plus:before {
  content: "\f217";
}
.fa-cart-arrow-down:before {
  content: "\f218";
}
.fa-diamond:before {
  content: "\f219";
}
.fa-ship:before {
  content: "\f21a";
}
.fa-user-secret:before {
  content: "\f21b";
}
.fa-motorcycle:before {
  content: "\f21c";
}
.fa-street-view:before {
  content: "\f21d";
}
.fa-heartbeat:before {
  content: "\f21e";
}
.fa-venus:before {
  content: "\f221";
}
.fa-mars:before {
  content: "\f222";
}
.fa-mercury:before {
  content: "\f223";
}
.fa-intersex:before,
.fa-transgender:before {
  content: "\f224";
}
.fa-transgender-alt:before {
  content: "\f225";
}
.fa-venus-double:before {
  content: "\f226";
}
.fa-mars-double:before {
  content: "\f227";
}
.fa-venus-mars:before {
  content: "\f228";
}
.fa-mars-stroke:before {
  content: "\f229";
}
.fa-mars-stroke-v:before {
  content: "\f22a";
}
.fa-mars-stroke-h:before {
  content: "\f22b";
}
.fa-neuter:before {
  content: "\f22c";
}
.fa-genderless:before {
  content: "\f22d";
}
.fa-facebook-official:before {
  content: "\f230";
}
.fa-pinterest-p:before {
  content: "\f231";
}
.fa-whatsapp:before {
  content: "\f232";
}
.fa-server:before {
  content: "\f233";
}
.fa-user-plus:before {
  content: "\f234";
}
.fa-user-times:before {
  content: "\f235";
}
.fa-hotel:before,
.fa-bed:before {
  content: "\f236";
}
.fa-viacoin:before {
  content: "\f237";
}
.fa-train:before {
  content: "\f238";
}
.fa-subway:before {
  content: "\f239";
}
.fa-medium:before {
  content: "\f23a";
}
.fa-yc:before,
.fa-y-combinator:before {
  content: "\f23b";
}
.fa-optin-monster:before {
  content: "\f23c";
}
.fa-opencart:before {
  content: "\f23d";
}
.fa-expeditedssl:before {
  content: "\f23e";
}
.fa-battery-4:before,
.fa-battery:before,
.fa-battery-full:before {
  content: "\f240";
}
.fa-battery-3:before,
.fa-battery-three-quarters:before {
  content: "\f241";
}
.fa-battery-2:before,
.fa-battery-half:before {
  content: "\f242";
}
.fa-battery-1:before,
.fa-battery-quarter:before {
  content: "\f243";
}
.fa-battery-0:before,
.fa-battery-empty:before {
  content: "\f244";
}
.fa-mouse-pointer:before {
  content: "\f245";
}
.fa-i-cursor:before {
  content: "\f246";
}
.fa-object-group:before {
  content: "\f247";
}
.fa-object-ungroup:before {
  content: "\f248";
}
.fa-sticky-note:before {
  content: "\f249";
}
.fa-sticky-note-o:before {
  content: "\f24a";
}
.fa-cc-jcb:before {
  content: "\f24b";
}
.fa-cc-diners-club:before {
  content: "\f24c";
}
.fa-clone:before {
  content: "\f24d";
}
.fa-balance-scale:before {
  content: "\f24e";
}
.fa-hourglass-o:before {
  content: "\f250";
}
.fa-hourglass-1:before,
.fa-hourglass-start:before {
  content: "\f251";
}
.fa-hourglass-2:before,
.fa-hourglass-half:before {
  content: "\f252";
}
.fa-hourglass-3:before,
.fa-hourglass-end:before {
  content: "\f253";
}
.fa-hourglass:before {
  content: "\f254";
}
.fa-hand-grab-o:before,
.fa-hand-rock-o:before {
  content: "\f255";
}
.fa-hand-stop-o:before,
.fa-hand-paper-o:before {
  content: "\f256";
}
.fa-hand-scissors-o:before {
  content: "\f257";
}
.fa-hand-lizard-o:before {
  content: "\f258";
}
.fa-hand-spock-o:before {
  content: "\f259";
}
.fa-hand-pointer-o:before {
  content: "\f25a";
}
.fa-hand-peace-o:before {
  content: "\f25b";
}
.fa-trademark:before {
  content: "\f25c";
}
.fa-registered:before {
  content: "\f25d";
}
.fa-creative-commons:before {
  content: "\f25e";
}
.fa-gg:before {
  content: "\f260";
}
.fa-gg-circle:before {
  content: "\f261";
}
.fa-tripadvisor:before {
  content: "\f262";
}
.fa-odnoklassniki:before {
  content: "\f263";
}
.fa-odnoklassniki-square:before {
  content: "\f264";
}
.fa-get-pocket:before {
  content: "\f265";
}
.fa-wikipedia-w:before {
  content: "\f266";
}
.fa-safari:before {
  content: "\f267";
}
.fa-chrome:before {
  content: "\f268";
}
.fa-firefox:before {
  content: "\f269";
}
.fa-opera:before {
  content: "\f26a";
}
.fa-internet-explorer:before {
  content: "\f26b";
}
.fa-tv:before,
.fa-television:before {
  content: "\f26c";
}
.fa-contao:before {
  content: "\f26d";
}
.fa-500px:before {
  content: "\f26e";
}
.fa-amazon:before {
  content: "\f270";
}
.fa-calendar-plus-o:before {
  content: "\f271";
}
.fa-calendar-minus-o:before {
  content: "\f272";
}
.fa-calendar-times-o:before {
  content: "\f273";
}
.fa-calendar-check-o:before {
  content: "\f274";
}
.fa-industry:before {
  content: "\f275";
}
.fa-map-pin:before {
  content: "\f276";
}
.fa-map-signs:before {
  content: "\f277";
}
.fa-map-o:before {
  content: "\f278";
}
.fa-map:before {
  content: "\f279";
}
.fa-commenting:before {
  content: "\f27a";
}
.fa-commenting-o:before {
  content: "\f27b";
}
.fa-houzz:before {
  content: "\f27c";
}
.fa-vimeo:before {
  content: "\f27d";
}
.fa-black-tie:before {
  content: "\f27e";
}
.fa-fonticons:before {
  content: "\f280";
}
.fa-reddit-alien:before {
  content: "\f281";
}
.fa-edge:before {
  content: "\f282";
}
.fa-credit-card-alt:before {
  content: "\f283";
}
.fa-codiepie:before {
  content: "\f284";
}
.fa-modx:before {
  content: "\f285";
}
.fa-fort-awesome:before {
  content: "\f286";
}
.fa-usb:before {
  content: "\f287";
}
.fa-product-hunt:before {
  content: "\f288";
}
.fa-mixcloud:before {
  content: "\f289";
}
.fa-scribd:before {
  content: "\f28a";
}
.fa-pause-circle:before {
  content: "\f28b";
}
.fa-pause-circle-o:before {
  content: "\f28c";
}
.fa-stop-circle:before {
  content: "\f28d";
}
.fa-stop-circle-o:before {
  content: "\f28e";
}
.fa-shopping-bag:before {
  content: "\f290";
}
.fa-shopping-basket:before {
  content: "\f291";
}
.fa-hashtag:before {
  content: "\f292";
}
.fa-bluetooth:before {
  content: "\f293";
}
.fa-bluetooth-b:before {
  content: "\f294";
}
.fa-percent:before {
  content: "\f295";
}
.fa-gitlab:before {
  content: "\f296";
}
.fa-wpbeginner:before {
  content: "\f297";
}
.fa-wpforms:before {
  content: "\f298";
}
.fa-envira:before {
  content: "\f299";
}
.fa-universal-access:before {
  content: "\f29a";
}
.fa-wheelchair-alt:before {
  content: "\f29b";
}
.fa-question-circle-o:before {
  content: "\f29c";
}
.fa-blind:before {
  content: "\f29d";
}
.fa-audio-description:before {
  content: "\f29e";
}
.fa-volume-control-phone:before {
  content: "\f2a0";
}
.fa-braille:before {
  content: "\f2a1";
}
.fa-assistive-listening-systems:before {
  content: "\f2a2";
}
.fa-asl-interpreting:before,
.fa-american-sign-language-interpreting:before {
  content: "\f2a3";
}
.fa-deafness:before,
.fa-hard-of-hearing:before,
.fa-deaf:before {
  content: "\f2a4";
}
.fa-glide:before {
  content: "\f2a5";
}
.fa-glide-g:before {
  content: "\f2a6";
}
.fa-signing:before,
.fa-sign-language:before {
  content: "\f2a7";
}
.fa-low-vision:before {
  content: "\f2a8";
}
.fa-viadeo:before {
  content: "\f2a9";
}
.fa-viadeo-square:before {
  content: "\f2aa";
}
.fa-snapchat:before {
  content: "\f2ab";
}
.fa-snapchat-ghost:before {
  content: "\f2ac";
}
.fa-snapchat-square:before {
  content: "\f2ad";
}
.fa-pied-piper:before {
  content: "\f2ae";
}
.fa-first-order:before {
  content: "\f2b0";
}
.fa-yoast:before {
  content: "\f2b1";
}
.fa-themeisle:before {
  content: "\f2b2";
}
.fa-google-plus-circle:before,
.fa-google-plus-official:before {
  content: "\f2b3";
}
.fa-fa:before,
.fa-font-awesome:before {
  content: "\f2b4";
}
.fa-handshake-o:before {
  content: "\f2b5";
}
.fa-envelope-open:before {
  content: "\f2b6";
}
.fa-envelope-open-o:before {
  content: "\f2b7";
}
.fa-linode:before {
  content: "\f2b8";
}
.fa-address-book:before {
  content: "\f2b9";
}
.fa-address-book-o:before {
  content: "\f2ba";
}
.fa-vcard:before,
.fa-address-card:before {
  content: "\f2bb";
}
.fa-vcard-o:before,
.fa-address-card-o:before {
  content: "\f2bc";
}
.fa-user-circle:before {
  content: "\f2bd";
}
.fa-user-circle-o:before {
  content: "\f2be";
}
.fa-user-o:before {
  content: "\f2c0";
}
.fa-id-badge:before {
  content: "\f2c1";
}
.fa-drivers-license:before,
.fa-id-card:before {
  content: "\f2c2";
}
.fa-drivers-license-o:before,
.fa-id-card-o:before {
  content: "\f2c3";
}
.fa-quora:before {
  content: "\f2c4";
}
.fa-free-code-camp:before {
  content: "\f2c5";
}
.fa-telegram:before {
  content: "\f2c6";
}
.fa-thermometer-4:before,
.fa-thermometer:before,
.fa-thermometer-full:before {
  content: "\f2c7";
}
.fa-thermometer-3:before,
.fa-thermometer-three-quarters:before {
  content: "\f2c8";
}
.fa-thermometer-2:before,
.fa-thermometer-half:before {
  content: "\f2c9";
}
.fa-thermometer-1:before,
.fa-thermometer-quarter:before {
  content: "\f2ca";
}
.fa-thermometer-0:before,
.fa-thermometer-empty:before {
  content: "\f2cb";
}
.fa-shower:before {
  content: "\f2cc";
}
.fa-bathtub:before,
.fa-s15:before,
.fa-bath:before {
  content: "\f2cd";
}
.fa-podcast:before {
  content: "\f2ce";
}
.fa-window-maximize:before {
  content: "\f2d0";
}
.fa-window-minimize:before {
  content: "\f2d1";
}
.fa-window-restore:before {
  content: "\f2d2";
}
.fa-times-rectangle:before,
.fa-window-close:before {
  content: "\f2d3";
}
.fa-times-rectangle-o:before,
.fa-window-close-o:before {
  content: "\f2d4";
}
.fa-bandcamp:before {
  content: "\f2d5";
}
.fa-grav:before {
  content: "\f2d6";
}
.fa-etsy:before {
  content: "\f2d7";
}
.fa-imdb:before {
  content: "\f2d8";
}
.fa-ravelry:before {
  content: "\f2d9";
}
.fa-eercast:before {
  content: "\f2da";
}
.fa-microchip:before {
  content: "\f2db";
}
.fa-snowflake-o:before {
  content: "\f2dc";
}
.fa-superpowers:before {
  content: "\f2dd";
}
.fa-wpexplorer:before {
  content: "\f2de";
}
.fa-meetup:before {
  content: "\f2e0";
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
/*!
*
* IPython base
*
*/
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
code {
  color: #000;
}
pre {
  font-size: inherit;
  line-height: inherit;
}
label {
  font-weight: normal;
}
/* Make the page background atleast 100% the height of the view port */
/* Make the page itself atleast 70% the height of the view port */
.border-box-sizing {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.corner-all {
  border-radius: 2px;
}
.no-padding {
  padding: 0px;
}
/* Flexible box model classes */
/* Taken from Alex Russell http://infrequently.org/2009/08/css-3-progress/ */
/* This file is a compatability layer.  It allows the usage of flexible box 
model layouts accross multiple browsers, including older browsers.  The newest,
universal implementation of the flexible box model is used when available (see
`Modern browsers` comments below).  Browsers that are known to implement this 
new spec completely include:

    Firefox 28.0+
    Chrome 29.0+
    Internet Explorer 11+ 
    Opera 17.0+

Browsers not listed, including Safari, are supported via the styling under the
`Old browsers` comments below.
*/
.hbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
.hbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.vbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
.vbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.hbox.reverse,
.vbox.reverse,
.reverse {
  /* Old browsers */
  -webkit-box-direction: reverse;
  -moz-box-direction: reverse;
  box-direction: reverse;
  /* Modern browsers */
  flex-direction: row-reverse;
}
.hbox.box-flex0,
.vbox.box-flex0,
.box-flex0 {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
  width: auto;
}
.hbox.box-flex1,
.vbox.box-flex1,
.box-flex1 {
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex,
.vbox.box-flex,
.box-flex {
  /* Old browsers */
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex2,
.vbox.box-flex2,
.box-flex2 {
  /* Old browsers */
  -webkit-box-flex: 2;
  -moz-box-flex: 2;
  box-flex: 2;
  /* Modern browsers */
  flex: 2;
}
.box-group1 {
  /*  Deprecated */
  -webkit-box-flex-group: 1;
  -moz-box-flex-group: 1;
  box-flex-group: 1;
}
.box-group2 {
  /* Deprecated */
  -webkit-box-flex-group: 2;
  -moz-box-flex-group: 2;
  box-flex-group: 2;
}
.hbox.start,
.vbox.start,
.start {
  /* Old browsers */
  -webkit-box-pack: start;
  -moz-box-pack: start;
  box-pack: start;
  /* Modern browsers */
  justify-content: flex-start;
}
.hbox.end,
.vbox.end,
.end {
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
}
.hbox.center,
.vbox.center,
.center {
  /* Old browsers */
  -webkit-box-pack: center;
  -moz-box-pack: center;
  box-pack: center;
  /* Modern browsers */
  justify-content: center;
}
.hbox.baseline,
.vbox.baseline,
.baseline {
  /* Old browsers */
  -webkit-box-pack: baseline;
  -moz-box-pack: baseline;
  box-pack: baseline;
  /* Modern browsers */
  justify-content: baseline;
}
.hbox.stretch,
.vbox.stretch,
.stretch {
  /* Old browsers */
  -webkit-box-pack: stretch;
  -moz-box-pack: stretch;
  box-pack: stretch;
  /* Modern browsers */
  justify-content: stretch;
}
.hbox.align-start,
.vbox.align-start,
.align-start {
  /* Old browsers */
  -webkit-box-align: start;
  -moz-box-align: start;
  box-align: start;
  /* Modern browsers */
  align-items: flex-start;
}
.hbox.align-end,
.vbox.align-end,
.align-end {
  /* Old browsers */
  -webkit-box-align: end;
  -moz-box-align: end;
  box-align: end;
  /* Modern browsers */
  align-items: flex-end;
}
.hbox.align-center,
.vbox.align-center,
.align-center {
  /* Old browsers */
  -webkit-box-align: center;
  -moz-box-align: center;
  box-align: center;
  /* Modern browsers */
  align-items: center;
}
.hbox.align-baseline,
.vbox.align-baseline,
.align-baseline {
  /* Old browsers */
  -webkit-box-align: baseline;
  -moz-box-align: baseline;
  box-align: baseline;
  /* Modern browsers */
  align-items: baseline;
}
.hbox.align-stretch,
.vbox.align-stretch,
.align-stretch {
  /* Old browsers */
  -webkit-box-align: stretch;
  -moz-box-align: stretch;
  box-align: stretch;
  /* Modern browsers */
  align-items: stretch;
}
div.error {
  margin: 2em;
  text-align: center;
}
div.error > h1 {
  font-size: 500%;
  line-height: normal;
}
div.error > p {
  font-size: 200%;
  line-height: normal;
}
div.traceback-wrapper {
  text-align: left;
  max-width: 800px;
  margin: auto;
}
div.traceback-wrapper pre.traceback {
  max-height: 600px;
  overflow: auto;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
body {
  background-color: #fff;
  /* This makes sure that the body covers the entire window and needs to
       be in a different element than the display: box in wrapper below */
  position: absolute;
  left: 0px;
  right: 0px;
  top: 0px;
  bottom: 0px;
  overflow: visible;
}
body > #header {
  /* Initially hidden to prevent FLOUC */
  display: none;
  background-color: #fff;
  /* Display over codemirror */
  position: relative;
  z-index: 100;
}
body > #header #header-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 5px;
  padding-bottom: 5px;
  padding-top: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
body > #header .header-bar {
  width: 100%;
  height: 1px;
  background: #e7e7e7;
  margin-bottom: -1px;
}
@media print {
  body > #header {
    display: none !important;
  }
}
#header-spacer {
  width: 100%;
  visibility: hidden;
}
@media print {
  #header-spacer {
    display: none;
  }
}
#ipython_notebook {
  padding-left: 0px;
  padding-top: 1px;
  padding-bottom: 1px;
}
[dir="rtl"] #ipython_notebook {
  margin-right: 10px;
  margin-left: 0;
}
[dir="rtl"] #ipython_notebook.pull-left {
  float: right !important;
  float: right;
}
.flex-spacer {
  flex: 1;
}
#noscript {
  width: auto;
  padding-top: 16px;
  padding-bottom: 16px;
  text-align: center;
  font-size: 22px;
  color: red;
  font-weight: bold;
}
#ipython_notebook img {
  height: 28px;
}
#site {
  width: 100%;
  display: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  overflow: auto;
}
@media print {
  #site {
    height: auto !important;
  }
}
/* Smaller buttons */
.ui-button .ui-button-text {
  padding: 0.2em 0.8em;
  font-size: 77%;
}
input.ui-button {
  padding: 0.3em 0.9em;
}
span#kernel_logo_widget {
  margin: 0 10px;
}
span#login_widget {
  float: right;
}
[dir="rtl"] span#login_widget {
  float: left;
}
span#login_widget > .button,
#logout {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button:focus,
#logout:focus,
span#login_widget > .button.focus,
#logout.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
span#login_widget > .button:hover,
#logout:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active:hover,
#logout:active:hover,
span#login_widget > .button.active:hover,
#logout.active:hover,
.open > .dropdown-togglespan#login_widget > .button:hover,
.open > .dropdown-toggle#logout:hover,
span#login_widget > .button:active:focus,
#logout:active:focus,
span#login_widget > .button.active:focus,
#logout.active:focus,
.open > .dropdown-togglespan#login_widget > .button:focus,
.open > .dropdown-toggle#logout:focus,
span#login_widget > .button:active.focus,
#logout:active.focus,
span#login_widget > .button.active.focus,
#logout.active.focus,
.open > .dropdown-togglespan#login_widget > .button.focus,
.open > .dropdown-toggle#logout.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  background-image: none;
}
span#login_widget > .button.disabled:hover,
#logout.disabled:hover,
span#login_widget > .button[disabled]:hover,
#logout[disabled]:hover,
fieldset[disabled] span#login_widget > .button:hover,
fieldset[disabled] #logout:hover,
span#login_widget > .button.disabled:focus,
#logout.disabled:focus,
span#login_widget > .button[disabled]:focus,
#logout[disabled]:focus,
fieldset[disabled] span#login_widget > .button:focus,
fieldset[disabled] #logout:focus,
span#login_widget > .button.disabled.focus,
#logout.disabled.focus,
span#login_widget > .button[disabled].focus,
#logout[disabled].focus,
fieldset[disabled] span#login_widget > .button.focus,
fieldset[disabled] #logout.focus {
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button .badge,
#logout .badge {
  color: #fff;
  background-color: #333;
}
.nav-header {
  text-transform: none;
}
#header > span {
  margin-top: 10px;
}
.modal_stretch .modal-dialog {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  min-height: 80vh;
}
.modal_stretch .modal-dialog .modal-body {
  max-height: calc(100vh - 200px);
  overflow: auto;
  flex: 1;
}
.modal-header {
  cursor: move;
}
@media (min-width: 768px) {
  .modal .modal-dialog {
    width: 700px;
  }
}
@media (min-width: 768px) {
  select.form-control {
    margin-left: 12px;
    margin-right: 12px;
  }
}
/*!
*
* IPython auth
*
*/
.center-nav {
  display: inline-block;
  margin-bottom: -4px;
}
[dir="rtl"] .center-nav form.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] .center-nav .navbar-text {
  float: right;
}
[dir="rtl"] .navbar-inner {
  text-align: right;
}
[dir="rtl"] div.text-left {
  text-align: right;
}
/*!
*
* IPython tree view
*
*/
/* We need an invisible input field on top of the sentense*/
/* "Drag file onto the list ..." */
.alternate_upload {
  background-color: none;
  display: inline;
}
.alternate_upload.form {
  padding: 0;
  margin: 0;
}
.alternate_upload input.fileinput {
  position: absolute;
  display: block;
  width: 100%;
  height: 100%;
  overflow: hidden;
  cursor: pointer;
  opacity: 0;
  z-index: 2;
}
.alternate_upload .btn-xs > input.fileinput {
  margin: -1px -5px;
}
.alternate_upload .btn-upload {
  position: relative;
  height: 22px;
}
::-webkit-file-upload-button {
  cursor: pointer;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
ul#tabs {
  margin-bottom: 4px;
}
ul#tabs a {
  padding-top: 6px;
  padding-bottom: 4px;
}
[dir="rtl"] ul#tabs.nav-tabs > li {
  float: right;
}
[dir="rtl"] ul#tabs.nav.nav-tabs {
  padding-right: 0;
}
ul.breadcrumb a:focus,
ul.breadcrumb a:hover {
  text-decoration: none;
}
ul.breadcrumb i.icon-home {
  font-size: 16px;
  margin-right: 4px;
}
ul.breadcrumb span {
  color: #5e5e5e;
}
.list_toolbar {
  padding: 4px 0 4px 0;
  vertical-align: middle;
}
.list_toolbar .tree-buttons {
  padding-top: 1px;
}
[dir="rtl"] .list_toolbar .tree-buttons .pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .list_toolbar .col-sm-4,
[dir="rtl"] .list_toolbar .col-sm-8 {
  float: right;
}
.dynamic-buttons {
  padding-top: 3px;
  display: inline-block;
}
.list_toolbar [class*="span"] {
  min-height: 24px;
}
.list_header {
  font-weight: bold;
  background-color: #EEE;
}
.list_placeholder {
  font-weight: bold;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
}
.list_container {
  margin-top: 4px;
  margin-bottom: 20px;
  border: 1px solid #ddd;
  border-radius: 2px;
}
.list_container > div {
  border-bottom: 1px solid #ddd;
}
.list_container > div:hover .list-item {
  background-color: red;
}
.list_container > div:last-child {
  border: none;
}
.list_item:hover .list_item {
  background-color: #ddd;
}
.list_item a {
  text-decoration: none;
}
.list_item:hover {
  background-color: #fafafa;
}
.list_header > div,
.list_item > div {
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
.list_header > div input,
.list_item > div input {
  margin-right: 7px;
  margin-left: 14px;
  vertical-align: text-bottom;
  line-height: 22px;
  position: relative;
  top: -1px;
}
.list_header > div .item_link,
.list_item > div .item_link {
  margin-left: -1px;
  vertical-align: baseline;
  line-height: 22px;
}
[dir="rtl"] .list_item > div input {
  margin-right: 0;
}
.new-file input[type=checkbox] {
  visibility: hidden;
}
.item_name {
  line-height: 22px;
  height: 24px;
}
.item_icon {
  font-size: 14px;
  color: #5e5e5e;
  margin-right: 7px;
  margin-left: 7px;
  line-height: 22px;
  vertical-align: baseline;
}
.item_modified {
  margin-right: 7px;
  margin-left: 7px;
}
[dir="rtl"] .item_modified.pull-right {
  float: left !important;
  float: left;
}
.item_buttons {
  line-height: 1em;
  margin-left: -5px;
}
.item_buttons .btn,
.item_buttons .btn-group,
.item_buttons .input-group {
  float: left;
}
.item_buttons > .btn,
.item_buttons > .btn-group,
.item_buttons > .input-group {
  margin-left: 5px;
}
.item_buttons .btn {
  min-width: 13ex;
}
.item_buttons .running-indicator {
  padding-top: 4px;
  color: #5cb85c;
}
.item_buttons .kernel-name {
  padding-top: 4px;
  color: #5bc0de;
  margin-right: 7px;
  float: left;
}
[dir="rtl"] .item_buttons.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .item_buttons .kernel-name {
  margin-left: 7px;
  float: right;
}
.toolbar_info {
  height: 24px;
  line-height: 24px;
}
.list_item input:not([type=checkbox]) {
  padding-top: 3px;
  padding-bottom: 3px;
  height: 22px;
  line-height: 14px;
  margin: 0px;
}
.highlight_text {
  color: blue;
}
#project_name {
  display: inline-block;
  padding-left: 7px;
  margin-left: -2px;
}
#project_name > .breadcrumb {
  padding: 0px;
  margin-bottom: 0px;
  background-color: transparent;
  font-weight: bold;
}
.sort_button {
  display: inline-block;
  padding-left: 7px;
}
[dir="rtl"] .sort_button.pull-right {
  float: left !important;
  float: left;
}
#tree-selector {
  padding-right: 0px;
}
#button-select-all {
  min-width: 50px;
}
[dir="rtl"] #button-select-all.btn {
  float: right ;
}
#select-all {
  margin-left: 7px;
  margin-right: 2px;
  margin-top: 2px;
  height: 16px;
}
[dir="rtl"] #select-all.pull-left {
  float: right !important;
  float: right;
}
.menu_icon {
  margin-right: 2px;
}
.tab-content .row {
  margin-left: 0px;
  margin-right: 0px;
}
.folder_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f114";
}
.folder_icon:before.fa-pull-left {
  margin-right: .3em;
}
.folder_icon:before.fa-pull-right {
  margin-left: .3em;
}
.folder_icon:before.pull-left {
  margin-right: .3em;
}
.folder_icon:before.pull-right {
  margin-left: .3em;
}
.notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
}
.notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.notebook_icon:before.pull-left {
  margin-right: .3em;
}
.notebook_icon:before.pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
  color: #5cb85c;
}
.running_notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before.pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.pull-right {
  margin-left: .3em;
}
.file_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f016";
  position: relative;
  top: -2px;
}
.file_icon:before.fa-pull-left {
  margin-right: .3em;
}
.file_icon:before.fa-pull-right {
  margin-left: .3em;
}
.file_icon:before.pull-left {
  margin-right: .3em;
}
.file_icon:before.pull-right {
  margin-left: .3em;
}
#notebook_toolbar .pull-right {
  padding-top: 0px;
  margin-right: -1px;
}
ul#new-menu {
  left: auto;
  right: 0;
}
#new-menu .dropdown-header {
  font-size: 10px;
  border-bottom: 1px solid #e5e5e5;
  padding: 0 0 3px;
  margin: -3px 20px 0;
}
.kernel-menu-icon {
  padding-right: 12px;
  width: 24px;
  content: "\f096";
}
.kernel-menu-icon:before {
  content: "\f096";
}
.kernel-menu-icon-current:before {
  content: "\f00c";
}
#tab_content {
  padding-top: 20px;
}
#running .panel-group .panel {
  margin-top: 3px;
  margin-bottom: 1em;
}
#running .panel-group .panel .panel-heading {
  background-color: #EEE;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
#running .panel-group .panel .panel-heading a:focus,
#running .panel-group .panel .panel-heading a:hover {
  text-decoration: none;
}
#running .panel-group .panel .panel-body {
  padding: 0px;
}
#running .panel-group .panel .panel-body .list_container {
  margin-top: 0px;
  margin-bottom: 0px;
  border: 0px;
  border-radius: 0px;
}
#running .panel-group .panel .panel-body .list_container .list_item {
  border-bottom: 1px solid #ddd;
}
#running .panel-group .panel .panel-body .list_container .list_item:last-child {
  border-bottom: 0px;
}
.delete-button {
  display: none;
}
.duplicate-button {
  display: none;
}
.rename-button {
  display: none;
}
.move-button {
  display: none;
}
.download-button {
  display: none;
}
.shutdown-button {
  display: none;
}
.dynamic-instructions {
  display: inline-block;
  padding-top: 4px;
}
/*!
*
* IPython text editor webapp
*
*/
.selected-keymap i.fa {
  padding: 0px 5px;
}
.selected-keymap i.fa:before {
  content: "\f00c";
}
#mode-menu {
  overflow: auto;
  max-height: 20em;
}
.edit_app #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.edit_app #menubar .navbar {
  /* Use a negative 1 bottom margin, so the border overlaps the border of the
    header */
  margin-bottom: -1px;
}
.dirty-indicator {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator.pull-left {
  margin-right: .3em;
}
.dirty-indicator.pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-dirty.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty.pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-clean.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f00c";
}
.dirty-indicator-clean:before.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.pull-right {
  margin-left: .3em;
}
#filename {
  font-size: 16pt;
  display: table;
  padding: 0px 5px;
}
#current-mode {
  padding-left: 5px;
  padding-right: 5px;
}
#texteditor-backdrop {
  padding-top: 20px;
  padding-bottom: 20px;
}
@media not print {
  #texteditor-backdrop {
    background-color: #EEE;
  }
}
@media print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container {
    padding: 0px;
    background-color: #fff;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
.CodeMirror-dialog {
  background-color: #fff;
}
/*!
*
* IPython notebook
*
*/
/* CSS font colors for translated ANSI escape sequences */
/* The color values are a mix of
   http://www.xcolors.net/dl/baskerville-ivorylight and
   http://www.xcolors.net/dl/euphrasia */
.ansi-black-fg {
  color: #3E424D;
}
.ansi-black-bg {
  background-color: #3E424D;
}
.ansi-black-intense-fg {
  color: #282C36;
}
.ansi-black-intense-bg {
  background-color: #282C36;
}
.ansi-red-fg {
  color: #E75C58;
}
.ansi-red-bg {
  background-color: #E75C58;
}
.ansi-red-intense-fg {
  color: #B22B31;
}
.ansi-red-intense-bg {
  background-color: #B22B31;
}
.ansi-green-fg {
  color: #00A250;
}
.ansi-green-bg {
  background-color: #00A250;
}
.ansi-green-intense-fg {
  color: #007427;
}
.ansi-green-intense-bg {
  background-color: #007427;
}
.ansi-yellow-fg {
  color: #DDB62B;
}
.ansi-yellow-bg {
  background-color: #DDB62B;
}
.ansi-yellow-intense-fg {
  color: #B27D12;
}
.ansi-yellow-intense-bg {
  background-color: #B27D12;
}
.ansi-blue-fg {
  color: #208FFB;
}
.ansi-blue-bg {
  background-color: #208FFB;
}
.ansi-blue-intense-fg {
  color: #0065CA;
}
.ansi-blue-intense-bg {
  background-color: #0065CA;
}
.ansi-magenta-fg {
  color: #D160C4;
}
.ansi-magenta-bg {
  background-color: #D160C4;
}
.ansi-magenta-intense-fg {
  color: #A03196;
}
.ansi-magenta-intense-bg {
  background-color: #A03196;
}
.ansi-cyan-fg {
  color: #60C6C8;
}
.ansi-cyan-bg {
  background-color: #60C6C8;
}
.ansi-cyan-intense-fg {
  color: #258F8F;
}
.ansi-cyan-intense-bg {
  background-color: #258F8F;
}
.ansi-white-fg {
  color: #C5C1B4;
}
.ansi-white-bg {
  background-color: #C5C1B4;
}
.ansi-white-intense-fg {
  color: #A1A6B2;
}
.ansi-white-intense-bg {
  background-color: #A1A6B2;
}
.ansi-default-inverse-fg {
  color: #FFFFFF;
}
.ansi-default-inverse-bg {
  background-color: #000000;
}
.ansi-bold {
  font-weight: bold;
}
.ansi-underline {
  text-decoration: underline;
}
/* The following styles are deprecated an will be removed in a future version */
.ansibold {
  font-weight: bold;
}
.ansi-inverse {
  outline: 0.5px dotted;
}
/* use dark versions for foreground, to improve visibility */
.ansiblack {
  color: black;
}
.ansired {
  color: darkred;
}
.ansigreen {
  color: darkgreen;
}
.ansiyellow {
  color: #c4a000;
}
.ansiblue {
  color: darkblue;
}
.ansipurple {
  color: darkviolet;
}
.ansicyan {
  color: steelblue;
}
.ansigray {
  color: gray;
}
/* and light for background, for the same reason */
.ansibgblack {
  background-color: black;
}
.ansibgred {
  background-color: red;
}
.ansibggreen {
  background-color: green;
}
.ansibgyellow {
  background-color: yellow;
}
.ansibgblue {
  background-color: blue;
}
.ansibgpurple {
  background-color: magenta;
}
.ansibgcyan {
  background-color: cyan;
}
.ansibggray {
  background-color: gray;
}
div.cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-radius: 2px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  border-width: 1px;
  border-style: solid;
  border-color: transparent;
  width: 100%;
  padding: 5px;
  /* This acts as a spacer between cells, that is outside the border */
  margin: 0px;
  outline: none;
  position: relative;
  overflow: visible;
}
div.cell:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: transparent;
}
div.cell.jupyter-soft-selected {
  border-left-color: #E3F2FD;
  border-left-width: 1px;
  padding-left: 5px;
  border-right-color: #E3F2FD;
  border-right-width: 1px;
  background: #E3F2FD;
}
@media print {
  div.cell.jupyter-soft-selected {
    border-color: transparent;
  }
}
div.cell.selected,
div.cell.selected.jupyter-soft-selected {
  border-color: #ababab;
}
div.cell.selected:before,
div.cell.selected.jupyter-soft-selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #42A5F5;
}
@media print {
  div.cell.selected,
  div.cell.selected.jupyter-soft-selected {
    border-color: transparent;
  }
}
.edit_mode div.cell.selected {
  border-color: #66BB6A;
}
.edit_mode div.cell.selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #66BB6A;
}
@media print {
  .edit_mode div.cell.selected {
    border-color: transparent;
  }
}
.prompt {
  /* This needs to be wide enough for 3 digit prompt numbers: In[100]: */
  min-width: 14ex;
  /* This padding is tuned to match the padding on the CodeMirror editor. */
  padding: 0.4em;
  margin: 0px;
  font-family: monospace;
  text-align: right;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
  /* Don't highlight prompt number selection */
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  /* Use default cursor */
  cursor: default;
}
@media (max-width: 540px) {
  .prompt {
    text-align: left;
  }
}
div.inner_cell {
  min-width: 0;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_area {
  border: 1px solid #cfcfcf;
  border-radius: 2px;
  background: #f7f7f7;
  line-height: 1.21429em;
}
/* This is needed so that empty prompt areas can collapse to zero height when there
   is no content in the output_subarea and the prompt. The main purpose of this is
   to make sure that empty JavaScript output_subareas have no height. */
div.prompt:empty {
  padding-top: 0;
  padding-bottom: 0;
}
div.unrecognized_cell {
  padding: 5px 5px 5px 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.unrecognized_cell .inner_cell {
  border-radius: 2px;
  padding: 5px;
  font-weight: bold;
  color: red;
  border: 1px solid #cfcfcf;
  background: #eaeaea;
}
div.unrecognized_cell .inner_cell a {
  color: inherit;
  text-decoration: none;
}
div.unrecognized_cell .inner_cell a:hover {
  color: inherit;
  text-decoration: none;
}
@media (max-width: 540px) {
  div.unrecognized_cell > div.prompt {
    display: none;
  }
}
div.code_cell {
  /* avoid page breaking on code cells when printing */
}
@media print {
  div.code_cell {
    page-break-inside: avoid;
  }
}
/* any special styling for code cells that are currently running goes here */
div.input {
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.input {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_prompt {
  color: #303F9F;
  border-top: 1px solid transparent;
}
div.input_area > div.highlight {
  margin: 0.4em;
  border: none;
  padding: 0px;
  background-color: transparent;
}
div.input_area > div.highlight > pre {
  margin: 0px;
  border: none;
  padding: 0px;
  background-color: transparent;
}
/* The following gets added to the <head> if it is detected that the user has a
 * monospace font with inconsistent normal/bold/italic height.  See
 * notebookmain.js.  Such fonts will have keywords vertically offset with
 * respect to the rest of the text.  The user should select a better font.
 * See: https://github.com/ipython/ipython/issues/1503
 *
 * .CodeMirror span {
 *      vertical-align: bottom;
 * }
 */
.CodeMirror {
  line-height: 1.21429em;
  /* Changed from 1em to our global default */
  font-size: 14px;
  height: auto;
  /* Changed to auto to autogrow */
  background: none;
  /* Changed from white to allow our bg to show through */
}
.CodeMirror-scroll {
  /*  The CodeMirror docs are a bit fuzzy on if overflow-y should be hidden or visible.*/
  /*  We have found that if it is visible, vertical scrollbars appear with font size changes.*/
  overflow-y: hidden;
  overflow-x: auto;
}
.CodeMirror-lines {
  /* In CM2, this used to be 0.4em, but in CM3 it went to 4px. We need the em value because */
  /* we have set a different line-height and want this to scale with that. */
  /* Note that this should set vertical padding only, since CodeMirror assumes
       that horizontal padding will be set on CodeMirror pre */
  padding: 0.4em 0;
}
.CodeMirror-linenumber {
  padding: 0 8px 0 4px;
}
.CodeMirror-gutters {
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.CodeMirror pre {
  /* In CM3 this went to 4px from 0 in CM2. This sets horizontal padding only,
    use .CodeMirror-lines for vertical */
  padding: 0 0.4em;
  border: 0;
  border-radius: 0;
}
.CodeMirror-cursor {
  border-left: 1.4px solid black;
}
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .CodeMirror-cursor {
    border-left: 2px solid black;
  }
}
@media screen and (min-width: 4320px) {
  .CodeMirror-cursor {
    border-left: 4px solid black;
  }
}
/*

Original style from softwaremaniacs.org (c) Ivan Sagalaev <Maniac@SoftwareManiacs.Org>
Adapted from GitHub theme

*/
.highlight-base {
  color: #000;
}
.highlight-variable {
  color: #000;
}
.highlight-variable-2 {
  color: #1a1a1a;
}
.highlight-variable-3 {
  color: #333333;
}
.highlight-string {
  color: #BA2121;
}
.highlight-comment {
  color: #408080;
  font-style: italic;
}
.highlight-number {
  color: #080;
}
.highlight-atom {
  color: #88F;
}
.highlight-keyword {
  color: #008000;
  font-weight: bold;
}
.highlight-builtin {
  color: #008000;
}
.highlight-error {
  color: #f00;
}
.highlight-operator {
  color: #AA22FF;
  font-weight: bold;
}
.highlight-meta {
  color: #AA22FF;
}
/* previously not defined, copying from default codemirror */
.highlight-def {
  color: #00f;
}
.highlight-string-2 {
  color: #f50;
}
.highlight-qualifier {
  color: #555;
}
.highlight-bracket {
  color: #997;
}
.highlight-tag {
  color: #170;
}
.highlight-attribute {
  color: #00c;
}
.highlight-header {
  color: blue;
}
.highlight-quote {
  color: #090;
}
.highlight-link {
  color: #00c;
}
/* apply the same style to codemirror */
.cm-s-ipython span.cm-keyword {
  color: #008000;
  font-weight: bold;
}
.cm-s-ipython span.cm-atom {
  color: #88F;
}
.cm-s-ipython span.cm-number {
  color: #080;
}
.cm-s-ipython span.cm-def {
  color: #00f;
}
.cm-s-ipython span.cm-variable {
  color: #000;
}
.cm-s-ipython span.cm-operator {
  color: #AA22FF;
  font-weight: bold;
}
.cm-s-ipython span.cm-variable-2 {
  color: #1a1a1a;
}
.cm-s-ipython span.cm-variable-3 {
  color: #333333;
}
.cm-s-ipython span.cm-comment {
  color: #408080;
  font-style: italic;
}
.cm-s-ipython span.cm-string {
  color: #BA2121;
}
.cm-s-ipython span.cm-string-2 {
  color: #f50;
}
.cm-s-ipython span.cm-meta {
  color: #AA22FF;
}
.cm-s-ipython span.cm-qualifier {
  color: #555;
}
.cm-s-ipython span.cm-builtin {
  color: #008000;
}
.cm-s-ipython span.cm-bracket {
  color: #997;
}
.cm-s-ipython span.cm-tag {
  color: #170;
}
.cm-s-ipython span.cm-attribute {
  color: #00c;
}
.cm-s-ipython span.cm-header {
  color: blue;
}
.cm-s-ipython span.cm-quote {
  color: #090;
}
.cm-s-ipython span.cm-link {
  color: #00c;
}
.cm-s-ipython span.cm-error {
  color: #f00;
}
.cm-s-ipython span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}
div.output_wrapper {
  /* this position must be relative to enable descendents to be absolute within it */
  position: relative;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  z-index: 1;
}
/* class for the output area when it should be height-limited */
div.output_scroll {
  /* ideally, this would be max-height, but FF barfs all over that */
  height: 24em;
  /* FF needs this *and the wrapper* to specify full width, or it will shrinkwrap */
  width: 100%;
  overflow: auto;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  display: block;
}
/* output div while it is collapsed */
div.output_collapsed {
  margin: 0px;
  padding: 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
div.out_prompt_overlay {
  height: 100%;
  padding: 0px 0.4em;
  position: absolute;
  border-radius: 2px;
}
div.out_prompt_overlay:hover {
  /* use inner shadow to get border that is computed the same on WebKit/FF */
  -webkit-box-shadow: inset 0 0 1px #000;
  box-shadow: inset 0 0 1px #000;
  background: rgba(240, 240, 240, 0.5);
}
div.output_prompt {
  color: #D84315;
}
/* This class is the outer container of all output sections. */
div.output_area {
  padding: 0px;
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.output_area .MathJax_Display {
  text-align: left !important;
}
div.output_area .rendered_html table {
  margin-left: 0;
  margin-right: 0;
}
div.output_area .rendered_html img {
  margin-left: 0;
  margin-right: 0;
}
div.output_area img,
div.output_area svg {
  max-width: 100%;
  height: auto;
}
div.output_area img.unconfined,
div.output_area svg.unconfined {
  max-width: none;
}
div.output_area .mglyph > img {
  max-width: none;
}
/* This is needed to protect the pre formating from global settings such
   as that of bootstrap */
.output {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.output_area {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
div.output_area pre {
  margin: 0;
  padding: 1px 0 1px 0;
  border: 0;
  vertical-align: baseline;
  color: black;
  background-color: transparent;
  border-radius: 0;
}
/* This class is for the output subarea inside the output_area and after
   the prompt div. */
div.output_subarea {
  overflow-x: auto;
  padding: 0.4em;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
  max-width: calc(100% - 14ex);
}
div.output_scroll div.output_subarea {
  overflow-x: visible;
}
/* The rest of the output_* classes are for special styling of the different
   output types */
/* all text output has this class: */
div.output_text {
  text-align: left;
  color: #000;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
}
/* stdout/stderr are 'text' as well as 'stream', but execute_result/error are *not* streams */
div.output_stderr {
  background: #fdd;
  /* very light red background for stderr */
}
div.output_latex {
  text-align: left;
}
/* Empty output_javascript divs should have no height */
div.output_javascript:empty {
  padding: 0;
}
.js-error {
  color: darkred;
}
/* raw_input styles */
div.raw_input_container {
  line-height: 1.21429em;
  padding-top: 5px;
}
pre.raw_input_prompt {
  /* nothing needed here. */
}
input.raw_input {
  font-family: monospace;
  font-size: inherit;
  color: inherit;
  width: auto;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
}
input.raw_input:focus {
  box-shadow: none;
}
p.p-space {
  margin-bottom: 10px;
}
div.output_unrecognized {
  padding: 5px;
  font-weight: bold;
  color: red;
}
div.output_unrecognized a {
  color: inherit;
  text-decoration: none;
}
div.output_unrecognized a:hover {
  color: inherit;
  text-decoration: none;
}
.rendered_html {
  color: #000;
  /* any extras will just be numbers: */
}
.rendered_html em {
  font-style: italic;
}
.rendered_html strong {
  font-weight: bold;
}
.rendered_html u {
  text-decoration: underline;
}
.rendered_html :link {
  text-decoration: underline;
}
.rendered_html :visited {
  text-decoration: underline;
}
.rendered_html h1 {
  font-size: 185.7%;
  margin: 1.08em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h2 {
  font-size: 157.1%;
  margin: 1.27em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h3 {
  font-size: 128.6%;
  margin: 1.55em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h4 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h5 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h6 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h1:first-child {
  margin-top: 0.538em;
}
.rendered_html h2:first-child {
  margin-top: 0.636em;
}
.rendered_html h3:first-child {
  margin-top: 0.777em;
}
.rendered_html h4:first-child {
  margin-top: 1em;
}
.rendered_html h5:first-child {
  margin-top: 1em;
}
.rendered_html h6:first-child {
  margin-top: 1em;
}
.rendered_html ul:not(.list-inline),
.rendered_html ol:not(.list-inline) {
  padding-left: 2em;
}
.rendered_html ul {
  list-style: disc;
}
.rendered_html ul ul {
  list-style: square;
  margin-top: 0;
}
.rendered_html ul ul ul {
  list-style: circle;
}
.rendered_html ol {
  list-style: decimal;
}
.rendered_html ol ol {
  list-style: upper-alpha;
  margin-top: 0;
}
.rendered_html ol ol ol {
  list-style: lower-alpha;
}
.rendered_html ol ol ol ol {
  list-style: lower-roman;
}
.rendered_html ol ol ol ol ol {
  list-style: decimal;
}
.rendered_html * + ul {
  margin-top: 1em;
}
.rendered_html * + ol {
  margin-top: 1em;
}
.rendered_html hr {
  color: black;
  background-color: black;
}
.rendered_html pre {
  margin: 1em 2em;
  padding: 0px;
  background-color: #fff;
}
.rendered_html code {
  background-color: #eff0f1;
}
.rendered_html p code {
  padding: 1px 5px;
}
.rendered_html pre code {
  background-color: #fff;
}
.rendered_html pre,
.rendered_html code {
  border: 0;
  color: #000;
  font-size: 100%;
}
.rendered_html blockquote {
  margin: 1em 2em;
}
.rendered_html table {
  margin-left: auto;
  margin-right: auto;
  border: none;
  border-collapse: collapse;
  border-spacing: 0;
  color: black;
  font-size: 12px;
  table-layout: fixed;
}
.rendered_html thead {
  border-bottom: 1px solid black;
  vertical-align: bottom;
}
.rendered_html tr,
.rendered_html th,
.rendered_html td {
  text-align: right;
  vertical-align: middle;
  padding: 0.5em 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}
.rendered_html th {
  font-weight: bold;
}
.rendered_html tbody tr:nth-child(odd) {
  background: #f5f5f5;
}
.rendered_html tbody tr:hover {
  background: rgba(66, 165, 245, 0.2);
}
.rendered_html * + table {
  margin-top: 1em;
}
.rendered_html p {
  text-align: left;
}
.rendered_html * + p {
  margin-top: 1em;
}
.rendered_html img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.rendered_html * + img {
  margin-top: 1em;
}
.rendered_html img,
.rendered_html svg {
  max-width: 100%;
  height: auto;
}
.rendered_html img.unconfined,
.rendered_html svg.unconfined {
  max-width: none;
}
.rendered_html .alert {
  margin-bottom: initial;
}
.rendered_html * + .alert {
  margin-top: 1em;
}
[dir="rtl"] .rendered_html p {
  text-align: right;
}
div.text_cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.text_cell > div.prompt {
    display: none;
  }
}
div.text_cell_render {
  /*font-family: "Helvetica Neue", Arial, Helvetica, Geneva, sans-serif;*/
  outline: none;
  resize: none;
  width: inherit;
  border-style: none;
  padding: 0.5em 0.5em 0.5em 0.4em;
  color: #000;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
a.anchor-link:link {
  text-decoration: none;
  padding: 0px 20px;
  visibility: hidden;
}
h1:hover .anchor-link,
h2:hover .anchor-link,
h3:hover .anchor-link,
h4:hover .anchor-link,
h5:hover .anchor-link,
h6:hover .anchor-link {
  visibility: visible;
}
.text_cell.rendered .input_area {
  display: none;
}
.text_cell.rendered .rendered_html {
  overflow-x: auto;
  overflow-y: hidden;
}
.text_cell.rendered .rendered_html tr,
.text_cell.rendered .rendered_html th,
.text_cell.rendered .rendered_html td {
  max-width: none;
}
.text_cell.unrendered .text_cell_render {
  display: none;
}
.text_cell .dropzone .input_area {
  border: 2px dashed #bababa;
  margin: -1px;
}
.cm-header-1,
.cm-header-2,
.cm-header-3,
.cm-header-4,
.cm-header-5,
.cm-header-6 {
  font-weight: bold;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
.cm-header-1 {
  font-size: 185.7%;
}
.cm-header-2 {
  font-size: 157.1%;
}
.cm-header-3 {
  font-size: 128.6%;
}
.cm-header-4 {
  font-size: 110%;
}
.cm-header-5 {
  font-size: 100%;
  font-style: italic;
}
.cm-header-6 {
  font-size: 100%;
  font-style: italic;
}
/*!
*
* IPython notebook webapp
*
*/
@media (max-width: 767px) {
  .notebook_app {
    padding-left: 0px;
    padding-right: 0px;
  }
}
#ipython-main-app {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook_panel {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook {
  font-size: 14px;
  line-height: 20px;
  overflow-y: hidden;
  overflow-x: auto;
  width: 100%;
  /* This spaces the page away from the edge of the notebook area */
  padding-top: 20px;
  margin: 0px;
  outline: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  min-height: 100%;
}
@media not print {
  #notebook-container {
    padding: 15px;
    background-color: #fff;
    min-height: 0;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
@media print {
  #notebook-container {
    width: 100%;
  }
}
div.ui-widget-content {
  border: 1px solid #ababab;
  outline: none;
}
pre.dialog {
  background-color: #f7f7f7;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0.4em;
  padding-left: 2em;
}
p.dialog {
  padding: 0.2em;
}
/* Word-wrap output correctly.  This is the CSS3 spelling, though Firefox seems
   to not honor it correctly.  Webkit browsers (Chrome, rekonq, Safari) do.
 */
pre,
code,
kbd,
samp {
  white-space: pre-wrap;
}
#fonttest {
  font-family: monospace;
}
p {
  margin-bottom: 0;
}
.end_space {
  min-height: 100px;
  transition: height .2s ease;
}
.notebook_app > #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
@media not print {
  .notebook_app {
    background-color: #EEE;
  }
}
kbd {
  border-style: solid;
  border-width: 1px;
  box-shadow: none;
  margin: 2px;
  padding-left: 2px;
  padding-right: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
.jupyter-keybindings {
  padding: 1px;
  line-height: 24px;
  border-bottom: 1px solid gray;
}
.jupyter-keybindings input {
  margin: 0;
  padding: 0;
  border: none;
}
.jupyter-keybindings i {
  padding: 6px;
}
.well code {
  background-color: #ffffff;
  border-color: #ababab;
  border-width: 1px;
  border-style: solid;
  padding: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
/* CSS for the cell toolbar */
.celltoolbar {
  border: thin solid #CFCFCF;
  border-bottom: none;
  background: #EEE;
  border-radius: 2px 2px 0px 0px;
  width: 100%;
  height: 29px;
  padding-right: 4px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
  display: -webkit-flex;
}
@media print {
  .celltoolbar {
    display: none;
  }
}
.ctb_hideshow {
  display: none;
  vertical-align: bottom;
}
/* ctb_show is added to the ctb_hideshow div to show the cell toolbar.
   Cell toolbars are only shown when the ctb_global_show class is also set.
*/
.ctb_global_show .ctb_show.ctb_hideshow {
  display: block;
}
.ctb_global_show .ctb_show + .input_area,
.ctb_global_show .ctb_show + div.text_cell_input,
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border-top-right-radius: 0px;
  border-top-left-radius: 0px;
}
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border: 1px solid #cfcfcf;
}
.celltoolbar {
  font-size: 87%;
  padding-top: 3px;
}
.celltoolbar select {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  width: inherit;
  font-size: inherit;
  height: 22px;
  padding: 0px;
  display: inline-block;
}
.celltoolbar select:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.celltoolbar select::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.celltoolbar select:-ms-input-placeholder {
  color: #999;
}
.celltoolbar select::-webkit-input-placeholder {
  color: #999;
}
.celltoolbar select::-ms-expand {
  border: 0;
  background-color: transparent;
}
.celltoolbar select[disabled],
.celltoolbar select[readonly],
fieldset[disabled] .celltoolbar select {
  background-color: #eeeeee;
  opacity: 1;
}
.celltoolbar select[disabled],
fieldset[disabled] .celltoolbar select {
  cursor: not-allowed;
}
textarea.celltoolbar select {
  height: auto;
}
select.celltoolbar select {
  height: 30px;
  line-height: 30px;
}
textarea.celltoolbar select,
select[multiple].celltoolbar select {
  height: auto;
}
.celltoolbar label {
  margin-left: 5px;
  margin-right: 5px;
}
.tags_button_container {
  width: 100%;
  display: flex;
}
.tag-container {
  display: flex;
  flex-direction: row;
  flex-grow: 1;
  overflow: hidden;
  position: relative;
}
.tag-container > * {
  margin: 0 4px;
}
.remove-tag-btn {
  margin-left: 4px;
}
.tags-input {
  display: flex;
}
.cell-tag:last-child:after {
  content: "";
  position: absolute;
  right: 0;
  width: 40px;
  height: 100%;
  /* Fade to background color of cell toolbar */
  background: linear-gradient(to right, rgba(0, 0, 0, 0), #EEE);
}
.tags-input > * {
  margin-left: 4px;
}
.cell-tag,
.tags-input input,
.tags-input button {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  box-shadow: none;
  width: inherit;
  font-size: inherit;
  height: 22px;
  line-height: 22px;
  padding: 0px 4px;
  display: inline-block;
}
.cell-tag:focus,
.tags-input input:focus,
.tags-input button:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.cell-tag::-moz-placeholder,
.tags-input input::-moz-placeholder,
.tags-input button::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.cell-tag:-ms-input-placeholder,
.tags-input input:-ms-input-placeholder,
.tags-input button:-ms-input-placeholder {
  color: #999;
}
.cell-tag::-webkit-input-placeholder,
.tags-input input::-webkit-input-placeholder,
.tags-input button::-webkit-input-placeholder {
  color: #999;
}
.cell-tag::-ms-expand,
.tags-input input::-ms-expand,
.tags-input button::-ms-expand {
  border: 0;
  background-color: transparent;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
.cell-tag[readonly],
.tags-input input[readonly],
.tags-input button[readonly],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  background-color: #eeeeee;
  opacity: 1;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  cursor: not-allowed;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button {
  height: auto;
}
select.cell-tag,
select.tags-input input,
select.tags-input button {
  height: 30px;
  line-height: 30px;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button,
select[multiple].cell-tag,
select[multiple].tags-input input,
select[multiple].tags-input button {
  height: auto;
}
.cell-tag,
.tags-input button {
  padding: 0px 4px;
}
.cell-tag {
  background-color: #fff;
  white-space: nowrap;
}
.tags-input input[type=text]:focus {
  outline: none;
  box-shadow: none;
  border-color: #ccc;
}
.completions {
  position: absolute;
  z-index: 110;
  overflow: hidden;
  border: 1px solid #ababab;
  border-radius: 2px;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  line-height: 1;
}
.completions select {
  background: white;
  outline: none;
  border: none;
  padding: 0px;
  margin: 0px;
  overflow: auto;
  font-family: monospace;
  font-size: 110%;
  color: #000;
  width: auto;
}
.completions select option.context {
  color: #286090;
}
#kernel_logo_widget .current_kernel_logo {
  display: none;
  margin-top: -1px;
  margin-bottom: -1px;
  width: 32px;
  height: 32px;
}
[dir="rtl"] #kernel_logo_widget {
  float: left !important;
  float: left;
}
.modal .modal-body .move-path {
  display: flex;
  flex-direction: row;
  justify-content: space;
  align-items: center;
}
.modal .modal-body .move-path .server-root {
  padding-right: 20px;
}
.modal .modal-body .move-path .path-input {
  flex: 1;
}
#menubar {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  margin-top: 1px;
}
#menubar .navbar {
  border-top: 1px;
  border-radius: 0px 0px 2px 2px;
  margin-bottom: 0px;
}
#menubar .navbar-toggle {
  float: left;
  padding-top: 7px;
  padding-bottom: 7px;
  border: none;
}
#menubar .navbar-collapse {
  clear: left;
}
[dir="rtl"] #menubar .navbar-toggle {
  float: right;
}
[dir="rtl"] #menubar .navbar-collapse {
  clear: right;
}
[dir="rtl"] #menubar .navbar-nav {
  float: right;
}
[dir="rtl"] #menubar .nav {
  padding-right: 0px;
}
[dir="rtl"] #menubar .navbar-nav > li {
  float: right;
}
[dir="rtl"] #menubar .navbar-right {
  float: left !important;
}
[dir="rtl"] ul.dropdown-menu {
  text-align: right;
  left: auto;
}
[dir="rtl"] ul#new-menu.dropdown-menu {
  right: auto;
  left: 0;
}
.nav-wrapper {
  border-bottom: 1px solid #e7e7e7;
}
i.menu-icon {
  padding-top: 4px;
}
[dir="rtl"] i.menu-icon.pull-right {
  float: left !important;
  float: left;
}
ul#help_menu li a {
  overflow: hidden;
  padding-right: 2.2em;
}
ul#help_menu li a i {
  margin-right: -1.2em;
}
[dir="rtl"] ul#help_menu li a {
  padding-left: 2.2em;
}
[dir="rtl"] ul#help_menu li a i {
  margin-right: 0;
  margin-left: -1.2em;
}
[dir="rtl"] ul#help_menu li a i.pull-right {
  float: left !important;
  float: left;
}
.dropdown-submenu {
  position: relative;
}
.dropdown-submenu > .dropdown-menu {
  top: 0;
  left: 100%;
  margin-top: -6px;
  margin-left: -1px;
}
[dir="rtl"] .dropdown-submenu > .dropdown-menu {
  right: 100%;
  margin-right: -1px;
}
.dropdown-submenu:hover > .dropdown-menu {
  display: block;
}
.dropdown-submenu > a:after {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: block;
  content: "\f0da";
  float: right;
  color: #333333;
  margin-top: 2px;
  margin-right: -10px;
}
.dropdown-submenu > a:after.fa-pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.fa-pull-right {
  margin-left: .3em;
}
.dropdown-submenu > a:after.pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.pull-right {
  margin-left: .3em;
}
[dir="rtl"] .dropdown-submenu > a:after {
  float: left;
  content: "\f0d9";
  margin-right: 0;
  margin-left: -10px;
}
.dropdown-submenu:hover > a:after {
  color: #262626;
}
.dropdown-submenu.pull-left {
  float: none;
}
.dropdown-submenu.pull-left > .dropdown-menu {
  left: -100%;
  margin-left: 10px;
}
#notification_area {
  float: right !important;
  float: right;
  z-index: 10;
}
[dir="rtl"] #notification_area {
  float: left !important;
  float: left;
}
.indicator_area {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] .indicator_area {
  float: left !important;
  float: left;
}
#kernel_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  border-left: 1px solid;
}
#kernel_indicator .kernel_indicator_name {
  padding-left: 5px;
  padding-right: 5px;
}
[dir="rtl"] #kernel_indicator {
  float: left !important;
  float: left;
  border-left: 0;
  border-right: 1px solid;
}
#modal_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] #modal_indicator {
  float: left !important;
  float: left;
}
#readonly-indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  margin-top: 2px;
  margin-bottom: 0px;
  margin-left: 0px;
  margin-right: 0px;
  display: none;
}
.modal_indicator:before {
  width: 1.28571429em;
  text-align: center;
}
.edit_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f040";
}
.edit_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.edit_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: ' ';
}
.command_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f10c";
}
.kernel_idle_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f111";
}
.kernel_busy_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f1e2";
}
.kernel_dead_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f127";
}
.kernel_disconnected_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.pull-right {
  margin-left: .3em;
}
.notification_widget {
  color: #777;
  z-index: 10;
  background: rgba(240, 240, 240, 0.5);
  margin-right: 4px;
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget:focus,
.notification_widget.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.notification_widget:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active:hover,
.notification_widget.active:hover,
.open > .dropdown-toggle.notification_widget:hover,
.notification_widget:active:focus,
.notification_widget.active:focus,
.open > .dropdown-toggle.notification_widget:focus,
.notification_widget:active.focus,
.notification_widget.active.focus,
.open > .dropdown-toggle.notification_widget.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  background-image: none;
}
.notification_widget.disabled:hover,
.notification_widget[disabled]:hover,
fieldset[disabled] .notification_widget:hover,
.notification_widget.disabled:focus,
.notification_widget[disabled]:focus,
fieldset[disabled] .notification_widget:focus,
.notification_widget.disabled.focus,
.notification_widget[disabled].focus,
fieldset[disabled] .notification_widget.focus {
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget .badge {
  color: #fff;
  background-color: #333;
}
.notification_widget.warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning:focus,
.notification_widget.warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.notification_widget.warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active:hover,
.notification_widget.warning.active:hover,
.open > .dropdown-toggle.notification_widget.warning:hover,
.notification_widget.warning:active:focus,
.notification_widget.warning.active:focus,
.open > .dropdown-toggle.notification_widget.warning:focus,
.notification_widget.warning:active.focus,
.notification_widget.warning.active.focus,
.open > .dropdown-toggle.notification_widget.warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  background-image: none;
}
.notification_widget.warning.disabled:hover,
.notification_widget.warning[disabled]:hover,
fieldset[disabled] .notification_widget.warning:hover,
.notification_widget.warning.disabled:focus,
.notification_widget.warning[disabled]:focus,
fieldset[disabled] .notification_widget.warning:focus,
.notification_widget.warning.disabled.focus,
.notification_widget.warning[disabled].focus,
fieldset[disabled] .notification_widget.warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.notification_widget.success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success:focus,
.notification_widget.success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.notification_widget.success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active:hover,
.notification_widget.success.active:hover,
.open > .dropdown-toggle.notification_widget.success:hover,
.notification_widget.success:active:focus,
.notification_widget.success.active:focus,
.open > .dropdown-toggle.notification_widget.success:focus,
.notification_widget.success:active.focus,
.notification_widget.success.active.focus,
.open > .dropdown-toggle.notification_widget.success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  background-image: none;
}
.notification_widget.success.disabled:hover,
.notification_widget.success[disabled]:hover,
fieldset[disabled] .notification_widget.success:hover,
.notification_widget.success.disabled:focus,
.notification_widget.success[disabled]:focus,
fieldset[disabled] .notification_widget.success:focus,
.notification_widget.success.disabled.focus,
.notification_widget.success[disabled].focus,
fieldset[disabled] .notification_widget.success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.notification_widget.info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info:focus,
.notification_widget.info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.notification_widget.info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active:hover,
.notification_widget.info.active:hover,
.open > .dropdown-toggle.notification_widget.info:hover,
.notification_widget.info:active:focus,
.notification_widget.info.active:focus,
.open > .dropdown-toggle.notification_widget.info:focus,
.notification_widget.info:active.focus,
.notification_widget.info.active.focus,
.open > .dropdown-toggle.notification_widget.info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  background-image: none;
}
.notification_widget.info.disabled:hover,
.notification_widget.info[disabled]:hover,
fieldset[disabled] .notification_widget.info:hover,
.notification_widget.info.disabled:focus,
.notification_widget.info[disabled]:focus,
fieldset[disabled] .notification_widget.info:focus,
.notification_widget.info.disabled.focus,
.notification_widget.info[disabled].focus,
fieldset[disabled] .notification_widget.info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.notification_widget.danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger:focus,
.notification_widget.danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.notification_widget.danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active:hover,
.notification_widget.danger.active:hover,
.open > .dropdown-toggle.notification_widget.danger:hover,
.notification_widget.danger:active:focus,
.notification_widget.danger.active:focus,
.open > .dropdown-toggle.notification_widget.danger:focus,
.notification_widget.danger:active.focus,
.notification_widget.danger.active.focus,
.open > .dropdown-toggle.notification_widget.danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  background-image: none;
}
.notification_widget.danger.disabled:hover,
.notification_widget.danger[disabled]:hover,
fieldset[disabled] .notification_widget.danger:hover,
.notification_widget.danger.disabled:focus,
.notification_widget.danger[disabled]:focus,
fieldset[disabled] .notification_widget.danger:focus,
.notification_widget.danger.disabled.focus,
.notification_widget.danger[disabled].focus,
fieldset[disabled] .notification_widget.danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger .badge {
  color: #d9534f;
  background-color: #fff;
}
div#pager {
  background-color: #fff;
  font-size: 14px;
  line-height: 20px;
  overflow: hidden;
  display: none;
  position: fixed;
  bottom: 0px;
  width: 100%;
  max-height: 50%;
  padding-top: 8px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  /* Display over codemirror */
  z-index: 100;
  /* Hack which prevents jquery ui resizable from changing top. */
  top: auto !important;
}
div#pager pre {
  line-height: 1.21429em;
  color: #000;
  background-color: #f7f7f7;
  padding: 0.4em;
}
div#pager #pager-button-area {
  position: absolute;
  top: 8px;
  right: 20px;
}
div#pager #pager-contents {
  position: relative;
  overflow: auto;
  width: 100%;
  height: 100%;
}
div#pager #pager-contents #pager-container {
  position: relative;
  padding: 15px 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
div#pager .ui-resizable-handle {
  top: 0px;
  height: 8px;
  background: #f7f7f7;
  border-top: 1px solid #cfcfcf;
  border-bottom: 1px solid #cfcfcf;
  /* This injects handle bars (a short, wide = symbol) for 
        the resize handle. */
}
div#pager .ui-resizable-handle::after {
  content: '';
  top: 2px;
  left: 50%;
  height: 3px;
  width: 30px;
  margin-left: -15px;
  position: absolute;
  border-top: 1px solid #cfcfcf;
}
.quickhelp {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  line-height: 1.8em;
}
.shortcut_key {
  display: inline-block;
  width: 21ex;
  text-align: right;
  font-family: monospace;
}
.shortcut_descr {
  display: inline-block;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
span.save_widget {
  height: 30px;
  margin-top: 4px;
  display: flex;
  justify-content: flex-start;
  align-items: baseline;
  width: 50%;
  flex: 1;
}
span.save_widget span.filename {
  height: 100%;
  line-height: 1em;
  margin-left: 16px;
  border: none;
  font-size: 146.5%;
  text-overflow: ellipsis;
  overflow: hidden;
  white-space: nowrap;
  border-radius: 2px;
}
span.save_widget span.filename:hover {
  background-color: #e6e6e6;
}
[dir="rtl"] span.save_widget.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] span.save_widget span.filename {
  margin-left: 0;
  margin-right: 16px;
}
span.checkpoint_status,
span.autosave_status {
  font-size: small;
  white-space: nowrap;
  padding: 0 5px;
}
@media (max-width: 767px) {
  span.save_widget {
    font-size: small;
    padding: 0 0 0 5px;
  }
  span.checkpoint_status,
  span.autosave_status {
    display: none;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  span.checkpoint_status {
    display: none;
  }
  span.autosave_status {
    font-size: x-small;
  }
}
.toolbar {
  padding: 0px;
  margin-left: -5px;
  margin-top: 2px;
  margin-bottom: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.toolbar select,
.toolbar label {
  width: auto;
  vertical-align: middle;
  margin-right: 2px;
  margin-bottom: 0px;
  display: inline;
  font-size: 92%;
  margin-left: 0.3em;
  margin-right: 0.3em;
  padding: 0px;
  padding-top: 3px;
}
.toolbar .btn {
  padding: 2px 8px;
}
.toolbar .btn-group {
  margin-top: 0px;
  margin-left: 5px;
}
.toolbar-btn-label {
  margin-left: 6px;
}
#maintoolbar {
  margin-bottom: -3px;
  margin-top: -8px;
  border: 0px;
  min-height: 27px;
  margin-left: 0px;
  padding-top: 11px;
  padding-bottom: 3px;
}
#maintoolbar .navbar-text {
  float: none;
  vertical-align: middle;
  text-align: right;
  margin-left: 5px;
  margin-right: 0px;
  margin-top: 0px;
}
.select-xs {
  height: 24px;
}
[dir="rtl"] .btn-group > .btn,
.btn-group-vertical > .btn {
  float: right;
}
.pulse,
.dropdown-menu > li > a.pulse,
li.pulse > a.dropdown-toggle,
li.pulse.open > a.dropdown-toggle {
  background-color: #F37626;
  color: white;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
/** WARNING IF YOU ARE EDITTING THIS FILE, if this is a .css file, It has a lot
 * of chance of beeing generated from the ../less/[samename].less file, you can
 * try to get back the less file by reverting somme commit in history
 **/
/*
 * We'll try to get something pretty, so we
 * have some strange css to have the scroll bar on
 * the left with fix button on the top right of the tooltip
 */
@-moz-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-webkit-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-moz-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
/*properties of tooltip after "expand"*/
.bigtooltip {
  overflow: auto;
  height: 200px;
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
}
/*properties of tooltip before "expand"*/
.smalltooltip {
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
  text-overflow: ellipsis;
  overflow: hidden;
  height: 80px;
}
.tooltipbuttons {
  position: absolute;
  padding-right: 15px;
  top: 0px;
  right: 0px;
}
.tooltiptext {
  /*avoid the button to overlap on some docstring*/
  padding-right: 30px;
}
.ipython_tooltip {
  max-width: 700px;
  /*fade-in animation when inserted*/
  -webkit-animation: fadeOut 400ms;
  -moz-animation: fadeOut 400ms;
  animation: fadeOut 400ms;
  -webkit-animation: fadeIn 400ms;
  -moz-animation: fadeIn 400ms;
  animation: fadeIn 400ms;
  vertical-align: middle;
  background-color: #f7f7f7;
  overflow: visible;
  border: #ababab 1px solid;
  outline: none;
  padding: 3px;
  margin: 0px;
  padding-left: 7px;
  font-family: monospace;
  min-height: 50px;
  -moz-box-shadow: 0px 6px 10px -1px #adadad;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  border-radius: 2px;
  position: absolute;
  z-index: 1000;
}
.ipython_tooltip a {
  float: right;
}
.ipython_tooltip .tooltiptext pre {
  border: 0;
  border-radius: 0;
  font-size: 100%;
  background-color: #f7f7f7;
}
.pretooltiparrow {
  left: 0px;
  margin: 0px;
  top: -16px;
  width: 40px;
  height: 16px;
  overflow: hidden;
  position: absolute;
}
.pretooltiparrow:before {
  background-color: #f7f7f7;
  border: 1px #ababab solid;
  z-index: 11;
  content: "";
  position: absolute;
  left: 15px;
  top: 10px;
  width: 25px;
  height: 25px;
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  -o-transform: rotate(45deg);
}
ul.typeahead-list i {
  margin-left: -10px;
  width: 18px;
}
[dir="rtl"] ul.typeahead-list i {
  margin-left: 0;
  margin-right: -10px;
}
ul.typeahead-list {
  max-height: 80vh;
  overflow: auto;
}
ul.typeahead-list > li > a {
  /** Firefox bug **/
  /* see https://github.com/jupyter/notebook/issues/559 */
  white-space: normal;
}
ul.typeahead-list  > li > a.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .typeahead-list {
  text-align: right;
}
.cmd-palette .modal-body {
  padding: 7px;
}
.cmd-palette form {
  background: white;
}
.cmd-palette input {
  outline: none;
}
.no-shortcut {
  min-width: 20px;
  color: transparent;
}
[dir="rtl"] .no-shortcut.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .command-shortcut.pull-right {
  float: left !important;
  float: left;
}
.command-shortcut:before {
  content: "(command mode)";
  padding-right: 3px;
  color: #777777;
}
.edit-shortcut:before {
  content: "(edit)";
  padding-right: 3px;
  color: #777777;
}
[dir="rtl"] .edit-shortcut.pull-right {
  float: left !important;
  float: left;
}
#find-and-replace #replace-preview .match,
#find-and-replace #replace-preview .insert {
  background-color: #BBDEFB;
  border-color: #90CAF9;
  border-style: solid;
  border-width: 1px;
  border-radius: 0px;
}
[dir="ltr"] #find-and-replace .input-group-btn + .form-control {
  border-left: none;
}
[dir="rtl"] #find-and-replace .input-group-btn + .form-control {
  border-right: none;
}
#find-and-replace #replace-preview .replace .match {
  background-color: #FFCDD2;
  border-color: #EF9A9A;
  border-radius: 0px;
}
#find-and-replace #replace-preview .replace .insert {
  background-color: #C8E6C9;
  border-color: #A5D6A7;
  border-radius: 0px;
}
#find-and-replace #replace-preview {
  max-height: 60vh;
  overflow: auto;
}
#find-and-replace #replace-preview pre {
  padding: 5px 10px;
}
.terminal-app {
  background: #EEE;
}
.terminal-app #header {
  background: #fff;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.terminal-app .terminal {
  width: 100%;
  float: left;
  font-family: monospace;
  color: white;
  background: black;
  padding: 0.4em;
  border-radius: 2px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
}
.terminal-app .terminal,
.terminal-app .terminal dummy-screen {
  line-height: 1em;
  font-size: 14px;
}
.terminal-app .terminal .xterm-rows {
  padding: 10px;
}
.terminal-app .terminal-cursor {
  color: black;
  background: white;
}
.terminal-app #terminado-container {
  margin-top: 20px;
}
/*# sourceMappingURL=style.min.css.map */
    </style>
<style type="text/css">
    .highlight .hll { background-color: #ffffcc }
.highlight  { background: #f8f8f8; }
.highlight .c { color: #408080; font-style: italic } /* Comment */
.highlight .err { border: 1px solid #FF0000 } /* Error */
.highlight .k { color: #008000; font-weight: bold } /* Keyword */
.highlight .o { color: #666666 } /* Operator */
.highlight .ch { color: #408080; font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: #408080; font-style: italic } /* Comment.Multiline */
.highlight .cp { color: #BC7A00 } /* Comment.Preproc */
.highlight .cpf { color: #408080; font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: #408080; font-style: italic } /* Comment.Single */
.highlight .cs { color: #408080; font-style: italic } /* Comment.Special */
.highlight .gd { color: #A00000 } /* Generic.Deleted */
.highlight .ge { font-style: italic } /* Generic.Emph */
.highlight .gr { color: #FF0000 } /* Generic.Error */
.highlight .gh { color: #000080; font-weight: bold } /* Generic.Heading */
.highlight .gi { color: #00A000 } /* Generic.Inserted */
.highlight .go { color: #888888 } /* Generic.Output */
.highlight .gp { color: #000080; font-weight: bold } /* Generic.Prompt */
.highlight .gs { font-weight: bold } /* Generic.Strong */
.highlight .gu { color: #800080; font-weight: bold } /* Generic.Subheading */
.highlight .gt { color: #0044DD } /* Generic.Traceback */
.highlight .kc { color: #008000; font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: #008000; font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: #008000; font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: #008000 } /* Keyword.Pseudo */
.highlight .kr { color: #008000; font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: #B00040 } /* Keyword.Type */
.highlight .m { color: #666666 } /* Literal.Number */
.highlight .s { color: #BA2121 } /* Literal.String */
.highlight .na { color: #7D9029 } /* Name.Attribute */
.highlight .nb { color: #008000 } /* Name.Builtin */
.highlight .nc { color: #0000FF; font-weight: bold } /* Name.Class */
.highlight .no { color: #880000 } /* Name.Constant */
.highlight .nd { color: #AA22FF } /* Name.Decorator */
.highlight .ni { color: #999999; font-weight: bold } /* Name.Entity */
.highlight .ne { color: #D2413A; font-weight: bold } /* Name.Exception */
.highlight .nf { color: #0000FF } /* Name.Function */
.highlight .nl { color: #A0A000 } /* Name.Label */
.highlight .nn { color: #0000FF; font-weight: bold } /* Name.Namespace */
.highlight .nt { color: #008000; font-weight: bold } /* Name.Tag */
.highlight .nv { color: #19177C } /* Name.Variable */
.highlight .ow { color: #AA22FF; font-weight: bold } /* Operator.Word */
.highlight .w { color: #bbbbbb } /* Text.Whitespace */
.highlight .mb { color: #666666 } /* Literal.Number.Bin */
.highlight .mf { color: #666666 } /* Literal.Number.Float */
.highlight .mh { color: #666666 } /* Literal.Number.Hex */
.highlight .mi { color: #666666 } /* Literal.Number.Integer */
.highlight .mo { color: #666666 } /* Literal.Number.Oct */
.highlight .sb { color: #BA2121 } /* Literal.String.Backtick */
.highlight .sc { color: #BA2121 } /* Literal.String.Char */
.highlight .sd { color: #BA2121; font-style: italic } /* Literal.String.Doc */
.highlight .s2 { color: #BA2121 } /* Literal.String.Double */
.highlight .se { color: #BB6622; font-weight: bold } /* Literal.String.Escape */
.highlight .sh { color: #BA2121 } /* Literal.String.Heredoc */
.highlight .si { color: #BB6688; font-weight: bold } /* Literal.String.Interpol */
.highlight .sx { color: #008000 } /* Literal.String.Other */
.highlight .sr { color: #BB6688 } /* Literal.String.Regex */
.highlight .s1 { color: #BA2121 } /* Literal.String.Single */
.highlight .ss { color: #19177C } /* Literal.String.Symbol */
.highlight .bp { color: #008000 } /* Name.Builtin.Pseudo */
.highlight .vc { color: #19177C } /* Name.Variable.Class */
.highlight .vg { color: #19177C } /* Name.Variable.Global */
.highlight .vi { color: #19177C } /* Name.Variable.Instance */
.highlight .il { color: #666666 } /* Literal.Number.Integer.Long */
    </style>
<style type="text/css">
    
/* Temporary definitions which will become obsolete with Notebook release 5.0 */
.ansi-black-fg { color: #3E424D; }
.ansi-black-bg { background-color: #3E424D; }
.ansi-black-intense-fg { color: #282C36; }
.ansi-black-intense-bg { background-color: #282C36; }
.ansi-red-fg { color: #E75C58; }
.ansi-red-bg { background-color: #E75C58; }
.ansi-red-intense-fg { color: #B22B31; }
.ansi-red-intense-bg { background-color: #B22B31; }
.ansi-green-fg { color: #00A250; }
.ansi-green-bg { background-color: #00A250; }
.ansi-green-intense-fg { color: #007427; }
.ansi-green-intense-bg { background-color: #007427; }
.ansi-yellow-fg { color: #DDB62B; }
.ansi-yellow-bg { background-color: #DDB62B; }
.ansi-yellow-intense-fg { color: #B27D12; }
.ansi-yellow-intense-bg { background-color: #B27D12; }
.ansi-blue-fg { color: #208FFB; }
.ansi-blue-bg { background-color: #208FFB; }
.ansi-blue-intense-fg { color: #0065CA; }
.ansi-blue-intense-bg { background-color: #0065CA; }
.ansi-magenta-fg { color: #D160C4; }
.ansi-magenta-bg { background-color: #D160C4; }
.ansi-magenta-intense-fg { color: #A03196; }
.ansi-magenta-intense-bg { background-color: #A03196; }
.ansi-cyan-fg { color: #60C6C8; }
.ansi-cyan-bg { background-color: #60C6C8; }
.ansi-cyan-intense-fg { color: #258F8F; }
.ansi-cyan-intense-bg { background-color: #258F8F; }
.ansi-white-fg { color: #C5C1B4; }
.ansi-white-bg { background-color: #C5C1B4; }
.ansi-white-intense-fg { color: #A1A6B2; }
.ansi-white-intense-bg { background-color: #A1A6B2; }

.ansi-bold { font-weight: bold; }

    </style>


<style type="text/css">
/* Overrides of notebook CSS for static HTML export */
body {
  overflow: visible;
  padding: 8px;
}

div#notebook {
  overflow: visible;
  border-top: none;
}@media print {
  div.cell {
    display: block;
    page-break-inside: avoid;
  } 
  div.output_wrapper { 
    display: block;
    page-break-inside: avoid; 
  }
  div.output { 
    display: block;
    page-break-inside: avoid; 
  }
}
</style>

<!-- Custom stylesheet, it must be in the same directory as the html file -->
<link rel="stylesheet" href="custom.css">

<!-- Loading mathjax macro -->
<!-- Load mathjax -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/latest.js?config=TeX-AMS_HTML"></script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [ ['$','$'], ["\\(","\\)"] ],
            displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
            processEscapes: true,
            processEnvironments: true
        },
        // Center justify equations in code and markdown cells. Elsewhere
        // we use CSS to left justify single line equations in code cells.
        displayAlign: 'center',
        "HTML-CSS": {
            styles: {'.MathJax_Display': {"margin": 0}},
            linebreaks: { automatic: true }
        }
    });
    </script>
    <!-- End of mathjax configuration --></head>
<body>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">

<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[1]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">google.colab</span> <span class="k">import</span> <span class="n">drive</span>
<span class="n">drive</span><span class="o">.</span><span class="n">mount</span><span class="p">(</span><span class="s1">&#39;/content/drive&#39;</span><span class="p">)</span> 
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Mounted at /content/drive
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="o">!</span>unzip <span class="s1">&#39;/content/drive/My Drive/facerec75.zip&#39;</span> -d <span class="s1">&#39;/content/sample_data/&#39;</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[59]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">os</span>
<span class="o">%</span><span class="k">matplotlib</span> inline
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">seaborn</span> <span class="k">as</span> <span class="nn">sns</span>
<span class="kn">from</span> <span class="nn">PIL</span> <span class="k">import</span> <span class="n">Image</span>
<span class="kn">from</span> <span class="nn">sklearn</span> <span class="k">import</span> <span class="n">metrics</span>
<span class="kn">from</span> <span class="nn">sklearn.preprocessing</span> <span class="k">import</span> <span class="n">StandardScaler</span><span class="p">,</span><span class="n">binarize</span>
<span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="k">import</span> <span class="n">train_test_split</span><span class="p">,</span> <span class="n">KFold</span><span class="p">,</span> <span class="n">cross_val_score</span><span class="p">,</span> <span class="n">GridSearchCV</span>
<span class="kn">from</span> <span class="nn">sklearn.metrics</span> <span class="k">import</span> <span class="n">accuracy_score</span><span class="p">,</span><span class="n">confusion_matrix</span><span class="p">,</span><span class="n">roc_curve</span><span class="p">,</span><span class="n">roc_auc_score</span>
<span class="kn">from</span> <span class="nn">imblearn.over_sampling</span> <span class="k">import</span> <span class="n">SMOTE</span>
 


<span class="kn">import</span> <span class="nn">tensorflow</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras.applications</span> <span class="k">import</span> <span class="n">VGG16</span><span class="p">,</span><span class="n">MobileNetV2</span><span class="p">,</span><span class="n">ResNet50V2</span><span class="p">,</span><span class="n">InceptionResNetV2</span><span class="p">,</span><span class="n">InceptionV3</span><span class="p">,</span><span class="n">NASNetLarge</span><span class="p">,</span><span class="n">NASNetMobile</span><span class="p">,</span><span class="n">VGG19</span><span class="p">,</span><span class="n">Xception</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras.optimizers</span> <span class="k">import</span> <span class="n">Adam</span><span class="p">,</span> <span class="n">RMSprop</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras.preprocessing.image</span> <span class="k">import</span> <span class="n">ImageDataGenerator</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras</span> <span class="k">import</span> <span class="n">optimizers</span><span class="p">,</span><span class="n">Sequential</span><span class="p">,</span><span class="n">Model</span><span class="p">,</span><span class="n">layers</span><span class="p">,</span><span class="n">models</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras.layers</span> <span class="k">import</span> <span class="n">Conv2D</span><span class="p">,</span><span class="n">MaxPool2D</span><span class="p">,</span><span class="n">BatchNormalization</span><span class="p">,</span><span class="n">Dropout</span><span class="p">,</span><span class="n">Activation</span><span class="p">,</span><span class="n">Flatten</span><span class="p">,</span><span class="n">Dense</span><span class="p">,</span><span class="n">MaxPooling2D</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras.callbacks</span> <span class="k">import</span> <span class="n">EarlyStopping</span><span class="p">,</span> <span class="n">ReduceLROnPlateau</span>

<span class="kn">from</span> <span class="nn">IPython.core.interactiveshell</span> <span class="k">import</span> <span class="n">InteractiveShell</span>
<span class="n">InteractiveShell</span><span class="o">.</span><span class="n">ast_node_interactivity</span> <span class="o">=</span> <span class="s2">&quot;all&quot;</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[61]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">anger_train</span> <span class="o">=</span> <span class="s1">&#39;/content/sample_data/facerec75/train/Angry&#39;</span>
<span class="n">disgust_train</span> <span class="o">=</span><span class="s1">&#39;/content/sample_data/facerec75/train/Disgust&#39;</span>
<span class="n">fear_train</span><span class="o">=</span><span class="s1">&#39;/content/sample_data/facerec75/train/Fear&#39;</span>
<span class="n">happy_train</span><span class="o">=</span><span class="s1">&#39;/content/sample_data/facerec75/train/Happy&#39;</span>
<span class="n">neutral_train</span><span class="o">=</span><span class="s1">&#39;/content/sample_data/facerec75/train/Neutral&#39;</span>
<span class="n">sad_train</span><span class="o">=</span><span class="s1">&#39;/content/sample_data/facerec75/train/Sad&#39;</span>
<span class="n">surprise_train</span><span class="o">=</span><span class="s1">&#39;/content/sample_data/facerec75/train/Surprise&#39;</span>


<span class="c1">#loading val path</span>
<span class="n">anger_val</span> <span class="o">=</span> <span class="s1">&#39;/content/sample_data/facerec75/validation/Angry&#39;</span>
<span class="n">disgust_val</span> <span class="o">=</span><span class="s1">&#39;/content/sample_data/facerec75/validation/Disgust&#39;</span>
<span class="n">fear_val</span><span class="o">=</span><span class="s1">&#39;/content/sample_data/facerec75/validation/Fear&#39;</span>
<span class="n">happy_val</span><span class="o">=</span><span class="s1">&#39;/content/sample_data/facerec75/validation/Happy&#39;</span>
<span class="n">neutral_val</span><span class="o">=</span><span class="s1">&#39;/content/sample_data/facerec75/validation/Neutral&#39;</span>
<span class="n">sad_val</span><span class="o">=</span><span class="s1">&#39;/content/sample_data/facerec75/validation/Sad&#39;</span>
<span class="n">surprise_val</span><span class="o">=</span><span class="s1">&#39;/content/sample_data/facerec75/validation/Surprise&#39;</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[62]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">read</span> <span class="o">=</span> <span class="k">lambda</span> <span class="n">imname</span><span class="p">:</span> <span class="n">np</span><span class="o">.</span><span class="n">asarray</span><span class="p">(</span><span class="n">Image</span><span class="o">.</span><span class="n">open</span><span class="p">(</span><span class="n">imname</span><span class="p">)</span><span class="o">.</span><span class="n">convert</span><span class="p">(</span><span class="s2">&quot;RGB&quot;</span><span class="p">))</span>

<span class="n">anger</span> <span class="o">=</span> <span class="p">[</span><span class="n">read</span><span class="p">(</span><span class="n">os</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">join</span><span class="p">(</span><span class="n">anger_train</span><span class="p">,</span> <span class="n">filename</span><span class="p">))</span> <span class="k">for</span> <span class="n">filename</span> <span class="ow">in</span> <span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="n">anger_train</span><span class="p">)]</span>
<span class="n">x_anger</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">(</span><span class="n">anger</span><span class="p">,</span> <span class="n">dtype</span><span class="o">=</span><span class="s1">&#39;float&#39;</span><span class="p">)</span>

<span class="n">disg</span> <span class="o">=</span> <span class="p">[</span><span class="n">read</span><span class="p">(</span><span class="n">os</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">join</span><span class="p">(</span><span class="n">disgust_train</span><span class="p">,</span> <span class="n">filename</span><span class="p">))</span> <span class="k">for</span> <span class="n">filename</span> <span class="ow">in</span> <span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="n">disgust_train</span><span class="p">)]</span>
<span class="n">x_disgust</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">(</span><span class="n">disg</span><span class="p">,</span> <span class="n">dtype</span><span class="o">=</span><span class="s1">&#39;float&#39;</span><span class="p">)</span>

<span class="n">fear</span> <span class="o">=</span> <span class="p">[</span><span class="n">read</span><span class="p">(</span><span class="n">os</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">join</span><span class="p">(</span><span class="n">fear_train</span><span class="p">,</span> <span class="n">filename</span><span class="p">))</span> <span class="k">for</span> <span class="n">filename</span> <span class="ow">in</span> <span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="n">fear_train</span><span class="p">)]</span>
<span class="n">x_fear</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">(</span><span class="n">fear</span><span class="p">,</span> <span class="n">dtype</span><span class="o">=</span><span class="s1">&#39;float&#39;</span><span class="p">)</span>

<span class="n">happy</span> <span class="o">=</span> <span class="p">[</span><span class="n">read</span><span class="p">(</span><span class="n">os</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">join</span><span class="p">(</span><span class="n">happy_train</span><span class="p">,</span> <span class="n">filename</span><span class="p">))</span> <span class="k">for</span> <span class="n">filename</span> <span class="ow">in</span> <span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="n">happy_train</span><span class="p">)]</span>
<span class="n">x_happy</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">(</span><span class="n">happy</span><span class="p">,</span> <span class="n">dtype</span><span class="o">=</span><span class="s1">&#39;float&#39;</span><span class="p">)</span>

<span class="n">neutral</span> <span class="o">=</span> <span class="p">[</span><span class="n">read</span><span class="p">(</span><span class="n">os</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">join</span><span class="p">(</span><span class="n">neutral_train</span><span class="p">,</span> <span class="n">filename</span><span class="p">))</span> <span class="k">for</span> <span class="n">filename</span> <span class="ow">in</span> <span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="n">neutral_train</span><span class="p">)]</span>
<span class="n">x_neutral</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">(</span><span class="n">neutral</span><span class="p">,</span> <span class="n">dtype</span><span class="o">=</span><span class="s1">&#39;float&#39;</span><span class="p">)</span>

<span class="n">sad</span> <span class="o">=</span> <span class="p">[</span><span class="n">read</span><span class="p">(</span><span class="n">os</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">join</span><span class="p">(</span><span class="n">sad_train</span><span class="p">,</span> <span class="n">filename</span><span class="p">))</span> <span class="k">for</span> <span class="n">filename</span> <span class="ow">in</span> <span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="n">sad_train</span><span class="p">)]</span>
<span class="n">x_sad</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">(</span><span class="n">sad</span><span class="p">,</span> <span class="n">dtype</span><span class="o">=</span><span class="s1">&#39;float&#39;</span><span class="p">)</span>

<span class="n">surp</span> <span class="o">=</span> <span class="p">[</span><span class="n">read</span><span class="p">(</span><span class="n">os</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">join</span><span class="p">(</span><span class="n">surprise_train</span><span class="p">,</span> <span class="n">filename</span><span class="p">))</span> <span class="k">for</span> <span class="n">filename</span> <span class="ow">in</span> <span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="n">surprise_train</span><span class="p">)]</span>
<span class="n">x_surp</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">(</span><span class="n">surp</span><span class="p">,</span> <span class="n">dtype</span><span class="o">=</span><span class="s1">&#39;float&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[63]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">anger</span> <span class="o">=</span> <span class="p">[</span><span class="n">read</span><span class="p">(</span><span class="n">os</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">join</span><span class="p">(</span><span class="n">anger_val</span><span class="p">,</span> <span class="n">filename</span><span class="p">))</span> <span class="k">for</span> <span class="n">filename</span> <span class="ow">in</span> <span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="n">anger_val</span><span class="p">)]</span>
<span class="n">x_anger_val</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">(</span><span class="n">anger</span><span class="p">,</span> <span class="n">dtype</span><span class="o">=</span><span class="s1">&#39;float&#39;</span><span class="p">)</span>


<span class="n">disg</span> <span class="o">=</span> <span class="p">[</span><span class="n">read</span><span class="p">(</span><span class="n">os</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">join</span><span class="p">(</span><span class="n">disgust_val</span><span class="p">,</span> <span class="n">filename</span><span class="p">))</span> <span class="k">for</span> <span class="n">filename</span> <span class="ow">in</span> <span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="n">disgust_val</span><span class="p">)]</span>
<span class="n">x_disgust_val</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">(</span><span class="n">disg</span><span class="p">,</span> <span class="n">dtype</span><span class="o">=</span><span class="s1">&#39;float&#39;</span><span class="p">)</span>

<span class="n">fear</span> <span class="o">=</span> <span class="p">[</span><span class="n">read</span><span class="p">(</span><span class="n">os</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">join</span><span class="p">(</span><span class="n">fear_val</span><span class="p">,</span> <span class="n">filename</span><span class="p">))</span> <span class="k">for</span> <span class="n">filename</span> <span class="ow">in</span> <span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="n">fear_val</span><span class="p">)]</span>
<span class="n">x_fear_val</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">(</span><span class="n">fear</span><span class="p">,</span> <span class="n">dtype</span><span class="o">=</span><span class="s1">&#39;float&#39;</span><span class="p">)</span>

<span class="n">happy</span> <span class="o">=</span> <span class="p">[</span><span class="n">read</span><span class="p">(</span><span class="n">os</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">join</span><span class="p">(</span><span class="n">happy_val</span><span class="p">,</span> <span class="n">filename</span><span class="p">))</span> <span class="k">for</span> <span class="n">filename</span> <span class="ow">in</span> <span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="n">happy_val</span><span class="p">)]</span>
<span class="n">x_happy_val</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">(</span><span class="n">happy</span><span class="p">,</span> <span class="n">dtype</span><span class="o">=</span><span class="s1">&#39;float&#39;</span><span class="p">)</span>

<span class="n">neutral</span> <span class="o">=</span> <span class="p">[</span><span class="n">read</span><span class="p">(</span><span class="n">os</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">join</span><span class="p">(</span><span class="n">neutral_val</span><span class="p">,</span> <span class="n">filename</span><span class="p">))</span> <span class="k">for</span> <span class="n">filename</span> <span class="ow">in</span> <span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="n">neutral_val</span><span class="p">)]</span>
<span class="n">x_neutral_val</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">(</span><span class="n">neutral</span><span class="p">,</span> <span class="n">dtype</span><span class="o">=</span><span class="s1">&#39;float&#39;</span><span class="p">)</span>

<span class="n">sad</span> <span class="o">=</span> <span class="p">[</span><span class="n">read</span><span class="p">(</span><span class="n">os</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">join</span><span class="p">(</span><span class="n">sad_val</span><span class="p">,</span> <span class="n">filename</span><span class="p">))</span> <span class="k">for</span> <span class="n">filename</span> <span class="ow">in</span> <span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="n">sad_val</span><span class="p">)]</span>
<span class="n">x_sad_val</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">(</span><span class="n">sad</span><span class="p">,</span> <span class="n">dtype</span><span class="o">=</span><span class="s1">&#39;float&#39;</span><span class="p">)</span>

<span class="n">surp</span> <span class="o">=</span> <span class="p">[</span><span class="n">read</span><span class="p">(</span><span class="n">os</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">join</span><span class="p">(</span><span class="n">surprise_val</span><span class="p">,</span> <span class="n">filename</span><span class="p">))</span> <span class="k">for</span> <span class="n">filename</span> <span class="ow">in</span> <span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="n">surprise_val</span><span class="p">)]</span>
<span class="n">x_surp_val</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">(</span><span class="n">surp</span><span class="p">,</span> <span class="n">dtype</span><span class="o">=</span><span class="s1">&#39;float&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[64]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">y_ang</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">zeros</span><span class="p">(</span><span class="n">x_anger</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span>
<span class="n">y_disg</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">ones</span><span class="p">(</span><span class="n">x_disgust</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span>
<span class="n">y_fear</span><span class="o">=</span><span class="n">np</span><span class="o">.</span><span class="n">ones</span><span class="p">(</span><span class="n">x_fear</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span><span class="o">*</span><span class="mi">2</span>
<span class="n">y_happy</span><span class="o">=</span><span class="n">np</span><span class="o">.</span><span class="n">ones</span><span class="p">(</span><span class="n">x_happy</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span><span class="o">*</span><span class="mi">3</span>
<span class="n">y_neu</span><span class="o">=</span><span class="n">np</span><span class="o">.</span><span class="n">ones</span><span class="p">(</span><span class="n">x_neutral</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span><span class="o">*</span><span class="mi">4</span>
<span class="n">y_sad</span><span class="o">=</span><span class="n">np</span><span class="o">.</span><span class="n">ones</span><span class="p">(</span><span class="n">x_sad</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span><span class="o">*</span><span class="mi">5</span>
<span class="n">y_surp</span><span class="o">=</span><span class="n">np</span><span class="o">.</span><span class="n">ones</span><span class="p">(</span><span class="n">x_surp</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span><span class="o">*</span><span class="mi">6</span>

<span class="n">y_ang_val</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">zeros</span><span class="p">(</span><span class="n">x_anger_val</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span>
<span class="n">y_disg_val</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">ones</span><span class="p">(</span><span class="n">x_disgust_val</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span>
<span class="n">y_fear_val</span> <span class="o">=</span><span class="n">np</span><span class="o">.</span><span class="n">ones</span><span class="p">(</span><span class="n">x_fear_val</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span><span class="o">*</span><span class="mi">2</span>
<span class="n">y_happy_val</span> <span class="o">=</span><span class="n">np</span><span class="o">.</span><span class="n">ones</span><span class="p">(</span><span class="n">x_happy_val</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span><span class="o">*</span><span class="mi">3</span>
<span class="n">y_neu_val</span> <span class="o">=</span><span class="n">np</span><span class="o">.</span><span class="n">ones</span><span class="p">(</span><span class="n">x_neutral_val</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span><span class="o">*</span><span class="mi">4</span>
<span class="n">y_sad_val</span> <span class="o">=</span><span class="n">np</span><span class="o">.</span><span class="n">ones</span><span class="p">(</span><span class="n">x_sad_val</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span><span class="o">*</span><span class="mi">5</span>
<span class="n">y_surp_val</span><span class="o">=</span><span class="n">np</span><span class="o">.</span><span class="n">ones</span><span class="p">(</span><span class="n">x_surp_val</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span><span class="o">*</span><span class="mi">6</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[67]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">x_anger</span><span class="p">,</span><span class="n">x_disgust</span><span class="p">,</span><span class="n">x_fear</span><span class="p">,</span><span class="n">x_happy</span><span class="p">,</span><span class="n">x_neutral</span><span class="p">,</span><span class="n">x_sad</span><span class="p">,</span><span class="n">x_surp</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span>
<span class="n">y_ang</span><span class="p">,</span><span class="n">y_disg</span><span class="p">,</span><span class="n">y_fear</span><span class="p">,</span><span class="n">y_happy</span><span class="p">,</span><span class="n">y_neu</span><span class="p">,</span><span class="n">y_sad</span><span class="p">,</span><span class="n">y_surp</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span>
<span class="n">x_anger_val</span><span class="p">,</span><span class="n">x_disgust_val</span><span class="p">,</span><span class="n">x_fear_val</span><span class="p">,</span><span class="n">x_happy_val</span><span class="p">,</span><span class="n">x_neutral_val</span><span class="p">,</span><span class="n">x_sad_val</span><span class="p">,</span><span class="n">x_surp_val</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span>
<span class="n">y_ang_val</span><span class="p">,</span><span class="n">y_disg_val</span><span class="p">,</span><span class="n">y_fear_val</span><span class="p">,</span><span class="n">y_happy_val</span><span class="p">,</span><span class="n">y_neu_val</span><span class="p">,</span><span class="n">y_sad_val</span><span class="p">,</span><span class="n">y_surp_val</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[65]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">x_train</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">concatenate</span><span class="p">((</span><span class="n">x_anger</span><span class="p">,</span><span class="n">x_disgust</span><span class="p">,</span><span class="n">x_fear</span><span class="p">,</span><span class="n">x_happy</span><span class="p">,</span><span class="n">x_neutral</span><span class="p">,</span><span class="n">x_sad</span><span class="p">,</span><span class="n">x_surp</span><span class="p">),</span> <span class="n">axis</span> <span class="o">=</span> <span class="mi">0</span><span class="p">)</span>
<span class="n">y_train</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">concatenate</span><span class="p">((</span><span class="n">y_ang</span><span class="p">,</span><span class="n">y_disg</span><span class="p">,</span><span class="n">y_fear</span><span class="p">,</span><span class="n">y_happy</span><span class="p">,</span><span class="n">y_neu</span><span class="p">,</span><span class="n">y_sad</span><span class="p">,</span><span class="n">y_surp</span><span class="p">),</span> <span class="n">axis</span> <span class="o">=</span> <span class="mi">0</span><span class="p">)</span>

<span class="n">x_val</span><span class="o">=</span><span class="n">np</span><span class="o">.</span><span class="n">concatenate</span><span class="p">((</span><span class="n">x_anger_val</span><span class="p">,</span><span class="n">x_disgust_val</span><span class="p">,</span><span class="n">x_fear_val</span><span class="p">,</span><span class="n">x_happy_val</span><span class="p">,</span><span class="n">x_neutral_val</span><span class="p">,</span><span class="n">x_sad_val</span><span class="p">,</span><span class="n">x_surp_val</span><span class="p">),</span> <span class="n">axis</span> <span class="o">=</span> <span class="mi">0</span><span class="p">)</span>
<span class="n">y_val</span><span class="o">=</span><span class="n">np</span><span class="o">.</span><span class="n">concatenate</span><span class="p">((</span><span class="n">y_ang_val</span><span class="p">,</span><span class="n">y_disg_val</span><span class="p">,</span><span class="n">y_fear_val</span><span class="p">,</span><span class="n">y_happy_val</span><span class="p">,</span><span class="n">y_neu_val</span><span class="p">,</span><span class="n">y_sad_val</span><span class="p">,</span><span class="n">y_surp_val</span><span class="p">),</span> <span class="n">axis</span> <span class="o">=</span> <span class="mi">0</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span> 
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[68]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">s</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">arange</span><span class="p">(</span><span class="n">x_train</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span>
<span class="n">np</span><span class="o">.</span><span class="n">random</span><span class="o">.</span><span class="n">shuffle</span><span class="p">(</span><span class="n">s</span><span class="p">)</span>
<span class="n">x_train</span> <span class="o">=</span> <span class="n">x_train</span><span class="p">[</span><span class="n">s</span><span class="p">]</span>
<span class="n">y_train</span> <span class="o">=</span> <span class="n">y_train</span><span class="p">[</span><span class="n">s</span><span class="p">]</span><span class="c1">#shuffling train set</span>

<span class="n">s</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">arange</span><span class="p">(</span><span class="n">x_val</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span>
<span class="n">np</span><span class="o">.</span><span class="n">random</span><span class="o">.</span><span class="n">shuffle</span><span class="p">(</span><span class="n">s</span><span class="p">)</span>
<span class="n">x_val</span> <span class="o">=</span> <span class="n">x_val</span><span class="p">[</span><span class="n">s</span><span class="p">]</span>
<span class="n">y_val</span> <span class="o">=</span> <span class="n">y_val</span><span class="p">[</span><span class="n">s</span><span class="p">]</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[69]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">x_train</span><span class="o">=</span><span class="n">x_train</span><span class="o">/</span><span class="mf">255.</span>
<span class="n">x_val</span><span class="o">=</span><span class="n">x_val</span><span class="o">/</span><span class="mf">255.</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[70]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">classs</span><span class="o">=</span><span class="p">[</span><span class="s2">&quot;anger&quot;</span><span class="p">,</span><span class="s2">&quot;disgust&quot;</span><span class="p">,</span><span class="s2">&quot;fear&quot;</span><span class="p">,</span><span class="s2">&quot;happy&quot;</span><span class="p">,</span><span class="s2">&quot;neutral&quot;</span><span class="p">,</span><span class="s2">&quot;sad&quot;</span><span class="p">,</span><span class="s2">&quot;surprise&quot;</span><span class="p">]</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[71]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">fig</span><span class="o">=</span><span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">12</span><span class="p">,</span> <span class="mi">8</span><span class="p">))</span>
<span class="n">columns</span> <span class="o">=</span> <span class="mi">3</span>
<span class="n">rows</span> <span class="o">=</span> <span class="mi">2</span>
<span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span> <span class="n">columns</span><span class="o">*</span><span class="n">rows</span> <span class="o">+</span><span class="mi">1</span><span class="p">):</span>
    <span class="n">ax</span> <span class="o">=</span> <span class="n">fig</span><span class="o">.</span><span class="n">add_subplot</span><span class="p">(</span><span class="n">rows</span><span class="p">,</span> <span class="n">columns</span><span class="p">,</span> <span class="n">i</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">imshow</span><span class="p">(</span><span class="n">x_train</span><span class="p">[</span><span class="n">i</span><span class="p">],</span> <span class="n">interpolation</span><span class="o">=</span><span class="s1">&#39;nearest&#39;</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="n">classs</span><span class="p">[</span><span class="nb">int</span><span class="p">(</span><span class="n">y_train</span><span class="p">[</span><span class="n">i</span><span class="p">])])</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[71]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.image.AxesImage at 0x7fb67cf3df28&gt;</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[71]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>Text(0.5, 0, &#39;happy&#39;)</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[71]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.image.AxesImage at 0x7fb67441c518&gt;</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[71]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>Text(0.5, 0, &#39;anger&#39;)</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[71]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.image.AxesImage at 0x7fb685fe1a58&gt;</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[71]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>Text(0.5, 0, &#39;happy&#39;)</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[71]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.image.AxesImage at 0x7fb674522f98&gt;</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[71]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>Text(0.5, 0, &#39;disgust&#39;)</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[71]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.image.AxesImage at 0x7fb674431518&gt;</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[71]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>Text(0.5, 0, &#39;happy&#39;)</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[71]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.image.AxesImage at 0x7fb674591a58&gt;</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[71]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>Text(0.5, 0, &#39;sad&#39;)</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[72]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">Y_train</span> <span class="o">=</span> <span class="n">tensorflow</span><span class="o">.</span><span class="n">keras</span><span class="o">.</span><span class="n">utils</span><span class="o">.</span><span class="n">to_categorical</span><span class="p">(</span><span class="n">y_train</span><span class="p">,</span> <span class="mi">7</span><span class="p">)</span>
<span class="n">Y_val</span><span class="o">=</span> <span class="n">tensorflow</span><span class="o">.</span><span class="n">keras</span><span class="o">.</span><span class="n">utils</span><span class="o">.</span><span class="n">to_categorical</span><span class="p">(</span><span class="n">y_val</span><span class="p">,</span> <span class="mi">7</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[73]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">METRICS</span> <span class="o">=</span> <span class="p">[</span>
     <span class="n">tensorflow</span><span class="o">.</span> <span class="n">keras</span><span class="o">.</span><span class="n">metrics</span><span class="o">.</span><span class="n">TruePositives</span><span class="p">(</span><span class="n">name</span><span class="o">=</span><span class="s1">&#39;tp&#39;</span><span class="p">),</span>
     <span class="n">tensorflow</span><span class="o">.</span> <span class="n">keras</span><span class="o">.</span><span class="n">metrics</span><span class="o">.</span><span class="n">FalsePositives</span><span class="p">(</span><span class="n">name</span><span class="o">=</span><span class="s1">&#39;fp&#39;</span><span class="p">),</span>
     <span class="n">tensorflow</span><span class="o">.</span> <span class="n">keras</span><span class="o">.</span><span class="n">metrics</span><span class="o">.</span><span class="n">TrueNegatives</span><span class="p">(</span><span class="n">name</span><span class="o">=</span><span class="s1">&#39;tn&#39;</span><span class="p">),</span>
      <span class="n">tensorflow</span><span class="o">.</span><span class="n">keras</span><span class="o">.</span><span class="n">metrics</span><span class="o">.</span><span class="n">FalseNegatives</span><span class="p">(</span><span class="n">name</span><span class="o">=</span><span class="s1">&#39;fn&#39;</span><span class="p">),</span> 
     <span class="n">tensorflow</span><span class="o">.</span> <span class="n">keras</span><span class="o">.</span><span class="n">metrics</span><span class="o">.</span><span class="n">BinaryAccuracy</span><span class="p">(</span><span class="n">name</span><span class="o">=</span><span class="s1">&#39;accuracy&#39;</span><span class="p">),</span>
     <span class="n">tensorflow</span><span class="o">.</span> <span class="n">keras</span><span class="o">.</span><span class="n">metrics</span><span class="o">.</span><span class="n">Precision</span><span class="p">(</span><span class="n">name</span><span class="o">=</span><span class="s1">&#39;precision&#39;</span><span class="p">),</span>
     <span class="n">tensorflow</span><span class="o">.</span> <span class="n">keras</span><span class="o">.</span><span class="n">metrics</span><span class="o">.</span><span class="n">Recall</span><span class="p">(</span><span class="n">name</span><span class="o">=</span><span class="s1">&#39;recall&#39;</span><span class="p">),</span>
     <span class="n">tensorflow</span><span class="o">.</span> <span class="n">keras</span><span class="o">.</span><span class="n">metrics</span><span class="o">.</span><span class="n">AUC</span><span class="p">(</span><span class="n">name</span><span class="o">=</span><span class="s1">&#39;auc&#39;</span><span class="p">),</span>
<span class="p">]</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[74]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">pre_trained_model</span> <span class="o">=</span><span class="n">InceptionResNetV2</span><span class="p">(</span><span class="n">weights</span><span class="o">=</span><span class="s2">&quot;imagenet&quot;</span><span class="p">,</span>
                  <span class="n">include_top</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span>
                  <span class="n">input_shape</span><span class="o">=</span><span class="p">(</span><span class="mi">75</span><span class="p">,</span> <span class="mi">75</span><span class="p">,</span> <span class="mi">3</span><span class="p">))</span>

<span class="k">for</span> <span class="n">layer</span> <span class="ow">in</span> <span class="n">pre_trained_model</span><span class="o">.</span><span class="n">layers</span><span class="p">:</span>
  <span class="n">layer</span><span class="o">.</span><span class="n">trainable</span> <span class="o">=</span> <span class="kc">True</span>


<span class="n">model</span> <span class="o">=</span> <span class="n">tensorflow</span><span class="o">.</span><span class="n">keras</span><span class="o">.</span><span class="n">Sequential</span><span class="p">([</span>
        <span class="n">pre_trained_model</span><span class="p">,</span>
        <span class="n">tensorflow</span><span class="o">.</span><span class="n">keras</span><span class="o">.</span><span class="n">layers</span><span class="o">.</span><span class="n">Flatten</span><span class="p">(),</span>
        <span class="n">tensorflow</span><span class="o">.</span><span class="n">keras</span><span class="o">.</span><span class="n">layers</span><span class="o">.</span><span class="n">Dropout</span><span class="p">(</span><span class="mf">0.25</span><span class="p">),</span>

        <span class="n">tensorflow</span><span class="o">.</span><span class="n">keras</span><span class="o">.</span><span class="n">layers</span><span class="o">.</span><span class="n">Dense</span><span class="p">(</span><span class="mi">256</span><span class="p">,</span><span class="n">activation</span><span class="o">=</span><span class="s1">&#39;relu&#39;</span><span class="p">),</span>
        <span class="n">tensorflow</span><span class="o">.</span><span class="n">keras</span><span class="o">.</span><span class="n">layers</span><span class="o">.</span><span class="n">Dropout</span><span class="p">(</span><span class="mf">0.25</span><span class="p">),</span>

        <span class="n">tensorflow</span><span class="o">.</span><span class="n">keras</span><span class="o">.</span><span class="n">layers</span><span class="o">.</span><span class="n">Dense</span><span class="p">(</span><span class="mi">256</span><span class="p">,</span><span class="n">activation</span><span class="o">=</span><span class="s1">&#39;relu&#39;</span><span class="p">),</span>
        <span class="n">tensorflow</span><span class="o">.</span><span class="n">keras</span><span class="o">.</span><span class="n">layers</span><span class="o">.</span><span class="n">Dropout</span><span class="p">(</span><span class="mf">0.25</span><span class="p">),</span>

        <span class="n">tensorflow</span><span class="o">.</span><span class="n">keras</span><span class="o">.</span><span class="n">layers</span><span class="o">.</span><span class="n">Dense</span><span class="p">(</span><span class="mi">100</span><span class="p">,</span><span class="n">activation</span><span class="o">=</span><span class="s1">&#39;relu&#39;</span><span class="p">),</span>
        <span class="n">tensorflow</span><span class="o">.</span><span class="n">keras</span><span class="o">.</span><span class="n">layers</span><span class="o">.</span><span class="n">Dropout</span><span class="p">(</span><span class="mf">0.25</span><span class="p">),</span>
 
        <span class="n">tensorflow</span><span class="o">.</span><span class="n">keras</span><span class="o">.</span><span class="n">layers</span><span class="o">.</span><span class="n">Dense</span><span class="p">(</span><span class="mi">7</span><span class="p">,</span><span class="n">activation</span><span class="o">=</span><span class="s1">&#39;softmax&#39;</span><span class="p">)</span>

<span class="p">])</span>
<span class="n">optim</span><span class="o">=</span><span class="n">optimizers</span><span class="o">.</span><span class="n">SGD</span><span class="p">(</span><span class="n">lr</span><span class="o">=</span><span class="mf">0.001</span><span class="p">,</span> <span class="n">decay</span><span class="o">=</span><span class="mi">1</span><span class="n">e</span><span class="o">-</span><span class="mi">6</span><span class="p">,</span> <span class="n">momentum</span><span class="o">=</span><span class="mf">0.9</span><span class="p">,</span> <span class="n">nesterov</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">model</span><span class="o">.</span><span class="n">compile</span><span class="p">(</span><span class="n">optimizer</span> <span class="o">=</span><span class="s1">&#39;sgd&#39;</span><span class="p">,</span> <span class="n">loss</span> <span class="o">=</span> <span class="s1">&#39;categorical_crossentropy&#39;</span><span class="p">,</span> <span class="n">metrics</span> <span class="o">=</span> <span class="n">METRICS</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Downloading data from https://storage.googleapis.com/tensorflow/keras-applications/inception_resnet_v2/inception_resnet_v2_weights_tf_dim_ordering_tf_kernels_notop.h5
219062272/219055592 [==============================] - 2s 0us/step
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">history</span><span class="o">=</span><span class="n">model</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span>
        <span class="n">x_train</span><span class="p">,</span><span class="n">Y_train</span><span class="p">,</span>
        <span class="n">epochs</span><span class="o">=</span><span class="mi">25</span><span class="p">,</span>
        <span class="n">validation_data</span><span class="o">=</span><span class="p">(</span><span class="n">x_val</span><span class="p">,</span><span class="n">Y_val</span><span class="p">),</span><span class="n">batch_size</span><span class="o">=</span><span class="mi">32</span><span class="p">,</span><span class="n">validation_batch_size</span><span class="o">=</span><span class="mi">16</span><span class="p">,</span><span class="n">shuffle</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Epoch 1/25
875/875 [==============================] - 121s 113ms/step - loss: 1.7410 - tp: 1895.6336 - fp: 756.7409 - tn: 83434.7660 - fn: 12136.2842 - accuracy: 0.8649 - precision: 0.6120 - recall: 0.1004 - auc: 0.6897 - val_loss: 1.7079 - val_tp: 1008.0000 - val_fp: 450.0000 - val_tn: 22512.0000 - val_fn: 2819.0000 - val_accuracy: 0.8780 - val_precision: 0.6914 - val_recall: 0.2634 - val_auc: 0.8055
Epoch 2/25
875/875 [==============================] - 95s 109ms/step - loss: 1.1855 - tp: 4969.6153 - fp: 1279.9623 - tn: 82911.5445 - fn: 9062.3025 - accuracy: 0.8944 - precision: 0.7982 - recall: 0.3488 - auc: 0.8783 - val_loss: 1.4676 - val_tp: 1254.0000 - val_fp: 493.0000 - val_tn: 22469.0000 - val_fn: 2573.0000 - val_accuracy: 0.8856 - val_precision: 0.7178 - val_recall: 0.3277 - val_auc: 0.8356
Epoch 3/25
875/875 [==============================] - 96s 109ms/step - loss: 0.9924 - tp: 6309.2568 - fp: 1535.6495 - tn: 82655.8573 - fn: 7722.6610 - accuracy: 0.9062 - precision: 0.8107 - recall: 0.4481 - auc: 0.9166 - val_loss: 1.4711 - val_tp: 1510.0000 - val_fp: 752.0000 - val_tn: 22210.0000 - val_fn: 2317.0000 - val_accuracy: 0.8854 - val_precision: 0.6676 - val_recall: 0.3946 - val_auc: 0.8449
Epoch 4/25
875/875 [==============================] - 95s 109ms/step - loss: 0.8669 - tp: 7495.5502 - fp: 1704.3276 - tn: 82487.1792 - fn: 6536.3676 - accuracy: 0.9162 - precision: 0.8177 - recall: 0.5321 - auc: 0.9370 - val_loss: 1.5021 - val_tp: 1591.0000 - val_fp: 833.0000 - val_tn: 22129.0000 - val_fn: 2236.0000 - val_accuracy: 0.8854 - val_precision: 0.6564 - val_recall: 0.4157 - val_auc: 0.8483
Epoch 5/25
875/875 [==============================] - 95s 109ms/step - loss: 0.7451 - tp: 8532.4760 - fp: 1702.4372 - tn: 82489.0696 - fn: 5499.4418 - accuracy: 0.9263 - precision: 0.8361 - recall: 0.6026 - auc: 0.9534 - val_loss: 1.6924 - val_tp: 1780.0000 - val_fp: 1108.0000 - val_tn: 21854.0000 - val_fn: 2047.0000 - val_accuracy: 0.8822 - val_precision: 0.6163 - val_recall: 0.4651 - val_auc: 0.8450
Epoch 6/25
875/875 [==============================] - 95s 109ms/step - loss: 0.6261 - tp: 9546.1404 - fp: 1712.7158 - tn: 82478.7911 - fn: 4485.7774 - accuracy: 0.9376 - precision: 0.8528 - recall: 0.6805 - auc: 0.9670 - val_loss: 1.8821 - val_tp: 1775.0000 - val_fp: 1239.0000 - val_tn: 21723.0000 - val_fn: 2052.0000 - val_accuracy: 0.8772 - val_precision: 0.5889 - val_recall: 0.4638 - val_auc: 0.8297
Epoch 7/25
875/875 [==============================] - 95s 109ms/step - loss: 0.5299 - tp: 10440.3539 - fp: 1603.5753 - tn: 82587.9315 - fn: 3591.5639 - accuracy: 0.9478 - precision: 0.8706 - recall: 0.7458 - auc: 0.9758 - val_loss: 1.9107 - val_tp: 1920.0000 - val_fp: 1228.0000 - val_tn: 21734.0000 - val_fn: 1907.0000 - val_accuracy: 0.8830 - val_precision: 0.6099 - val_recall: 0.5017 - val_auc: 0.8406
Epoch 8/25
875/875 [==============================] - 95s 109ms/step - loss: 0.4287 - tp: 11263.4372 - fp: 1408.4178 - tn: 82783.0890 - fn: 2768.4806 - accuracy: 0.9586 - precision: 0.8944 - recall: 0.8056 - auc: 0.9836 - val_loss: 2.1963 - val_tp: 1962.0000 - val_fp: 1414.0000 - val_tn: 21548.0000 - val_fn: 1865.0000 - val_accuracy: 0.8776 - val_precision: 0.5812 - val_recall: 0.5127 - val_auc: 0.8327
Epoch 9/25
875/875 [==============================] - 95s 109ms/step - loss: 0.3514 - tp: 11837.1610 - fp: 1232.6130 - tn: 82958.8938 - fn: 2194.7568 - accuracy: 0.9658 - precision: 0.9092 - recall: 0.8452 - auc: 0.9887 - val_loss: 2.1357 - val_tp: 1985.0000 - val_fp: 1456.0000 - val_tn: 21506.0000 - val_fn: 1842.0000 - val_accuracy: 0.8769 - val_precision: 0.5769 - val_recall: 0.5187 - val_auc: 0.8287
Epoch 10/25
875/875 [==============================] - 95s 109ms/step - loss: 0.2794 - tp: 12375.6084 - fp: 1032.7603 - tn: 83158.7466 - fn: 1656.3094 - accuracy: 0.9735 - precision: 0.9262 - recall: 0.8853 - auc: 0.9923 - val_loss: 2.5215 - val_tp: 2049.0000 - val_fp: 1493.0000 - val_tn: 21469.0000 - val_fn: 1778.0000 - val_accuracy: 0.8779 - val_precision: 0.5785 - val_recall: 0.5354 - val_auc: 0.8181
Epoch 11/25
875/875 [==============================] - 95s 109ms/step - loss: 0.2365 - tp: 12680.8573 - fp: 876.7763 - tn: 83314.7306 - fn: 1351.0605 - accuracy: 0.9776 - precision: 0.9365 - recall: 0.9045 - auc: 0.9941 - val_loss: 2.4939 - val_tp: 2048.0000 - val_fp: 1510.0000 - val_tn: 21452.0000 - val_fn: 1779.0000 - val_accuracy: 0.8772 - val_precision: 0.5756 - val_recall: 0.5351 - val_auc: 0.8232
Epoch 12/25
875/875 [==============================] - 95s 109ms/step - loss: 0.1946 - tp: 12956.3071 - fp: 753.0765 - tn: 83438.4304 - fn: 1075.6107 - accuracy: 0.9817 - precision: 0.9463 - recall: 0.9246 - auc: 0.9957 - val_loss: 2.8293 - val_tp: 1982.0000 - val_fp: 1632.0000 - val_tn: 21330.0000 - val_fn: 1845.0000 - val_accuracy: 0.8702 - val_precision: 0.5484 - val_recall: 0.5179 - val_auc: 0.8042
Epoch 13/25
875/875 [==============================] - 95s 109ms/step - loss: 0.1790 - tp: 13045.1587 - fp: 704.5263 - tn: 83486.9806 - fn: 986.7591 - accuracy: 0.9831 - precision: 0.9496 - recall: 0.9310 - auc: 0.9961 - val_loss: 2.6760 - val_tp: 2074.0000 - val_fp: 1520.0000 - val_tn: 21442.0000 - val_fn: 1753.0000 - val_accuracy: 0.8778 - val_precision: 0.5771 - val_recall: 0.5419 - val_auc: 0.8155
Epoch 14/25
875/875 [==============================] - 95s 109ms/step - loss: 0.1484 - tp: 13240.7397 - fp: 576.6998 - tn: 83614.8071 - fn: 791.1781 - accuracy: 0.9863 - precision: 0.9595 - recall: 0.9442 - auc: 0.9971 - val_loss: 2.9509 - val_tp: 2045.0000 - val_fp: 1609.0000 - val_tn: 21353.0000 - val_fn: 1782.0000 - val_accuracy: 0.8734 - val_precision: 0.5597 - val_recall: 0.5344 - val_auc: 0.8037
Epoch 15/25
875/875 [==============================] - 95s 109ms/step - loss: 0.1244 - tp: 13389.7991 - fp: 492.3790 - tn: 83699.1279 - fn: 642.1187 - accuracy: 0.9891 - precision: 0.9667 - recall: 0.9564 - auc: 0.9974 - val_loss: 2.9112 - val_tp: 2102.0000 - val_fp: 1567.0000 - val_tn: 21395.0000 - val_fn: 1725.0000 - val_accuracy: 0.8771 - val_precision: 0.5729 - val_recall: 0.5493 - val_auc: 0.8128
Epoch 16/25
875/875 [==============================] - 95s 109ms/step - loss: 0.1210 - tp: 13397.2774 - fp: 484.2260 - tn: 83707.2808 - fn: 634.6404 - accuracy: 0.9890 - precision: 0.9661 - recall: 0.9563 - auc: 0.9977 - val_loss: 3.0583 - val_tp: 2113.0000 - val_fp: 1564.0000 - val_tn: 21398.0000 - val_fn: 1714.0000 - val_accuracy: 0.8776 - val_precision: 0.5747 - val_recall: 0.5521 - val_auc: 0.8128
Epoch 17/25
875/875 [==============================] - 95s 109ms/step - loss: 0.0926 - tp: 13571.8619 - fp: 361.5331 - tn: 83829.9737 - fn: 460.0559 - accuracy: 0.9917 - precision: 0.9739 - recall: 0.9675 - auc: 0.9985 - val_loss: 3.4470 - val_tp: 2104.0000 - val_fp: 1586.0000 - val_tn: 21376.0000 - val_fn: 1723.0000 - val_accuracy: 0.8765 - val_precision: 0.5702 - val_recall: 0.5498 - val_auc: 0.8023
Epoch 18/25
875/875 [==============================] - 95s 109ms/step - loss: 0.0906 - tp: 13591.7888 - fp: 369.1187 - tn: 83822.3881 - fn: 440.1290 - accuracy: 0.9922 - precision: 0.9746 - recall: 0.9703 - auc: 0.9983 - val_loss: 3.3513 - val_tp: 2101.0000 - val_fp: 1591.0000 - val_tn: 21371.0000 - val_fn: 1726.0000 - val_accuracy: 0.8762 - val_precision: 0.5691 - val_recall: 0.5490 - val_auc: 0.8011
Epoch 19/25
875/875 [==============================] - 95s 109ms/step - loss: 0.0804 - tp: 13620.3550 - fp: 324.3265 - tn: 83867.1804 - fn: 411.5628 - accuracy: 0.9929 - precision: 0.9781 - recall: 0.9723 - auc: 0.9986 - val_loss: 3.3337 - val_tp: 2112.0000 - val_fp: 1584.0000 - val_tn: 21378.0000 - val_fn: 1715.0000 - val_accuracy: 0.8769 - val_precision: 0.5714 - val_recall: 0.5519 - val_auc: 0.8010
Epoch 20/25
829/875 [===========================&gt;..] - ETA: 4s - loss: 0.0665 - tp: 12969.6393 - fp: 251.4668 - tn: 79428.5332 - fn: 310.3607 - accuracy: 0.9943 - precision: 0.9819 - recall: 0.9778 - auc: 0.9988</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">saved1_keras_model_filepath</span> <span class="o">=</span> <span class="s1">&#39;./modelexpression87%.h5&#39;</span>
<span class="n">model</span><span class="o">.</span><span class="n">save</span><span class="p">(</span><span class="n">saved1_keras_model_filepath</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">cv2</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">from</span> <span class="nn">time</span> <span class="k">import</span> <span class="n">sleep</span>
<span class="kn">from</span> <span class="nn">keras.preprocessing.image</span> <span class="k">import</span> <span class="n">img_to_array</span>

<span class="n">face_classifier</span> <span class="o">=</span> <span class="n">cv2</span><span class="o">.</span><span class="n">CascadeClassifier</span><span class="p">(</span><span class="s1">&#39;/content/haarcascade_frontalface_default.xml&#39;</span><span class="p">)</span>

<span class="k">def</span> <span class="nf">face_detector</span><span class="p">(</span><span class="n">img</span><span class="p">):</span>
    <span class="c1"># Convert image to grayscale</span>
    <span class="n">gray</span> <span class="o">=</span> <span class="n">cv2</span><span class="o">.</span><span class="n">cvtColor</span><span class="p">(</span><span class="n">img</span><span class="p">,</span><span class="n">cv2</span><span class="o">.</span><span class="n">COLOR_BGR2GRAY</span><span class="p">)</span>
    <span class="n">faces</span> <span class="o">=</span> <span class="n">face_classifier</span><span class="o">.</span><span class="n">detectMultiScale</span><span class="p">(</span><span class="n">gray</span><span class="p">,</span> <span class="mf">1.3</span><span class="p">,</span> <span class="mi">5</span><span class="p">)</span>
    <span class="k">if</span> <span class="n">faces</span> <span class="ow">is</span> <span class="p">():</span>
        <span class="k">return</span> <span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">),</span> <span class="n">np</span><span class="o">.</span><span class="n">zeros</span><span class="p">((</span><span class="mi">75</span><span class="p">,</span><span class="mi">75</span><span class="p">),</span> <span class="n">np</span><span class="o">.</span><span class="n">uint8</span><span class="p">),</span> <span class="n">img</span>
    
    <span class="k">for</span> <span class="p">(</span><span class="n">x</span><span class="p">,</span><span class="n">y</span><span class="p">,</span><span class="n">w</span><span class="p">,</span><span class="n">h</span><span class="p">)</span> <span class="ow">in</span> <span class="n">faces</span><span class="p">:</span>
        <span class="n">cv2</span><span class="o">.</span><span class="n">rectangle</span><span class="p">(</span><span class="n">img</span><span class="p">,(</span><span class="n">x</span><span class="p">,</span><span class="n">y</span><span class="p">),(</span><span class="n">x</span><span class="o">+</span><span class="n">w</span><span class="p">,</span><span class="n">y</span><span class="o">+</span><span class="n">h</span><span class="p">),(</span><span class="mi">255</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">),</span><span class="mi">2</span><span class="p">)</span>
        <span class="n">roi_gray</span> <span class="o">=</span> <span class="n">gray</span><span class="p">[</span><span class="n">y</span><span class="p">:</span><span class="n">y</span><span class="o">+</span><span class="n">h</span><span class="p">,</span> <span class="n">x</span><span class="p">:</span><span class="n">x</span><span class="o">+</span><span class="n">w</span><span class="p">]</span>

    <span class="k">try</span><span class="p">:</span>
        <span class="n">roi_gray</span> <span class="o">=</span> <span class="n">cv2</span><span class="o">.</span><span class="n">resize</span><span class="p">(</span><span class="n">roi_gray</span><span class="p">,</span> <span class="p">(</span><span class="mi">75</span><span class="p">,</span> <span class="mi">75</span><span class="p">),</span> <span class="n">interpolation</span> <span class="o">=</span> <span class="n">cv2</span><span class="o">.</span><span class="n">INTER_AREA</span><span class="p">)</span>
    <span class="k">except</span><span class="p">:</span>
        <span class="k">return</span> <span class="p">(</span><span class="n">x</span><span class="p">,</span><span class="n">w</span><span class="p">,</span><span class="n">y</span><span class="p">,</span><span class="n">h</span><span class="p">),</span> <span class="n">np</span><span class="o">.</span><span class="n">zeros</span><span class="p">((</span><span class="mi">75</span><span class="p">,</span><span class="mi">75</span><span class="p">),</span> <span class="n">np</span><span class="o">.</span><span class="n">uint8</span><span class="p">),</span> <span class="n">img</span>
    <span class="k">return</span> <span class="p">(</span><span class="n">x</span><span class="p">,</span><span class="n">w</span><span class="p">,</span><span class="n">y</span><span class="p">,</span><span class="n">h</span><span class="p">),</span> <span class="n">roi_gray</span><span class="p">,</span> <span class="n">img</span>

<span class="n">cap</span> <span class="o">=</span> <span class="n">cv2</span><span class="o">.</span><span class="n">VideoCapture</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>

<span class="k">while</span> <span class="kc">True</span><span class="p">:</span>

    <span class="n">ret</span><span class="p">,</span> <span class="n">frame</span> <span class="o">=</span> <span class="n">cap</span><span class="o">.</span><span class="n">read</span><span class="p">()</span>
    <span class="n">rect</span><span class="p">,</span> <span class="n">face</span><span class="p">,</span> <span class="n">image</span> <span class="o">=</span> <span class="n">face_detector</span><span class="p">(</span><span class="n">frame</span><span class="p">)</span>
    <span class="k">if</span> <span class="n">np</span><span class="o">.</span><span class="n">sum</span><span class="p">([</span><span class="n">face</span><span class="p">])</span> <span class="o">!=</span> <span class="mf">0.0</span><span class="p">:</span>
        <span class="n">roi</span> <span class="o">=</span> <span class="n">face</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s2">&quot;float&quot;</span><span class="p">)</span> <span class="o">/</span> <span class="mf">255.0</span>
        <span class="n">roi</span> <span class="o">=</span> <span class="n">img_to_array</span><span class="p">(</span><span class="n">roi</span><span class="p">)</span>
        <span class="n">roi</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">expand_dims</span><span class="p">(</span><span class="n">roi</span><span class="p">,</span> <span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>

        <span class="c1"># make a prediction on the ROI, then lookup the class</span>
        <span class="n">preds</span> <span class="o">=</span> <span class="n">model</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">roi</span><span class="p">)[</span><span class="mi">0</span><span class="p">]</span>
        <span class="n">label</span> <span class="o">=</span> <span class="n">class_labels</span><span class="p">[</span><span class="n">preds</span><span class="o">.</span><span class="n">argmax</span><span class="p">()]</span>  
        <span class="n">label_position</span> <span class="o">=</span> <span class="p">(</span><span class="n">rect</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span> <span class="o">+</span> <span class="nb">int</span><span class="p">((</span><span class="n">rect</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span><span class="o">/</span><span class="mi">2</span><span class="p">)),</span> <span class="n">rect</span><span class="p">[</span><span class="mi">2</span><span class="p">]</span> <span class="o">+</span> <span class="mi">25</span><span class="p">)</span>
        <span class="n">cv2</span><span class="o">.</span><span class="n">putText</span><span class="p">(</span><span class="n">image</span><span class="p">,</span> <span class="n">label</span><span class="p">,</span> <span class="n">label_position</span> <span class="p">,</span> <span class="n">cv2</span><span class="o">.</span><span class="n">FONT_HERSHEY_SIMPLEX</span><span class="p">,</span><span class="mi">2</span><span class="p">,</span> <span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">255</span><span class="p">,</span><span class="mi">0</span><span class="p">),</span> <span class="mi">3</span><span class="p">)</span>
    <span class="k">else</span><span class="p">:</span>
        <span class="n">cv2</span><span class="o">.</span><span class="n">putText</span><span class="p">(</span><span class="n">image</span><span class="p">,</span> <span class="s2">&quot;No Face Found&quot;</span><span class="p">,</span> <span class="p">(</span><span class="mi">20</span><span class="p">,</span> <span class="mi">60</span><span class="p">)</span> <span class="p">,</span> <span class="n">cv2</span><span class="o">.</span><span class="n">FONT_HERSHEY_SIMPLEX</span><span class="p">,</span><span class="mi">2</span><span class="p">,</span> <span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">255</span><span class="p">,</span><span class="mi">0</span><span class="p">),</span> <span class="mi">3</span><span class="p">)</span>
        
    <span class="n">cv2</span><span class="o">.</span><span class="n">imshow</span><span class="p">(</span><span class="s1">&#39;All&#39;</span><span class="p">,</span> <span class="n">image</span><span class="p">)</span>
    <span class="k">if</span> <span class="n">cv2</span><span class="o">.</span><span class="n">waitKey</span><span class="p">(</span><span class="mi">1</span><span class="p">)</span> <span class="o">==</span> <span class="mi">13</span><span class="p">:</span> <span class="c1">#13 is the Enter Key</span>
        <span class="k">break</span>
        
<span class="n">cap</span><span class="o">.</span><span class="n">release</span><span class="p">()</span>
<span class="n">cv2</span><span class="o">.</span><span class="n">destroyAllWindows</span><span class="p">()</span>      
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">model</span><span class="o">.</span><span class="n">evaluate</span><span class="p">(</span><span class="n">x_test</span><span class="p">,</span><span class="n">y_test1</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">y_pred</span><span class="o">=</span><span class="n">model</span><span class="o">.</span><span class="n">predict_classes</span><span class="p">(</span><span class="n">x_test</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">classif</span><span class="o">=</span><span class="n">metrics</span><span class="o">.</span><span class="n">classification_report</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span><span class="n">y_pred</span><span class="p">,</span><span class="n">target_names</span><span class="o">=</span><span class="n">classs</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">classif</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">sklearn.metrics</span> <span class="k">import</span> <span class="n">confusion_matrix</span>
<span class="n">con</span><span class="o">=</span><span class="n">confusion_matrix</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span><span class="n">y_pred</span><span class="p">)</span>
<span class="n">con</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[&nbsp;]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>(35887, 48, 48, 1)</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="n">acc</span> <span class="o">=</span> <span class="n">history</span><span class="o">.</span><span class="n">history</span><span class="p">[</span><span class="s1">&#39;accuracy&#39;</span><span class="p">]</span>
<span class="n">val_acc</span> <span class="o">=</span> <span class="n">history</span><span class="o">.</span><span class="n">history</span><span class="p">[</span><span class="s1">&#39;val_accuracy&#39;</span><span class="p">]</span>
<span class="n">loss</span> <span class="o">=</span> <span class="n">history</span><span class="o">.</span><span class="n">history</span><span class="p">[</span><span class="s1">&#39;loss&#39;</span><span class="p">]</span>
<span class="n">val_loss</span> <span class="o">=</span> <span class="n">history</span><span class="o">.</span><span class="n">history</span><span class="p">[</span><span class="s1">&#39;val_loss&#39;</span><span class="p">]</span>

<span class="n">epochs</span> <span class="o">=</span> <span class="nb">range</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">acc</span><span class="p">))</span>

<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">epochs</span><span class="p">,</span> <span class="n">acc</span><span class="p">,</span> <span class="s1">&#39;r&#39;</span><span class="p">,</span> <span class="n">label</span><span class="o">=</span><span class="s1">&#39;Training accuracy&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">epochs</span><span class="p">,</span> <span class="n">val_acc</span><span class="p">,</span> <span class="s1">&#39;b&#39;</span><span class="p">,</span> <span class="n">label</span><span class="o">=</span><span class="s1">&#39;Validation accuracy&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;Training and validation accuracy&#39;</span><span class="p">)</span>

<span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">()</span>

<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">epochs</span><span class="p">,</span> <span class="n">loss</span><span class="p">,</span> <span class="s1">&#39;r&#39;</span><span class="p">,</span> <span class="n">label</span><span class="o">=</span><span class="s1">&#39;Training Loss&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">epochs</span><span class="p">,</span> <span class="n">val_loss</span><span class="p">,</span> <span class="s1">&#39;b&#39;</span><span class="p">,</span> <span class="n">label</span><span class="o">=</span><span class="s1">&#39;Validation Loss&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;Training and validation loss&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">legend</span><span class="p">()</span>

<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">xtrain</span><span class="o">=</span><span class="n">images</span><span class="p">[</span><span class="mi">0</span><span class="p">:</span><span class="mi">28709</span><span class="p">]</span>
<span class="n">xval</span><span class="o">=</span><span class="n">images</span><span class="p">[</span><span class="mi">28709</span><span class="p">:</span><span class="mi">32298</span><span class="p">]</span>
<span class="n">xtest</span><span class="o">=</span><span class="n">images</span><span class="p">[</span><span class="mi">32298</span><span class="p">:]</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">xval</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span><span class="o">.</span><span class="n">shape</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[&nbsp;]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>(48, 48, 3)</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">plt</span><span class="o">.</span><span class="n">imshow</span><span class="p">(</span><span class="n">images</span><span class="p">[</span><span class="mi">10</span><span class="p">]</span><span class="o">.</span><span class="n">reshape</span><span class="p">(</span><span class="mi">48</span><span class="p">,</span><span class="mi">48</span><span class="p">,</span><span class="mi">3</span><span class="p">),</span><span class="n">cmap</span><span class="o">=</span><span class="s1">&#39;gray&#39;</span><span class="p">),</span><span class="nb">print</span><span class="p">(</span><span class="n">data1</span><span class="p">[</span><span class="s1">&#39;emotion&#39;</span><span class="p">][</span><span class="mi">10</span><span class="p">])</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>0
</pre>
</div>
</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[&nbsp;]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>(&lt;matplotlib.image.AxesImage at 0x7f26cc0ae048&gt;, None)</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">ytrain</span><span class="o">=</span><span class="n">data1</span><span class="p">[</span><span class="s1">&#39;emotion&#39;</span><span class="p">][</span><span class="mi">0</span><span class="p">:</span><span class="mi">28709</span><span class="p">]</span>
<span class="n">trainlabel</span><span class="o">=</span><span class="n">ytrain</span><span class="o">.</span><span class="n">replace</span><span class="p">([</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">,</span><span class="mi">2</span><span class="p">,</span><span class="mi">3</span><span class="p">,</span><span class="mi">4</span><span class="p">,</span><span class="mi">5</span><span class="p">,</span><span class="mi">6</span><span class="p">],</span><span class="n">expression</span><span class="p">)</span>
<span class="n">y_train</span><span class="o">=</span><span class="n">trainlabel</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="n">expression</span><span class="p">,[</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">,</span><span class="mi">2</span><span class="p">,</span><span class="mi">3</span><span class="p">,</span><span class="mi">4</span><span class="p">,</span><span class="mi">5</span><span class="p">,</span><span class="mi">6</span><span class="p">])</span>
<span class="n">ytrain</span> <span class="o">=</span> <span class="n">tensorflow</span><span class="o">.</span><span class="n">keras</span><span class="o">.</span><span class="n">utils</span><span class="o">.</span><span class="n">to_categorical</span><span class="p">(</span><span class="n">ytrain</span><span class="p">,</span> <span class="mi">7</span><span class="p">)</span>

<span class="n">yval</span><span class="o">=</span><span class="n">data1</span><span class="p">[</span><span class="s1">&#39;emotion&#39;</span><span class="p">][</span><span class="mi">28709</span><span class="p">:</span><span class="mi">32298</span><span class="p">]</span>
<span class="n">vallabel</span><span class="o">=</span><span class="n">yval</span><span class="o">.</span><span class="n">replace</span><span class="p">([</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">,</span><span class="mi">2</span><span class="p">,</span><span class="mi">3</span><span class="p">,</span><span class="mi">4</span><span class="p">,</span><span class="mi">5</span><span class="p">,</span><span class="mi">6</span><span class="p">],</span><span class="n">expression</span><span class="p">)</span>
<span class="n">y_val</span><span class="o">=</span><span class="n">vallabel</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="n">expression</span><span class="p">,[</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">,</span><span class="mi">2</span><span class="p">,</span><span class="mi">3</span><span class="p">,</span><span class="mi">4</span><span class="p">,</span><span class="mi">5</span><span class="p">,</span><span class="mi">6</span><span class="p">])</span>
<span class="n">yval</span> <span class="o">=</span> <span class="n">tensorflow</span><span class="o">.</span><span class="n">keras</span><span class="o">.</span><span class="n">utils</span><span class="o">.</span><span class="n">to_categorical</span><span class="p">(</span><span class="n">yval</span><span class="p">,</span> <span class="mi">7</span><span class="p">)</span>

<span class="n">ytest</span><span class="o">=</span><span class="n">data1</span><span class="p">[</span><span class="s1">&#39;emotion&#39;</span><span class="p">][</span><span class="mi">32298</span><span class="p">:]</span>
<span class="n">testlabel</span><span class="o">=</span><span class="n">ytest</span><span class="o">.</span><span class="n">replace</span><span class="p">([</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">,</span><span class="mi">2</span><span class="p">,</span><span class="mi">3</span><span class="p">,</span><span class="mi">4</span><span class="p">,</span><span class="mi">5</span><span class="p">,</span><span class="mi">6</span><span class="p">],</span><span class="n">expression</span><span class="p">)</span>
<span class="n">y_test</span><span class="o">=</span><span class="n">testlabel</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="n">expression</span><span class="p">,[</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">,</span><span class="mi">2</span><span class="p">,</span><span class="mi">3</span><span class="p">,</span><span class="mi">4</span><span class="p">,</span><span class="mi">5</span><span class="p">,</span><span class="mi">6</span><span class="p">])</span>
<span class="n">ytest</span> <span class="o">=</span> <span class="n">tensorflow</span><span class="o">.</span><span class="n">keras</span><span class="o">.</span><span class="n">utils</span><span class="o">.</span><span class="n">to_categorical</span><span class="p">(</span><span class="n">ytest</span><span class="p">,</span> <span class="mi">7</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">tensorflow.keras</span> <span class="k">import</span> <span class="n">Sequential</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras.layers</span> <span class="k">import</span> <span class="n">Conv2D</span><span class="p">,</span><span class="n">MaxPooling2D</span><span class="p">,</span><span class="n">BatchNormalization</span><span class="p">,</span><span class="n">Dropout</span><span class="p">,</span><span class="n">Activation</span><span class="p">,</span><span class="n">Flatten</span><span class="p">,</span><span class="n">Dense</span>


<span class="kn">from</span> <span class="nn">tensorflow.keras</span> <span class="k">import</span> <span class="n">optimizers</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras.regularizers</span> <span class="k">import</span> <span class="n">l2</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras.applications</span> <span class="k">import</span> <span class="n">VGG16</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras.applications</span> <span class="k">import</span>  <span class="n">MobileNetV2</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras.applications</span> <span class="k">import</span>  <span class="n">ResNet50V2</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras</span> <span class="k">import</span> <span class="n">Model</span>

<span class="n">image_size</span><span class="o">=</span><span class="mi">48</span>


<span class="n">model</span> <span class="o">=</span> <span class="n">Sequential</span><span class="p">()</span>
<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">Conv2D</span><span class="p">(</span><span class="mi">32</span><span class="p">,</span><span class="n">kernel_size</span><span class="o">=</span><span class="p">(</span><span class="mi">3</span><span class="p">,</span> <span class="mi">3</span><span class="p">),</span><span class="n">padding</span> <span class="o">=</span> <span class="s1">&#39;same&#39;</span><span class="p">,</span><span class="n">strides</span><span class="o">=</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span> <span class="mi">1</span><span class="p">),</span><span class="n">kernel_regularizer</span><span class="o">=</span><span class="n">l2</span><span class="p">(</span><span class="mf">0.001</span><span class="p">),</span><span class="n">input_shape</span> <span class="o">=</span> <span class="p">(</span><span class="mi">48</span><span class="p">,</span> <span class="mi">48</span><span class="p">,</span> <span class="mi">3</span><span class="p">)))</span>
<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">Dropout</span><span class="p">(</span><span class="mf">0.1</span><span class="p">))</span>
<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">Activation</span><span class="p">(</span><span class="s1">&#39;relu&#39;</span><span class="p">))</span>
<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">MaxPooling2D</span><span class="p">(</span><span class="n">pool_size</span> <span class="o">=</span> <span class="p">(</span><span class="mi">2</span><span class="p">,</span><span class="mi">2</span><span class="p">)))</span>

<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">Conv2D</span><span class="p">(</span><span class="mi">64</span><span class="p">,</span><span class="n">kernel_size</span><span class="o">=</span><span class="p">(</span><span class="mi">3</span><span class="p">,</span> <span class="mi">3</span><span class="p">),</span><span class="n">padding</span> <span class="o">=</span> <span class="s1">&#39;same&#39;</span><span class="p">,</span><span class="n">strides</span><span class="o">=</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span> <span class="mi">1</span><span class="p">),</span><span class="n">kernel_regularizer</span><span class="o">=</span><span class="n">l2</span><span class="p">(</span><span class="mf">0.001</span><span class="p">)))</span>
<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">Dropout</span><span class="p">(</span><span class="mf">0.1</span><span class="p">))</span>
<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">Activation</span><span class="p">(</span><span class="s1">&#39;relu&#39;</span><span class="p">))</span>
<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">MaxPooling2D</span><span class="p">(</span><span class="n">pool_size</span> <span class="o">=</span> <span class="p">(</span><span class="mi">2</span><span class="p">,</span><span class="mi">2</span><span class="p">)))</span>

<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">Conv2D</span><span class="p">(</span><span class="mi">128</span><span class="p">,</span><span class="n">kernel_size</span><span class="o">=</span><span class="p">(</span><span class="mi">3</span><span class="p">,</span> <span class="mi">3</span><span class="p">),</span><span class="n">padding</span> <span class="o">=</span> <span class="s1">&#39;same&#39;</span><span class="p">,</span><span class="n">strides</span><span class="o">=</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span> <span class="mi">1</span><span class="p">),</span><span class="n">kernel_regularizer</span><span class="o">=</span><span class="n">l2</span><span class="p">(</span><span class="mf">0.001</span><span class="p">)))</span>
<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">Dropout</span><span class="p">(</span><span class="mf">0.1</span><span class="p">))</span>
<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">Activation</span><span class="p">(</span><span class="s1">&#39;relu&#39;</span><span class="p">))</span>
<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">MaxPooling2D</span><span class="p">(</span><span class="n">pool_size</span> <span class="o">=</span> <span class="p">(</span><span class="mi">2</span><span class="p">,</span><span class="mi">2</span><span class="p">)))</span>

<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">Conv2D</span><span class="p">(</span><span class="mi">256</span><span class="p">,</span><span class="n">kernel_size</span><span class="o">=</span><span class="p">(</span><span class="mi">3</span><span class="p">,</span> <span class="mi">3</span><span class="p">),</span><span class="n">padding</span> <span class="o">=</span> <span class="s1">&#39;same&#39;</span><span class="p">,</span><span class="n">strides</span><span class="o">=</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span> <span class="mi">1</span><span class="p">),</span><span class="n">kernel_regularizer</span><span class="o">=</span><span class="n">l2</span><span class="p">(</span><span class="mf">0.001</span><span class="p">)))</span>
<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">Dropout</span><span class="p">(</span><span class="mf">0.1</span><span class="p">))</span>
<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">Activation</span><span class="p">(</span><span class="s1">&#39;relu&#39;</span><span class="p">))</span>
<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">MaxPooling2D</span><span class="p">(</span><span class="n">pool_size</span> <span class="o">=</span> <span class="p">(</span><span class="mi">2</span><span class="p">,</span><span class="mi">2</span><span class="p">)))</span>

<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">Flatten</span><span class="p">())</span>
<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">Dense</span><span class="p">(</span><span class="mi">128</span><span class="p">,</span><span class="n">activation</span><span class="o">=</span><span class="s1">&#39;relu&#39;</span><span class="p">))</span>
<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">Dropout</span><span class="p">(</span><span class="mf">0.2</span><span class="p">))</span>
<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">Dense</span><span class="p">(</span><span class="mi">256</span><span class="p">,</span><span class="n">activation</span><span class="o">=</span><span class="s1">&#39;relu&#39;</span><span class="p">))</span>
<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">Dropout</span><span class="p">(</span><span class="mf">0.2</span><span class="p">))</span>
<span class="n">model</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">Dense</span><span class="p">(</span><span class="mi">7</span><span class="p">,</span><span class="n">activation</span><span class="o">=</span><span class="s2">&quot;softmax&quot;</span><span class="p">))</span>

<span class="n">model</span><span class="o">.</span><span class="n">compile</span><span class="p">(</span><span class="n">loss</span><span class="o">=</span><span class="s2">&quot;categorical_crossentropy&quot;</span><span class="p">,</span> <span class="n">optimizer</span><span class="o">=</span><span class="s2">&quot;Adam&quot;</span><span class="p">,</span><span class="n">metrics</span><span class="o">=</span><span class="p">[</span><span class="s2">&quot;accuracy&quot;</span><span class="p">])</span>

<span class="nb">print</span><span class="p">(</span><span class="n">model</span><span class="o">.</span><span class="n">summary</span><span class="p">())</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Model: &#34;sequential_6&#34;
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
conv2d_23 (Conv2D)           (None, 48, 48, 32)        896       
_________________________________________________________________
dropout_30 (Dropout)         (None, 48, 48, 32)        0         
_________________________________________________________________
activation_23 (Activation)   (None, 48, 48, 32)        0         
_________________________________________________________________
max_pooling2d_21 (MaxPooling (None, 24, 24, 32)        0         
_________________________________________________________________
conv2d_24 (Conv2D)           (None, 24, 24, 64)        18496     
_________________________________________________________________
dropout_31 (Dropout)         (None, 24, 24, 64)        0         
_________________________________________________________________
activation_24 (Activation)   (None, 24, 24, 64)        0         
_________________________________________________________________
max_pooling2d_22 (MaxPooling (None, 12, 12, 64)        0         
_________________________________________________________________
conv2d_25 (Conv2D)           (None, 12, 12, 128)       73856     
_________________________________________________________________
dropout_32 (Dropout)         (None, 12, 12, 128)       0         
_________________________________________________________________
activation_25 (Activation)   (None, 12, 12, 128)       0         
_________________________________________________________________
max_pooling2d_23 (MaxPooling (None, 6, 6, 128)         0         
_________________________________________________________________
conv2d_26 (Conv2D)           (None, 6, 6, 256)         295168    
_________________________________________________________________
dropout_33 (Dropout)         (None, 6, 6, 256)         0         
_________________________________________________________________
activation_26 (Activation)   (None, 6, 6, 256)         0         
_________________________________________________________________
max_pooling2d_24 (MaxPooling (None, 3, 3, 256)         0         
_________________________________________________________________
flatten_5 (Flatten)          (None, 2304)              0         
_________________________________________________________________
dense_12 (Dense)             (None, 128)               295040    
_________________________________________________________________
dropout_34 (Dropout)         (None, 128)               0         
_________________________________________________________________
dense_13 (Dense)             (None, 256)               33024     
_________________________________________________________________
dropout_35 (Dropout)         (None, 256)               0         
_________________________________________________________________
dense_14 (Dense)             (None, 7)                 1799      
=================================================================
Total params: 718,279
Trainable params: 718,279
Non-trainable params: 0
_________________________________________________________________
None
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">history</span><span class="o">=</span><span class="n">model</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">xtrain</span><span class="p">,</span><span class="n">ytrain</span><span class="p">,</span><span class="n">batch_size</span><span class="o">=</span><span class="mi">32</span><span class="p">,</span><span class="n">validation_data</span><span class="o">=</span><span class="p">(</span><span class="n">xtest</span><span class="p">,</span><span class="n">ytest</span><span class="p">),</span><span class="n">epochs</span><span class="o">=</span><span class="mi">100</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Epoch 1/100
898/898 [==============================] - 7s 8ms/step - loss: 1.8373 - accuracy: 0.2509 - val_loss: 1.7937 - val_accuracy: 0.2452
Epoch 2/100
898/898 [==============================] - 6s 7ms/step - loss: 1.7308 - accuracy: 0.3012 - val_loss: 1.6392 - val_accuracy: 0.3597
Epoch 3/100
898/898 [==============================] - 7s 7ms/step - loss: 1.5938 - accuracy: 0.3858 - val_loss: 1.5637 - val_accuracy: 0.4026
Epoch 4/100
898/898 [==============================] - 7s 8ms/step - loss: 1.5373 - accuracy: 0.4135 - val_loss: 1.5185 - val_accuracy: 0.4213
Epoch 5/100
898/898 [==============================] - 7s 7ms/step - loss: 1.4970 - accuracy: 0.4300 - val_loss: 1.4739 - val_accuracy: 0.4480
Epoch 6/100
898/898 [==============================] - 7s 7ms/step - loss: 1.4696 - accuracy: 0.4423 - val_loss: 1.4498 - val_accuracy: 0.4542
Epoch 7/100
898/898 [==============================] - 6s 7ms/step - loss: 1.4470 - accuracy: 0.4494 - val_loss: 1.4137 - val_accuracy: 0.4784
Epoch 8/100
898/898 [==============================] - 6s 7ms/step - loss: 1.4224 - accuracy: 0.4654 - val_loss: 1.4258 - val_accuracy: 0.4653
Epoch 9/100
898/898 [==============================] - 6s 7ms/step - loss: 1.4018 - accuracy: 0.4759 - val_loss: 1.3945 - val_accuracy: 0.4778
Epoch 10/100
898/898 [==============================] - 7s 7ms/step - loss: 1.3847 - accuracy: 0.4804 - val_loss: 1.3764 - val_accuracy: 0.4751
Epoch 11/100
898/898 [==============================] - 6s 7ms/step - loss: 1.3669 - accuracy: 0.4881 - val_loss: 1.3616 - val_accuracy: 0.4957
Epoch 12/100
898/898 [==============================] - 7s 7ms/step - loss: 1.3538 - accuracy: 0.4943 - val_loss: 1.3636 - val_accuracy: 0.4909
Epoch 13/100
898/898 [==============================] - 7s 7ms/step - loss: 1.3441 - accuracy: 0.5017 - val_loss: 1.3608 - val_accuracy: 0.4940
Epoch 14/100
898/898 [==============================] - 7s 7ms/step - loss: 1.3327 - accuracy: 0.5058 - val_loss: 1.3519 - val_accuracy: 0.4935
Epoch 15/100
898/898 [==============================] - 7s 7ms/step - loss: 1.3203 - accuracy: 0.5105 - val_loss: 1.3453 - val_accuracy: 0.4923
Epoch 16/100
898/898 [==============================] - 6s 7ms/step - loss: 1.3175 - accuracy: 0.5142 - val_loss: 1.3225 - val_accuracy: 0.5060
Epoch 17/100
898/898 [==============================] - 6s 7ms/step - loss: 1.3081 - accuracy: 0.5162 - val_loss: 1.3101 - val_accuracy: 0.5141
Epoch 18/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2963 - accuracy: 0.5228 - val_loss: 1.3141 - val_accuracy: 0.5183
Epoch 19/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2911 - accuracy: 0.5233 - val_loss: 1.3232 - val_accuracy: 0.5049
Epoch 20/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2871 - accuracy: 0.5267 - val_loss: 1.3129 - val_accuracy: 0.5169
Epoch 21/100
898/898 [==============================] - 7s 7ms/step - loss: 1.2851 - accuracy: 0.5268 - val_loss: 1.3078 - val_accuracy: 0.5121
Epoch 22/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2751 - accuracy: 0.5339 - val_loss: 1.2933 - val_accuracy: 0.5252
Epoch 23/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2722 - accuracy: 0.5329 - val_loss: 1.3010 - val_accuracy: 0.5183
Epoch 24/100
898/898 [==============================] - 7s 7ms/step - loss: 1.2616 - accuracy: 0.5364 - val_loss: 1.2923 - val_accuracy: 0.5227
Epoch 25/100
898/898 [==============================] - 7s 7ms/step - loss: 1.2591 - accuracy: 0.5407 - val_loss: 1.3092 - val_accuracy: 0.5146
Epoch 26/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2569 - accuracy: 0.5429 - val_loss: 1.2995 - val_accuracy: 0.5191
Epoch 27/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2499 - accuracy: 0.5431 - val_loss: 1.2842 - val_accuracy: 0.5364
Epoch 28/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2413 - accuracy: 0.5493 - val_loss: 1.3087 - val_accuracy: 0.5219
Epoch 29/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2417 - accuracy: 0.5461 - val_loss: 1.2829 - val_accuracy: 0.5316
Epoch 30/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2408 - accuracy: 0.5492 - val_loss: 1.3028 - val_accuracy: 0.5222
Epoch 31/100
898/898 [==============================] - 7s 7ms/step - loss: 1.2362 - accuracy: 0.5513 - val_loss: 1.2925 - val_accuracy: 0.5274
Epoch 32/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2353 - accuracy: 0.5508 - val_loss: 1.2862 - val_accuracy: 0.5283
Epoch 33/100
898/898 [==============================] - 7s 7ms/step - loss: 1.2285 - accuracy: 0.5563 - val_loss: 1.2834 - val_accuracy: 0.5258
Epoch 34/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2336 - accuracy: 0.5528 - val_loss: 1.2756 - val_accuracy: 0.5291
Epoch 35/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2183 - accuracy: 0.5575 - val_loss: 1.2873 - val_accuracy: 0.5288
Epoch 36/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2213 - accuracy: 0.5561 - val_loss: 1.2673 - val_accuracy: 0.5333
Epoch 37/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2234 - accuracy: 0.5584 - val_loss: 1.2989 - val_accuracy: 0.5258
Epoch 38/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2181 - accuracy: 0.5583 - val_loss: 1.2769 - val_accuracy: 0.5305
Epoch 39/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2098 - accuracy: 0.5628 - val_loss: 1.2956 - val_accuracy: 0.5280
Epoch 40/100
898/898 [==============================] - 7s 7ms/step - loss: 1.2124 - accuracy: 0.5656 - val_loss: 1.2741 - val_accuracy: 0.5297
Epoch 41/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2126 - accuracy: 0.5580 - val_loss: 1.3150 - val_accuracy: 0.5183
Epoch 42/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2078 - accuracy: 0.5608 - val_loss: 1.2762 - val_accuracy: 0.5375
Epoch 43/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2042 - accuracy: 0.5655 - val_loss: 1.2889 - val_accuracy: 0.5305
Epoch 44/100
898/898 [==============================] - 7s 7ms/step - loss: 1.2029 - accuracy: 0.5655 - val_loss: 1.2762 - val_accuracy: 0.5366
Epoch 45/100
898/898 [==============================] - 7s 7ms/step - loss: 1.2047 - accuracy: 0.5652 - val_loss: 1.2977 - val_accuracy: 0.5286
Epoch 46/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2040 - accuracy: 0.5641 - val_loss: 1.2982 - val_accuracy: 0.5352
Epoch 47/100
898/898 [==============================] - 7s 7ms/step - loss: 1.1972 - accuracy: 0.5691 - val_loss: 1.2745 - val_accuracy: 0.5419
Epoch 48/100
898/898 [==============================] - 7s 7ms/step - loss: 1.1927 - accuracy: 0.5697 - val_loss: 1.2828 - val_accuracy: 0.5366
Epoch 49/100
898/898 [==============================] - 6s 7ms/step - loss: 1.2022 - accuracy: 0.5642 - val_loss: 1.2934 - val_accuracy: 0.5347
Epoch 50/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1963 - accuracy: 0.5673 - val_loss: 1.2893 - val_accuracy: 0.5358
Epoch 51/100
898/898 [==============================] - 7s 7ms/step - loss: 1.1895 - accuracy: 0.5696 - val_loss: 1.2789 - val_accuracy: 0.5383
Epoch 52/100
898/898 [==============================] - 7s 7ms/step - loss: 1.1894 - accuracy: 0.5680 - val_loss: 1.2660 - val_accuracy: 0.5375
Epoch 53/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1905 - accuracy: 0.5715 - val_loss: 1.2649 - val_accuracy: 0.5428
Epoch 54/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1861 - accuracy: 0.5743 - val_loss: 1.2692 - val_accuracy: 0.5439
Epoch 55/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1885 - accuracy: 0.5727 - val_loss: 1.2843 - val_accuracy: 0.5358
Epoch 56/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1773 - accuracy: 0.5741 - val_loss: 1.2763 - val_accuracy: 0.5397
Epoch 57/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1834 - accuracy: 0.5725 - val_loss: 1.2766 - val_accuracy: 0.5408
Epoch 58/100
898/898 [==============================] - 7s 7ms/step - loss: 1.1797 - accuracy: 0.5761 - val_loss: 1.2813 - val_accuracy: 0.5436
Epoch 59/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1754 - accuracy: 0.5784 - val_loss: 1.2735 - val_accuracy: 0.5355
Epoch 60/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1784 - accuracy: 0.5738 - val_loss: 1.2733 - val_accuracy: 0.5386
Epoch 61/100
898/898 [==============================] - 7s 7ms/step - loss: 1.1675 - accuracy: 0.5775 - val_loss: 1.2839 - val_accuracy: 0.5316
Epoch 62/100
898/898 [==============================] - 7s 7ms/step - loss: 1.1763 - accuracy: 0.5778 - val_loss: 1.2744 - val_accuracy: 0.5394
Epoch 63/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1730 - accuracy: 0.5785 - val_loss: 1.2636 - val_accuracy: 0.5447
Epoch 64/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1748 - accuracy: 0.5771 - val_loss: 1.2833 - val_accuracy: 0.5333
Epoch 65/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1729 - accuracy: 0.5727 - val_loss: 1.3047 - val_accuracy: 0.5339
Epoch 66/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1735 - accuracy: 0.5801 - val_loss: 1.2931 - val_accuracy: 0.5238
Epoch 67/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1693 - accuracy: 0.5783 - val_loss: 1.2693 - val_accuracy: 0.5511
Epoch 68/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1690 - accuracy: 0.5822 - val_loss: 1.2671 - val_accuracy: 0.5380
Epoch 69/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1697 - accuracy: 0.5780 - val_loss: 1.2803 - val_accuracy: 0.5405
Epoch 70/100
898/898 [==============================] - 7s 7ms/step - loss: 1.1692 - accuracy: 0.5799 - val_loss: 1.3011 - val_accuracy: 0.5311
Epoch 71/100
898/898 [==============================] - 7s 7ms/step - loss: 1.1597 - accuracy: 0.5843 - val_loss: 1.2627 - val_accuracy: 0.5439
Epoch 72/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1626 - accuracy: 0.5828 - val_loss: 1.2727 - val_accuracy: 0.5425
Epoch 73/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1634 - accuracy: 0.5809 - val_loss: 1.2825 - val_accuracy: 0.5419
Epoch 74/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1624 - accuracy: 0.5833 - val_loss: 1.3017 - val_accuracy: 0.5274
Epoch 75/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1544 - accuracy: 0.5862 - val_loss: 1.2832 - val_accuracy: 0.5403
Epoch 76/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1618 - accuracy: 0.5817 - val_loss: 1.2863 - val_accuracy: 0.5411
Epoch 77/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1575 - accuracy: 0.5844 - val_loss: 1.2847 - val_accuracy: 0.5311
Epoch 78/100
898/898 [==============================] - 7s 7ms/step - loss: 1.1588 - accuracy: 0.5844 - val_loss: 1.3003 - val_accuracy: 0.5277
Epoch 79/100
898/898 [==============================] - 7s 7ms/step - loss: 1.1572 - accuracy: 0.5876 - val_loss: 1.3068 - val_accuracy: 0.5333
Epoch 80/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1619 - accuracy: 0.5819 - val_loss: 1.2789 - val_accuracy: 0.5400
Epoch 81/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1529 - accuracy: 0.5848 - val_loss: 1.2867 - val_accuracy: 0.5397
Epoch 82/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1592 - accuracy: 0.5820 - val_loss: 1.2971 - val_accuracy: 0.5233
Epoch 83/100
898/898 [==============================] - 7s 7ms/step - loss: 1.1588 - accuracy: 0.5819 - val_loss: 1.2873 - val_accuracy: 0.5347
Epoch 84/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1525 - accuracy: 0.5841 - val_loss: 1.2647 - val_accuracy: 0.5472
Epoch 85/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1536 - accuracy: 0.5844 - val_loss: 1.2741 - val_accuracy: 0.5433
Epoch 86/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1545 - accuracy: 0.5867 - val_loss: 1.2799 - val_accuracy: 0.5453
Epoch 87/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1511 - accuracy: 0.5855 - val_loss: 1.2703 - val_accuracy: 0.5436
Epoch 88/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1461 - accuracy: 0.5869 - val_loss: 1.3108 - val_accuracy: 0.5180
Epoch 89/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1489 - accuracy: 0.5877 - val_loss: 1.3219 - val_accuracy: 0.5230
Epoch 90/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1518 - accuracy: 0.5874 - val_loss: 1.2767 - val_accuracy: 0.5442
Epoch 91/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1511 - accuracy: 0.5869 - val_loss: 1.2880 - val_accuracy: 0.5339
Epoch 92/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1464 - accuracy: 0.5901 - val_loss: 1.3023 - val_accuracy: 0.5280
Epoch 93/100
898/898 [==============================] - 7s 7ms/step - loss: 1.1506 - accuracy: 0.5881 - val_loss: 1.2855 - val_accuracy: 0.5336
Epoch 94/100
898/898 [==============================] - 7s 7ms/step - loss: 1.1470 - accuracy: 0.5873 - val_loss: 1.2865 - val_accuracy: 0.5425
Epoch 95/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1454 - accuracy: 0.5924 - val_loss: 1.3174 - val_accuracy: 0.5258
Epoch 96/100
898/898 [==============================] - 7s 7ms/step - loss: 1.1409 - accuracy: 0.5939 - val_loss: 1.2791 - val_accuracy: 0.5378
Epoch 97/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1424 - accuracy: 0.5924 - val_loss: 1.2735 - val_accuracy: 0.5450
Epoch 98/100
898/898 [==============================] - 6s 7ms/step - loss: 1.1509 - accuracy: 0.5876 - val_loss: 1.2781 - val_accuracy: 0.5355
Epoch 99/100
898/898 [==============================] - 7s 7ms/step - loss: 1.1421 - accuracy: 0.5924 - val_loss: 1.2692 - val_accuracy: 0.5408
Epoch 100/100
898/898 [==============================] - 7s 8ms/step - loss: 1.1402 - accuracy: 0.5916 - val_loss: 1.2811 - val_accuracy: 0.5411
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">epochs</span> <span class="o">=</span> <span class="mi">300</span>
<span class="n">batch_size</span> <span class="o">=</span> <span class="mi">128</span>
<span class="n">history</span> <span class="o">=</span> <span class="n">model</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">xtrain</span><span class="p">,</span> <span class="n">ytrain</span><span class="p">,</span> <span class="n">validation_data</span><span class="o">=</span><span class="p">(</span><span class="n">xval</span><span class="p">,</span> <span class="n">yval</span><span class="p">),</span>
                    <span class="n">epochs</span><span class="o">=</span> <span class="n">epochs</span><span class="p">,</span> <span class="n">batch_size</span><span class="o">=</span> <span class="n">batch_size</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Epoch 1/300
225/225 [==============================] - 12s 54ms/step - loss: 2.2722 - accuracy: 0.2303 - val_loss: 1.7973 - val_accuracy: 0.3438
Epoch 2/300
225/225 [==============================] - 12s 52ms/step - loss: 1.6487 - accuracy: 0.3736 - val_loss: 1.4080 - val_accuracy: 0.4458
Epoch 3/300
225/225 [==============================] - 12s 52ms/step - loss: 1.4334 - accuracy: 0.4513 - val_loss: 1.2989 - val_accuracy: 0.5052
Epoch 4/300
225/225 [==============================] - 12s 51ms/step - loss: 1.3249 - accuracy: 0.4966 - val_loss: 1.2201 - val_accuracy: 0.5336
Epoch 5/300
225/225 [==============================] - 12s 51ms/step - loss: 1.2596 - accuracy: 0.5266 - val_loss: 1.1931 - val_accuracy: 0.5467
Epoch 6/300
225/225 [==============================] - 12s 52ms/step - loss: 1.2005 - accuracy: 0.5522 - val_loss: 1.1563 - val_accuracy: 0.5589
Epoch 7/300
225/225 [==============================] - 12s 51ms/step - loss: 1.1506 - accuracy: 0.5755 - val_loss: 1.1324 - val_accuracy: 0.5804
Epoch 8/300
225/225 [==============================] - 12s 51ms/step - loss: 1.0990 - accuracy: 0.5982 - val_loss: 1.1029 - val_accuracy: 0.5904
Epoch 9/300
225/225 [==============================] - 12s 52ms/step - loss: 1.0614 - accuracy: 0.6115 - val_loss: 1.0886 - val_accuracy: 0.5968
Epoch 10/300
225/225 [==============================] - 12s 52ms/step - loss: 1.0205 - accuracy: 0.6254 - val_loss: 1.0806 - val_accuracy: 0.5974
Epoch 11/300
225/225 [==============================] - 12s 51ms/step - loss: 0.9648 - accuracy: 0.6524 - val_loss: 1.1223 - val_accuracy: 0.5899
Epoch 12/300
225/225 [==============================] - 12s 51ms/step - loss: 0.9166 - accuracy: 0.6740 - val_loss: 1.1070 - val_accuracy: 0.6055
Epoch 13/300
225/225 [==============================] - 12s 51ms/step - loss: 0.8709 - accuracy: 0.6885 - val_loss: 1.0808 - val_accuracy: 0.6119
Epoch 14/300
225/225 [==============================] - 12s 52ms/step - loss: 0.8161 - accuracy: 0.7110 - val_loss: 1.1267 - val_accuracy: 0.6108
Epoch 15/300
225/225 [==============================] - 12s 52ms/step - loss: 0.7626 - accuracy: 0.7326 - val_loss: 1.1174 - val_accuracy: 0.6088
Epoch 16/300
225/225 [==============================] - 11s 51ms/step - loss: 0.7127 - accuracy: 0.7527 - val_loss: 1.1475 - val_accuracy: 0.6305
Epoch 17/300
225/225 [==============================] - 11s 51ms/step - loss: 0.6553 - accuracy: 0.7727 - val_loss: 1.1854 - val_accuracy: 0.6286
Epoch 18/300
225/225 [==============================] - 11s 51ms/step - loss: 0.6123 - accuracy: 0.7899 - val_loss: 1.1883 - val_accuracy: 0.6333
Epoch 19/300
225/225 [==============================] - 12s 51ms/step - loss: 0.5641 - accuracy: 0.8075 - val_loss: 1.2185 - val_accuracy: 0.6219
Epoch 20/300
225/225 [==============================] - 11s 51ms/step - loss: 0.5052 - accuracy: 0.8303 - val_loss: 1.3367 - val_accuracy: 0.6266
Epoch 21/300
225/225 [==============================] - 11s 50ms/step - loss: 0.4870 - accuracy: 0.8337 - val_loss: 1.2670 - val_accuracy: 0.6227
Epoch 22/300
225/225 [==============================] - 11s 51ms/step - loss: 0.4319 - accuracy: 0.8549 - val_loss: 1.3505 - val_accuracy: 0.6278
Epoch 23/300
225/225 [==============================] - 11s 51ms/step - loss: 0.4105 - accuracy: 0.8628 - val_loss: 1.4078 - val_accuracy: 0.6236
Epoch 24/300
225/225 [==============================] - 11s 51ms/step - loss: 0.3843 - accuracy: 0.8715 - val_loss: 1.4464 - val_accuracy: 0.6219
Epoch 25/300
225/225 [==============================] - 11s 51ms/step - loss: 0.3502 - accuracy: 0.8856 - val_loss: 1.5208 - val_accuracy: 0.6194
Epoch 26/300
225/225 [==============================] - 11s 50ms/step - loss: 0.3330 - accuracy: 0.8901 - val_loss: 1.4772 - val_accuracy: 0.6211
Epoch 27/300
225/225 [==============================] - 11s 50ms/step - loss: 0.3099 - accuracy: 0.8971 - val_loss: 1.4876 - val_accuracy: 0.6406
Epoch 28/300
225/225 [==============================] - 11s 50ms/step - loss: 0.2968 - accuracy: 0.9016 - val_loss: 1.5689 - val_accuracy: 0.6186
Epoch 29/300
225/225 [==============================] - 11s 51ms/step - loss: 0.2874 - accuracy: 0.9068 - val_loss: 1.5879 - val_accuracy: 0.6275
Epoch 30/300
225/225 [==============================] - 11s 50ms/step - loss: 0.2557 - accuracy: 0.9175 - val_loss: 1.5935 - val_accuracy: 0.6339
Epoch 31/300
225/225 [==============================] - 11s 50ms/step - loss: 0.2555 - accuracy: 0.9164 - val_loss: 1.6012 - val_accuracy: 0.6342
Epoch 32/300
225/225 [==============================] - 11s 50ms/step - loss: 0.2465 - accuracy: 0.9212 - val_loss: 1.6229 - val_accuracy: 0.6275
Epoch 33/300
225/225 [==============================] - 11s 50ms/step - loss: 0.2277 - accuracy: 0.9273 - val_loss: 1.6120 - val_accuracy: 0.6233
Epoch 34/300
225/225 [==============================] - 11s 50ms/step - loss: 0.2217 - accuracy: 0.9283 - val_loss: 1.6635 - val_accuracy: 0.6383
Epoch 35/300
225/225 [==============================] - 11s 50ms/step - loss: 0.2215 - accuracy: 0.9287 - val_loss: 1.6368 - val_accuracy: 0.6322
Epoch 36/300
225/225 [==============================] - 11s 51ms/step - loss: 0.1964 - accuracy: 0.9379 - val_loss: 1.7317 - val_accuracy: 0.6278
Epoch 37/300
225/225 [==============================] - 11s 50ms/step - loss: 0.2022 - accuracy: 0.9358 - val_loss: 1.7263 - val_accuracy: 0.6369
Epoch 38/300
225/225 [==============================] - 11s 51ms/step - loss: 0.1905 - accuracy: 0.9391 - val_loss: 1.7288 - val_accuracy: 0.6244
Epoch 39/300
225/225 [==============================] - 11s 51ms/step - loss: 0.1920 - accuracy: 0.9398 - val_loss: 1.7373 - val_accuracy: 0.6325
Epoch 40/300
225/225 [==============================] - 11s 51ms/step - loss: 0.1839 - accuracy: 0.9423 - val_loss: 1.7650 - val_accuracy: 0.6297
Epoch 41/300
225/225 [==============================] - 12s 51ms/step - loss: 0.1902 - accuracy: 0.9393 - val_loss: 1.8678 - val_accuracy: 0.6255
Epoch 42/300
225/225 [==============================] - 12s 52ms/step - loss: 0.1763 - accuracy: 0.9444 - val_loss: 1.8455 - val_accuracy: 0.6356
Epoch 43/300
225/225 [==============================] - 11s 51ms/step - loss: 0.1724 - accuracy: 0.9441 - val_loss: 1.7704 - val_accuracy: 0.6408
Epoch 44/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1644 - accuracy: 0.9475 - val_loss: 1.8506 - val_accuracy: 0.6208
Epoch 45/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1683 - accuracy: 0.9473 - val_loss: 1.8694 - val_accuracy: 0.6225
Epoch 46/300
225/225 [==============================] - 11s 51ms/step - loss: 0.1642 - accuracy: 0.9490 - val_loss: 1.8190 - val_accuracy: 0.6342
Epoch 47/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1577 - accuracy: 0.9489 - val_loss: 1.7870 - val_accuracy: 0.6392
Epoch 48/300
225/225 [==============================] - 11s 51ms/step - loss: 0.1407 - accuracy: 0.9566 - val_loss: 1.9050 - val_accuracy: 0.6330
Epoch 49/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1502 - accuracy: 0.9526 - val_loss: 1.8654 - val_accuracy: 0.6333
Epoch 50/300
225/225 [==============================] - 11s 51ms/step - loss: 0.1514 - accuracy: 0.9530 - val_loss: 1.8779 - val_accuracy: 0.6239
Epoch 51/300
225/225 [==============================] - 11s 51ms/step - loss: 0.1473 - accuracy: 0.9531 - val_loss: 1.8857 - val_accuracy: 0.6322
Epoch 52/300
225/225 [==============================] - 11s 51ms/step - loss: 0.1456 - accuracy: 0.9553 - val_loss: 1.8686 - val_accuracy: 0.6328
Epoch 53/300
225/225 [==============================] - 11s 51ms/step - loss: 0.1377 - accuracy: 0.9575 - val_loss: 1.8854 - val_accuracy: 0.6381
Epoch 54/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1311 - accuracy: 0.9600 - val_loss: 1.9818 - val_accuracy: 0.6361
Epoch 55/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1361 - accuracy: 0.9571 - val_loss: 1.9572 - val_accuracy: 0.6308
Epoch 56/300
225/225 [==============================] - 11s 51ms/step - loss: 0.1297 - accuracy: 0.9609 - val_loss: 1.9798 - val_accuracy: 0.6328
Epoch 57/300
225/225 [==============================] - 11s 51ms/step - loss: 0.1270 - accuracy: 0.9620 - val_loss: 1.9748 - val_accuracy: 0.6322
Epoch 58/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1229 - accuracy: 0.9610 - val_loss: 1.9699 - val_accuracy: 0.6392
Epoch 59/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1321 - accuracy: 0.9598 - val_loss: 1.8946 - val_accuracy: 0.6367
Epoch 60/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1248 - accuracy: 0.9626 - val_loss: 1.9753 - val_accuracy: 0.6266
Epoch 61/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1242 - accuracy: 0.9628 - val_loss: 1.8926 - val_accuracy: 0.6358
Epoch 62/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1300 - accuracy: 0.9590 - val_loss: 1.8876 - val_accuracy: 0.6361
Epoch 63/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1237 - accuracy: 0.9609 - val_loss: 1.9182 - val_accuracy: 0.6275
Epoch 64/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1208 - accuracy: 0.9627 - val_loss: 1.9939 - val_accuracy: 0.6314
Epoch 65/300
225/225 [==============================] - 11s 51ms/step - loss: 0.1136 - accuracy: 0.9653 - val_loss: 1.9984 - val_accuracy: 0.6375
Epoch 66/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1168 - accuracy: 0.9638 - val_loss: 1.9884 - val_accuracy: 0.6333
Epoch 67/300
225/225 [==============================] - 11s 51ms/step - loss: 0.1173 - accuracy: 0.9653 - val_loss: 1.9282 - val_accuracy: 0.6255
Epoch 68/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1118 - accuracy: 0.9667 - val_loss: 1.9442 - val_accuracy: 0.6369
Epoch 69/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1098 - accuracy: 0.9666 - val_loss: 1.9716 - val_accuracy: 0.6372
Epoch 70/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1062 - accuracy: 0.9661 - val_loss: 1.9595 - val_accuracy: 0.6264
Epoch 71/300
225/225 [==============================] - 11s 51ms/step - loss: 0.1133 - accuracy: 0.9657 - val_loss: 1.9812 - val_accuracy: 0.6389
Epoch 72/300
225/225 [==============================] - 12s 51ms/step - loss: 0.1142 - accuracy: 0.9645 - val_loss: 1.9521 - val_accuracy: 0.6395
Epoch 73/300
225/225 [==============================] - 12s 51ms/step - loss: 0.1085 - accuracy: 0.9665 - val_loss: 2.0527 - val_accuracy: 0.6395
Epoch 74/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1117 - accuracy: 0.9666 - val_loss: 1.9621 - val_accuracy: 0.6330
Epoch 75/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1043 - accuracy: 0.9676 - val_loss: 1.9648 - val_accuracy: 0.6347
Epoch 76/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1009 - accuracy: 0.9681 - val_loss: 2.0308 - val_accuracy: 0.6356
Epoch 77/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1077 - accuracy: 0.9678 - val_loss: 1.9809 - val_accuracy: 0.6369
Epoch 78/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1049 - accuracy: 0.9682 - val_loss: 1.9850 - val_accuracy: 0.6255
Epoch 79/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0988 - accuracy: 0.9696 - val_loss: 2.0776 - val_accuracy: 0.6372
Epoch 80/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1031 - accuracy: 0.9695 - val_loss: 1.9910 - val_accuracy: 0.6328
Epoch 81/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0936 - accuracy: 0.9721 - val_loss: 2.0021 - val_accuracy: 0.6300
Epoch 82/300
225/225 [==============================] - 11s 50ms/step - loss: 0.1050 - accuracy: 0.9689 - val_loss: 2.0092 - val_accuracy: 0.6372
Epoch 83/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0952 - accuracy: 0.9709 - val_loss: 1.9623 - val_accuracy: 0.6361
Epoch 84/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0972 - accuracy: 0.9705 - val_loss: 2.0133 - val_accuracy: 0.6356
Epoch 85/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0957 - accuracy: 0.9712 - val_loss: 1.9741 - val_accuracy: 0.6305
Epoch 86/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0970 - accuracy: 0.9697 - val_loss: 1.9825 - val_accuracy: 0.6350
Epoch 87/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0905 - accuracy: 0.9719 - val_loss: 2.0570 - val_accuracy: 0.6269
Epoch 88/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0883 - accuracy: 0.9735 - val_loss: 2.0326 - val_accuracy: 0.6392
Epoch 89/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0858 - accuracy: 0.9745 - val_loss: 2.0658 - val_accuracy: 0.6372
Epoch 90/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0884 - accuracy: 0.9745 - val_loss: 1.9955 - val_accuracy: 0.6339
Epoch 91/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0908 - accuracy: 0.9723 - val_loss: 2.0854 - val_accuracy: 0.6280
Epoch 92/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0880 - accuracy: 0.9740 - val_loss: 2.0490 - val_accuracy: 0.6227
Epoch 93/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0885 - accuracy: 0.9725 - val_loss: 2.0276 - val_accuracy: 0.6333
Epoch 94/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0857 - accuracy: 0.9740 - val_loss: 2.0236 - val_accuracy: 0.6325
Epoch 95/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0847 - accuracy: 0.9734 - val_loss: 2.0414 - val_accuracy: 0.6367
Epoch 96/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0826 - accuracy: 0.9739 - val_loss: 2.0406 - val_accuracy: 0.6239
Epoch 97/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0866 - accuracy: 0.9734 - val_loss: 2.0669 - val_accuracy: 0.6308
Epoch 98/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0895 - accuracy: 0.9738 - val_loss: 2.0156 - val_accuracy: 0.6330
Epoch 99/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0777 - accuracy: 0.9782 - val_loss: 2.0762 - val_accuracy: 0.6406
Epoch 100/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0776 - accuracy: 0.9768 - val_loss: 2.0581 - val_accuracy: 0.6336
Epoch 101/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0835 - accuracy: 0.9751 - val_loss: 2.1316 - val_accuracy: 0.6381
Epoch 102/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0777 - accuracy: 0.9745 - val_loss: 2.1280 - val_accuracy: 0.6447
Epoch 103/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0811 - accuracy: 0.9763 - val_loss: 2.0577 - val_accuracy: 0.6325
Epoch 104/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0904 - accuracy: 0.9732 - val_loss: 2.0208 - val_accuracy: 0.6319
Epoch 105/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0791 - accuracy: 0.9752 - val_loss: 2.0525 - val_accuracy: 0.6422
Epoch 106/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0777 - accuracy: 0.9765 - val_loss: 2.1250 - val_accuracy: 0.6353
Epoch 107/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0780 - accuracy: 0.9765 - val_loss: 2.0556 - val_accuracy: 0.6308
Epoch 108/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0807 - accuracy: 0.9758 - val_loss: 2.0513 - val_accuracy: 0.6389
Epoch 109/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0736 - accuracy: 0.9780 - val_loss: 2.1041 - val_accuracy: 0.6450
Epoch 110/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0804 - accuracy: 0.9756 - val_loss: 2.1204 - val_accuracy: 0.6383
Epoch 111/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0807 - accuracy: 0.9748 - val_loss: 2.0745 - val_accuracy: 0.6336
Epoch 112/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0789 - accuracy: 0.9754 - val_loss: 2.0158 - val_accuracy: 0.6395
Epoch 113/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0779 - accuracy: 0.9764 - val_loss: 2.0258 - val_accuracy: 0.6367
Epoch 114/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0730 - accuracy: 0.9770 - val_loss: 2.0793 - val_accuracy: 0.6364
Epoch 115/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0698 - accuracy: 0.9799 - val_loss: 2.1492 - val_accuracy: 0.6414
Epoch 116/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0729 - accuracy: 0.9781 - val_loss: 2.0427 - val_accuracy: 0.6442
Epoch 117/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0748 - accuracy: 0.9770 - val_loss: 2.1034 - val_accuracy: 0.6406
Epoch 118/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0761 - accuracy: 0.9770 - val_loss: 2.0631 - val_accuracy: 0.6350
Epoch 119/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0721 - accuracy: 0.9777 - val_loss: 2.1547 - val_accuracy: 0.6378
Epoch 120/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0717 - accuracy: 0.9770 - val_loss: 2.1339 - val_accuracy: 0.6364
Epoch 121/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0767 - accuracy: 0.9771 - val_loss: 2.0923 - val_accuracy: 0.6358
Epoch 122/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0761 - accuracy: 0.9774 - val_loss: 2.0415 - val_accuracy: 0.6347
Epoch 123/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0656 - accuracy: 0.9815 - val_loss: 2.0827 - val_accuracy: 0.6383
Epoch 124/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0717 - accuracy: 0.9790 - val_loss: 2.0746 - val_accuracy: 0.6411
Epoch 125/300
225/225 [==============================] - 12s 51ms/step - loss: 0.0653 - accuracy: 0.9803 - val_loss: 2.1439 - val_accuracy: 0.6395
Epoch 126/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0742 - accuracy: 0.9778 - val_loss: 2.1047 - val_accuracy: 0.6386
Epoch 127/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0680 - accuracy: 0.9796 - val_loss: 2.0742 - val_accuracy: 0.6397
Epoch 128/300
225/225 [==============================] - 12s 51ms/step - loss: 0.0698 - accuracy: 0.9793 - val_loss: 2.1104 - val_accuracy: 0.6434
Epoch 129/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0683 - accuracy: 0.9794 - val_loss: 2.1281 - val_accuracy: 0.6439
Epoch 130/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0706 - accuracy: 0.9782 - val_loss: 2.0829 - val_accuracy: 0.6333
Epoch 131/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0644 - accuracy: 0.9818 - val_loss: 2.1424 - val_accuracy: 0.6389
Epoch 132/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0687 - accuracy: 0.9789 - val_loss: 2.1621 - val_accuracy: 0.6381
Epoch 133/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0708 - accuracy: 0.9797 - val_loss: 2.1208 - val_accuracy: 0.6305
Epoch 134/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0681 - accuracy: 0.9787 - val_loss: 2.1575 - val_accuracy: 0.6386
Epoch 135/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0582 - accuracy: 0.9821 - val_loss: 2.1859 - val_accuracy: 0.6372
Epoch 136/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0646 - accuracy: 0.9802 - val_loss: 2.2177 - val_accuracy: 0.6350
Epoch 137/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0634 - accuracy: 0.9809 - val_loss: 2.2057 - val_accuracy: 0.6286
Epoch 138/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0602 - accuracy: 0.9819 - val_loss: 2.2204 - val_accuracy: 0.6369
Epoch 139/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0561 - accuracy: 0.9835 - val_loss: 2.1973 - val_accuracy: 0.6314
Epoch 140/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0651 - accuracy: 0.9811 - val_loss: 2.2462 - val_accuracy: 0.6289
Epoch 141/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0620 - accuracy: 0.9814 - val_loss: 2.2028 - val_accuracy: 0.6325
Epoch 142/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0600 - accuracy: 0.9816 - val_loss: 2.2215 - val_accuracy: 0.6319
Epoch 143/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0620 - accuracy: 0.9810 - val_loss: 2.1501 - val_accuracy: 0.6378
Epoch 144/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0614 - accuracy: 0.9807 - val_loss: 2.1801 - val_accuracy: 0.6344
Epoch 145/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0586 - accuracy: 0.9829 - val_loss: 2.2703 - val_accuracy: 0.6342
Epoch 146/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0642 - accuracy: 0.9813 - val_loss: 2.2584 - val_accuracy: 0.6350
Epoch 147/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0586 - accuracy: 0.9826 - val_loss: 2.2167 - val_accuracy: 0.6311
Epoch 148/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0608 - accuracy: 0.9817 - val_loss: 2.1515 - val_accuracy: 0.6425
Epoch 149/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0569 - accuracy: 0.9833 - val_loss: 2.2746 - val_accuracy: 0.6347
Epoch 150/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0600 - accuracy: 0.9825 - val_loss: 2.1647 - val_accuracy: 0.6311
Epoch 151/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0631 - accuracy: 0.9817 - val_loss: 2.1247 - val_accuracy: 0.6395
Epoch 152/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0606 - accuracy: 0.9819 - val_loss: 2.1662 - val_accuracy: 0.6330
Epoch 153/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0582 - accuracy: 0.9817 - val_loss: 2.2161 - val_accuracy: 0.6397
Epoch 154/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0557 - accuracy: 0.9825 - val_loss: 2.2287 - val_accuracy: 0.6408
Epoch 155/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0523 - accuracy: 0.9846 - val_loss: 2.2601 - val_accuracy: 0.6408
Epoch 156/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0588 - accuracy: 0.9834 - val_loss: 2.2215 - val_accuracy: 0.6383
Epoch 157/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0614 - accuracy: 0.9817 - val_loss: 2.1542 - val_accuracy: 0.6358
Epoch 158/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0588 - accuracy: 0.9824 - val_loss: 2.2097 - val_accuracy: 0.6375
Epoch 159/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0612 - accuracy: 0.9816 - val_loss: 2.2138 - val_accuracy: 0.6342
Epoch 160/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0577 - accuracy: 0.9830 - val_loss: 2.1439 - val_accuracy: 0.6339
Epoch 161/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0591 - accuracy: 0.9825 - val_loss: 2.1764 - val_accuracy: 0.6442
Epoch 162/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0567 - accuracy: 0.9825 - val_loss: 2.1807 - val_accuracy: 0.6386
Epoch 163/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0574 - accuracy: 0.9820 - val_loss: 2.2214 - val_accuracy: 0.6397
Epoch 164/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0558 - accuracy: 0.9833 - val_loss: 2.1890 - val_accuracy: 0.6383
Epoch 165/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0547 - accuracy: 0.9834 - val_loss: 2.2808 - val_accuracy: 0.6372
Epoch 166/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0575 - accuracy: 0.9834 - val_loss: 2.2160 - val_accuracy: 0.6322
Epoch 167/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0566 - accuracy: 0.9826 - val_loss: 2.2669 - val_accuracy: 0.6336
Epoch 168/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0514 - accuracy: 0.9844 - val_loss: 2.2012 - val_accuracy: 0.6358
Epoch 169/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0565 - accuracy: 0.9828 - val_loss: 2.2059 - val_accuracy: 0.6408
Epoch 170/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0549 - accuracy: 0.9838 - val_loss: 2.2073 - val_accuracy: 0.6361
Epoch 171/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0500 - accuracy: 0.9852 - val_loss: 2.2318 - val_accuracy: 0.6358
Epoch 172/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0526 - accuracy: 0.9847 - val_loss: 2.2460 - val_accuracy: 0.6344
Epoch 173/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0489 - accuracy: 0.9857 - val_loss: 2.3421 - val_accuracy: 0.6372
Epoch 174/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0586 - accuracy: 0.9828 - val_loss: 2.2185 - val_accuracy: 0.6272
Epoch 175/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0566 - accuracy: 0.9831 - val_loss: 2.2919 - val_accuracy: 0.6406
Epoch 176/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0511 - accuracy: 0.9848 - val_loss: 2.1883 - val_accuracy: 0.6395
Epoch 177/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0490 - accuracy: 0.9858 - val_loss: 2.2383 - val_accuracy: 0.6330
Epoch 178/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0552 - accuracy: 0.9835 - val_loss: 2.2067 - val_accuracy: 0.6286
Epoch 179/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0491 - accuracy: 0.9855 - val_loss: 2.2404 - val_accuracy: 0.6330
Epoch 180/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0492 - accuracy: 0.9850 - val_loss: 2.2542 - val_accuracy: 0.6308
Epoch 181/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0481 - accuracy: 0.9855 - val_loss: 2.2668 - val_accuracy: 0.6344
Epoch 182/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0532 - accuracy: 0.9845 - val_loss: 2.2484 - val_accuracy: 0.6400
Epoch 183/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0498 - accuracy: 0.9855 - val_loss: 2.2134 - val_accuracy: 0.6375
Epoch 184/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0492 - accuracy: 0.9853 - val_loss: 2.2716 - val_accuracy: 0.6369
Epoch 185/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0485 - accuracy: 0.9849 - val_loss: 2.2833 - val_accuracy: 0.6353
Epoch 186/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0521 - accuracy: 0.9836 - val_loss: 2.2194 - val_accuracy: 0.6264
Epoch 187/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0501 - accuracy: 0.9854 - val_loss: 2.2967 - val_accuracy: 0.6408
Epoch 188/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0487 - accuracy: 0.9847 - val_loss: 2.3413 - val_accuracy: 0.6283
Epoch 189/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0518 - accuracy: 0.9842 - val_loss: 2.2388 - val_accuracy: 0.6361
Epoch 190/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0522 - accuracy: 0.9850 - val_loss: 2.2352 - val_accuracy: 0.6244
Epoch 191/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0475 - accuracy: 0.9858 - val_loss: 2.2931 - val_accuracy: 0.6291
Epoch 192/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0481 - accuracy: 0.9858 - val_loss: 2.2158 - val_accuracy: 0.6392
Epoch 193/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0494 - accuracy: 0.9857 - val_loss: 2.2561 - val_accuracy: 0.6417
Epoch 194/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0488 - accuracy: 0.9858 - val_loss: 2.1997 - val_accuracy: 0.6372
Epoch 195/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0433 - accuracy: 0.9873 - val_loss: 2.2488 - val_accuracy: 0.6367
Epoch 196/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0501 - accuracy: 0.9851 - val_loss: 2.3077 - val_accuracy: 0.6350
Epoch 197/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0516 - accuracy: 0.9846 - val_loss: 2.2033 - val_accuracy: 0.6400
Epoch 198/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0470 - accuracy: 0.9854 - val_loss: 2.2233 - val_accuracy: 0.6339
Epoch 199/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0459 - accuracy: 0.9864 - val_loss: 2.2962 - val_accuracy: 0.6383
Epoch 200/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0503 - accuracy: 0.9855 - val_loss: 2.2529 - val_accuracy: 0.6456
Epoch 201/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0451 - accuracy: 0.9866 - val_loss: 2.3106 - val_accuracy: 0.6375
Epoch 202/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0457 - accuracy: 0.9858 - val_loss: 2.3243 - val_accuracy: 0.6322
Epoch 203/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0461 - accuracy: 0.9862 - val_loss: 2.3223 - val_accuracy: 0.6266
Epoch 204/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0491 - accuracy: 0.9853 - val_loss: 2.3112 - val_accuracy: 0.6386
Epoch 205/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0469 - accuracy: 0.9857 - val_loss: 2.3348 - val_accuracy: 0.6336
Epoch 206/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0455 - accuracy: 0.9853 - val_loss: 2.3487 - val_accuracy: 0.6353
Epoch 207/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0456 - accuracy: 0.9860 - val_loss: 2.3160 - val_accuracy: 0.6406
Epoch 208/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0427 - accuracy: 0.9879 - val_loss: 2.3298 - val_accuracy: 0.6361
Epoch 209/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0498 - accuracy: 0.9852 - val_loss: 2.3147 - val_accuracy: 0.6383
Epoch 210/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0438 - accuracy: 0.9871 - val_loss: 2.3767 - val_accuracy: 0.6381
Epoch 211/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0447 - accuracy: 0.9866 - val_loss: 2.3486 - val_accuracy: 0.6342
Epoch 212/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0465 - accuracy: 0.9864 - val_loss: 2.2854 - val_accuracy: 0.6408
Epoch 213/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0439 - accuracy: 0.9867 - val_loss: 2.3450 - val_accuracy: 0.6403
Epoch 214/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0461 - accuracy: 0.9859 - val_loss: 2.3276 - val_accuracy: 0.6375
Epoch 215/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0475 - accuracy: 0.9861 - val_loss: 2.3022 - val_accuracy: 0.6361
Epoch 216/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0466 - accuracy: 0.9859 - val_loss: 2.3119 - val_accuracy: 0.6414
Epoch 217/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0424 - accuracy: 0.9873 - val_loss: 2.3563 - val_accuracy: 0.6411
Epoch 218/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0448 - accuracy: 0.9861 - val_loss: 2.2864 - val_accuracy: 0.6381
Epoch 219/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0453 - accuracy: 0.9868 - val_loss: 2.3385 - val_accuracy: 0.6367
Epoch 220/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0399 - accuracy: 0.9875 - val_loss: 2.3103 - val_accuracy: 0.6330
Epoch 221/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0489 - accuracy: 0.9847 - val_loss: 2.3312 - val_accuracy: 0.6383
Epoch 222/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0406 - accuracy: 0.9878 - val_loss: 2.3398 - val_accuracy: 0.6436
Epoch 223/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0438 - accuracy: 0.9861 - val_loss: 2.2538 - val_accuracy: 0.6434
Epoch 224/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0417 - accuracy: 0.9878 - val_loss: 2.3213 - val_accuracy: 0.6425
Epoch 225/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0438 - accuracy: 0.9873 - val_loss: 2.3255 - val_accuracy: 0.6375
Epoch 226/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0419 - accuracy: 0.9881 - val_loss: 2.2865 - val_accuracy: 0.6420
Epoch 227/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0472 - accuracy: 0.9863 - val_loss: 2.2940 - val_accuracy: 0.6447
Epoch 228/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0405 - accuracy: 0.9875 - val_loss: 2.3599 - val_accuracy: 0.6417
Epoch 229/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0463 - accuracy: 0.9866 - val_loss: 2.3155 - val_accuracy: 0.6456
Epoch 230/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0413 - accuracy: 0.9879 - val_loss: 2.3786 - val_accuracy: 0.6420
Epoch 231/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0472 - accuracy: 0.9862 - val_loss: 2.2800 - val_accuracy: 0.6422
Epoch 232/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0392 - accuracy: 0.9887 - val_loss: 2.3069 - val_accuracy: 0.6408
Epoch 233/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0380 - accuracy: 0.9881 - val_loss: 2.4034 - val_accuracy: 0.6336
Epoch 234/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0445 - accuracy: 0.9866 - val_loss: 2.3503 - val_accuracy: 0.6356
Epoch 235/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0395 - accuracy: 0.9879 - val_loss: 2.3150 - val_accuracy: 0.6378
Epoch 236/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0411 - accuracy: 0.9874 - val_loss: 2.3908 - val_accuracy: 0.6406
Epoch 237/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0430 - accuracy: 0.9870 - val_loss: 2.3426 - val_accuracy: 0.6411
Epoch 238/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0397 - accuracy: 0.9874 - val_loss: 2.3922 - val_accuracy: 0.6439
Epoch 239/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0421 - accuracy: 0.9879 - val_loss: 2.3286 - val_accuracy: 0.6378
Epoch 240/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0413 - accuracy: 0.9869 - val_loss: 2.3374 - val_accuracy: 0.6434
Epoch 241/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0391 - accuracy: 0.9884 - val_loss: 2.3148 - val_accuracy: 0.6422
Epoch 242/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0443 - accuracy: 0.9875 - val_loss: 2.3660 - val_accuracy: 0.6291
Epoch 243/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0451 - accuracy: 0.9865 - val_loss: 2.3502 - val_accuracy: 0.6428
Epoch 244/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0397 - accuracy: 0.9875 - val_loss: 2.3744 - val_accuracy: 0.6408
Epoch 245/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0379 - accuracy: 0.9891 - val_loss: 2.3563 - val_accuracy: 0.6386
Epoch 246/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0441 - accuracy: 0.9870 - val_loss: 2.3149 - val_accuracy: 0.6317
Epoch 247/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0429 - accuracy: 0.9870 - val_loss: 2.3471 - val_accuracy: 0.6369
Epoch 248/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0410 - accuracy: 0.9874 - val_loss: 2.3472 - val_accuracy: 0.6414
Epoch 249/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0378 - accuracy: 0.9879 - val_loss: 2.3638 - val_accuracy: 0.6450
Epoch 250/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0421 - accuracy: 0.9872 - val_loss: 2.3320 - val_accuracy: 0.6406
Epoch 251/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0446 - accuracy: 0.9865 - val_loss: 2.3190 - val_accuracy: 0.6300
Epoch 252/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0360 - accuracy: 0.9894 - val_loss: 2.3917 - val_accuracy: 0.6375
Epoch 253/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0380 - accuracy: 0.9880 - val_loss: 2.4073 - val_accuracy: 0.6227
Epoch 254/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0364 - accuracy: 0.9891 - val_loss: 2.4112 - val_accuracy: 0.6305
Epoch 255/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0409 - accuracy: 0.9878 - val_loss: 2.3690 - val_accuracy: 0.6342
Epoch 256/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0397 - accuracy: 0.9878 - val_loss: 2.3989 - val_accuracy: 0.6344
Epoch 257/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0386 - accuracy: 0.9882 - val_loss: 2.3967 - val_accuracy: 0.6431
Epoch 258/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0433 - accuracy: 0.9867 - val_loss: 2.3316 - val_accuracy: 0.6364
Epoch 259/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0401 - accuracy: 0.9877 - val_loss: 2.4198 - val_accuracy: 0.6397
Epoch 260/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0357 - accuracy: 0.9889 - val_loss: 2.4506 - val_accuracy: 0.6367
Epoch 261/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0386 - accuracy: 0.9884 - val_loss: 2.3695 - val_accuracy: 0.6353
Epoch 262/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0387 - accuracy: 0.9889 - val_loss: 2.4201 - val_accuracy: 0.6358
Epoch 263/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0365 - accuracy: 0.9887 - val_loss: 2.4978 - val_accuracy: 0.6280
Epoch 264/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0409 - accuracy: 0.9877 - val_loss: 2.5059 - val_accuracy: 0.6305
Epoch 265/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0384 - accuracy: 0.9882 - val_loss: 2.3551 - val_accuracy: 0.6344
Epoch 266/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0363 - accuracy: 0.9890 - val_loss: 2.4170 - val_accuracy: 0.6314
Epoch 267/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0381 - accuracy: 0.9876 - val_loss: 2.4324 - val_accuracy: 0.6264
Epoch 268/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0397 - accuracy: 0.9882 - val_loss: 2.4905 - val_accuracy: 0.6300
Epoch 269/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0395 - accuracy: 0.9883 - val_loss: 2.3740 - val_accuracy: 0.6395
Epoch 270/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0342 - accuracy: 0.9893 - val_loss: 2.4664 - val_accuracy: 0.6375
Epoch 271/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0393 - accuracy: 0.9882 - val_loss: 2.4078 - val_accuracy: 0.6317
Epoch 272/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0362 - accuracy: 0.9891 - val_loss: 2.4683 - val_accuracy: 0.6344
Epoch 273/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0404 - accuracy: 0.9879 - val_loss: 2.3521 - val_accuracy: 0.6300
Epoch 274/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0386 - accuracy: 0.9873 - val_loss: 2.4072 - val_accuracy: 0.6420
Epoch 275/300
225/225 [==============================] - 11s 51ms/step - loss: 0.0377 - accuracy: 0.9871 - val_loss: 2.4219 - val_accuracy: 0.6353
Epoch 276/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0372 - accuracy: 0.9887 - val_loss: 2.4397 - val_accuracy: 0.6356
Epoch 277/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0325 - accuracy: 0.9898 - val_loss: 2.4976 - val_accuracy: 0.6314
Epoch 278/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0365 - accuracy: 0.9888 - val_loss: 2.4258 - val_accuracy: 0.6255
Epoch 279/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0376 - accuracy: 0.9887 - val_loss: 2.4409 - val_accuracy: 0.6417
Epoch 280/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0332 - accuracy: 0.9893 - val_loss: 2.5175 - val_accuracy: 0.6353
Epoch 281/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0353 - accuracy: 0.9898 - val_loss: 2.4888 - val_accuracy: 0.6328
Epoch 282/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0392 - accuracy: 0.9882 - val_loss: 2.4012 - val_accuracy: 0.6344
Epoch 283/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0357 - accuracy: 0.9892 - val_loss: 2.4574 - val_accuracy: 0.6378
Epoch 284/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0346 - accuracy: 0.9894 - val_loss: 2.4106 - val_accuracy: 0.6392
Epoch 285/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0375 - accuracy: 0.9886 - val_loss: 2.4018 - val_accuracy: 0.6286
Epoch 286/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0388 - accuracy: 0.9882 - val_loss: 2.4026 - val_accuracy: 0.6403
Epoch 287/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0375 - accuracy: 0.9890 - val_loss: 2.3855 - val_accuracy: 0.6411
Epoch 288/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0378 - accuracy: 0.9884 - val_loss: 2.4093 - val_accuracy: 0.6408
Epoch 289/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0334 - accuracy: 0.9900 - val_loss: 2.3785 - val_accuracy: 0.6417
Epoch 290/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0346 - accuracy: 0.9897 - val_loss: 2.3888 - val_accuracy: 0.6400
Epoch 291/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0352 - accuracy: 0.9887 - val_loss: 2.4243 - val_accuracy: 0.6336
Epoch 292/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0387 - accuracy: 0.9890 - val_loss: 2.4244 - val_accuracy: 0.6428
Epoch 293/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0340 - accuracy: 0.9893 - val_loss: 2.4464 - val_accuracy: 0.6289
Epoch 294/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0377 - accuracy: 0.9886 - val_loss: 2.3623 - val_accuracy: 0.6403
Epoch 295/300
225/225 [==============================] - 11s 50ms/step - loss: 0.0350 - accuracy: 0.9888 - val_loss: 2.4207 - val_accuracy: 0.6375
Epoch 296/300
225/225 [==============================] - 12s 51ms/step - loss: 0.0359 - accuracy: 0.9891 - val_loss: 2.4476 - val_accuracy: 0.6308
Epoch 297/300
225/225 [==============================] - 12s 52ms/step - loss: 0.0352 - accuracy: 0.9890 - val_loss: 2.3930 - val_accuracy: 0.6392
Epoch 298/300
225/225 [==============================] - 12s 51ms/step - loss: 0.0364 - accuracy: 0.9890 - val_loss: 2.3780 - val_accuracy: 0.6381
Epoch 299/300
225/225 [==============================] - 12s 52ms/step - loss: 0.0378 - accuracy: 0.9885 - val_loss: 2.4243 - val_accuracy: 0.6400
Epoch 300/300
225/225 [==============================] - 12s 52ms/step - loss: 0.0340 - accuracy: 0.9898 - val_loss: 2.3963 - val_accuracy: 0.6383
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span> <span class="n">y_pred</span> <span class="o">=</span> <span class="n">model</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">xtest</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">newpred</span><span class="o">=</span><span class="p">[]</span>
<span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">y_pred</span><span class="p">)):</span>
  <span class="n">newpred</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">y_pred</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">argmax</span><span class="p">())</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">model</span><span class="o">.</span><span class="n">evaluate</span><span class="p">(</span><span class="n">xtest</span><span class="p">,</span><span class="n">ytest</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>113/113 [==============================] - 1s 6ms/step - loss: 2.2723 - accuracy: 0.6450
</pre>
</div>
</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[&nbsp;]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>[2.2723379135131836, 0.645026445388794]</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#displaying the confusion matrix</span>
<span class="kn">from</span> <span class="nn">sklearn</span> <span class="k">import</span> <span class="n">metrics</span>
<span class="kn">from</span> <span class="nn">sklearn.metrics</span> <span class="k">import</span> <span class="n">confusion_matrix</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>

<span class="n">classif</span><span class="o">=</span><span class="n">metrics</span><span class="o">.</span><span class="n">classification_report</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span><span class="n">newpred</span><span class="p">,</span><span class="n">target_names</span><span class="o">=</span><span class="n">expression</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">classif</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>              precision    recall  f1-score   support

       Angry       0.57      0.56      0.56       491
     Disgust       0.75      0.65      0.70        55
        Fear       0.53      0.47      0.50       528
       Happy       0.82      0.85      0.83       879
         Sad       0.48      0.53      0.51       594
    Surprise       0.78      0.77      0.78       416
     Neutral       0.60      0.60      0.60       626

    accuracy                           0.65      3589
   macro avg       0.65      0.63      0.64      3589
weighted avg       0.64      0.65      0.64      3589

</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">saved1_keras_model_filepath</span> <span class="o">=</span> <span class="s1">&#39;./modelown65%.h5&#39;</span>
<span class="n">model</span><span class="o">.</span><span class="n">save</span><span class="p">(</span><span class="n">saved1_keras_model_filepath</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">y_test</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[&nbsp;]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>32298    0
32299    5
32300    6
32301    4
32302    2
        ..
35882    6
35883    3
35884    0
35885    3
35886    2
Name: emotion, Length: 3589, dtype: int64</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">cv2</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">from</span> <span class="nn">time</span> <span class="k">import</span> <span class="n">sleep</span>
<span class="kn">from</span> <span class="nn">keras.preprocessing.image</span> <span class="k">import</span> <span class="n">img_to_array</span>

<span class="n">face_classifier</span> <span class="o">=</span> <span class="n">cv2</span><span class="o">.</span><span class="n">CascadeClassifier</span><span class="p">(</span><span class="s1">&#39;./Haarcascades/haarcascade_frontalface_default.xml&#39;</span><span class="p">)</span>

<span class="k">def</span> <span class="nf">face_detector</span><span class="p">(</span><span class="n">img</span><span class="p">):</span>
    <span class="c1"># Convert image to grayscale</span>
    <span class="n">gray</span> <span class="o">=</span> <span class="n">cv2</span><span class="o">.</span><span class="n">cvtColor</span><span class="p">(</span><span class="n">img</span><span class="p">,</span><span class="n">cv2</span><span class="o">.</span><span class="n">COLOR_BGR2GRAY</span><span class="p">)</span>
    <span class="n">faces</span> <span class="o">=</span> <span class="n">face_classifier</span><span class="o">.</span><span class="n">detectMultiScale</span><span class="p">(</span><span class="n">gray</span><span class="p">,</span> <span class="mf">1.3</span><span class="p">,</span> <span class="mi">5</span><span class="p">)</span>
    <span class="k">if</span> <span class="n">faces</span> <span class="ow">is</span> <span class="p">():</span>
        <span class="k">return</span> <span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">),</span> <span class="n">np</span><span class="o">.</span><span class="n">zeros</span><span class="p">((</span><span class="mi">48</span><span class="p">,</span><span class="mi">48</span><span class="p">),</span> <span class="n">np</span><span class="o">.</span><span class="n">uint8</span><span class="p">),</span> <span class="n">img</span>
    
    <span class="k">for</span> <span class="p">(</span><span class="n">x</span><span class="p">,</span><span class="n">y</span><span class="p">,</span><span class="n">w</span><span class="p">,</span><span class="n">h</span><span class="p">)</span> <span class="ow">in</span> <span class="n">faces</span><span class="p">:</span>
        <span class="n">cv2</span><span class="o">.</span><span class="n">rectangle</span><span class="p">(</span><span class="n">img</span><span class="p">,(</span><span class="n">x</span><span class="p">,</span><span class="n">y</span><span class="p">),(</span><span class="n">x</span><span class="o">+</span><span class="n">w</span><span class="p">,</span><span class="n">y</span><span class="o">+</span><span class="n">h</span><span class="p">),(</span><span class="mi">255</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">),</span><span class="mi">2</span><span class="p">)</span>
        <span class="n">roi_gray</span> <span class="o">=</span> <span class="n">gray</span><span class="p">[</span><span class="n">y</span><span class="p">:</span><span class="n">y</span><span class="o">+</span><span class="n">h</span><span class="p">,</span> <span class="n">x</span><span class="p">:</span><span class="n">x</span><span class="o">+</span><span class="n">w</span><span class="p">]</span>

    <span class="k">try</span><span class="p">:</span>
        <span class="n">roi_gray</span> <span class="o">=</span> <span class="n">cv2</span><span class="o">.</span><span class="n">resize</span><span class="p">(</span><span class="n">roi_gray</span><span class="p">,</span> <span class="p">(</span><span class="mi">48</span><span class="p">,</span> <span class="mi">48</span><span class="p">),</span> <span class="n">interpolation</span> <span class="o">=</span> <span class="n">cv2</span><span class="o">.</span><span class="n">INTER_AREA</span><span class="p">)</span>
    <span class="k">except</span><span class="p">:</span>
        <span class="k">return</span> <span class="p">(</span><span class="n">x</span><span class="p">,</span><span class="n">w</span><span class="p">,</span><span class="n">y</span><span class="p">,</span><span class="n">h</span><span class="p">),</span> <span class="n">np</span><span class="o">.</span><span class="n">zeros</span><span class="p">((</span><span class="mi">48</span><span class="p">,</span><span class="mi">48</span><span class="p">),</span> <span class="n">np</span><span class="o">.</span><span class="n">uint8</span><span class="p">),</span> <span class="n">img</span>
    <span class="k">return</span> <span class="p">(</span><span class="n">x</span><span class="p">,</span><span class="n">w</span><span class="p">,</span><span class="n">y</span><span class="p">,</span><span class="n">h</span><span class="p">),</span> <span class="n">roi_gray</span><span class="p">,</span> <span class="n">img</span>

<span class="n">cap</span> <span class="o">=</span> <span class="n">cv2</span><span class="o">.</span><span class="n">VideoCapture</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>

<span class="k">while</span> <span class="kc">True</span><span class="p">:</span>

    <span class="n">ret</span><span class="p">,</span> <span class="n">frame</span> <span class="o">=</span> <span class="n">cap</span><span class="o">.</span><span class="n">read</span><span class="p">()</span>
    <span class="n">rect</span><span class="p">,</span> <span class="n">face</span><span class="p">,</span> <span class="n">image</span> <span class="o">=</span> <span class="n">face_detector</span><span class="p">(</span><span class="n">frame</span><span class="p">)</span>
    <span class="k">if</span> <span class="n">np</span><span class="o">.</span><span class="n">sum</span><span class="p">([</span><span class="n">face</span><span class="p">])</span> <span class="o">!=</span> <span class="mf">0.0</span><span class="p">:</span>
        <span class="n">roi</span> <span class="o">=</span> <span class="n">face</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s2">&quot;float&quot;</span><span class="p">)</span> <span class="o">/</span> <span class="mf">255.0</span>
        <span class="n">roi</span> <span class="o">=</span> <span class="n">img_to_array</span><span class="p">(</span><span class="n">roi</span><span class="p">)</span>
        <span class="n">roi</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">expand_dims</span><span class="p">(</span><span class="n">roi</span><span class="p">,</span> <span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>

        <span class="c1"># make a prediction on the ROI, then lookup the class</span>
        <span class="n">preds</span> <span class="o">=</span> <span class="n">classifier</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">roi</span><span class="p">)[</span><span class="mi">0</span><span class="p">]</span>
        <span class="n">label</span> <span class="o">=</span> <span class="n">class_labels</span><span class="p">[</span><span class="n">preds</span><span class="o">.</span><span class="n">argmax</span><span class="p">()]</span>  
        <span class="n">label_position</span> <span class="o">=</span> <span class="p">(</span><span class="n">rect</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span> <span class="o">+</span> <span class="nb">int</span><span class="p">((</span><span class="n">rect</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span><span class="o">/</span><span class="mi">2</span><span class="p">)),</span> <span class="n">rect</span><span class="p">[</span><span class="mi">2</span><span class="p">]</span> <span class="o">+</span> <span class="mi">25</span><span class="p">)</span>
        <span class="n">cv2</span><span class="o">.</span><span class="n">putText</span><span class="p">(</span><span class="n">image</span><span class="p">,</span> <span class="n">label</span><span class="p">,</span> <span class="n">label_position</span> <span class="p">,</span> <span class="n">cv2</span><span class="o">.</span><span class="n">FONT_HERSHEY_SIMPLEX</span><span class="p">,</span><span class="mi">2</span><span class="p">,</span> <span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">255</span><span class="p">,</span><span class="mi">0</span><span class="p">),</span> <span class="mi">3</span><span class="p">)</span>
    <span class="k">else</span><span class="p">:</span>
        <span class="n">cv2</span><span class="o">.</span><span class="n">putText</span><span class="p">(</span><span class="n">image</span><span class="p">,</span> <span class="s2">&quot;No Face Found&quot;</span><span class="p">,</span> <span class="p">(</span><span class="mi">20</span><span class="p">,</span> <span class="mi">60</span><span class="p">)</span> <span class="p">,</span> <span class="n">cv2</span><span class="o">.</span><span class="n">FONT_HERSHEY_SIMPLEX</span><span class="p">,</span><span class="mi">2</span><span class="p">,</span> <span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">255</span><span class="p">,</span><span class="mi">0</span><span class="p">),</span> <span class="mi">3</span><span class="p">)</span>
        
    <span class="n">cv2</span><span class="o">.</span><span class="n">imshow</span><span class="p">(</span><span class="s1">&#39;All&#39;</span><span class="p">,</span> <span class="n">image</span><span class="p">)</span>
    <span class="k">if</span> <span class="n">cv2</span><span class="o">.</span><span class="n">waitKey</span><span class="p">(</span><span class="mi">1</span><span class="p">)</span> <span class="o">==</span> <span class="mi">13</span><span class="p">:</span> <span class="c1">#13 is the Enter Key</span>
        <span class="k">break</span>
        
<span class="n">cap</span><span class="o">.</span><span class="n">release</span><span class="p">()</span>
<span class="n">cv2</span><span class="o">.</span><span class="n">destroyAllWindows</span><span class="p">()</span>      
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span> 
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[58]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span> 
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[58]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>True</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span> 
</pre></div>

    </div>
</div>
</div>

</div>
    </div>
  </div>
</body>

 


</html>

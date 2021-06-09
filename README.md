# Css Print Framework

Simply include the right stylesheet(s) in your html and load it only for a printer.

```bash
$ npm install css-print-framework
```

## Basic Usage

Load css into `<head>` like this:

```html
<!-- Load print.css for happy printing -->
<link rel="stylesheet" href="print.css">

<!-- Set page size here: A5, A4 or A3 -->
<!-- Set also "landscape" if you need -->
<style>@page { size: A5 }</style>
```

Set the class of `<body>` and also set "sheet" for each sheet.

```html
<!-- Set "A5", "A4" or "A3" for class name -->
<!-- Set also "landscape" if you need -->
<body class="A5">

  <!-- Each sheet element should have the class "sheet" -->
  <!-- "padding-**mm" is optional: you can set 10, 15, 20 or 25 -->
  <section class="sheet padding-10mm">

    <!-- Write HTML just like a web page -->
    <article>This is an A5 document.</article>

  </section>

  <!-- The title will be on a new page -->
  <h1 class="break-before">My title</h1>

  <p class="break-after">I will break after this paragraph</p>
  <!-- Break here, the next paragraph will be on a new page -->
  <p>I am on a new page</p>

  <!-- Avoid break inside -->
  <div class="avoid-break-inside">
    <img src="image.png" />
    <p>I really don't want this part to be cut</p>
  </div>

</body>
```

All available page sizes is listed below:

- A5, A5 landscape
- A4, A4 landscape
- A3, A3 landscape
- letter, letter landscape
- legal, legal landscape

### Comparisons

type | expression | learning cost | editable | in-browser | multipage
:-- | :-- | :-- | :-- | :-- | :--
HTML | Enough | already known | No | OK | ~100 pages \*
SVG | Enough | not so difficult | No | OK |
PDF | Perfect | difficult | No | NG | no limit \*\*
Excel | Not cool | *sigh* | Yes | NG | uncontrollable


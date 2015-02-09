remarkable-classy
===

This is a plugin for the [remarkable](https://github.com/jonschlinkert/remarkable) markdown parser. It works equally well on the server (node.js/io.js) and in the browser.

Need to style some text written with markdown but are lacking that extra *oomph*? Plug in `remarkable-classy` to make your markup remarkable *and* classy.

Install (server)
---

```
$ npm install --save remarkable-classy
```

Install (browser)
---

```
$ bower install --save remarkable-classy
```

Plug
---

On the server, or using Browserify:

```js
var classy = require("remarkable-classy"),
  Remarkable = require("remarkable"),
  md = new Remarkable();

md.use(classy);
```

For plain old browser usage, without Browserify, just include the JavaScript files for remarkable and remarkable-classy first:

```html
<script src="/bower_components/remarkable/dist/remarkable.min.js"></script>
<script src="/bower_components/remarkable-classy/index.js"></script>
```

Then, in your JavaScript code, use the global `classy` name with the global `Remarkable` name:

```js
var md = new Remarkable();
md.use(classy);
```



Use
---

Anything in curly brackets (`{}`) gets interpreted as a class string for that element.

```
This is paragraph 1.

This is paragraph 2 and I wish there was a way to make it blue.
{blue}
```

converts to:

```html
<p>This is paragraph 1.</p>

<p class="blue">This is paragraph 2 and I wish there was a way to make it blue.</p>
```

Go crazy (or not)
---

```
# All kinds of headings work! {classy}

## Atx... {classy} ##

... and Setext {classy}
---

_em {classy}_ and __strong {classy}__ are supported as well.
{classy}

- so
- are
- ul tags
{classy}

> blockquotes?
> {classy}
>
> why not!
{classy}
```

converts to:

```html
<h1 class="classy">All kinds of headings work!</h1>

<h2 class="classy">Atx...</h2>

<h2 class="classy">... and Setext</h2>

<p class="classy"><em class="classy">em</em> and <strong class="classy">strong</strong> are supported as well.

<ul class="classy">
	<li>so</li>
	<li>are</li>
	<li>ul tags</li>
</ul>

<blockquote class="classy">
	<p class="classy">blockquotes?</p>
	<p>why not!</p>
</blockquote>
```

Very classy indeed!

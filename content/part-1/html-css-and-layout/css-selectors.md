+++
title="CSS Selectors and Specificity"
weight=2
+++

We've seen that we use HTML to markup content, to give that content structure and meaning, and that we use CSS to style and present the content.

We've seen that we can use different CSS selectors to target the HTML elements that we want particular CSS rules to apply to. It is actually possible to write multiple CSS rules that all target the same element. For example, if we have a webpage with the following content:

```html
<p class="warning"></p>
```

and a CSS file with the following rules:

```css
p {
    color: red;
}

.warning {
    color: blue;
}
```

Which CSS declaration will be applied to our code? How does a web browser work out which rules to apply and which to ignore?

There are a couple of processes that help the browser determine which rules to apply. Firstly, CSS files are read from top to bottom. Rules that are further down in the file overwrite rules that are closer to the top. So, for example, if we have a webpage with the following content:

```html
<p class="warning">here is some text</p>
```

and a CSS file with the following rules:

```css
p {
    color: red;
}

p {
    color: blue;
}
```

The text in the paragraph will end up blue, as the second rule overwrites the first as it is further down in the style sheet. You can see this example below:

<p class="codepen" data-height="265" data-theme-id="0" data-default-tab="css,result" data-user="martinjc" data-slug-hash="BaBbygv" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="CSS Order">
  <span>See the Pen <a href="https://codepen.io/martinjc/pen/BaBbygv">
  CSS Order</a> by Martin Chorley (<a href="https://codepen.io/martinjc">@martinjc</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

However, the order is not the only thing that determines which rules should apply. There is also the concept of 'Specificity'.

## Specificity

Specificity is the mechanism that allows Web Browsers to determine which CSS rule should be applied to an element. The rules for specificity are simple to follow.

For each CSS selector that matches a given HTML element:

-   Each element selector is given a value of 0-0-1
-   Each class or pseudo-class selector is given a value of 0-1-0
-   Each ID selector is given a value of 1-0-0

The values are added together, and the rule with the highest specifity is the one that is applied to the element.

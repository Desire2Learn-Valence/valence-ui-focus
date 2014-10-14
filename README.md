#VUI Focus [![Build Status](https://travis-ci.org/Desire2Learn-Valence/valence-ui-focus.svg?branch=master)](https://travis-ci.org/Desire2Learn-Valence/valence-ui-focus)

This library contains uncompiled LESS and compiled CSS which can be used to
apply an outline style to elements when they receive focus. This accessibility
feature helps identify to the user which element currently has focus.

In most cases, you'll want to use this library on elements which do not already
have a visible or obvious focus indicator. This typically includes links,
checkboxes and radio inputs.

##Usage

Install as a development dependency:

```shell
npm install --save-dev vui-focus
```

Import the library into your LESS file:

```css
@import 'node_modules/vui-focus/dist/focus'
```

##LESS Mixin

In LESS, call `#vui.focusOutline()` mixin from your CSS selector, usually with
the `focus` pseudo-selector applied:

```css
a:focus {
  #vui.focusOutline();
}
```

The outline width, color, style, and offset values can also be overriden when calling the LESS mixin:

```css
a:focus {
  #vui.focusOutline(
    @outlineWidth: 2px,
    @outlineColor: #00FF00,
    @outlineStyle: solid,
    @outlineOffset: 2px
  );
}
```

You can also access the corresponding global LESS variables:

```css
div {
  border-width: @vui-focusOutlineWidth;
  border-style: @vui-focusOutlineStyle;
  border-color: @vui-focusOutlineColor;
}
```

#CSS

If you'd prefer to use plain CSS instead of LESS, bundle up the provided
`focus.css` file with your application's CSS. Then apply the CSS class
`vui-outline` to any element in your HTML. When that element receives focus,
the outline style will be applied automatically.

```html
<a class="vui-outline">my link</a>
```

## Contributing

### Code Style

This repository is configured with [EditorConfig](http://editorconfig.org) rules and contributions should make use of them. See the valence-ui [Code Style wiki page](https://github.com/Desire2Learn-Valence/valence-ui-helpers/wiki/Code-Style) for details.

# Starlight Color

`starlight-color` is a simple library for styling console text using ANSI escape codes. You can apply **colors**, **background colors**, and **text styles** like bold, underline, italic, and more.

---

## Installation

```bash
npm install starlight-color@latest
```

---

## Import

```js
import { colors, bgColors, styles, style } from 'starlight-color';
```

> The import line is **the same** in both JavaScript and Starlight.

---

## JavaScript Usage

```js
import { colors, bgColors, styles, style } from 'starlight-color';

// Basic colors
console.log(colors.red("This is red text"));
console.log(colors.cyan("This is cyan text"));

// Background colors
console.log(bgColors.yellow("Yellow background"));
console.log(bgColors.brightBlue("Bright blue background"));

// Styles
console.log(styles.bold("Bold text"));
console.log(styles.underline("Underlined text"));

// Combined styling
console.log(style("Green bold underlined text", { color: "green", bold: true, underline: true }));

// 256-color support
console.log(style("Custom foreground 202", { fg256: 202 }));
console.log(style("Custom background 120", { bg256: 120 }));
```

---

## Starlight Usage

> In Starlight, use `sldeploy()` instead of `console.log()` to output styled text.

```sl
import { colors, bgColors, styles, style } from 'starlight-color';

sldeploy(colors.red("This is red text"));
sldeploy(bgColors.yellow("Yellow background"));
sldeploy(styles.bold("Bold text"));
sldeploy(style("Green bold underlined text", { "color": "green", "bold": true, "underline": true }));

sldeploy(style("Custom foreground 202", { "fg256": 202 }));
sldeploy(style("Custom background 120", { "bg256": 120 }));
```

---

## API

### Colors

```js
colors.black(text)
colors.red(text)
colors.green(text)
colors.yellow(text)
colors.blue(text)
colors.magenta(text)
colors.cyan(text)
colors.white(text)
colors.gray(text)
colors.brightRed(text)
colors.brightGreen(text)
colors.brightYellow(text)
colors.brightBlue(text)
colors.brightMagenta(text)
colors.brightCyan(text)
colors.brightWhite(text)
colors.fg256(n, text)   // 256-color foreground
```

### Background Colors

```js
bgColors.black(text)
bgColors.red(text)
bgColors.green(text)
bgColors.yellow(text)
bgColors.blue(text)
bgColors.magenta(text)
bgColors.cyan(text)
bgColors.white(text)
bgColors.brightBlack(text)
bgColors.brightRed(text)
bgColors.brightGreen(text)
bgColors.brightYellow(text)
bgColors.brightBlue(text)
bgColors.brightMagenta(text)
bgColors.brightCyan(text)
bgColors.brightWhite(text)
bgColors.bg256(n, text) // 256-color background
```

### Styles

```js
styles.bold(text)
styles.dim(text)
styles.italic(text)
styles.underline(text)
styles.inverse(text)
styles.hidden(text)
styles.strikethrough(text)
```

### Combined Styling

```js
style(text, { 
  color,       // text color
  bg,          // background color
  bold, dim, italic, underline, inverse, hidden, strike, 
  fg256, bg256 // 256-color support
})
```

---

## Notes

* In **JavaScript**, use `console.log()` to print styled text.
* In **Starlight**, use `sldeploy()` for output.
* You can combine multiple styles and colors using `style()`.
* Supports both named colors and 256-color mode.


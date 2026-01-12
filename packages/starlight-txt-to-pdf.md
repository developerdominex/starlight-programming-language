# starlight-txt-to-pdf

A utility to **convert TXT files to PDF** with **text formatting, headers, footers, colors, bold/italic styles, and image embedding**. Works in both **JavaScript** and **Starlight**.

---

## Installation

Install via npm:

```bash
npm install starlight-txt-to-pdf@latest
```

---

## Import

For both **JavaScript** and **Starlight**:

```js
import { txtToPdf } from "starlight-txt-to-pdf";
```

---

## Usage in JavaScript

```js
import { txtToPdf } from "starlight-txt-to-pdf";

(async () => {
  try {
    const output = await txtToPdf("letter.txt", "letter.pdf", {
      header: "My PDF Document 💌"
    });
    console.log("PDF saved to:", output);
  } catch (err) {
    console.error("Error generating PDF:", err.message);
  }
})();
```

### Features:

* Convert a plain TXT file to PDF.
* Supports **text colors**: `[color:red]Hello[/color]`.
* Supports **bold/italic**: `[b]Bold[/b]`, `[i]Italic[/i]`.
* Supports **headers and footers**.
* Supports **absolute positioning**: `[pos:x,y]Text[/pos]`.
* Supports **embedded images**: `[img:path/to/image.png,x=100,y=200,w=150,h=150]`.
* Automatic **page breaks** when text exceeds page height.
* Default page size: A4 (595 × 842 points).

---

## Usage in Starlight

```sl
import { txtToPdf } from "starlight-txt-to-pdf";

await txtToPdf("letter.txt", "letter.pdf", { header: "My PDF Document 💌" });
sldeploy("PDF generated: letter.pdf");
```

### Example TXT content with formatting:

```
# My Love Letter 💖
[color:red][b]Dear Alice,[/b][/color]

I hope this letter finds you well.

## Memories
[i]Remember the day we first met?[/i]

[img:heart.png,x=200,y=500,w=100,h=100]
```

* Text colors, bold, italic, and headers will render correctly in PDF.
* Images can be positioned anywhere using the `[img:...]` tag.
* Use `[pos:x,y]Text[/pos]` for custom coordinates.

---

## Notes

* The function is **asynchronous**. Use `await` in Starlight or JS.
* Default **header** text is `"Love Letter 💖"` if none is provided.
* Supported text colors: `red, green, blue, yellow, cyan, magenta, gray, white, black`.
* Images must be **PNG or JPG**.
* Page dimensions and margins can be adjusted inside the function if needed.

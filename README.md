# Simple Signing (PDF)

Sign a PDF in your browser. Place a transparent PNG of your signature at the size and position you want, then save a flattened PDF. Everything runs locally in pure JavaScript; no files are uploaded and no server or install is needed.

## Use

1. Open `index.html` in Chrome, Edge or Firefox. If the page opens but the PDF will not render, serve the folder with any static server (for example `python -m http.server`) and open the localhost address.
2. Open a PDF and a signature PNG, either with the buttons or by dragging both onto the window. Each file is identified by its contents, so the order and file names do not matter.
3. A signature chosen while a PDF is open is placed straight onto it (at the drop point if you dropped it on a page). If no PDF is open yet, the signature waits until you click **Add signature**.
4. Drag to move, drag a corner to resize (proportions stay locked), or type an exact width in inches. Arrow keys nudge (Shift for larger steps) and Del removes. You can add several signatures, on any pages.
5. Click **Save flattened PDF**. The file downloads as `<name>-signed.pdf`.

## What "flattened" means here

The signature is drawn into the page content, so it is part of the page and cannot be moved or removed as a separate annotation. Text and vector content stay selectable; pages are not turned into images. The **Flatten form fields** option (on by default) also bakes any fillable form fields into the page.

Rotated pages and crop boxes are handled, so the signature lands where you see it.

## Sharing it

Give people the whole folder; `index.html` loads its libraries from `lib/` by relative path.

```
index.html
lib/
  pdf.min.js, pdf.worker.min.js     PDF.js 3.11.174 (rendering)
  pdf-lib.min.js                    pdf-lib 1.17.1 (writing the signed PDF)
  *.LICENSE*                        their licences
```

## Third-party software

- [PDF.js](https://github.com/mozilla/pdf.js), Apache License 2.0
- [pdf-lib](https://github.com/Hopding/pdf-lib), MIT License

## License

[MIT](LICENSE). The bundled libraries keep their own licences (see above).

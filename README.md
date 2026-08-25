# Image → Excel Pixel Art

Turns an image into an Excel spreadsheet made entirely of colored cells —
a "pixel art" version of the image, built by averaging the color of small
10x10 pixel blocks and filling each spreadsheet cell with that color.

## Demo

*(add a screenshot here: your original image next to the colored-cell
spreadsheet, zoomed out in Excel so the picture is visible)*

## How it works

1. The image is loaded with Pillow.
2. It's split into 10x10 pixel blocks.
3. Each block's average RGB color is computed and converted to hex.
4. One Excel cell per block is filled with that color using `openpyxl`.
5. The result is saved as `pixel_image.xlsx` — zoom out in Excel/Google
   Sheets to see the picture emerge from the colored grid.

## Setup

```bash
pip install -r requirements.txt
```

## Usage

The image path is set directly inside `image_to_excel.py`:

```python
img = Image.open(r"C:\Users\ALI\OneDrive\Desktop\python\inception.jfif")
```

Before running, edit this line to point to your own image path, then run:

```bash
python image_to_excel.py
```

The output is always saved as `pixel_image.xlsx` in the folder you run the
script from.

## Notes

- Large images can produce a very large spreadsheet and take a while to
  generate, since the block size (10x10) is fixed in the script.
- Works with jpg, png, jfif, and anything else Pillow can open.

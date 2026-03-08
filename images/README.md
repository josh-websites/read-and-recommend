# Images Folder

Store all site images here. This entire folder is automatically copied to `dist/images/` during the build.

## 📁 Folder Structure

```
static/images/
├── books/          # Book cover images
├── products/       # Product images
└── site/           # Site-wide images (favicon, og-image, etc.)
```

## 📚 Book Covers

**Location:** `static/images/books/`

**Naming:** Use simple, lowercase, hyphenated names matching your review filename
- `dune.webp` for `reviews/dune.md`
- `foundation.webp` for `reviews/foundation.md`
- `1984.webp` for `reviews/1984.md`

**Format:** WebP (recommended for best compression)

**Usage in reviews:**
```markdown
---
title: Dune
author: Frank Herbert
image: dune.webp
---
```

**What happens:**
- Image displays at top of review (desktop: centered, mobile: full width)
- If `image:` field is empty or missing, no image shows (no broken placeholder)
- Image automatically includes alt text with book title and author

## 🛍️ Product Images

**Location:** `static/images/products/`

**Naming:** Descriptive product names
- `kindle-paperwhite.webp`
- `kobo-libra.webp`
- `reading-light-amber.webp`

**Usage in product reviews:**
```markdown
---
title: Kindle Paperwhite
category: eReaders
image: kindle-paperwhite.webp
---
```

## 🌐 Site Images

**Location:** `static/images/site/`

**Common files:**
- `og-image.webp` - Social media preview image (1200x630px recommended)
- `logo.webp` - Site logo if needed
- `banner.webp` - Any site-wide graphics

## 📐 Image Specifications

### Book Covers
- **Recommended size:** 300-500px wide
- **Aspect ratio:** Typical book proportions (2:3 or similar)
- **Format:** WebP
- **File size:** Keep under 100KB for fast loading

### Product Images
- **Recommended size:** 400-600px wide
- **Aspect ratio:** Product dependent (usually 1:1 or 4:3)
- **Format:** WebP
- **File size:** Keep under 150KB

### Social Share Images
- **Size:** 1200x630px (Open Graph standard)
- **Format:** WebP or JPG
- **File size:** Keep under 200KB

## 🔄 How to Get Book Cover Images

### From Amazon:
1. Go to the book's Amazon page
2. Right-click on the book cover
3. "Open image in new tab"
4. Save the image
5. Convert to WebP (see below)

### Alternative Sources:
- Google Books
- Goodreads (via right-click)
- Publisher websites
- Open Library (openlibrary.org)

## 🖼️ Converting to WebP

### Online Tools:
- https://cloudconvert.com/jpg-to-webp
- https://convertio.co/jpg-webp/

### Command Line (if you have cwebp):
```bash
cwebp -q 80 input.jpg -o output.webp
```

### Photoshop/GIMP:
- File → Export As → WebP format

## ✨ Image Display Behavior

**With Image:**
```
[Book Cover Image]
Title and author below
Review content
Amazon button
```

**Without Image:**
```
Title and author at top
Review content starts immediately
Amazon button
```

**No broken placeholders!** If image field is empty or file doesn't exist, the template gracefully skips the image section.

## 🎨 Image Styling

**Desktop:**
- Centered in container
- Max width: 300px
- Green border
- Drop shadow
- White background padding

**Mobile:**
- Full width (responsive)
- Subtle border
- Minimal shadow
- Clean eReader aesthetic

## 📝 Best Practices

✅ **DO:**
- Use WebP format for best compression
- Keep files under 100KB
- Use descriptive, lowercase, hyphenated names
- Match image filename to review filename
- Include `image:` field in frontmatter

❌ **DON'T:**
- Use spaces in filenames
- Upload huge images (>500KB)
- Use PNG/JPG when WebP works
- Include file path (just filename)

## 🚀 Build Process

When you run `build.bat`:
1. Build script copies entire `static/images/` to `dist/images/`
2. Templates check if `image` field has a value
3. If yes, displays: `/images/books/{{ book.image }}`
4. If no, skips image section entirely

**Result:** Clean pages whether or not images exist!

## 💡 Optional Images

Images are completely optional! You can:
- Add images to all reviews
- Add images to some reviews
- Add no images at all
- Add images later to existing reviews

Just add the `image:` field to frontmatter when you have a cover to include.

## 🔍 Finding Missing Images

If you want to see which reviews don't have images, search your vault for:
```
image: 
```
(Empty image field)

Then add images when you have time!

# Based Brainbreak Website

A simple, ad-free website for sharing brain break activities. No trackers, no cookies, just helpful activities to energise and engage students.

## What is a Brain Break?

Brain breaks are short mental or physical activities that help students refocus, energise, and prepare for learning. They typically last 3-10 minutes and can involve movement, games, puzzles, or relaxation exercises.

## Acknowledgement

This website is based on [Based Cooking](https://based.cooking) by [Luke Smith](https://lukesmith.xyz). The original source code is available [here](https://github.com/lukesmithxyz/based-cooking). The site uses Hugo with [this simple theme](https://github.com/lukesmithxyz/lugo).

## How to Contribute

There are three ways to help:

1. **Add a brain break** - Share your favorite classroom activities
2. **Add images** - Create simple illustrations for existing brain breaks
3. **Fix errors** - Correct typos or improve instructions

## Submitting a Brain Break

### Quick Start

1. Look at existing brain breaks in the `content/` folder for examples
2. Create a new file following the naming format: `activity-name.md`
3. Write clear, step-by-step instructions that teachers can read aloud
4. Submit via GitHub (instructions below)

### Writing Guidelines

Your brain break should:

- Use "we" language (e.g., "We're going to play...")
- Include step-by-step instructions
- Be clear enough to read word-for-word without improvisation
- Use simple, concrete language

### GitHub Submission Steps

1. **Create a GitHub account** (if needed):

   - Visit [github.com](https://github.com) and click "Sign up"

2. **Fork this repository**:

   - Go to [github.com/brainbreaks/brainbreak](https://github.com/brainbreaks/brainbreak)
   - Click "Fork" in the top-right corner

3. **Add your brain break**:

   - Navigate to the `content/` folder in your fork
   - Click "Add file" → "Create new file"
   - Name it using hyphens: `my-brain-break.md`
   - Copy the format from [example.md](example.md)

4. **Commit your changes**:

   - Write a brief commit message
   - Click "Commit changes"

5. **Submit a pull request**:
   - Click "Pull requests" → "New pull request"
   - Click "Create pull request"
   - Add a title and description
   - Submit for review

### File Format Requirements

- **Location**: All brain breaks go in the `content/` folder
- **Naming**: Use lowercase with hyphens between words (e.g., `silent-chairs.md`)
- **Format**: Follow the structure in [example.md](example.md)
- **Line endings**: Unix-style (`\n`) - automatic on Linux/Mac

### Tags

Use existing tags when possible.

### Images (Optional)

- **Location**: `/pix` folder
- **Format**: `.webp` for small file size (<100KB preferred)
- **Naming**: Match your file name (e.g., `silent-chairs.webp`)
- **Additional images**: Use two-digit numbering (`silent-chairs-01.webp`)
- **Linking**: Use absolute paths (`/pix/filename.webp`)

Reference to image
![Example Picture](/pix/example.webp)

## Manipulating Images
magick image-name.jpg image-name.webp

magick image-webp -auto-orient -strip image.webp

magick image.webp -rotate -90 image.webp
-rotate 90 = clockwise 
-rotate -90 = counter-clockwise (anti-clockwise) 


### Author Credit (Optional)

To add your information:

1. Create `data/authors/your-name.json`
2. Include any of these fields:

   - `website`
   - `donate`
   - `email`
   - `btc`, `xmr`, `eth` (crypto addresses)

3. In your brain break file, use: `author: your-name`

See `data/authors/example.json` for the format.

## License

This website and all content is in the public domain. By submitting content, you waive ownership claims but are encouraged to credit yourself as the contributor.

# Based Brainbreak Website

This is a simple brainbreak website where users can submit brainbreaks here for credit.
There are no ads, trackers or cookies.

This site is compiled and organized with Hugo, using [this very simple theme](https://github.com/lukesmithxyz/lugo).

## Ways to contribute

- By adding a brainbreak.
- Create an image for the brainbreak if no nice picture already
  exists. Submitted images should be small `.webp` files ideally less than 100K
  or so.
- Fix errors in brainbreaks or add minor improvements.

## Rules for submission

- Model submission files after [example.md](example.md). Put them in `content/`.
- File names should be the name of the dish with words separated by hyphens
  (`-`). Not underscores, and definitely not spaces.
- The file needs to be `\n` terminated in unix-fashion (if you're on Linux you
  don't need to care, it should be automatic).

You may include a json file with your personal links/donation addresses in
`data/authors/your-name.json`.

See example (`data/authors/example.json`) for a model. You can include: `website`, `donate` (general donation link), `email` or crypto addresses as `btc`, `xmr` and `eth`.

### Tags

Remember to add tags to your brainbreak, but try to use tags already used by other brainbreaks.

### Images

Images are stored in `/pix`.

Each brainbreak can have a title image at the top and perhaps several instructional
images as absolutely necessary.

Images should be in `.webp` format and with as small file size as possible. If
you submit an image for say, `silent-chairs.md`, it should be added as
`pix/silent-chairs.webp`.

If you would like to add additional directional images,
they should be numbered with two digits like: `pix/silent-chairs-01.webp`, etc.

Note also that images should have links beginning with a slash in this use
case, i.e. `/pix/...`.

# Running this site locally

git clone https://github.com/lukesmithxyz/based.cooking.git
mkdir themes
cd themes
git clone https://github.com/lukesmithxyz/lugo.git
hugo server --noHTTPCache

GitHub Secrets settings
Repository-level secrets → tied to a single repo.
Go to your repo on GitHub → Settings → Secrets and variables → Actions → “New repository secret.”

https://landchad.net/basic/nginx/

## Acknowledgement

This website is a copy of [Based Cooking](https://based.cooking) which was created by [Luke Smith](https://lukesmith.xyz)

## License

This website and all its content is in the public domain.
By submitting text or images or anything else to this repository,
you waive any pretense of ownership to it,
although you are welcome and recommended to give yourself credit
at the bottom of a submitted page for you adding it
(including personal or donation links).

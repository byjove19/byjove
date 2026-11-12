# ByJove Tech: Portfolio

My personal portfolio. Full stack developer, getting deeper into cybersecurity. The hero is a live ASCII lagoon that switches between a sunlit reef and a night reef with the dark/light theme.

**Live site:** https://byjovetech.netlify.app/

## What's in it

- **Live ASCII lagoon hero** built with [ascii-things](https://ascii-things.dev/)
- **Dark / light toggle** that also swaps the scene (light = reef, dark = night reef). It remembers your choice and follows your system setting until you pick one
- **Project cards** with screenshots, short write-ups and tech lines
- Responsive down to phone width, keyboard-friendly, respects reduced motion
- No framework and no build step: plain HTML, CSS and JavaScript

## Featured projects

| Project | What it is |
| --- | --- |
| [85 Gifts](https://85-gifts-vendors.vercel.app/) | Vendor platform for storefronts, events, inventory, invoices and payment links |
| [Jbees Eatery & Lounge](https://jbees.com.ng) | Fast, SEO-tuned restaurant website |
| [Audita](https://audita-rfxa.onrender.com) | Financial review platform for auditors and eateries |
| [Sage & Silk](https://sage-silk-gpxx.onrender.com/) | Clothing store with admin dashboard and checkout |
| [StreamHive](https://streamhiveapp.onrender.com) | Movie streaming platform with admin dashboard |
| [JhoKitchen](https://jhokitchen.netlify.app/) | Food ordering and live delivery tracking |
| [Stella Empire](https://stellaempire.netlify.app/) | Beauty and style booking platform |

## Project structure

```
.
├── index.html            # page content
├── style.css             # styles, light and dark theme variables
├── main.js               # lagoon scene, theme toggle, image fallbacks
├── vendor/
│   └── ascii-lagoon.js   # ascii-things lagoon scene, bundled (no CDN needed)
├── images/
│   ├── JovitaResume.pdf  # resume (add your own)
│   └── projects/         # project screenshots
└── capture-shots.mjs     # optional: auto-generates the screenshots
```

## Run it locally

It's a static site, but it uses ES modules, so open it through a local server (double-clicking `index.html` won't work):

```bash
python3 -m http.server 8000
# or
npx serve
```

Then open http://localhost:8000.

## Deploy

Netlify: drag the folder onto the Netlify dashboard, or connect this repo. Set the publish directory to the repo root and leave the build command empty.

## Edit the content

- **Add or change a project:** copy a `<a class="card">` block in `index.html` and edit the link, text and image path
- **Project screenshots:** drop a `.jpg` into `images/projects/` with the name the card expects. If an image is missing, the card shows a placeholder with the project name
- **Auto-generate screenshots:** run `capture-shots.mjs` on your own machine

  ```bash
  npm i -D playwright
  npx playwright install chromium
  node capture-shots.mjs
  ```

- **Change the scene:** in `main.js`, the `variantFor` function picks the lagoon variant. The package also has `turtle`, `manta`, `seahorse`, `dolphin`, `hammerhead` and `tang`
- **Colors and fonts:** the theme variables are at the top of `style.css`

## Credits

- Hero scene: [ascii-things](https://ascii-things.dev/) (MIT)
- Fonts: JetBrains Mono and Space Grotesk via Google Fonts

## License

The ascii-things code in `vendor/` keeps its original MIT license. All other content, including copy, project descriptions and screenshots, is © ByJove Technologies. Please don't copy it as your own.

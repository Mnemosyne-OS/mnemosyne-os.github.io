# mnemosyne-os.github.io

Source of [mnemosyne-os.github.io](https://mnemosyne-os.github.io/), the GitHub Pages host of the Mnemosyne OS organization. It is an entry page: static files, no build step, published by GitHub Pages on every push to `main`.

If you are looking for the product, you are one click away from it:

- **Download it**, Windows / macOS / Linux: the cards at the top of [the entry page](https://mnemosyne-os.github.io/#download), or [the latest release](https://github.com/Mnemosyne-OS/Mnemosyne-Neural-OS/releases/latest)
- **The application** (source, releases, issues): [Mnemosyne-Neural-OS](https://github.com/Mnemosyne-OS/Mnemosyne-Neural-OS)
- **Every repository of the organization, one line each**: [github.com/Mnemosyne-OS](https://github.com/Mnemosyne-OS)
- **Documentation**: [docs.mnemosyne-os.io](https://docs.mnemosyne-os.io)
- **Product site**: [mnemosyne-os.io](https://mnemosyne-os.io) · **Organizations**: [mnemosyne-os.com](https://mnemosyne-os.com)
- **Benchmark archive and audit kit**, served on this host from its own repository: [mnemosyne-os.github.io/MnemosyneOS---benchmarks/](https://mnemosyne-os.github.io/MnemosyneOS---benchmarks/)

## What is in here

| File | Role |
|---|---|
| `index.html` | The entry page, self-contained (inline CSS, inline JSON-LD) |
| `llms.txt`, `ai.txt` | What this host is and who publishes it, written for answer engines |
| `robots.txt`, `sitemap.xml` | Crawl directives and the three URLs of this host |
| `.nojekyll` | Tells Pages to serve the files as they are |
| `00a1698bc10b517ba255a93f7744858d.txt` | IndexNow key |

## Editing

Edit the files directly and push to `main`. There is nothing to build. Keep the `Brand` node in the JSON-LD identical to the one on mnemosyne-os.io: the four hosts assert one `@id`, and a retyped copy would publish a rival entity instead of merging into it.

### The download cards

The download buttons carry hardcoded links to a published release, and a script
rewrites them from the GitHub API so the page follows the latest one on its own.
The rewrite is all or nothing: if one asset of the five cannot be matched, none of
the links are touched, because half a page on the new version and half on the old
one is worse than a page that is honestly one version behind.

So the hardcoded fallback is the thing that goes stale, not the page. After a
release that **renames** an asset — the script matches on the filename suffix
(`-Setup-x64.exe`, `-Portable-x64.exe`, `-mac-arm64.dmg`, `-x86_64.AppImage`,
`-amd64.deb`) — update the `data-asset` attributes here too, along with the
`href`s, the sizes, the version line and `softwareVersion` in the JSON-LD.

The per-platform notes state what is true today: Windows is Certum code-signed,
macOS is not notarized yet, Linux has no signing gate. When macOS notarization
lands, that card's warning comes out.

Mnemosyne OS is published by XPACEGEMS LLC.

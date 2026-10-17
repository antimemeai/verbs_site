# verbs.sh

A small static splash for Verbs, using the antimeme site's paper/ink palette,
Inter Tight, IBM Plex Mono, static wordmark, and restrained layout. No runtime
JavaScript, dependencies, analytics, or mandatory site build.

The synopsis draws from the Verbs design direction and operator decisions,
not just the founding brief. It describes work underway. The published 0.1.0
packages and present C++ header are explicitly identified as seeds/placeholders,
not the planned invariant/type/checking system.

## Preview and edit

Run `./scripts/serve`, then open <http://localhost:8001>. The optional argument
sets the port. The server binds only to 127.0.0.1.

Edit `public/index.html` and `public/styles.css`. Keep the splash one screen
where there is sufficient room; let phones and enlarged text scroll instead
of clipping. Assets and their font licenses are local under `public/fonts/`,
copied from the existing antimeme site. The two HTML headers are hand-edited;
keep their nav links consistent. The CSS uses the same typefaces, palette,
widths, focus outlines, and header/footer treatment as antimeme.ai.

## Current C++ source reference

`/cpp/` is a generated, escaped, verbatim view of the current seed header,
not a full API autodocumentation system. It links its precise source revision
and includes the source MIT license. No parser guesses signatures or turns
design sketches into implemented API. Doxygen is not installed on the working
host; selecting a full API-docs generator is deferred, not silently adopted.

Regenerate deliberately from the sibling source repository:

```sh
./scripts/render-cpp --revision origin/main
./scripts/check
```

Or pin `--revision` to a specific public commit. Generation reads committed Git
objects, never dirty files, and performs no network calls. Confirm the chosen
commit is public before publishing a new snapshot. Edit the reference chrome
in `templates/cpp.html`, then regenerate. The checked-in HTML and license let
the web host serve the site without the source checkout or a build tool.

`./scripts/check` checks static links/IDs/assets and source fidelity against
the pinned commit; it needs Python 3 and the sibling `../verbs` checkout.
Browser checks are separate and exercise actual layout and keyboard behavior.
This site does not build or validate the Verbs implementation.

## Cloudflare Pages

Connect `antimemeai/verbs_site` as a new Pages project:

- Production branch: `master`
- Framework: `None`
- Build command: `exit 0`
- Output directory: `public`
- Root: repository root
- Environment variables: none

The generated reference is already committed. Only `public/` is published.
After the Pages URL is working, add `verbs.sh` under Custom domains and follow
Cloudflare's DNS/nameserver instructions for that domain. Verify HTTPS, the
splash, `/cpp/`, fonts, favicon, and outgoing links. Pushing this repository
alone does not configure Pages or make the domain live.

Task tracking uses bd, prefix `vsite`. `bd backup` keeps its tracked export
alongside the repository; the local Dolt database is not published.

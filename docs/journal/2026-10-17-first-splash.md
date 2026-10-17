# First verbs.sh splash

The operator requested a quick Verbs splash in essentially the antimeme
site's style: a rough design-intent synopsis now, C++ autodocs soonish, polish
later. Bound the pass to 30 minutes: plain static splash, honest current-source
reference if possible without new dependencies, local preview, direct checks,
and one source recheck. No third assurance layer or implementation changes.

Created verbs_site as a separate repository. Used the existing antimeme palette
(#f8f7f2 / #181916), typefaces, widths, static underscore, nav, keyboard focus
and footer treatment. Copied its two local font files and both OFL texts.
No runtime JS, external font requests, animations, analytics, framework, or
mandatory site build. The splash has one synopsis, a seed-release status note,
and C++ / source / crate links. Footer points back to antimeme.ai and the
source code's MIT license. It does not invent a new legal ownership claim.

Read the founding brief as orientation only, plus the current operator
journal and design/SPEC.md revision 3 at source commit
fe4ebbaeeb4ccf14bef87f6fa87bb50a07b846c4. In particular, did not advertise
the old brief's discovery/daemon portfolio or C++23 as the settled direction.
Synopsis describes work being built: invariants in types, checking bypasses,
edit feedback for agents, C++ first, Rust later, no required model. It does
not claim the proposed system is already implemented. The 0.1.0 packages
remain explicitly identified as placeholders, matching operator decisions.

Doxygen is not installed. The only C++ implementation is the small
packages/cpp/include/verbs/verbs.hpp seed with check and violation. Instead
of adopting a docs stack or manufacturing API from design examples, generated
/cpp/ as a verbatim, escaped source view with precise commit link and MIT
license. This is not full API autodocumentation. scripts/render-cpp reads
committed Git objects and the owned template; it never parses C++ or reads
dirty code. The checked-in HTML/license are directly servable. Confirmed the
pinned raw GitHub header returns 200 and matches the captured source exactly.

scripts/check passed: one h1 per page, unique IDs, working local paths/assets,
no scripts/motion, escaped code text equal to the pinned header, deterministic
rendered reference and license. Direct Chrome checks covered both pages at
320×568, 390×844, 600×800, 601×800, 768×1024, 1024×600, 1280×720,
1440×900, 1920×1080, and 720×450. Splash fits every tested size, including
phones. Source reference fits roomy desktop screens; smaller windows scroll
without clipping. Checked horizontal bounds, header/nav separation, loaded
fonts, footer ordering, keyboard skip link, C++ current-page state and source
text. Assets/routes return 200; README, AGENTS, .git, .beads and templates paths
return 404. Requests stay local. Both internal navigation directions work.
Driver: /tmp/verbs-site-check.mjs. Existing crates storefront-probe limitations
from the antimeme pass were not re-probed or claimed fixed.

The single source recheck inspected the synopsis/metadata against current
intent and the small renderer's revision resolution/escaping/template order.
No additional findings. git diff --check passed. No Verbs implementation or
antimeme site files were changed. Local preview remains at port 8001; the
operator's antimeme preview on 8000 is separate and was not stopped.

Initialized bd successfully with prefix vsite. vsite-7h2 covers this static
implementation and is closed. vsite-ob2 tracks proper generated C++ API docs
when the implementation warrants them. vsite-8zt is blocked on Cloudflare
Pages/domain access or dashboard setup. Created the public GitHub repository
https://github.com/antimemeai/verbs_site. README has the exact Pages settings:
master, no framework, exit 0, public/. No Cloudflare CLI was available; this
pass did not configure Pages/DNS, and does not claim verbs.sh is live.

bd's initial automatic backup push warned that master had no upstream before
the first site push; its local backup was retained. Publish the site commit
with git push -u origin master to establish the upstream. No failed/unknown
remote creation was replayed.

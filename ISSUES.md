# Documentation audit — Google Developer Documentation Style Guide

Audit of all 101 markdown files (`README.md` + `gitkraken-client/*.md`, ~12,700 lines) against the
[Google Developer Documentation Style Guide](https://developers.google.com/style). Performed 2026-08-25.

Each section below is a self-contained issue: title, description, the style rule violated, scope,
concrete examples, and fix instructions precise enough for a coding agent to execute without
re-auditing the repo. Reproduction commands are given instead of exhaustive line lists where the
issue is systemic — file:line numbers drift as the docs change, greps don't.

All paths are relative to the repo root.

---

## Tier 1 — Content/rendering bugs

These aren't style nitpicks — they render incorrectly or point somewhere wrong. Fix first.

### Issue 1: Fix broken/malformed HTML across docs

**Labels:** bug, docs
**Priority:** high

**Description:** Several files contain HTML that will render visibly broken — unclosed tags, stray
closing tags with no opener, or malformed attributes.

**Locations:**
- `gitkraken-client/hiding-and-soloing.md:33-36` — a `<p>` tag is opened mid-attribute inside an
  `<i>` tag, and `class='fa fa-dot-circle-o icon-orange'>` is orphaned on its own line outside any
  tag. This needs a full rewrite of the block, not a copyedit:
  ```
  <p>To solo a branch, right-click the branch and select `Solo`. This initiates Solo Mode, with soloed branches highlighted in orange and with a solid orange <i><p>Soloing a branch will hide all other branches which have not been soloed, showing <i>only</i> soloed branches.</p>
  class='fa fa-dot-circle-o icon-orange'></i> icon to the left of the branch name.</p>
  ```
- `gitkraken-client/staging.md:23,27,41` — button markup has a stray `</span>` with no opening tag,
  e.g. `<button class='...'>Stage File</span></button>`. Compare clean markup in `squash.md:41`.
- `gitkraken-client/interface.md:42` — stray closing tag before its opener: `GitKraken Desktop also
  has a </kbd>Redo</kbd> button` should be `<kbd>Redo</kbd>`.
- `gitkraken-client/keyboard-shortcuts.md` — unclosed `<kbd>` tags in table cells, e.g. line
  122-123, 129-130, 181-182, 196-197, 201-202, 206-207, 211-212, 216-217, 234-235, 294-295,
  299-300 (pattern: `<kbd>Shift</kbd><kbd>K</td>` — missing `</kbd>` before `</td>`).
- `gitkraken-client/github-actions.md:23,37,45,53` — headings missing the required space after
  `###` (`###Create Workflow`), so they won't render as headings in strict Markdown parsers.
- `gitkraken-client/pull-requests.md:51` — malformed callout class:
  `<div class='callout callout--basicwarning'>` is not a real callout type (compare the correct
  `callout--warning` in `pushing-and-pulling.md:26`); will render without intended styling.

**Fix instructions:** For each location, correct the HTML/Markdown so it parses and renders as
intended. Use a sibling instance of the same pattern in the same file (or a nearby file) as the
reference for correct markup. For `hiding-and-soloing.md`, rewrite the paragraph from scratch —
the icon description and the "soloing hides other branches" sentence are two separate ideas that
got interleaved and need to be split into two clean sentences/paragraphs.

---

### Issue 2: Fix broken internal links

**Labels:** bug, docs
**Priority:** high

**Description:** Two broken/incorrect internal links found in `gitkraken-organization.md`.

**Locations:**
- `gitkraken-client/gitkraken-organization.md:17` — anchor link has a double `#`:
  `/gitkraken-client/gitkraken-organization/##roles` (should be a single `#roles`).
- `gitkraken-client/gitkraken-organization.md:179` — wrong product path:
  `/gitlens/gitkraken-organization/#transfer-ownership` should be
  `/gitkraken-client/gitkraken-organization/#transfer-ownership` (every other internal link in the
  doc uses `/gitkraken-client/`).

**Fix instructions:** Correct both links as noted. Then run
`grep -rn '/gitlens/' gitkraken-client/*.md` and `grep -rn '##' gitkraken-client/*.md | grep -v '^\S*:\s*##'`
(i.e., search for `##` appearing inside a URL path, not as a heading marker) across the whole repo
to catch any other instances of the same two mistakes.

---

### Issue 3: Remove duplicated/misplaced content block in buy.md

**Labels:** bug, docs
**Priority:** medium

**Description:** `gitkraken-client/buy.md:15-32` contains a verbatim copy of the "OAuth integration
with Bitbucket" / "Connecting to multiple Bitbucket accounts" sections from
`gitkraken-client/bitbucket.md`, apparently pasted onto the wrong page. A page titled "How to buy"
should not open with Bitbucket OAuth setup instructions.

**Fix instructions:** Delete the misplaced block from `buy.md`. Confirm `bitbucket.md` still has
the canonical version of that content intact and that no other page linked directly into the
now-removed anchor.

---

## Tier 2 — Repo-wide style/consistency issues

Each of these is systemic — the same violation recurs across many files. One issue, one fix
convention, applied everywhere it appears.

### Issue 4: Add alt text to all documentation images

**Labels:** accessibility, docs
**Priority:** high (largest-impact issue in the audit)

**Description:** Every `<img>` element in the repo omits the `alt` attribute — confirmed to be
effectively universal, not a handful of stragglers. No file uses native Markdown image syntax
(`![]()`) at all; every image is a raw `<img src=... srcset=... class=...>` tag with no
alt-equivalent. This means every screenshot/GIF in the docs is invisible to screen readers.

**Representative locations (not exhaustive — see reproduction command):**
`activity-logs.md`, `adding-and-removing.md`, `detached-head-state.md`, `diff.md` (18 images),
`editing-files.md`, `git-lfs.md` (14), `github-gitkraken-client.md` (17), `github-issues.md` (11),
`githooks.md`, `favorites.md`, `fork.md`, `error-logs.md`, `gitkraken-account.md`,
`gitkraken-organization.md` (10), `gitkraken-launchpad.md`, `interface.md` (16),
`gitlab-gitkraken-client.md`, `jira.md`, `organizations.md`, `pull-requests.md` (21),
`self-signed-certificates.md`, `single-sign-on.md` (54), `pushing-and-pulling.md` (17),
`profiles.md`, `new-pro-purchases.md`, `squash.md`, `staging.md`, `stashing.md`, `tags.md`,
`themes.md`, `workspaces.md`, `team-view.md`, `teams.md`, `terminal.md`, `timelines.md`, `tips.md`,
`trello.md`, `trial-activation.md`, `upgrade-enterprise.md`, `windows-subsystem-for-linux.md`,
`submodules.md`.

**Reproduction command:** `grep -rn '<img' gitkraken-client/*.md | grep -v 'alt='` lists every
offending tag with its file and line number.

**Fix instructions:** For each `<img>` tag, add a concise, descriptive `alt` attribute derived from
the surrounding paragraph/heading context — describe what the screenshot shows or what UI action it
illustrates (e.g. `alt="The Stage File button in the GitKraken Desktop toolbar"`). Do not use the
filename or generic text like "screenshot" as the alt text. Decorative images with no informational
content (rare in this corpus) may use `alt=""`.

---

### Issue 5: Convert headings to sentence case

**Labels:** style, docs
**Priority:** medium

**Description:** Google style mandates sentence case for headings (capitalize only the first word
and proper nouns). Title Case is used throughout the repo, often inconsistently within the same
file.

**Examples:**
- `commits.md:42` `### Committing with Co-Authors` (Title Case) vs. `:20` `## Making a commit`
  (sentence case) — same file.
- `commit-signing-with-gpg.md:50,83,102,112` all Title Case vs. `:61` `### Configure GPG in
  GitKraken` sentence case — same file.
- `jira.md` — every heading is Title Case: `### Connect Jira Integration`, `### Preview Jira
  Issues`, `### Create New Jira Issue`.
- `preferences.md` — `### Auto-Fetch`, `### Default Branch Name`, `### External Merge Tool`.
- `github-issues.md:16,35,45,53,61,69` — six consecutive Title Case headings.
- `gitkraken-organization.md:27,45,55,167,175` — `## Add Users`, `## Reallocate Licenses`, etc.
- `staging.md:75` `## Ignoring Files` vs. `:16` `## Staging files` — same file, inconsistent.
- `stashing.md`, `themes.md`, `teams.md`, `workspaces.md`, `pull-requests.md`,
  `new-pro-purchases.md`, `profiles.md` all have the same mixed pattern.

**Fix instructions:** Rewrite every heading in every file to sentence case. Preserve capitalization
of proper nouns and product names (GitKraken, GitHub, GitLab, Bitbucket, Jira, Azure DevOps, SSH,
LDAP, SAML, etc.). Do not change heading *wording*, only capitalization.

---

### Issue 6: Fix heading hierarchy (no skipped levels, no raw HTML headings)

**Labels:** style, docs, accessibility
**Priority:** medium

**Description:** Several files skip a heading level (jump from the implicit page-title H1 straight
to H3, or from H3 to H5), which breaks screen-reader document-outline navigation. A few files also
mix raw `<h3>` HTML tags with Markdown `##`/`###` headings inconsistently within the same file.

**Locations:**
- Files that open at H3 with no H2 anywhere in the document: `jira.md`, `keyboard-shortcuts.md`,
  `gitkraken-launchpad.md`, `insights.md`, `squash.md`, `tags.md`, `teams.md`, `trello.md`,
  `trial-activation.md`, `team-view.md`.
- `experimental-features.md:24,32` — jumps from H3 (`### Git Executable`) directly to H5
  (`##### Features using the Git Executable`), skipping H4.
- `interface.md` and `hiding-and-soloing.md` use raw `<h3>` HTML tags in some places and Markdown
  `##`/`###` in others, within the same file.
- `tips.md:36,41` — raw `<h3>Core:</h3>` / `<h3>File:</h3>` sub-labels nested *inside* an
  already-H3 section (same-level heading nested under itself).

**Fix instructions:** Renumber headings in each affected file so the body starts at H2 and never
skips a level. Convert raw `<h3>` HTML tags to Markdown `###` (or the correct level for that
document) to match sibling headings in the same file. For `tips.md`, either promote "Core:" and
"File:" to real H4s under their H3 parent, or convert them to bold lead-in text if they're just
labeling sub-lists rather than starting new sections.

---

### Issue 7: Standardize UI-element and menu-path markup

**Labels:** style, docs
**Priority:** medium

**Description:** At least five different, overlapping HTML/Markdown conventions are used across the
repo for the same concept — a clickable UI element (button, menu item, tab) or a menu path — and
`<kbd>` (which should mean "literal keyboard key") is frequently used for non-keystroke content
instead.

**Conventions found in the wild for the identical "menu path" concept:**
- `<kbd><strong>File > Clone Repo</strong></kbd>` (`authentication.md:27,44`, `favorites.md:15`)
- `<kbd><i>...icon...</i></kbd>` (`azure-devops.md:25`, `bitbucket-server.md:29`,
  `github-enterprise.md:29,53`)
- `<em class='context-menu'>Preferences <i class='fa fa-caret-right'></i>Commit Template</em>`
  (`commits.md:82`, `branching-and-merging.md:118`, `diff.md:73,90`, `organizations.md:23,38,51`)
- Plain backticks with an arrow or `>`: `` `Preferences` → `GPG Preferences` ``
  (`commit-signing-with-gpg.md:57`), `` `Preferences` > `General` `` (`windows-subsystem-for-linux.md:85`)
- Color-coded `<span style='color:...'>` for buttons/states (`gitkraken-account.md:42`,
  `gitkraken-subscriptions.md:20,31,33,55`) — this is also an independent accessibility problem,
  since color alone conveys the action/state with no text cue.
- `<button class="...">` HTML for some clickable actions, plain backticks for others in the very
  same file (`editing-files.md:17,26,49`).
- `<kbd>` misapplied to non-keystroke content: a table column header (`interface.md:325`
  `<kbd>Branch/Tag</kbd>`), a tab name (`existing-pro-purchases.md:20`, `fork.md:16`), a file path
  (`githooks.md:173`), a context-menu label that isn't a key press (`tags.md:15`, `trello.md:97`).

**Adopted convention (decision made during audit triage — do not re-litigate):**
- **Bold** for anything the user clicks: buttons, menu items, tabs, checkboxes.
- **Code font** (backticks) for literal/file text: file paths, exact strings to type, code, file
  names.
- **`<kbd>`** reserved strictly for actual keyboard key presses (e.g. `<kbd>Ctrl</kbd> +
  <kbd>S</kbd>`), never for menu items or UI labels.
- Menu paths (a sequence of clicks) render as bold items joined by a literal `>`, e.g.
  **Preferences > Integrations**, no nested `<kbd>`/`<em>`/icon markup.

**Fix instructions:** Sweep every file and re-markup UI-element references per the convention
above. This is a large, mechanical, repo-wide change — safe to do file-by-file since each
conversion is local and doesn't depend on other files. Leave existing legitimate `<kbd>` keystroke
usage untouched (e.g. `undo-and-redo.md:40-48`, `tips.md:71-72` already do this correctly and can
serve as the reference pattern).

---

### Issue 8: Replace future-tense "will" with present tense for standing product behavior

**Labels:** style, docs
**Priority:** low (large volume, but purely a readability polish)

**Description:** Google style prefers present tense to describe what a product currently does;
reserve "will" for genuinely conditional/future events. "Will" is used ~400+ times repo-wide to
describe static, already-shipped behavior, heavily concentrated in the release-notes files
(`7x.md`, `8x.md`, `9x.md` — nearly every line) and feature docs (`git-lfs.md`, `githooks.md`,
`git-flow.md`, `single-sign-on.md`, `diff.md`).

**Examples:**
- `diff.md:54,60,66` — "Hunk view will show the diff as blocks…", "Inline view will show…", "Split
  view will show…" (three parallel headings, all should be "shows").
- `detached-head-state.md:31,40` — "the `HEAD` tag indicator will disappear…", "GitKraken Desktop
  will explicitly remind you…"
- `git-flow.md:24,49,67,75` — "GitKraken Desktop will create them…", "…will merge the feature
  branch into `develop`, and delete…"
- `7x.md:32,37`, `8x.md:41`, `9x.md:68` — release notes describing already-shipped features in
  future tense throughout.

**Reproduction command:** `grep -rn ' will ' gitkraken-client/*.md` surfaces all candidates; not
every hit needs a fix (genuinely conditional statements like "if you enable X, GitKraken will…"
are correct as-is) — judgment is needed per instance.

**Fix instructions:** For each instance describing standard/current behavior, convert "X will do Y"
to present tense "X does Y." Leave truly conditional or genuinely-future statements in "will." The
release-notes files (`7x.md`/`8x.md`/`9x.md`) are the highest-volume offenders and can be treated
as a single sub-pass within this issue.

---

### Issue 9: Remove "please" and "in order to" from instructional text

**Labels:** style, docs
**Priority:** low

**Description:** Google style discourages "please" in procedural instructions (acceptable only in
genuinely polite requests, e.g. asking a user to contact support) and flags "in order to" as
unnecessarily wordy — "to" is sufficient.

**"Please" in instructions (should be removed):**
`git-lfs.md:62`, `githooks.md:191`, `faq.md:139`, `experimental-features.md:20`, `jira.md:80`,
`organizations.md:140`, `pull-requests.md:69`, `quotes.md:28,44`, `renewals.md:30`,
`serverless.md:35,106`, `single-sign-on.md:174`, `gitkraken-account.md:33`,
`gitkraken-subscriptions.md:24,43`, `gitkraken-resellers.md:71`, `gitkraken-edu-pack.md:44`,
`windows-subsystem-for-linux.md:65`.
(Contact-support instances like `error-logs.md:20`, `diff.md:184` are acceptable per Google style's
allowance for polite requests — leave those as-is.)

**"In order to" (replace with "to"):**
`common-issues.md:104`, `7x.md:200`, `guide.md:78,112`, `insights.md:37,59`,
`interactive-rebase.md:49`, `terms-and-conditions.md:30` (twice in one line), `workspaces.md:129`,
`faq.md:127`.

**Fix instructions:** Delete "please" from each flagged instructional sentence (rephrase only if
removal leaves an awkward fragment). Replace "in order to" with "to" in every flagged instance.

---

### Issue 10: Fix non-descriptive link text ("here", bare URLs)

**Labels:** accessibility, style, docs
**Priority:** medium

**Description:** Google style (and WCAG) require link text that makes sense out of context — a
screen-reader user tabbing through a page's link list should be able to tell where each link goes
from its text alone. "Click here" / "here" / bare URLs as link text fail this.

**Locations:**
- `commit-signing-with-gpg.md:40` — "can be found [here](...)"
- `authentication.md:114` — "download PuTTY and Pageant from their page ... here"
- `error-logs.md:20` — link text is literally "here"
- `faq.md:87,122,128,179` — four separate "here" links
- `experimental-features.md:185` — "see our documentation here"
- `github-enterprise-issues.md:27` — "Follow the instructions here"
- `existing-pro-purchases.md:18` — bare URL `https://app.gitkraken.com` used as link text
- `preferences.md:179`, `quotes.md:32` — "here" links
- `themes.md:30` — "find the Data Location on your operating system here"
- `workspaces.md:129` — "more information on this setting here"
- `trial-activation.md:48` — literal URL as link text
- `how-to-install-self-hosted.md:12,13,14,74,113,168,260,299` — eight instances of the identical
  link text "Jump" (e.g. "[Jump](#install_centos) to CentOS"), indistinguishable from each other
  out of context.

**Fix instructions:** Rewrite each link's visible text to describe its destination, e.g. "download
PuTTY and Pageant" instead of "here"; "Jump to CentOS installation steps" instead of bare "Jump".
Never use a raw URL as link text when descriptive text is available.

---

### Issue 11: Standardize product naming to "GitKraken Desktop"

**Labels:** consistency, docs
**Priority:** medium

**Description:** `current.md:66` documents the official rename from "GitKraken Client" to
"GitKraken Desktop," but the rename was never propagated across the doc set. Several pages still
use the pre-rename name "GitKraken Git GUI" verbatim (suggesting shared/copy-pasted boilerplate),
release-notes pages still say "GitKraken Client," and many pages alternate bare "GitKraken" — which
is ambiguous with the company name — mid-paragraph with "GitKraken Desktop."

**Stale "GitKraken Git GUI" (should be "GitKraken Desktop"):**
`jira.md:4,10,27,31`, `trello.md` (title, description, lines 10,22,28), `gitlab-issues.md:10`,
`jira-data-center.md:10`, `gitlab-self-managed-issues.md:10`, `github-issues.md:10`,
`github-enterprise-issues.md:10`.

**Stale "GitKraken Client" (release notes; should be "GitKraken Desktop" per the rename, unless the
release note is historically describing a version before the rename — use judgment per file):**
`7x.md`, `8x.md`, `9x.md` throughout.

**Ambiguous bare "GitKraken" mixed with "GitKraken Desktop" in the same file:**
`authentication.md:10,60,125`, `azure-devops.md:9`, `commit-signing-with-gpg.md:52,63`,
`gitkraken-edu-pack.md:34`, `gitlab-gitkraken-client.md:10`, `gitlab-self-hosted.md:14`,
`github-gitkraken-client.md:10,30,32,51,122`.

**Other naming issue:** `self-hosted.md:12` stacks four different names for one product in a single
sentence: "GitKraken On-Premise Self-Hosted Server," "GitKraken Enterprise Self-Hosted,"
"GitKraken Enterprise On-Premise Server," "GitKraken Self-Hosted."

**Fix instructions:** Replace "GitKraken Git GUI" with "GitKraken Desktop" everywhere. In the
release-notes files, use "GitKraken Desktop" for entries describing current behavior; leave
historical entries that are unambiguously about a specific old version as-is if changing them would
misrepresent history. Replace ambiguous bare "GitKraken" with "GitKraken Desktop" when referring to
the application specifically (not the company). Pick one name for the self-hosted product in
`self-hosted.md:12` and use it consistently in that file.

---

### Issue 12: Fix list formatting (parallel structure + consistent punctuation)

**Labels:** style, docs
**Priority:** low

**Description:** Google style requires list items within a single list to be grammatically parallel
(all noun phrases or all imperative verb phrases) and punctuated consistently (complete-sentence
items get a period, fragments don't — pick one per list and apply it to every item).

**Examples:**
- `stashing.md:24-29` — first three items are Title Case UI labels (**Apply Stash**, **Pop
  Stash**, **Delete Stash**), last three shift to sentence case (**Hide**, **Hide all stashes**,
  **Show all stashes**) in the same list.
- `organizations.md:63-66` and the near-identical role list in `new-pro-purchases.md:88-91`
  describe the same four roles but use different punctuation conventions from each other.
- `azure-devops.md:13-18` — every item is a sentence fragment except the last, which ends in a
  period.
- `jira.md:53-58` — noun-phrase items ("Title and Description", "Status", "Assignee") mixed with a
  verb-phrase item ("Add comments").
- `trello.md:55-58` — same pattern as `jira.md:53-58`.
- `configure-self-managed.md:45-49` — sentence fragments and full sentences mixed in one bullet
  group.
- `open-clone-init.md:42-45` — periods on items 1 and 3 but not item 2.

**Fix instructions:** For each flagged list, rewrite every item to share the same grammatical form
(pick noun-phrase or imperative-verb-phrase, whichever fits the list's purpose) and apply periods
consistently — either every item ends in a period or none do, based on whether items are complete
sentences.

---

### Issue 13: Expand acronyms on first use; standardize number formatting

**Labels:** style, docs
**Priority:** low

**Description:** Google style requires spelling out an acronym in full on first use per page
(with the acronym in parentheses), and prefers spelled-out numbers zero through nine in running
text, numerals for 10 and above.

**Unexpanded acronyms:**
- `jira.md:76,80` — "JQL" never expanded in-page (only available via an external link).
- `self-hosted.md:17` — "LDAP" never expanded.
- `single-sign-on.md:121,124,133,140,147` — "SAML" used repeatedly without expansion, even though
  the same file correctly expands "IdP," "SSO," and "JIT" on first use — inconsistent within one
  document.

**Inconsistent number formatting:**
- `serverless.md:25` "There are 3 steps" vs. `open-clone-init.md:42` "you'll find three options" vs.
  `organizations.md:61` "There are four roles" — same construction, inconsistent numeral/word
  choice across files describing the same kind of thing.
- `pushing-and-pulling.md:98` — "an example 2 commits made locally, and 2 that have been made"
  (numerals) vs. Google style's preference for "two."
- `github-gitkraken-client.md:68` — "watch what used to be 8 steps be completed in one" — numeral
  and spelled-out number in the same sentence.
- `terms-and-conditions.md:20,28,34` — redundant "1 (one) business day," "12 (twelve) months,"
  "sixty (60) days" — pick numeral-only, drop the parenthetical duplicate.

**Fix instructions:** Expand SAML, JQL, and LDAP in full parenthetically on first use in each file
where they appear. Convert single-digit numbers in running text to spelled-out words (zero through
nine); use numerals for 10+. Remove redundant "numeral (word)" / "word (numeral)" duplication in
`terms-and-conditions.md`.

---

## Tier 3 — Cleanup / verification

### Issue 14: Typo and grammar sweep

**Labels:** docs, good-first-issue
**Priority:** low (mechanical, no judgment calls — good candidate for a coding agent to batch-fix
in one pass)

**Description:** Concrete typos and grammar errors found during the audit. No style judgment
needed — each is a straightforward correction.

- `common-issues.md:104` — "with with" (duplicated word) and "integrtion" → "integration"
- `configure-self-managed.md:20` — "the the license file" (duplicated word)
- `8x.md:703` — "GirKraken" → "GitKraken"
- `7x.md:178` — "generated when initializing a repository form GitKraken" → "from"
- `bitbucket.md:47` — "Alternativley" → "Alternatively"
- `diff.md:135` — "Alternativley" → "Alternatively"; "WIP sleected" → "selected"
- `github-gitkraken-client.md:57` — "Alternativley" → "Alternatively"
- `existing-pro-purchases.md:25` — "will populate the cost of add additional users" → garbled,
  rewrite as "...will show the prorated cost of adding the additional users."
- `git-lfs.md:49` — "GitKraken Desktopdoes not require" — missing space
- `github-actions.md:29` — "availible" → "available"; `:18` stray space before a period
- `github-issues.md:37` — "initally" → "initially"
- `gitlab-issues.md:44` — "initally" → "initially"; `:76` "thier" → "their"
- `faq.md:127` — see also Issue 9 ("in order to")
- `how-to-install.md:37` — "insalled" → "installed"
- `gitkraken-resellers.md:70` — "quantiy" → "quantity"; `:52` "fillout" → "fill out"
- `gitkraken-launchpad.md:10` — "relevant to you for a selected filters" — singular/plural mismatch
- `gitkraken-launchpad.md:37` — orphaned trailing `"` with no matching open quote
- `gitkraken-launchpad.md:45` — "created by you" appears twice in the same sentence
- `gitkraken-organization.md:14` — "for yourself" repeated, awkward/redundant phrasing
- `self-signed-certificates.md` — dense cluster: "certifiate" (10), "somthing" (26), "cerificate"
  (57), "certifacte" (75), "Cerificate" (85), "teminal" (90), "recieving" (104), "recieve" (117)
- `preferences.md:113` — "credentials that currently stored by" — missing "are"
- `pull-requests.md:32` — "commited" → "committed"
- `new-pro-purchases.md:70` — "consuume" → "consume"
- `organizations.md:104` — "Note," should be "Note:" to match the callout convention used
  elsewhere in the same file
- `quotes.md:28` — "cost of add additional users" — garbled, rewrite as "cost of adding additional
  users"
- `renewals.md:30` — "utlize" → "utilize" (though also flag for Issue 9's "utilize → use" fix)
- `squash.md:45` — voice shift to first-person plural ("we have rewritten our branch's history")
  mid-instruction where the rest of the doc uses second person — rewrite as "...because you have
  rewritten your branch's history."
- `staging.md:61` — "more than one changes needs to be discard" → "more than one change needs to
  be discarded"
- `teams.md:13-14` — "conflcits" → "conflicts"; "gorup" → "group"
- `trello.md:87` — "You may create a branches tied to a card" — article/plural mismatch, rewrite as
  "You may create branches tied to a card."
- `timelines.md:4` — frontmatter description references "Jira issues," a copy-paste leftover
  unrelated to this page's actual Timelines/milestones content; `:20` garbled run-on sentence;
  `:24` "connected to you GitKraken account" → "your"
- `windows-subsystem-for-linux.md:24` — "severly" → "severely"; `:121` "seperate" → "separate"
- `tips.md:108` — "right-cliking" → "right-clicking"
- `gitkraken-subscriptions.md:17` — "each while can further elaborate" — garbled, likely meant
  "each, which can further elaborate..."
- `cherrypick.md` — four different spellings of the same feature name in one 28-line file
  ("Cherry Pick" in frontmatter/heading, "Cherrypick Commit" and "cherry-pick" and "cherry pick" in
  body) — pick one term and use it consistently throughout the file.

**Fix instructions:** Apply each correction as listed. This issue has no open judgment calls and is
a good candidate to hand to a coding agent as-is.

---

### Issue 15: Verify supported OS versions in system-requirements.md

**Labels:** docs
**Priority:** medium (content accuracy, not a prose-style fix)

**Description:** `gitkraken-client/system-requirements.md` (lines 12, 20-27) lists CentOS/RHEL7 and
Ubuntu 14.04/16.04/17.04 ("Zesty") as supported platforms — all long past end-of-life.

**Research path (try before escalating to a human):**
1. Check internal consistency — grep the repo for other OS-version mentions
   (`how-to-install.md`, `how-to-install-self-hosted.md`, `windows-subsystem-for-linux.md`) and
   flag any that already disagree with `system-requirements.md`.
2. Fetch GitKraken's public download/system-requirements page — if it states current minimum OS
   versions, that's an authoritative, citable source; update the file to match directly.
3. Cross-check the currently-listed versions against public EOL dates (CentOS/RHEL 7: EOL
   2024-06-30; Ubuntu 14.04: EOL 2019-04; Ubuntu 16.04: EOL 2021-04; Ubuntu 17.04: EOL 2018-01, never
   an LTS release) — all four are unambiguously stale regardless of what the replacement should be.
4. If step 2 is inconclusive, GitKraken Desktop is Electron-based — propose a baseline aligned with
   current Electron/Chromium OS-support requirements (recent Ubuntu LTS, current RHEL major, current
   Windows/macOS), clearly labeled as *proposed* pending confirmation.

**Fix instructions:** Open a PR with findings from steps 1-3, citing sources inline. If step 2 gives
a definitive answer, use it directly. If not, use step 4's reasoning to propose a specific list and
tag a docs/support reviewer for confirmation before merging — don't block the issue from being
worked at all. Only skip straight to a "needs human" comment with no PR if none of steps 1-4 can be
completed (e.g., no network access).

---

## Tier 4 — Additional issues found outside the style-guide sweep

These surfaced from directly inspecting the repo's assets and structure (image references, code
fences, frontmatter) rather than the Google style categories — flagged separately since they're
correctness/tooling issues, not prose style.

### Issue 16: Fix broken and case-mismatched image references

**Labels:** bug, docs
**Priority:** high

**Description:** Cross-referencing every `/wp-content/uploads/...` image path used in the docs
against the files actually present in `_images/` turns up 26 references with no exact-case match —
12 are case-mismatches (the asset exists under a different capitalization) and 14 have no matching
file at all under any capitalization.

**Case-mismatches (asset exists, but casing differs — a real risk if the site is served from a
case-sensitive filesystem/host, even though it may resolve fine locally on macOS/Windows):**
- `9x.md:1041` references `Insights.png` → disk has `_images/insights.png`
- `organizations.md:32` references `gk-plans.png` → disk has `_images/GK-plans.png`
- `single-sign-on.md:185,189,193,197,201,205,209,213,217,221` reference
  `sso-example-idp-{1,2,3,4,5,6-1,7,8,9,10}.jpg` → disk has the same files with a `.JPG` extension
- `windows-subsystem-for-linux.md:87,125` reference `wsl-host-settings@2x.png` /
  `wsl-toast@2x.png` → disk has `.PNG` (uppercase extension)

**No matching asset found at all (verify against the live production site before assuming these are
dead — `_images/` in this repo may not be a complete mirror of every asset path, especially the
nested `timelines/...` paths which don't appear under any name in `_images/`):**
- `9x.md:1027` — `Focus-View.png`
- `pushing-and-pulling.md:130` — `set-default.png` / `set-default@2x.png`
- `timelines.md:14,18,26,30` — `gitkrakentimelines.gif`, `timelines-overview.png` (+@2x),
  `gitkraken-integration.png` (+@2x), `default.png` (+@2x) — all under
  `/wp-content/uploads/timelines/...` subpaths
- `diff.md:173` — `multi-selected-patch-v2.png` (disk has `multi-selected-patch.png` without
  `-v2`, possibly a stale reference to a renamed/replaced file)
- `tips.md:18` — `profile-example.png` / `profile-example@2x.png`
- `organizations.md:172` — `reactivate-pro-suite.png` / `reactivate-pro-suite@2x.png`

**Fix instructions:** For the case-mismatches, rename either the reference or the asset so they
match exactly (recommend lowercasing all asset filenames and references for consistency, since
that's the majority pattern in `_images/`). For the "no matching asset" group, check the live site
to determine whether each image genuinely renders today; if it does, source the correct asset file
and add it to `_images/`; if it's genuinely broken in production too, either restore the correct
image or remove the `<img>` tag and surrounding reference to it.

---

### Issue 17: Add language tags to fenced code blocks

**Labels:** docs, good-first-issue
**Priority:** low

**Description:** Of the fenced code blocks in the repo, all but one omit a language annotation
(` ```bash `, ` ```json `, etc.), so none of them get syntax highlighting when rendered. 12 files
are affected, mostly showing shell commands and terminal output.

**Locations:** `commit-signing-with-gpg.md:193,196`, `commits.md:45,50`, `faq.md:160,162`,
`git-lfs.md` (multiple: lines 55-93 region), and 7 other files — reproduce the full list with:
`grep -rn '^```$' gitkraken-client/*.md`

**Fix instructions:** For each untagged fence, add the appropriate language tag based on content —
` ```shell ` or ` ```console ` for terminal commands/output, ` ```json `/` ```yaml ` for config
snippets, etc. This is mechanical: read each block's content to pick the right tag, no prose
judgment needed.

---

### Issue 18: Add missing frontmatter to trials.md and experimental-features.md

**Labels:** docs, bug
**Priority:** medium

**Description:** Every other file in `gitkraken-client/` (86 of 88 checked) has a consistent
frontmatter block (`title:`, `taxonomy:`, `description:`, `category:`). `gitkraken-client/trials.md`
and `gitkraken-client/experimental-features.md` have no frontmatter at all, which likely breaks
site navigation, page titles, and SEO metadata for those two pages if the site generator relies on
these fields (every sibling page has them, strongly suggesting they're required, not optional).

**Fix instructions:** Add a frontmatter block to both files matching the structure used in a
sibling file on a similar topic (e.g. base `experimental-features.md`'s frontmatter on
`preferences.md`, and `trials.md`'s on `trial-activation.md`). Fill in an accurate `title` and
`description` reflecting each page's actual content; confirm the correct `taxonomy`/`category`
values by checking what similar pages use.

---

### Issue 19: Miscellaneous content-organization issues found during the audit

**Labels:** docs
**Priority:** low

**Description:** A handful of smaller organizational issues noticed while reading files for the
style audit, that don't fit the systemic patterns above.

- `authentication.md` — frontmatter `title` is "Other Integrations," but the page is entirely
  about HTTPS/SSH authentication and proxy configuration, not third-party integrations (a distinct
  topic already covered by `azure-devops.md`, `bitbucket.md`, etc.). This is likely to confuse
  both readers and any tooling that indexes docs by title. Suggest retitling to something like
  "Authentication" or "Git authentication (HTTPS/SSH)."
- `authentication.md:110` — heading `### I'm having an SSH issue.` uses first-person phrasing with
  a trailing period, inconsistent with every other heading in the file (noun phrases like "Proxy
  configuration," "Forget all"). Reword to match, e.g. "SSH troubleshooting."
- `GKC-Security.md:12` — table header "How is this information secured in the transfer" reads
  awkwardly; reword to "How is this information secured in transit" or "...during transfer." Minor,
  but this table underpins a security/compliance claim and should read cleanly.
- `self-hosted.md` — **needs-human-input**: noticeably thinner than its sibling page
  `serverless.md` covering the analogous on-prem product — only one screenshot, no per-OS install
  instructions, and the file ends abruptly after a callout box. Worth a human check on whether
  content is genuinely missing (vs. intentionally deferring to `how-to-install-self-hosted.md`)
  before assigning a rewrite.

**Fix instructions:** Retitle `authentication.md` and reword the two flagged headings/table cell as
noted — mechanical. The `self-hosted.md` content-gap item needs a docs-team decision on scope before
any agent writes new content; don't assign it for drafting until that's confirmed.

---

## Suggested handoff

- Issues 1-3 and 16 (bugs): quick wins, assign first — 16 in particular may affect what readers
  actually see today and is worth prioritizing alongside 1-3.
- Issue 4 (alt text) and Issue 7 (UI markup) are the highest-value/highest-effort items — good
  candidates for a dedicated coding-agent pass each, one PR per issue given the file count.
- Issues 5, 6, 8-13 are each safe to batch-fix repo-wide in a single PR per issue.
- Issue 14 and Issue 17 are fully mechanical — best "good first issue" picks for a coding agent
  with no ambiguity.
- Issue 18 is small and quick — good to pair with Issue 14/17 in the same batch.
- Issue 15 has a research path an agent can work through first (see the issue for steps); only
  escalate to a human reviewer if that path is inconclusive. Part of Issue 19 (`self-hosted.md`
  content gap) is still blocked on a human scoping decision before any drafting starts.

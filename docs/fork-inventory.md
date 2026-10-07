# Fork inventory / Fork 內容盤點

Audited on **2026-10-07** for **`zivechu/open-design`**. The pre-audit `main` head is [`2302efa5db0776a4364f92584196d6380c2f9404`](https://github.com/zivechu/open-design/commit/2302efa5db0776a4364f92584196d6380c2f9404), also present in [upstream](https://github.com/nexu-io/open-design/commit/2302efa5db0776a4364f92584196d6380c2f9404), committed on **2026-05-27**. Its tree is `8104d2ce7e9c858991d2e0b649b4fd6cc0bca564`; `package.json` declares version `0.8.0`.

This records the observed source baseline; it does not assert an intentional freeze or a maintenance policy. Later upstream README counts describe a different checkout and must not be copied into this fork without recounting. Download/release links and activity badges inherited from upstream describe upstream distributions and activity, not builds or activity of this fork.

此盤點以 fork 的原始碼基準為準，不推定維護者刻意凍結版本。更新時應重新計數，不能直接採用上游最新 README 的數字。

## Verified source inventory

| Catalog | Count | Mechanical source and scope |
|---|---:|---|
| Skills / 技能條目 | **137** | Tracked `skills/<slug>/SKILL.md`; 137 distinct frontmatter `name` values. Includes catalog stubs and older rendering entries still owned by this directory. |
| Design Templates / 設計範本 | **110** | Tracked `design-templates/<slug>/SKILL.md`; 110 distinct frontmatter `name` values. Derived `examples/*.html` cards are not additional packages. |
| Design Systems / 設計系統 | **150** | Tracked `design-systems/<slug>/DESIGN.md`. The loader accepts legacy packages without `manifest.json`; only `default/` has that optional manifest at this baseline. |
| Bundled Plugins / 內建外掛 | **401** | Tracked `plugins/_official/<tier>/<slug>/open-design.json`; 401 distinct manifest `name` values. Only this subtree is scanned by the bundled-plugin boot walker. |
| All plugin manifests / 所有外掛 manifest | **415** | All tracked `plugins/**/open-design.json`: 401 bundled + 2 community fixtures + 12 specification examples. This is not the bundled-plugin count. |

**A skill entry is not necessarily a fully vendored workflow.** For example, [`skills/ui-ux-pro-max/SKILL.md`](../skills/ui-ux-pro-max/SKILL.md) explicitly declares discovery-only scope. [`skills/AGENTS.md`](../skills/AGENTS.md) and [`scripts/seed-curated-design-skills.ts`](../scripts/seed-curated-design-skills.ts) explain the curated stubs and separate upstream installation. The inventory counts committed entries, not available external assets or successful executions.

技能條目不等於完整內建的工作流程；外掛也可能包裝既有設計系統或範本。因此，各目錄的數量應分別標示，不能相加後宣稱為更多技能或設計系統。

| Bundled plugin tier | Count |
|---|---:|
| `atoms/` | 13 |
| `design-systems/` | 142 |
| `examples/` | 140 |
| `image-templates/` | 45 |
| `scenarios/` | 11 |
| `video-templates/` | 50 |
| **Total** | **401** |

The 142 design-system plugin wrappers are distinct from the 150 packages under `design-systems/`. These are different catalogs, not conflicting totals. A valid `open-design.json` can stand alone: a sibling `SKILL.md` is optional in [`resolvePluginFolder`](../apps/daemon/src/plugins/registry.ts), so counting only manifest/skill pairs would undercount plugins.

Loader references: [`skills.ts`](../apps/daemon/src/skills.ts), [`design-systems.ts`](../apps/daemon/src/design-systems.ts), [`plugins/bundled.ts`](../apps/daemon/src/plugins/bundled.ts), and [`plugins/AGENTS.md`](../plugins/AGENTS.md). Counts exclude user-installed content, external marketplace listings, authoring directories without a catalog entry file, and nested side files.

## Statements audited

The following values refer to the pre-audit files at the baseline commit above. README fixes change counts, catalog ownership, and fork/upstream positioning; unrelated product claims are outside this audit.

| Location | Previous statement | Resolution |
|---|---|---|
| GitHub About | `19 Skills`, `71 brand-grade Design Systems` | Both stale. Suggested replacement below; About is repository metadata and is not changed by merging documentation. |
| English README introduction, badges, Skills opening, prompt-stack count, startup steps, directory tree, comparison, roadmap | `132` skills | Use 137 **entries**, disclose stubs, and separately identify 110 design-template packages. |
| English README at-a-glance and comparison | `129` systems; `2 + 70 + 57` presented as the total | Use 150 packages counted from `DESIGN.md`; remove an obsolete provenance subtotal as an inventory formula. |
| English README overview and Skills section | `27 prototype + 4 deck`; elsewhere `32 prototype + 9 deck` | These do not define either current directory inventory. Explain the split and mark the example tables as selections. |
| English README saved-template picker | “same surface as the shipped 132” | Rendering packages belong to the 110-package design-template catalog. |
| English README screenshots | `150-system library` as screenshot content | Retain the verified source count; use neutral screenshot captions because historical pixels were not recounted. |
| Traditional Chinese README introduction, overview, Skills opening, prompt stack, startup steps, directory tree, comparison, roadmap | `31` skills; badge says `131` | Align to 137 skill entries and separately identify 110 design-template packages. |
| Traditional Chinese README introduction, captions, prompt stack, startup steps, directory tree, Design System section, comparison, roadmap | `72` systems; overview says `129`; badge says `149` | Align source inventory to 150 packages and remove numeric screenshot captions. |
| Traditional Chinese README Skills section and saved templates | `27 prototype + 4 deck`; “內建 31 套” in the saved-template picker | Explain catalog ownership; saved-template comparison refers to 110 rendering packages. |
| Both READMEs: showcase links, deck attribution/licenses, HyperFrames paths, directory example lists | Moved rendering packages still addressed as `skills/<slug>/` | Point to their verified `design-templates/<slug>/` locations; retain entries still owned by `skills/`. |
| Both READMEs: skill/plug-in positioning | “Skills are files, not plugins”; rendering examples described as the entire skill catalog | Describe the separate skill/template catalogs and plugin manifests without changing runtime content. |
| Traditional Chinese README title | “官方開源替代品” | Remove “官方”; the English source claims an open-source alternative, not Anthropic endorsement. |
| Both READMEs: announcement, releases/downloads, activity badges | Upstream promotion/activity presented without fork scope | Label the source baseline and upstream links; preserve the inherited announcement as historical context. |
| Both READMEs: source checkout and design-system examples | Clone commands target upstream; a selected brand list is labeled the full catalog | Clone this fork for the documented inventory and label the abbreviated brand list as selected examples. |
| CHANGELOG `0.8.0` | `149` systems; README badge update `31 → 131` and `72 → 149` | Preserve as inherited release history, with an explicit historical-scope notice and current fork counts under Unreleased. These are not current inventory claims. |
| CHANGELOG `0.1.0` | `72` systems / `31` skills; later `57` imported specs | Preserve dated release events, not a current-total formula. |
| Both READMEs: plugins | No current bundled-plugin inventory | Add the verified 401-manifest breakdown; exclude community/spec fixtures. |

## Recount from a checkout

Run from the repository root. The command uses tracked paths rather than all local folders, parses JSON, rejects duplicate plugin names, and uses only Node built-ins. Use a fully populated checkout so the tracked manifests can be read. For the audited snapshot, check out the baseline SHA above.

```bash
node --input-type=module <<'NODE'
import { execFileSync } from 'node:child_process';
import { readFileSync } from 'node:fs';
const paths = execFileSync('git', ['ls-files', '-z'], { encoding: 'utf8' })
  .split('\0').filter(Boolean);
const count = pattern => paths.filter(p => pattern.test(p)).length;
const bundled = paths.filter(p =>
  /^plugins\/_official\/[^/]+\/[^/]+\/open-design\.json$/.test(p));
const names = bundled.map(p => JSON.parse(readFileSync(p, 'utf8')).name);
if (names.some(name => typeof name !== 'string' || !name) ||
    new Set(names).size !== names.length) throw new Error('Invalid/duplicate plugin names');
const byTier = {};
for (const p of bundled) {
  const tier = p.split('/')[2];
  byTier[tier] = (byTier[tier] ?? 0) + 1;
}
console.log(JSON.stringify({
  skills: count(/^skills\/[^/]+\/SKILL\.md$/),
  designTemplates: count(/^design-templates\/[^/]+\/SKILL\.md$/),
  designSystems: count(/^design-systems\/[^/]+\/DESIGN\.md$/),
  designSystemManifests: count(/^design-systems\/[^/]+\/manifest\.json$/),
  bundledPlugins: names.length,
  allPluginManifests: count(/^plugins\/.*\/open-design\.json$/),
  byTier,
}, null, 2));
NODE
```

Expected counts at this baseline: `137`, `110`, `150`, `1`, `401`, `415`; the tier breakdown must sum to `401`. Schema validation and the daemon's frontmatter parser were also used during the audit; the recount command is a source-inventory check, not an execution test.

## Suggested GitHub About description

> Fork of nexu-io/open-design at 2302efa5db07 (2026-05-27). Local-first, open-source design workspace with 137 skill entries (including catalog stubs), 110 design templates, 150 design systems, and 401 bundled plugins. BYOK coding-agent workflows.

About requires a separate repository-metadata update. Keeping the baseline in the description distinguishes this fork from newer upstream releases.

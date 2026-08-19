# Outstanding tasks

Small things that need a human with account access. Nothing here is urgent, but the
first one has a clock on it.

---

## 1. Google Search Console — remove the indexed al-folio demo URLs

**Why this matters.** The site was forked from the al-folio theme and shipped with its
demo content live: 29 template blog posts and 9 placeholder projects, all crawled and
indexed under this domain. Pages titled things like _"project 3 with very long name"_
were appearing in search results for the lab. Those files were deleted in `3c312e4`
(Aug 2026) and now 404, but **Google keeps serving deleted pages from its index for
months** unless asked to drop them. This is the step that actually clears them.

The sitemap is now 33 real URLs. It was 85, of which 67 were template documentation.

### Step 1 — Add the property

<https://search.google.com/search-console> → **Add property** → **URL prefix**

(Not _Domain_ — that needs DNS records, which we don't control on `github.io`.)

```
https://aai-research-lab.github.io/
```

### Step 2 — Verify ownership

Choose the **HTML tag** method. Google shows a meta tag; copy **only the content
value**, not the whole tag.

Then set **both** of these in `_config.yml` — the first alone does nothing:

| Line | Setting                       | Change to                     |
| ---- | ----------------------------- | ----------------------------- |
| ~126 | `google_site_verification:`   | the content value from Google |
| ~418 | `enable_google_verification:` | `true`                        |

Commit, push, wait for the deploy to go green in the Actions tab, then confirm the tag
is actually live before clicking Verify:

```bash
curl -s https://aai-research-lab.github.io/ | grep google-site-verification
```

If that returns nothing, `enable_google_verification` is still `false`. Verification
will fail with no useful explanation, which is the usual reason this step stalls.

### Step 3 — Submit the sitemap

**Indexing → Sitemaps** → enter `sitemap.xml` → Submit.

### Step 4 — Remove the demo URLs

**Indexing → Removals** → **New request** → **Temporarily remove URL**.

For each of the following, select **"Remove all URLs with this prefix"** — _not_
"Remove this URL only", or you'd be filing 67 separate requests:

```
https://aai-research-lab.github.io/blog/
https://aai-research-lab.github.io/projects/
https://aai-research-lab.github.io/_pages/
```

The third one matters because team bios were briefly served as raw markdown at their
source paths (fixed in `8d33356`).

Each request suppresses matching URLs for about six months — long enough for Google to
recrawl, hit the 404s, and drop them permanently.

### Step 5 — Check

Search Google for `site:aai-research-lab.github.io`. Anything still showing under
`/blog/`, `/projects/` or `/_pages/` is cached and should clear over the following days.
A week later, **Indexing → Pages** should list the old URLs under "Not found (404)",
which is the desired outcome.

---

## 2. Optional settings, currently off

| Setting                          | Where                      | Effect if enabled                                                                                    |
| -------------------------------- | -------------------------- | ---------------------------------------------------------------------------------------------------- |
| `social: false`                  | `_pages/about.md` line ~22 | ORCID, Google Scholar and GitHub are all configured, but the icons don't render on the front page    |
| `enable_google_analytics: false` | `_config.yml` ~415         | No traffic data at all. Also needs `google_analytics:` (~121) set to a `G-XXXXXXXXXX` measurement ID |

---

## 3. Nice to have

- **Photos for four team members.** Evelyn Juarez, Ayush Kumar, Prince Otegbulu and
  Victory Unegbu currently share the lab photo. JPEG, max 800px wide, under ~150 KB —
  see `CONTRIBUTING.md`.
- **Evelyn Juarez's LinkedIn**, the only current member without one.
- **Santiago T. Garcia's photo** — still the lab photo rather than a headshot.
- **Repository history is ~120 MB**, because the deleted al-folio media still lives in
  past commits. The working tree is small. `git filter-repo --strip-blobs-bigger-than 1M`
  would fix it, but rewrites every commit SHA and forces everyone to re-clone. Only
  worth doing if slow clones become annoying.

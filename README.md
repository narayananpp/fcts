# FCTS project page

Static, self-contained. Open `index.html` directly, or drop the whole folder on any static host
(GitHub Pages, Netlify, S3). No build step, no framework, no external requests — fonts, videos and
images are all local, so it also works offline and from a USB stick.

## Fill in before publishing

Everything you need to edit is near the top of `index.html`:

1. **Authors** — the line `<p class="authors" id="authors">Author list to be added</p>`.
   Replace with names and affiliation.
2. **Paper link** — `<a class="btn solid" href="#" aria-disabled="true" id="link-pdf">`.
   Set `href` to your PDF URL and delete `aria-disabled="true"`.
3. **Video link** — `id="link-video"` currently jumps to the embedded player. Point it at an
   external URL if you prefer.
4. **BibTeX** — the `<pre id="bib">` block near the bottom.

## Structure

| Section | What it shows |
|---|---|
| Hero | The 24 s teaser, autoplaying and looping |
| Abstract | Paper abstract |
| One expansion | Interactive Figure 2 walkthrough, 7 steps, with autoplay |
| The branch the search kept | Five terrain families along the winning branch |
| The evaluation environments | Both site scans with route overlays |
| Where the baselines stop | Three synchronized 3-way comparisons; baselines freeze at their real failure frames |
| What the final policy does | Uncut follow-cam runs, split into validation terrains and evaluation sites |
| Results | Table II with inline bars |
| On hardware | Three real-robot clips |
| Supplementary video | The full 2:54 video |

## Notes

- Total size is about 62 MB, nearly all video. The hero (4 MB) and the case panels (4 MB) load
  eagerly; every other clip uses `preload="none"` and a poster image, so the first paint is light.
- The case comparison drives three `<video>` elements off one clock, freezing each baseline at its
  measured failure time (Case 1: 3.97 s / 2.73 s, Case 2: 3.07 s / 5.00 s, Case 3: 6.00 s / 3.50 s).
  Those constants are in the `CASES` array if you ever re-cut the clips.
- The red failure markers are positioned as percentages in the same array (`mark`), so nudge them
  there if a clip changes.
- Respects `prefers-reduced-motion`: the walkthrough and case players won't autoplay.

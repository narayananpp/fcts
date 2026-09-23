# FCTS — project page

Source for the project page of **FCTS: Failure-Guided Curriculum Tree Search Over Generated Terrain for Legged Parkour**.

Quadruped parkour policies fail on the compound geometry of real industrial and disaster-response sites because their training curricula never cover it. FCTS turns each localized traversal failure — its location, termination mode, robot state and surrounding geometry — into the terrain the policy trains on next, and uses Monte Carlo Tree Search to explore competing curriculum trajectories under a fixed budget. On held-out courses rebuilt from scanned sites it raises success from 28.4% to 85.8% on a medium course and from 14.9% to 44.7% on a hard one, and transfers to a physical quadruped.

The page carries the abstract, an interactive walkthrough of the method, synchronized baseline comparisons, uncut policy rollouts, results and the hardware video.

## Running it

Static. Open `index.html`, or serve the folder. No build step and no external requests.

## Before publishing

In `index.html`: the author line (`id="authors"`), the paper link (`id="link-pdf"` — set `href` and remove `aria-disabled`), and the BibTeX block (`id="bib"`).

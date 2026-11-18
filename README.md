# From Circuits to Solid Models: SolidWorks Portfolio

**Author:** Raymundo "R@y" Olguin
B.S. Electrical & Computer Engineering (Electrical Engineering focus) · Minors: Planetary Science, Mathematics, Computer Engineering, Italian
BE-221 Introduction to CAD · University of Arizona · Fall 2026
**Live site:** https://rayolguinm.github.io/SolidWorks/

## What this is
An interactive web portfolio of 11 homework sets and 1 project: 70 SolidWorks part files, 11 assemblies and 23 ANSI drawings. It has a four-viewport 3D studio, engineering analysis typeset in LaTeX, a referenced validation audit, and a phone layout for iPhone.

Every model, mesh, preview and drawing sheet was extracted directly from the original `.SLDPRT`, `.SLDASM` and `.SLDDRW` binaries. Nothing was redrawn by hand.

## Page architecture
The page tells one story in two parts.

**Part I · The story**
| Block | Anchor | Content |
|---|---|---|
| Hero | `#overview` | Title, author byline, major and minors, headline counts |
| Prologue | `#story` | Why an electrical engineer learns CAD; one card for the EE major and each minor (Computer Engineering, Mathematics, Planetary Science, Italian); clickable semester timeline |
| Act I · From sketch to solid (*Dallo schizzo al solido*) | `#act1` | HW1 to HW4 |
| Act II · The language of drawings (*Il linguaggio del disegno*) | `#act2` | HW5, HW6 |
| Act III · Parts that move together (*Parti che si muovono insieme*) | `#act3` | HW7, HW8 |
| Act IV · Designing for production (*Progettare per la produzione*) | `#act4` | HW9, HW10, HW11 |
| Act V · From file to object (*Dal file all'oggetto*) | `#act5` | Project 1 |

Each act opens with a short story paragraph and an "Electrical engineering lens" that ties the work back to EE. Each homework section lists its models (click to open in the 3D studio) and drawings (click to open in the zoomable sheet viewer).

**Part II · The evidence**
| Appendix | Anchor | Content |
|---|---|---|
| A · Technical skill map | `#skills` | Feature counts read from the files, capabilities list |
| B · 3D viewport studio | `#studio` | Third-angle 4-up viewports, section, explode, display modes, mass properties |
| C · Engineering analysis | `#analysis` | C.1 to C.11 (projections, SE(3) transforms, mass properties, tessellation, rack and pinion, four-bar, spring, threads, 3D printing, gear trains, tolerance stacks) |
| D · Drawing set | `#drawings` | All 23 sheets |
| E · Validation audit and references | `#refs` | Claim-by-claim audit and APA 7 reference list (peer-reviewed papers, reference books and standards; no Wikipedia) |

The sticky navigation highlights the act or appendix you are reading.

## What is new in this version
- **HW10 · Compound Gear Trains & Motion Study.** Two-stage (Project 10-11, 7.11 : 1) and three-stage (Project 10-15, 18.96 : 1) spur-gear reducers with Toolbox 16DP 14.5° gears, 24:64 gear mates and a rotary motor motion study. 2 assemblies, 5 unique parts, 2 exploded BOM drawings.
- **HW11 · Tolerancing & Worst-Case Stack-Up.** Step block (Figure P8-2), three-hole plate with chain vs baseline dimensioning (Figure P8-5), and Box Top / Box Bottom fit check (Project 8-12). 4 parts, 3 drawings.
- **Analysis C.10:** gear geometry, train value, contact ratio, a pinion interference note, and the inertia the motor sees (reflected inertia from the meshes).
- **Analysis C.11:** worst-case and root-sum-square tolerance stacks, with the EE resistor-divider analogy.
- **Validation:** 7 new closed-form volume checks (13 total, max error 0.51%), 7 new audit rows, 3 new peer-reviewed references (Greenwood & Chase 1987; Chase & Parkinson 1991; Pasch & Seering 1984).
- **Story architecture:** new hero, prologue, five acts with Italian titles, timeline, Part I / Part II structure, active-section navigation, Italian minor added everywhere.
- **Share image:** `og-image.png` regenerated with the new title and counts.

## Files
| Path | Purpose |
|---|---|
| `index.html` | The page. Open Graph / Twitter tags in `<head>` give LinkedIn its preview. |
| `og-image.png` | 1200 × 627 share image that LinkedIn shows with the link. |
| `README.md` | This file. |
| `assets/*.txt` | Compressed triangle meshes (base64 of zlib-deflated binary: header, float32 positions in meters, int8 normals, uint32 indices). |
| `assets/*_prev.png` | SolidWorks preview thumbnails extracted from each file. |
| `assets/*_sheet.png` | Drawing sheets extracted at native resolution. |
| `assets/*_user.png`, `*.jpg` | Sketch screenshots and renders. |

New HW10 and HW11 assets follow the same naming pattern, for example `assets/HW10_Olguin_HW10_Olguin_Prj1015_HW10_Olguin_Prj1015.txt` and `assets/HW11_Olguin_HW11_Olguin_Prj85_sheet.png`.

## Publish on GitHub Pages
1. In the `rayolguinm/SolidWorks` repository, upload `index.html`, `og-image.png`, `README.md` **and the whole `assets` folder** (Add file > Upload files, drag them in, commit). Existing asset files are unchanged; the new ones are added alongside them.
2. Settings > Pages: Branch `main`, folder `/ (root)`.
3. After the green check, open the site and hard-refresh.
4. LinkedIn caches previews. To show the new share image, paste the link into https://www.linkedin.com/post-inspector/ and click Inspect.

## Notes
- The 3D studio needs WebGL and loads Three.js and MathJax from the jsDelivr CDN, so the page needs an internet connection.
- Opening `index.html` directly from disk will not load the meshes because browsers block `fetch` on `file://`. Use the live site or a local server (`python -m http.server`).
- The gear interference note in C.10 is a design observation about ideal 14.5° full-depth gearing. It does not change the assemblies or the ratios.

Modeled, drafted and written by Raymundo "R@y" Olguin.

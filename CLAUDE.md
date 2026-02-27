# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the conference website for **NERCCS 2026** (Ninth Northeast Regional Conference on Complex Systems), held March 11–13, 2026 at the University of Rochester. The site is a static GitHub Pages site with no build step.

## Repository Structure

- `index.html` — Single-page conference website (all content lives here)
- `NERCCS2026-program-book.tex` — LaTeX source for the conference program booklet
- `NERCCS2026-program-book.pdf` — Compiled program book (linked from `index.html`)
- `css/` — Bootstrap + custom styles (`style.css`)
- `js/` — jQuery, Bootstrap, and custom scripts
- `img/` — Speaker photos, logos, venue images
- `fonts/` — Web fonts

## Editing the Website

The entire website is a single static HTML file (`index.html`). Key sections and their `id` anchors:

| Section | Anchor ID |
|---|---|
| About | `#section-about` |
| Call for Submissions | `#section-cfp` |
| Keynote Speakers | `#section-speakers` |
| Program | `#section-program` |
| Venue | `#section-venue` |
| Registration | `#section-registration` |
| Organizers / Sponsors | `#section-organizers` |

Content is frequently commented out using `<!-- ... -->` to toggle visibility of items (e.g., award results, travel funding notices, EasyChair links). Check for commented-out blocks before adding new content.

## Editing the Program Book (LaTeX)

The program book (`NERCCS2026-program-book.tex`) uses custom macros for consistent formatting:

- `\TimeBlock{label}{time}{location}` — Block heading (keynote, break, session block)
- `\Session{room}{title}{chair}` — Parallel session header with optional chair
- `\Talk{time}{title}{author}{affiliation}{notes}` — Individual talk entry (inside `itemize`)
- `\BreakItem{label}{time}` — Simple break/meal line
- `\OverviewGrid` — At-a-glance table grid (placed at end of document)

To compile the PDF: `pdflatex NERCCS2026-program-book.tex` (run twice for cross-references). Then update the tracked PDF.

## Deployment

Push to `main` branch — GitHub Pages serves the site automatically from the repo root. No build step required.

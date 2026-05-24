# Music Favorites — Changelog

## v2.0 — 2026-05-24
- **Complete rebuild: User-created categories instead of hardcoded sections**
  - Removed hardcoded song data (app starts empty)
  - Users now create their own categories (Sleep, Workout, Chill, Focus, etc.)
  - Added Category Management in Settings (create, delete categories)
  - Items organized by category, then by star rating (5-Star, 4-Star, etc.)
  - Updated data model: items now use `category` field
- Simplified render logic for cleaner, more maintainable code
- Updated Help guide to reflect new category-based organization
- Generic app template ready to share with other users
- All data remains private in localStorage (no server-side storage)

## v1.6 — 2026-05-24
- Reorganized section order: New, Favorites, Sleep, Hypnosis, Other
- Renamed "Miscellaneous" section to "Other" (includes Holiday items)
- Updated filter buttons to match new section order
- New section now shows recently added items
- Added "Mark as New" checkbox to add/edit modal
- Added Section dropdown: pick Sleep, Hypnosis, or Holiday to auto-set Type
- Sections now collapse by default on page load
- Drag & drop sorting now functional in edit mode

## v1.5 — 2026-05-24
- Restructured section layout: headers now directly precede their content bodies
- Fixed section headers to display as full-width stacked buttons matching Workout Log style
- Fixed sub-headers to use proper `.sub-section-label` styling
- Reduced Expand All / Collapse All button size and added teal accent color
- Added Export Data button: download all music favorites as JSON
- Added Import Data button: restore data from previously exported JSON file
- Added Help section in settings with usage guide

## v1.4 — 2026-05-24
- Switched accent color to teal blue (#17a2b8)
- Changed header title to solid teal instead of gradient
- Hidden bottom tab navigation buttons (Music, Positive, Sleep)
- Styled section headers (Favorites, Holiday, Hypnosis, Sleep, Miscellaneous) as equal-width flex row
- Added "All" filter to music section so you can exit filtered views
- Added spacing between filter buttons (6px gap)
- Items sorted by star rating (highest first)
- Added visual interest with teal accents on edit buttons, active tab, and add button

## v1.3 — 2026-05-24
- Redesigned to match Workout Log's minimal, clean aesthetic
- Uppercase section headers with clear hierarchy
- Simple row-based item layout
- Clean spacing and minimal visual clutter
- Collapsible sections matching Workout Log pattern

## v1.2 — 2026-05-23
- Redesigned item structure to match Workout Log: compact row layout
- Removed badge pills to save space (NEW, PLAYLIST, HOLIDAY, etc.)
- Smaller card size (56px min-height vs previous larger cards)
- Cleaner two-line layout: title on first line, artist + year on second
- Reduced icon size from 46px to 36px

## v1.1 — 2026-05-23
- Fixed Favorites section to exclude holiday, hypnosis, and sleep-music items
- Favorites now properly contains only regular music items (albums, playlists, etc.) rated 1-3 stars
- Hypnosis and Sleep sections now appear only in Music tab when matching items exist

## v1.0 — 2026-05-23
- Initial release
- Three tabs: Music, Positive, Sleep
- Music tab: Playlists, Albums, Singles, Holiday, Not Yet Rated sections
- Filter chips: All, ♥♥♥♥, Albums, Playlists, New, Review, Unrated, Singles, Holiday
- Sleep tab: Hypnosis and Sleep Music sections with 😵‍💫 sleep rating display
- Positive tab: Trinity Affirmations list
- Search bar with clear button
- Tap any card to open in Apple Music
- Purple accent (#bf5af2), dark iOS theme matching Workout app
- PWA manifest — add to iPhone home screen via Safari Share → Add to Home Screen

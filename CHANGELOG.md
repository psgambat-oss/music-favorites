# My Music Library — Changelog

## v2.4 — 2026-05-29
- **UI improvements: Section alignment and default collapse state**
  - Added explicit `justify-content: flex-start` to `.section-main` and `.sub-section-label` for consistent left alignment
  - All sections now render as collapsed by default when entering filters
  - Cleaner interface: users can expand sections individually or use "Expand All" button
  - Chevrons properly indicate collapsed/expanded state

## v2.3 — 2026-05-29
- **UI refinement: Left-aligned chevron indicators**
  - Moved chevron icons (›) to left side of all expandable headers for more conventional UI pattern
  - Applied to category headers, rating sub-headers, and artist headers
  - Improves visual consistency and makes expandable sections more obvious
- **CSS spacing improvements**
  - Updated `.section-main` to use `gap: 8px` instead of `justify-content: space-between`
  - Added `gap: 8px` to `.sub-section-label` for proper chevron-content spacing
  - Maintains visual hierarchy and readability
- **Bug fix**
  - Fixed missing chevron in category rating headers (catContent rendering path)
  - Ensures consistent visual presentation across all view modes

## v2.2 — 2026-05-25
- **Card layout redesign**
  - Reorganized card display: Title, Year • Rating, Artist on separate rows
  - Eliminates text wrapping for long titles
  - Improved readability and visual hierarchy
- **Star rating display throughout**
  - Gray star (★) displays after all rating labels
  - Ratings shown as "FOUR (4) ★" in cards, section headers, and dialog
  - Added dynamic rating preview in Add/Edit modal
- **CSV import improvements**
  - Proper CSV parser handles quoted fields with commas (e.g., artist names like "The Reds, Pinks, and Purples")
  - Case-insensitive category validation (GENERAL matches General)
  - Skip instruction rows automatically when importing template
- **Bug fixes**
  - Filter Buttons now import/export correctly with bidirectional sync
  - Type field normalized to lowercase (Album → album)

## v2.1 — 2026-05-25
- **Renamed app: "Sound Vault" → "My Music Library"**
  - Updated app title, meta tags, and manifest
  - Home screen display: "Music Library" (short_name for better mobile fit)
  - More personalized and descriptive app name
- **Export improvements: Native file sharing**
  - iOS/Android: Share sheet (AirDrop, Mail, Messages, etc.)
  - Desktop: Download to Downloads folder
  - Uses `navigator.canShare()` API with fallback to `URL.createObjectURL()`
  - Filename updated to `my-music-library-YYYY-MM-DD.json`
- **Top Artists feature**
  - New `isTopArtist` flag on items
  - Settings → "Top Artists Management" section with checkboxes
  - Subtle ★ badge (teal, 70% opacity) displays next to artist name
  - In Artist view: top artists bubble to top of list
  - Badge also appears on artist section headers
  - New localStorage key: `music_favorites_top_artists_v1`
- **Rating vs Artist toggle relocation**
  - Moved from below Expand/Collapse to same line (left side)
  - Now visible in ALL category filter views, not just "All"
  - Hidden when searching or filtering by type
  - Maintains all previous functionality
- **List import feature: Import artists**
  - New Settings section: "Import Artists"
  - Paste artist names (one per line) into textarea
  - Select target category
  - Creates items with auto-populated fields (artist, category, type, rating=0)
  - Items marked as "New" for easy identification
  - New functions: `parseArtistList()`, `importArtistsList()`

## v2.0.2 — 2026-05-24
- **Feature: Sort toggle integrated into All filter mode**
  - Added "Rating • Artist" toggle below Expand/Collapse buttons
  - Only visible when "All" filter is active
  - Click to switch between rating-based and artist-based sorting
  - Active sort mode displays in bright teal, inactive mode in gray
  - New `renderSortToggle()` function manages toggle rendering
  - New `setSortMode(mode)` function handles sort mode switching
  - Maintains sort preference across page reloads
- **UI cleanup: Removed star icons from rating sub-categories**
  - Rating headers now show "Five (5)", "Four (4)", etc. instead of "⭐ Five (5)"
  - Cleaner, more minimal appearance
- **Updated app icon**
  - New musical note icon with sound waves on teal gradient background

## v2.0.1 — 2026-05-24
- **Bug fix: Settings modal buttons now clickable**
  - Added `pointer-events: auto` to `.modal-btn` CSS class
  - Export, Import, and Help buttons in Settings now respond to clicks
  - Cleaned up redundant inline pointer-events styles

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

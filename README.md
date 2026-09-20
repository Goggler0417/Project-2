# Bookmark Database Editor v1.2

- **Version:** v1.2
- **Main file:** `index.html`
- **Folder:** `v1.2`
- **Run:** open `index.html` in a modern browser.
- **Storage:** browser `localStorage`.

## v1.2 changes

### Main Page → Page → Tab
Each Page can contain multiple Tabs. Each Tab has its own independent:
- Schema
- Records
- Categories
- Tags
- Profiles
- Search/sort settings
- Layout settings

### Tab customization
Tab settings support:
- name / icon / description
- Grid or List layout
- title Field
- search on/off
- independent Schema
- Field add/delete/rename/type change

### Popup editing
Page, Tab, Schema and Record editing are handled through Popups.

### Hyperlinks
URL fields are rendered as clickable links and open in a new browser tab.

### Field types
`text`, `long_text`, `url`, `number`, `boolean`, `date`, `datetime`, `image`, `file`, `color`, `rating`, `tag`, `tag[]`, `category`, `category[]`, `profile`, `profile[]`, `relation`, `relation[]`, `enum`, `duration`, `markdown`, `json`.

### Planned extensions
- title itself linking to a URL Field (`titleLinkField`)
- richer Table layout
- actual image/file storage
- relation UI
- dedicated Tag/Category/Profile management Tabs
- per-Tab custom actions and detail layouts
- cross-Page relations
- cloud upload/download sync
- site-specific extractors

The old DB is intentionally not converted automatically. The planned data flow remains:

RAW HYPERLINKS → SITE-SPECIFIC EXTRACTOR → PAGE/TAB SCHEMA → BOOKMARK DATABASE

# Tagmark v2.28

Legacy UI integration pass.

- Uses the legacy app's bookmark card, folder, profile card, tag-chip and editor visual grammar as the primary renderer.
- Schema remains generic: field names, data types, input types, display types, Tag Head restrictions and options remain configurable.
- Bookmark folders are independent of schema fields and persist through `record.folderId`.
- Folders and standalone bookmarks share the same sorted result stream, matching the legacy app's placement model.
- Tag display is shared across Bookmark/Profile/Character views.
- `item` display uses the field name as the label and strips the Tag Head from tag values.
- Character details remain collapsed by default and expand from the character name.

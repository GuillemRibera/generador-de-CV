# Repository overview
- Single-file web app: `CreadordeCV.html` (~974 lines). All HTML/CSS/JS in one file.
- Purpose: bilingual (ES/CA) CV/resume generator with live preview, inline editing, drag-and-drop block reordering, image upload (photo), autosave to `localStorage`.
- Outputs: print/PDF via `window.print()`, Microsoft Word `.doc` (HTML wrapped as MS Word), LibreOffice `.odt` (same HTML blob), and JSON export/import of form data.
- Footer credits and CC BY-NC-SA license (linked in HTML).

# How to run / develop
- No build system, package manager, dependencies, or dev server. Just open `CreadordeCV.html` directly in a browser (file:// works). 
- Changes are hot-in-place: edit the file and refresh browser.
- Data persistence: `localStorage` key `cv_builder_data` (JSON). Use "Exportar/Importar Datos (JSON)" or clear via UI ("Borrar todos los datos").

# Code structure (key parts in `CreadordeCV.html`)
- Translations: `translations` object (ES/CA) with keys used by `changeLanguage(lang)`. Language state in `currentLang`, photo in `photoBase64`.
- Form building: dynamic blocks via `addExperience/addEducation/addComplementary/addLanguage`, data gathered by `gatherFormData()`, restored by `populateForm()`.
- Preview/render: `generatePreview()` builds HTML for `#resume-content`; `initEditor()` enables inline click-to-edit on `.editable` and block styling on `.block-editable`; `initNativeDragAndDrop()` reorders blocks.
- Exports: `downloadFile(format)` clones preview, strips `.editable/.block-editable/non-exportable`, wraps in MS Word HTML for `.doc`/`.odt`. Print CSS hides form/editor/controls.
- Auto-save: `autoSave()` on input/select changes via `attachAutoSave()`.

# Conventions / gotchas
- Bilingual: when adding UI strings, add to both `es` and `ca` in `translations` and update `changeLanguage()` to wire them (placeholders/labels). Default `es`.
- Photo: FileReader -> data URL stored as `photoBase64`; preview renders as circular image in header.
- Exports rely on inline styles + tables for layout (Word/ODT compatibility). Background colors on blocks require export to `.doc/.odt` to render well outside print.
- Drag handle is inside `.block-controls` (made draggable on mousedown); blocks use native HTML5 drag-drop in preview.
- No tests, linting, or CI configured. No external CDN deps (all code inline; only CC image loaded from mirrors.creativecommons.org).
- Git repo initialized on branch `main` with single commit adding `CreadordeCV.html`.

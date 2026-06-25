# Moodle Assessment & Feedback Utilities

A collection of lightweight, single-file HTML utilities designed for higher education practitioners to streamline student assessment preparation, bulk feedback delivery, and rubric management. 

These tools are built using **vanilla JavaScript** and modern responsive CSS (via Tailwind CDN) to ensure they require **zero server configuration, zero installation, and operate entirely client-side** in the browser. 

---

## The Toolkit At a Glance

| Tool File | Production Name | Primary Target User | Key Function | Output Artifact |
| :--- | :--- | :--- | :--- | :--- |
| `builder-builder-zip.html` | **Submission Builder Builder (ZIP/Media)** | Staff / Academics | Designs reflection forms that capture large media files. | A standalone `.html` web form |
| `moodles.html` | **Moodles: Bulk Feedback Generator** | Marking Tutors | Cross-references Moodle ZIP structure with grading CSVs. | A bulk-uploadable Feedback ZIP |
| `Turnitin_rubric_viewer.html` | **Turnitin Rubric & RBC Tool** | Staff / External Examiners | Visualizes, edits, and exports proprietary Turnitin `.rbc` files. | Fixed `.rbc` or formatted `.docx` |

> **Archived:** `builder-builder.html` (Standard, no media support) has been retired in favour of `builder-builder-zip.html` and moved to `_archive/`.

---

## Deep Dive into Content

### 1. Submission Builder Builder (`builder-builder-zip.html`)

This utility allows academics to construct bespoke digital scaffolding forms for students to compile their submissions. Instead of receiving a chaotic array of files, tutors can configure exactly what they need a student to declare or reflect upon.

* **How it works:** Tutors open the app, arrange components on the workspace canvas (Student Details, Rich Text blocks, Checklist tables, Targeted Reflection Questions, File Attachment slots, and AI Disclosures), and click **Export HTML**.
* **The Output:** A completely customized, beautifully styled single-file HTML form. Tutors distribute this file directly to students (via Moodle, email, or a shared drive).
* **Student Experience:** Students fill out the form locally. The form tracks their word counts, alerts them if they embed images, verifies necessary checklist items, saves progress automatically to local storage, and compiles everything into a bundled `.zip` submission package (containing a `.docx` document and all attached media files) ready for final upload.

### 2. Moodles: Bulk Feedback Generator (`moodles.html`)
Manually parsing student file folders down from Moodle and matching them to individual feedback matrices is an administrative bottleneck. **Moodles** automates this mapping seamlessly in a 3-step client-side wizard.

* **Step 1:** Drop in the untouched `submissions.zip` downloaded directly from Moodle. The app instantaneously extracts student names, folder names, and individual unique Moodle Submission IDs into an interactive, filterable data table.
* **Step 2 (Optional):** Upload the matching Moodle Grading Sheet CSV. The tool auto-detects column variants (`Submission id`, `Username`, `Grade`) and merges student institutional data, emails, and primary marks directly into the interface grid.
* **Step 3:** Supply a `.docx` Feedback Template embedded with dynamic text tokens (`{{Name}}`, `{{MoodleID}}`, `{{StudentID}}`, `{{Grade}}`). 
* **The Output:** Click **Generate** to instantaneously download a single master ZIP file containing custom, populated Word feedback files correctly labeled and partitioned into individual student directories. Drop this ZIP back into Moodle's bulk upload tool to update the entire cohort at once.

### 3. Turnitin Rubric Tool (`Turnitin_rubric_viewer.html`)
Turnitin uses a nested JSON structure with the proprietary extension `.rbc` to import/export criteria maps. These files are notoriously difficult to audit, tweak, or convert into documentation for internal validation sheets or external examiner handbooks.

* **How it works:** Upload any native Turnitin `.rbc` file. The viewer cleanly unravels the matrix data, structuring it into an elegant table with a persistent sidebar column tracking weights and individual grade bands.
* **Edit & Manipulate:** Enable **Edit Mode** to live-edit criteria names, adjust wording descriptions on the fly, or quickly add entirely new row conditions.
* **The Output:** Cleanly serialize modifications back out into a fresh `.rbc` file for Turnitin re-import, or convert the layout into a perfectly formatted, landscape-oriented Microsoft Word document (`.docx`) table for course specifications.

---

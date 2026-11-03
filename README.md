<p align="center">
  <img src="assets/hero.svg" alt="Wexvo — Sensitive text. Local control. Offline Windows privacy workspace." width="100%">
</p>

<p align="center"><strong>Offline by design.</strong> Human review before sharing.</p>

<p align="center">
  <a href="#watch-the-workflow">Video</a> &nbsp;·&nbsp;
  <a href="#see-wexvo-in-action">Preview</a> &nbsp;·&nbsp;
  <a href="#a-small-step-before-you-share">How it works</a> &nbsp;·&nbsp;
  <a href="#everyday-controls">Controls</a> &nbsp;·&nbsp;
  <a href="#privacy-with-clear-boundaries">Privacy</a> &nbsp;·&nbsp;
  <a href="#validation-and-current-status">Validation</a>
</p>

---

Wexvo helps you prepare sensitive text before pasting it into an AI assistant. It replaces detected identities with placeholders, keeps the result available for review, and can restore known placeholders in the answer using the active session.

Built for Windows, with local Dutch and English detection and a practical workflow for technical logs, correspondence and document text.

> **Beta.** Automated detection can miss sensitive data or mask useful context. Always review before sharing.

## Watch the workflow

**59 seconds · Double Copy from your app · 1920 × 1200 · English captions**

https://github.com/user-attachments/assets/d6bface5-82a5-4987-8774-f0e55b0eaa47

Select text in your app → press Ctrl+C twice → Quick Review opens automatically → review the green placeholders → ChatGPT → copy its answer twice → review restored values in blue.

[Download the full-resolution MP4](assets/wexvo-background-workflow.mp4) · [Manual corrections, swaps and undo](assets/wexvo-walkthrough.mp4) · [Read the steps](#a-small-step-before-you-share)

<sub>Start with Wexvo running in the background: select text and copy twice to open Quick Review. No need to open the full editor. Recorded with fictional email text in Notepad, Google Chrome and the Wexvo executable. Use fullscreen for the clearest text.</sub>

<details>
<summary>About this recording</summary>

The new opening records a fictional email in Notepad: selection, Double Copy and the automatic green Quick Review, with the full Wexvo editor hidden. It is followed by the previously recorded real Chrome round trip. These are separate recording sessions, so placeholder labels differ; the transition is labelled in the video. Setup and idle time were cut, and English captions and a final close-up were added. The sequence from selecting the ChatGPT answer through the automatic blue restore review remains uncut. No separate clipboard bridge or recreated application screen is used. Clipboard behaviour can vary between applications and systems.

</details>

## See Wexvo in action

<p align="center">
  <img src="assets/workspace.png" alt="Actual Wexvo editor with a fictional everyday email: names, an email address and meeting times are masked while the message remains readable." width="100%">
</p>

<p align="center"><sub>An everyday email: original text on the left, reviewed output on the right.</sub></p>

<table>
  <tr>
    <td width="50%" valign="top">
      <h3>Review what leaves your device</h3>
      <img src="assets/quick-review.png" alt="Actual Quick Review showing a fictional email with green placeholders and Copy and close, Open full editor and Cancel controls.">
      <p>Inspect green placeholders, add manual redactions and confirm when you are ready.</p>
    </td>
    <td width="50%" valign="top">
      <h3>Review what comes back</h3>
      <img src="assets/restore-review.png" alt="Actual restoration review showing fictional original values highlighted in blue and the Undo swap control.">
      <p>Inspect restored values in blue. Swap blocks when needed, then explicitly copy the answer.</p>
    </td>
  </tr>
</table>

<sub>Actual application captures, rendered offscreen with newly written fictional examples. The header is an illustration. No private documents or real contact details are shown.</sub>

## A small step before you share

| 1 · Copy twice | 2 · Review locally | 3 · Confirm and paste |
| :--- | :--- | :--- |
| Select text and press **Ctrl+C twice** in quick succession. | Check the masked result. Click a word to redact it everywhere, or select text and choose **Redact everywhere**. | Choose **Copy and close**, or press **Ctrl+Enter**. Then paste into your chosen application. |

**For the return journey:** copy an AI answer containing Wexvo placeholders twice. Wexvo shows the restored answer for review when the relevant mapping is available. Confirm to copy it back to your document.

Keep the same Wexvo session open throughout the round trip. Unknown or unavailable placeholders cannot be reconstructed; they require attention rather than guessed values.

Double Copy starts enabled, with a default interval of **600 ms**. Adjust it or turn it off in **Options → Double Copy…**. These choices last only until Wexvo closes. Detection relies on clipboard updates, so behaviour can vary between applications.

## Made for useful context

| Everyday text | Technical output | Document workflows |
| :--- | :--- | :--- |
| Review names, contact details, addresses and identifiers in correspondence. | Mask network identities and credentials while aiming to preserve services, ports, software versions and CVE references. | Import text from TXT, Word, PowerPoint, Excel, PDF and supported images, with local OCR where needed. |

**Manual corrections stay close to the text.** Use **Undo Manual** to reverse a manual redaction. Restored blue blocks can be dragged onto one another to swap values; **Undo swap** reverses the last swap.

**More room when you need it.** Choose **Open full editor** to carry the current review into the full workspace without repeating the analysis. Copying in the full editor leaves it open.

Document import extracts text for review. It does **not** certify that the original file, its layout or its metadata has been permanently sanitised.

## Everyday controls

| Where | Action | Control |
| :--- | :--- | :--- |
| Any supported application | Open a compact review | Select text, then press **Ctrl+C twice** |
| Quick Review | Copy the reviewed result and close | **Ctrl+Enter** or **Copy and close** |
| Quick Review | Cancel without copying | **Esc** or **Cancel** |
| Full editor | Paste replacement input | **Ctrl+V** |
| Full editor | Copy the current redacted or restored result | **Ctrl+Shift+C** or the copy button |
| Full editor | Use the existing Restore Answer action | **Ctrl+R** or **Restore Answer** |
| System tray | Show or hide the workspace | Left-click the Wexvo icon |
| Options | Configure optional Windows global hotkeys | **Global shortcuts…** |
| Options | Adjust Double Copy | **Double Copy…** |
| Options | Open the interactive introduction | **Quick tour…** |
| Tray menu | Exit completely | **Exit Wexvo Completely** |

**Global hotkeys are configurable, not a requirement.** Use the combinations shown in your current **Global shortcuts…** settings. Windows or another application may already reserve a combination. The tray icon and Double Copy provide alternative access.

<details>
<summary><strong>Restore actions and clipboard behaviour</strong></summary>

The recommended Double Copy workflow opens a review before copying redacted or restored text. **Copy and close** confirms that review; **Cancel** does not copy it. A pending redaction mapping is committed only on confirmation. Moving a pending review to the full editor does not itself commit it.

The existing **Restore Answer** button / **Ctrl+R** follows its separate editor workflow: it displays the answer and also copies successfully restored text. The optional **Blind Redact / Restore** action can update the clipboard without a review window. Choose Double Copy when you want to check the result before it reaches the clipboard.

</details>

## Privacy with clear boundaries

- **Local processing.** Detection and document processing use the bundled runtime and models. No AI account or remote inference service is required.
- **Session-only state.** Preferences and placeholder mappings live in memory. Closing Wexvo or choosing **Wipe All** removes the application's session state; the safety timer can also expire review or clipboard data.
- **Explicit sharing.** You decide which reviewed content to paste into another application. Masking identifiers does not remove every kind of confidential information or determine whether sharing is permitted.
- **No forensic promise.** Application cleanup cannot guarantee that Windows paging, crash dumps, clipboard tools or other software retain no copies. The single-file Windows build temporarily extracts its runtime; the portable-folder build avoids that extraction.

## Validation and current status

**Current build: 1.1.10 · Verified 30 October 2026**

### Measured on public, human-annotated data

Measured on a sealed test split that was run once, after development, without tuning on it. The figures below
were measured on 1.1.9 and still apply: 1.1.10 changes packaging only and leaves every detection rule untouched.

| Dataset | Fully masked |
| :--- | ---: |
| English court judgments (Text Anonymization Benchmark): all direct identifiers | **98.9%** |
| — of which person names / case numbers | 98.7% / 100% |
| Dutch news (CoNLL-2002): person names | **93.0%** (Max coverage on), 92.1% (off) |
| Real system logs (Loghub, 10 systems): IP addresses / host names | 100% / 100% |
| Words masked outside any annotation | 1.5–3.1% |

These datasets contain no Dutch citizen service numbers, IBANs or Dutch addresses; those detectors are validated separately. Roughly 1 in 14 names in Dutch news stayed readable, mostly author initials in brackets.

### Technical verification

| Verification | Recorded result |
| :--- | :--- |
| Unit suite | **395 tests per configuration**, passed with source and native cores, Max coverage on and off |
| Full regression matrix | **86 jobs passed**: 54 detection jobs, 28 GUI jobs and 4 unit-suite jobs |
| Windows packages | Both single-file and portable EXEs passed **--selftest** |
| Packaging checks | **All 22 own modules** compiled to native code; no Wexvo Python source or bytecode in the package |
| Temporary extraction | Single-file extraction removed after selftest; portable selftest created no extraction directory |

These are recorded local results, **not live CI, an independent certification or a guarantee of perfect detection**.

<details>
<summary><strong>Known detection limitations and external evaluation</strong></summary>

Build 1.1.10 changes packaging only: the entry point no longer ships any readable logic, and all 23 own modules are compiled to native code. Detection is unchanged from 1.1.9, which adds detection of case and file numbers, completes half-detected names, and stops reading class paths, components and units in machine logs as names. It does not eliminate all detection errors.

An existing benchmark of **77 externally sourced, openly licensed fictional emails** was rechecked in both detection modes with fresh and shared sessions. On the reviewed fragments, **70 unwanted masks in the development split and 80–82 in the previously reviewed holdout remain** (the range reflects two build environments), alongside **8 incomplete known full-name occurrences in development and 0 in holdout**. Restore round-trip failures were zero. These counts are not document-level error rates or overall precision/recall; the annotations are partial, and this reused holdout is a regression set rather than a new independent evaluation.

Those accuracy audits still report failure. They are separate from the passing technical regression matrix. Neither the screenshots nor the regression totals establish that the tool is ready for unattended handling of confidential documents.

</details>

## Project

**Windows · Python · PySide6 · spaCy · Regex · ONNX Runtime · Cython/MSVC · PyInstaller**

Wexvo is in beta. This public repository contains the project presentation and visual assets; application source code is not published here. Windows builds are available from [Releases](../../releases), with SHA-256 checksums. Wexvo is not offered under an open-source licence.

Next priorities: clean-machine Windows checks and usability feedback from realistic workflows.

---

<p align="center"><sub>Wexvo · Sensitive text. Local control.</sub></p>

<p align="center">
  <img src="assets/wexvo_logo.png" alt="Wexvo" width="280">
</p>

<h1 align="center">Sensitive text. Local control.</h1>

<p align="center">
  Review, mask and restore sensitive text before sharing it with AI.
</p>

<p align="center">
  <strong>Windows desktop</strong> · <strong>Offline processing</strong> · <strong>Dutch & English</strong>
</p>

---

Wexvo is a Windows desktop application that helps you prepare sensitive text for use with AI assistants. It detects personal information and technical identifiers locally, replaces them with placeholders, and lets you review the result before copying it. When an AI response contains known placeholders, Wexvo can restore the corresponding values from the active session.

Built around a practical workflow for IT logs, security reports and everyday documents: keep useful context, review sensitive details and stay in control of what you share.

> **Beta · Private development**
> Detection can miss sensitive information or mask useful context. Always review the output. This tool does not decide whether you are permitted to share a document.

## One workflow, in both directions

| Prepare a prompt | Restore an answer |
| :--- | :--- |
| Copy the same text twice to open Quick Review. | Copy an AI answer containing Wexvo placeholders twice. |
| Inspect the masked output and add manual corrections. | Inspect restored values in the compact review window. |
| Choose **Kopiëren en sluiten** or press **Ctrl+Enter**. | Check the result, then explicitly copy it. |
| Paste the reviewed text into your chosen application. | Paste the reviewed answer into your document. |

Double Copy is enabled when no preference has been saved. It can be disabled or adjusted in Options. It relies on clipboard updates; copying conventions vary between applications.

## Designed for review

**Quick Review** keeps the original text hidden by default and shows a category summary. Click a word to mask it everywhere, or select text and use **Redact everywhere**. **Undo Manual** reverses manual masking.

**Visible restoration** highlights restored values in blue. Drag one restored block onto another to swap values, and use **Undo wissel** to reverse a swap. Unknown or ambiguous placeholders remain visibly flagged for review.

**A full editor when needed** provides more room for large documents. Opening the full editor transfers the current review and its changes without repeating the analysis. Copying in the full editor keeps the window open.

**Background access** includes a tray icon and configurable Windows global shortcuts. The optional blind clipboard action processes text without a review window; use it only when that behaviour is appropriate for your workflow.

## Technical context matters

Wexvo combines pattern matching, Dutch and English language models, and contextual rules. Detection covers categories such as names, contact details, addresses, identifiers, credentials, IP addresses and hostnames.

For terminal output and logs, the goal is to preserve information needed for diagnosis, including service names, ports, software versions and CVE identifiers. Synthetic regression cases cover network scans, authentication logs, HTTP output and other technical formats. Exact behaviour depends on context and must be checked in the review.

## Documents and text

| Input | Processing |
| :--- | :--- |
| Clipboard and plain text | Local analysis and editable masked output |
| Word, PowerPoint and Excel | Text extraction for review |
| PDF | Text extraction, with local OCR where needed |
| Supported images | Local OCR before text analysis |

Document import produces text for review. It is not a claim that the original file has been permanently redacted or that its original layout and metadata have been sanitised.

## Privacy boundaries

- Detection and document processing run locally, using bundled models in the Windows build.
- The application does not require an AI account or a remote inference service.
- Placeholder mappings belong to the active session; they are not a permanent recovery archive. Closing the application or using **Wipe All** removes the application's session state.
- Only known, available mappings can restore placeholders. Keep the relevant session open while completing a round trip.
- Automatic cleanup and cancellation protect the review workflow, but are not a forensic guarantee that operating-system memory, paging, crash dumps or other applications contain no copies.
- Any external application receives the content you choose to paste into it. Masking identifiers does not remove every form of confidential information.

## Everyday controls

| Action | Control |
| :--- | :--- |
| Open a compact review | Copy identical text twice within the configured interval |
| Confirm Quick Review | **Ctrl+Enter** / **Kopiëren en sluiten** |
| Cancel Quick Review | **Esc** / **Annuleren** |
| Show or hide Wexvo | Click the tray icon |
| Instant popup | **Win+Shift+W** by default |
| Blind Redact / Restore | **Win+Shift+X** by default |
| Change global shortcuts | **Options → Global shortcuts…** |
| Adjust Double Copy | **Options → Dubbel-Copy…** |
| Exit the application | **Exit Wexvo Completely** in the tray menu |

## Validation

The latest local verification on **24 October 2026** completed with:

| Check | Result |
| :--- | :--- |
| Unit suite | 270 tests passed |
| Windows GUI regression checks | 329 checks passed |
| Redteam audits and holdout checks | No failures in the final run |
| Synthetic stress and name-context checks | No failures in the final run |
| Large Word document checks | Three generated documents, approximately 68–69k characters each, checked in both detection modes |
| Packaged executable | Built with the existing `wexvo.spec`; `--selftest` exited successfully |

These are local regression results, not a live CI badge, independent security certification or a guarantee of perfect detection. The final GUI checks were run serially with access to the Windows clipboard. Two clipboard assertions failed in an earlier run and passed in the isolated and final complete reruns; that intermittent behaviour remains relevant when assessing reliability.

New domain and document fixtures are synthetic. They include IT, legal, medical, education, financial and everyday text, with explicit checks for sensitive values and context that should remain readable.

## Implementation

**Python · PySide6 · spaCy · Regex · ONNX Runtime · PyInstaller**

The application uses background workers for analysis, a central clipboard service, and pending review mappings that are committed on explicit confirmation. The Windows package includes its runtime and models. Development dependency installation is separate from offline application use.

## Project status

Wexvo is under private development. No public release or public source licence is announced on this page. Distribution instructions, repository documentation links and release downloads will be added when the first upload has been reviewed.

Near-term priorities are independent evaluation, clean-machine Windows testing, usability feedback and a reviewed distribution process.

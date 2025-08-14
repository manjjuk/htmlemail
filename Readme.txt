HTML Letter Generator

A. Overview
-----------
- This webpage allows you to create typeset letters directly in your browser.
- Input addresses, recipient information, subject, body text, and sender signature.
- Generate a formatted HTML page, copy it into a word processor, or save/load your input as JSON.

B. Features
-----------
- Input fields for sender/recipient addresses, recipient name, reference number, subject, body text, and signature.
- Generate Page button: outputs a clean, formatted HTML letter.
- Download Data button: saves all input as a JSON file.
- Upload Data button: loads previously saved JSON files.
- Preserves multi-line text for addresses and signature.
- Copies correctly to Word processors with line breaks preserved.
- Supports printing via browser.

C. How to Use
-------------
1. Open the HTML file in a modern browser.
2. Fill in the fields:
   - Date: Use the date picker.
   - Sender Address: Multiple lines allowed (use Enter).
   - Recipient Address: Multiple lines allowed (use Enter).
   - Recipient Name
   - Reference Number
   - Subject
   - Body Text: Paragraphs separated by blank lines.
   - Signature: Two or more lines allowed.
3. Click Generate Page:
   - Opens a new tab with your formatted letter.
   - Preserves line breaks in addresses and signature.
4. Click Download Data to save your inputs as JSON.
5. Click Upload Data to load previously saved JSON inputs.

D. Functions and Logic Flow
---------------------------
- Utilities:
  - escapeHtml(text): Escapes special HTML characters (&, <, >) to prevent rendering issues.
  - sanitizeFilename(name): Removes invalid filename characters for downloaded files.
- Form Handling:
  - getFormData(): Reads all input fields and returns an object.
  - setFormData(data): Fills input fields from a JSON object.
- Button Logic:
  - Upload Data: Opens a file picker, reads JSON, and fills the form.
  - Download Data: Converts current form inputs to JSON and triggers file download.
  - Generate Page: Validates fields, formats text, and creates a new HTML letter page.
- Text Formatting:
  - formatForHtml(text): Converts newlines (\n) to <br /> to preserve line breaks in HTML.
  - Body Text: Paragraphs separated by blank lines are wrapped in <p> tags.
  - Signature & Addresses: Multi-line text preserved using formatForHtml().
- Page Generation Logic:
  - Validate required fields using HTML5 validation.
  - Parse date and format it as DD-MMM-YYYY.
  - Escape user inputs to prevent HTML issues.
  - Convert body text paragraphs and multi-line addresses/signature to HTML.
  - Construct a complete HTML document with CSS for layout and print media.
  - Open the generated HTML in a new tab or trigger a download if popups are blocked.
  - Preserve line breaks in signature and addresses using white-space: pre-line and <br />.

E. Example JSON Input
---------------------
{
  "date": "2025-08-14",
  "senderAddress": "ABC Company\n123 Elm Street\nLondon, UK",
  "recipientAddress": "John Doe\n456 Oak Road\nManchester, UK",
  "recipient": "John Doe",
  "reference": "ABC-0123-456",
  "subject": "Business Proposal",
  "bodyText": "Lorem ipsum dolor sit amet, consectetur adipiscing elit.\n\nSed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
  "signature": "Mary Smith\nManaging Director"
}

F. Notes
--------
- Multi-line fields (addresses, signature, body paragraphs) are preserved in both the webpage and when copied to word processors.
- The page uses plain HTML, CSS, and JavaScript — no external libraries required.
- Works offline in any modern browser.

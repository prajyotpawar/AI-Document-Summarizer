# Briefly AI — Document Summarizer

A responsive React + Vite document summarizer powered by the Gemini API. It supports PDF, DOCX, TXT, and Markdown files; pasted text; summary styles; language selection; key points; action items; follow-up questions; copy and Markdown download; local recent-history; and theme switching.

## Run locally

1. Install Node.js 20+.
2. Copy `.env.example` to `.env`.
3. Create a Gemini API key in [Google AI Studio](https://aistudio.google.com/app/apikey) and place it in `.env`.
4. Run:

   ```bash
   npm install
   npm run dev
   ```

5. Open the local URL printed by Vite.

## Important security note

This starter uses `VITE_GEMINI_API_KEY`, which is exposed in the browser bundle. It is suitable only for a local/personal prototype. **Do not publish a site with a real API key embedded in client-side code.** For public deployment, move Gemini requests to a server-side endpoint (for example, a small Node/Express API) and store the key in the server environment. Configure quotas and billing/usage limits in Google AI Studio / Google Cloud as appropriate.

## Supported input

- PDF: text-based PDFs (scanned/image-only PDFs need OCR, which is not included).
- DOCX: Microsoft Word documents.
- TXT and MD: plain text / Markdown.
- Pasted text: paste text directly in the editor.

The free quota, available models, and rate limits depend on Google's current policy and your account/region. A free API key does not mean unlimited requests.

## Build

```bash
npm run build
npm run preview
```

## Troubleshooting

- **API key error**: check `.env` is named exactly, restart Vite after editing it, and verify the key in AI Studio.
- **429 / quota**: wait for quota reset or review current usage/rate limits.
- **Unsupported model**: change `VITE_GEMINI_MODEL` to a model currently available to your API key.
- **PDF has no extracted text**: it may be scanned; run OCR separately before uploading.
- **Large document**: use a smaller file or split it into sections. This app caps extracted text to reduce accidental oversized requests.

This project is a functional starter, but no software can be guaranteed error-free across every browser, API quota, file, or network condition. Test with your own key and documents before relying on it.

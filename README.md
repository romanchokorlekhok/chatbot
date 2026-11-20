# SHUVO AI — Version 1.0

A responsive Bengali-first AI chatbot using Gemini API and Netlify Functions.

## Included
- Custom responsive chat interface
- Gemini text chat and image understanding
- Chat history saved in browser localStorage
- Optional image-generation endpoint (requires a supported paid API model/billing)
- API key stays on the server, not in browser JavaScript

## 1. Create a Gemini API key
Visit https://aistudio.google.com/apikey and create a key.

## 2. Deploy to Netlify (easiest)
1. Extract this ZIP.
2. Upload the project folder to a GitHub repository.
3. In Netlify, choose **Add new site → Import an existing project** and connect that repository.
4. Open **Site configuration → Environment variables**.
5. Add `GEMINI_API_KEY` with your API key as the value.
6. Add `GEMINI_TEXT_MODEL` = `gemini-2.5-flash`.
7. Deploy / trigger a new deploy.

Do not put your API key in `app.js`, `index.html`, or any public file.

## 3. Run locally (PC or Termux)
Install Node.js, then in this project directory run:

```bash
npm install
npx netlify dev
```

Create a `.env` file in the project root (copy `.env.example`) and add your key:

```env
GEMINI_API_KEY=your_real_key_here
GEMINI_TEXT_MODEL=gemini-2.5-flash
```

Open the local URL printed by Netlify CLI.

## Image generation note
Gemini text chat and image understanding can use the Gemini API Free Tier where available and subject to quotas. Google's current pricing page lists the newer Gemini image-generation API models as having no Free Tier. To enable image generation, check current pricing and billing, then set `GEMINI_IMAGE_MODEL` in Netlify environment variables (for example `gemini-3.1-flash-image`) and redeploy.

## Important safety notes
- This starter is for personal testing. It has no user login, per-user quotas, or abuse protection.
- Anyone who can access the deployed site may be able to use your API quota. Keep the site private while testing, monitor usage in Google AI Studio, and rotate the key if it is exposed.
- Free-tier availability and limits can vary by model, account, and region.
- Do not upload sensitive personal or confidential images.

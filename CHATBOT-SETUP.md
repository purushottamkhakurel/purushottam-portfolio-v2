# Ask Purushottam chatbot setup

The chat interface is included on the home, journal, and article pages. AI replies require a free Gemini API key and a Cloudflare Worker backend.

## 1. Create a Gemini API key
1. Open https://aistudio.google.com/app/apikey
2. Sign in and create an API key.
3. Keep the key private. Never add it to this repository or browser JavaScript.

Gemini's free tier has model and rate limits. Free-tier content may be used by Google to improve its products. Check https://ai.google.dev/gemini-api/docs/pricing.

## 2. Deploy the Cloudflare Worker
1. Sign in at https://dash.cloudflare.com/ and open Workers & Pages.
2. Create a Worker named `ask-purushottam`.
3. Replace its starter code with `cloudflare/ask-purushottam-worker.js`.
4. Under Worker Settings → Variables and Secrets, add a secret named `GEMINI_API_KEY` and paste the Gemini key.
5. Deploy and copy the public workers.dev URL.

Cloudflare Workers Free currently includes 100,000 requests/day: https://developers.cloudflare.com/workers/platform/limits/.

## 3. Connect the website
In `js/chatbot.js`, replace the placeholder `https://YOUR-WORKER-NAME.YOUR-SUBDOMAIN.workers.dev` with the Worker URL. Commit the change.

The Worker allows only the portfolio domains listed in `ALLOWED_ORIGINS`. Add any alternate domain there if needed.

The Gemini key remains server-side. This free-tier setup is subject to provider limits and terms.

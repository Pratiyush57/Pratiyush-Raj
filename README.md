# News Gamer Talks

## Run the site and automatic news updates

The site uses a small Node.js server so Google Search and Gemini credentials stay on the server. Node.js 18 or later is required.

1. Create a Google Programmable Search Engine configured to search the entire web, then enable the Custom Search JSON API in its Google Cloud project.
2. Create a Gemini API key in Google AI Studio.
3. Copy `.env.example` to `.env` and fill in `GOOGLE_SEARCH_API_KEY`, `GOOGLE_SEARCH_ENGINE_ID`, and `GEMINI_API_KEY`. Keep `.env` private; it is excluded from Git.
4. Run `npm start` and open `http://localhost:3000`.

The site searches recent PlayStation, Xbox, PC, and mobile gaming news, asks Gemini to summarize stories from those results, and searches Google Images for game-specific artwork filtered for public-domain or Creative Commons reuse. Each generated story links to its reporting source and image source; stories without a matching reuse-filtered image are skipped. Results are cached on the server for 30 minutes. Google API quotas and billing may apply.

Opening `index.html` directly does not run the news service. If credentials are missing or an API request fails, the page displays an error while keeping its existing stories available.

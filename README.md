# Paatu Petti 📀

A mood-based music player built on YouTube. Pick a CD from the shelf, step into the scene, and the playlist plays on the TV.

## 1. Get a YouTube API key (free, ~5 min)
1. Go to https://console.cloud.google.com/ and create a project.
2. Open **APIs & Services → Library**, search **YouTube Data API v3**, and click **Enable**.
3. Go to **APIs & Services → Credentials → Create credentials → API key**.
4. **Restrict it** (important, since the key is visible in a public site):
   - Application restrictions → **Websites** → add `https://<your-username>.github.io/*`
   - API restrictions → **YouTube Data API v3** only

Quota: 10,000 units/day free. Each search costs 100 units, so ~100 searches/day. Playback costs nothing. Genre mixes are cached for 24h.

## 2. Host on GitHub Pages
1. Create a repo (e.g. `Paatu-Petti`) and upload `index.html` + this README.
2. Repo **Settings → Pages → Source: Deploy from branch → main / root**.
3. Your site goes live at `https://<your-username>.github.io/Paatu-Petti/`.
4. Open it, click **⚙ YouTube API key**, and paste the key. Or paste it into `YT_API_KEY` at the top of the script.

> Opening `index.html` by double-click (file://) can break YouTube embeds. Test on GitHub Pages or with `python -m http.server`.

## 3. Customize
- In the script, `GENRES` controls each CD: name, tagline, colours, and the **YouTube search query** that builds its mix. Tweak the queries to taste.
- `screen: [left%, top%, width%, height%]` is where the player sits inside each scene.
- To add a new scene, write an SVG (viewBox 1600×900), leave a screen area, and add an entry to `GENRES`.

## Controls
Space = play/pause · → next · ← previous · ⤢ Big screen to blow up the video.

# Summer '26 Playlist

The group's summer playlist sorted into one long day, from sunrise to after midnight. Each chapter is styled as a different 2010s interface.

Everything is in `index.html`. It has no build step and no dependencies. Fonts come from Google Fonts, and album art and 30-second previews come from Spotify's CDN.

## Put it on GitHub Pages

1. Create a new repository on GitHub, for example `summer-26`.
2. Upload `index.html` and this README to the repository root. Use **Add file → Upload files**, or push them with git.
3. Go to **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, pick `main` and `/ (root)`, then save.
4. After a minute the site is live at `https://<your-username>.github.io/summer-26/`.

## How playback works

- Browsers won't play sound until a visitor interacts with the page. The **Start the day with sound** button, or the play button in the bottom player, turns autoplay on.
- With autoplay on, each chapter plays its featured track when you scroll into it. When a clip ends, the next song in the same chapter plays.
- Every song also has its own **Preview** button.
- If Spotify ever stops serving a preview, the player says so and the cover links to the track on Spotify.

## Editing songs

Song data is near the top of the main `<script>`, in the `CH` array. Each chapter has:

- a time (`min` is minutes after midnight, and `label` is the displayed time)
- a title
- `feature`: the Spotify track ID that autoplays
- a list of songs, written as `S(spotifyTrackId, title, artist, pickedBy, why)`

Album art, release year, length and preview URL for each track ID are stored in the `TR` table above it.

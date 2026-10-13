# Musify Dashboard

See your whole Spotify listening history in one page: your top 500 songs, how much you listened each year, and when you first played each track.

Upload the zip file Spotify sends you and the dashboard is built straight away, **entirely in your browser**. Your data is never uploaded anywhere.

## Features

- **Top 500 songs**, ranked by number of streams, with the artist, album, minutes listened and the date you first streamed each song
- **Year filter**: pick a year, or click a bar in the chart, to see your top songs and totals for that year
- **Streams per year** chart
- **Summary**: total streams, hours listened, unique songs and artists, and your most-streamed song
- **Search** by song, artist or album, and sort by any column
- **Streams ≥ 30s or all plays**: a stream counts only plays of 30 seconds or more, which is the rule Spotify uses. You can switch to count every play, including skips.
- **Light and dark** themes
- **Private by design**: no server, no tracking and no third-party libraries. It's a single HTML file.

## How to use it

1. **Request your data from Spotify.** Go to your [Spotify account privacy page](https://www.spotify.com/account/privacy/), tick **Extended streaming history**, and click **Request data**. Confirm the request from the email Spotify sends you.
2. **Wait for the email** saying your data is ready. Spotify says this can take up to 30 days, but it's often sooner.
3. **Open the dashboard** and drop in `my_spotify_data.zip`. There's no need to unzip it.

The **Account data** export also works, but it only covers the last year.

## Run it locally

No installation is needed. Download `index.html` and open it in a recent version of Chrome, Edge, Firefox or Safari.

### Optional: build a dashboard with your data built in

`build.py` creates `dashboard.html`, a dashboard with your data already inside, from a folder of `Streaming_History_Audio_*.json` files:

```bash
python3 build.py /path/to/Spotify\ Extended\ Streaming\ History
```

> `dashboard.html` contains your personal listening history, so don't commit it. It's listed in `.gitignore`.

## Notes

- Songs are grouped by artist and title, so a track released on both a single and an album counts once.
- Podcasts, audiobooks and videos are excluded.

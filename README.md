# Musify Dashboard

See your whole **Spotify** listening history or **YouTube** watch history in one page: your top 500 songs or videos, your top channels, how much you listened or watched over time, and when you first played each one.

Choose Spotify or YouTube, upload the zip file you get from them, and the dashboard is built straight away, **entirely in your browser**. Your data is never uploaded anywhere.

https://alissonkn.github.io/musify-dashboard/

## Features

- **Top 500 songs**, ranked by number of streams, with the artist, album, minutes listened and the date you first streamed each song
- **Year filter**: pick a year, or click a bar in the chart, to see your top songs and totals for that year
- **Streams per year** chart
- **Summary**: total streams, hours listened, unique songs and artists, and your most-streamed song
- **Search** by song, artist or album, and sort by any column
- **Streams ≥ 30s or all plays**: a stream counts only plays of 30 seconds or more, which is the rule Spotify uses. You can switch to count every play, including skips.
- **YouTube**: top 500 videos, **top channels**, and videos per month or year. Switch to **Music only** for your YouTube Music songs and artists.
- **Share to Instagram Stories**: creates a story image of your current view (stats, top 5 and the site address). On a phone it opens the share sheet, where you pick Instagram → Stories. On a computer you can download the image.
- **Light and dark** themes
- **Private by design**: no server and no third-party libraries. It's a single HTML file.

## How to use it

Pick **Spotify** or **YouTube** at the top of the upload screen, then upload the matching file.

### Spotify

1. **Request your data from Spotify.** Go to your [Spotify account privacy page](https://www.spotify.com/account/privacy/), tick **Extended streaming history**, and click **Request data**. Confirm the request from the email Spotify sends you.
2. **Wait for the email** saying your data is ready. Spotify says this can take up to 30 days, but it's often sooner.
3. **Open the dashboard** and drop in `my_spotify_data.zip`. There's no need to unzip it.

The **Account data** export also works, but it only covers the last year.

### YouTube

1. Go to [Google Takeout](https://takeout.google.com/), click **Deselect all**, and tick **YouTube and YouTube Music**.
2. Click **All YouTube data included**, choose **Deselect all**, tick only **history**, and click **OK**.
3. Click **Multiple formats** and change **history** from **HTML** to **JSON**. This step is required.
4. Click **Next step**, then **Create export**. The email usually arrives within minutes.
5. Choose **YouTube** on the dashboard and drop in `takeout-….zip`.

YouTube doesn't record how long you watched, so every video you opened counts as one play. The export only includes the history Google still keeps. If auto-delete is on in your YouTube history settings, older history isn't included. Exports in any language work.

## Run it locally

No installation is needed. Download `index.html` and open it in a recent version of Chrome, Edge, Firefox or Safari.

### Optional: build a dashboard with your data built in

`build.py` creates `dashboard.html`, a dashboard with your data already inside, from a folder of `Streaming_History_Audio_*.json` files:

```bash
python3 build.py /path/to/Spotify\ Extended\ Streaming\ History
```

> `dashboard.html` contains your personal listening history, so don't commit it. It's listed in `.gitignore`.

## Visitor stats

The hosted page uses [GoatCounter](https://www.goatcounter.com/), a privacy-friendly counter with no cookies, to count page visits and how many Spotify and YouTube dashboards are generated. It never sends any of your listening data.

## Notes

- Songs are grouped by artist and title, so a track released on both a single and an album counts once.
- Podcasts, audiobooks and videos are excluded from Spotify.
- YouTube excludes community posts, ads, and videos that have since been removed or made private. In **Music only**, " - Topic" is removed from channel names, and songs are grouped by artist and title.

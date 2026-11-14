# GIF / MP4 → Telegram Sticker

A single-page, in-browser converter that turns a GIF, MP4, WEBM or MOV into a Telegram video sticker — or a still image into a static sticker. Nothing is uploaded; encoding happens locally with WebCodecs.

## Output (per [Telegram's requirements](https://core.telegram.org/stickers))

| Mode | Format | Size | Limits |
|---|---|---|---|
| Video sticker | WEBM · VP9 · no audio | one side 512 px, other ≤ 512 px | ≤ 3 s, ≤ 30 fps, ≤ 256 KB |
| Video emoji / pack icon | WEBM · VP9 · no audio | 100 × 100 px | ≤ 3 s, ≤ 30 fps, ≤ 256 KB |
| Static sticker | PNG (WEBP fallback) | one side 512 px, other ≤ 512 px | ≤ 512 KB |

Features: trim, auto-speed to fit 3 s, frame-rate choice, keep-aspect / pad / crop framing, automatic bitrate reduction until the file is under 256 KB, and a pass/fail checklist.

## Uploading to Telegram

In [@Stickers](https://t.me/stickers): `/newvideo` for video stickers, `/newemojipack` for emoji, `/newpack` for static stickers. Send the file **as a file/document**, not as a video or photo.

## Browser support

Current Chrome, Edge or Firefox (WebCodecs VP9 encoder; GIF decoding via ImageDecoder). Safari can't decode GIF frames.

## Run locally

It's one static file — open `index.html` or serve the folder with any static server.

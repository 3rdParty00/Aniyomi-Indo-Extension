# Otakudesu Enhanced

An Aniyomi-compatible extension module for Otaku Desu, built as a separate package so it does not overwrite an installed `Otakudesu` extension.

Current canonical target: `https://otakudesu.blog`. Otaku Desu's landing page currently identifies `otakudesu.blog` as the official site and says `otakudesu.io` redirects to it.

## Included
- Search / genre / ongoing / complete
- Details and episodes
- Otaku Desu mirror AJAX + nonce flow
- FileLions/StreamWish, YourUpload, DesuStream, Mp4upload and VidHide handling
- Preferred quality
- Diagnostics for the four current scenarios
- 60-second slow-start classification
- TLS verification is never bypassed

## Important
This is a source module, not a standalone Android app. It is designed to be copied into a maintained Aniyomi-compatible extension monorepo because the official Aniyomi extension repository was archived in 2025.

See `docs/BUILD.md` and `docs/TEST_MATRIX.md`.

# Build

1. Clone/use a maintained Aniyomi-compatible extension source repository.
2. Copy `src/id/otakudesuenhanced` from this package into that repository's `src/id/`.
3. If the repository does not auto-discover source modules, add the module in its `settings.gradle`/`settings.gradle.kts` according to that fork's convention.
4. Run `./gradlew tasks`.
5. Build the module exposed for `src/id/otakudesuenhanced`.
6. Install the resulting APK manually for testing.

The build script depends on the repository's shared:
- `:lib:youruploadextractor`
- `:lib:streamwishextractor`
- `:lib:vidhideextractor`

These are standard shared extractor modules used by the current Aniyomi-compatible OtakuDesu implementation.

This package intentionally does not vendor the entire Aniyomi build system, because doing so would pin you to a specific fork/version and would make the extension less portable.

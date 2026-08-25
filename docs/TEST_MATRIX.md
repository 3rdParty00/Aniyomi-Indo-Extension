# Test matrix

## Scenario 1 — domain wrong/missing
Symptoms:
- no source list
- browser also cannot reach the domain

Expected diagnostic categories:
- DOMAIN_OFFLINE_OR_CHANGED
- SSL_ERROR
- NETWORK_ERROR
- NETWORK_TIMEOUT

Fix: update `baseUrl`.

## Scenario 2 — domain works in browser, extension list is empty
Symptoms:
- browser can open the site
- extension returns no catalog entries

Expected logs:
- SCENARIO_2_CANDIDATE
- CATALOG_PARSE_FAILED
- PARSER_FAILED

Check:
- HTTP response
- Cloudflare/anti-bot response
- selectors
- User-Agent/headers

## Scenario 3 — anime/episode list exists, video is unavailable
Expected logs:
- SCENARIO_3_VIDEO_NOT_AVAILABLE
- VIDEO_RESOLVE_FAILED
- VIDEO_TOKEN_FAILED
- VIDEO_HOST_UNSUPPORTED
- VIDEO_HOST_UNSUPPORTED_OR_FAILED

Check:
- mirror selector
- base64 payload
- nonce
- AJAX response
- iframe
- host extractor

## Scenario 4 — video eventually starts after about 60 seconds or more, then plays without buffering
Expected log:
- SCENARIO_4_SLOW_STARTUP_CANDIDATE

This is not classified as a parser failure. It indicates that resolution is slow. If multiple mirrors are available, compare their startup times and prefer the fastest stable mirror in a later iteration.

## Additional future categories
The logger is intentionally extensible for:
- BUFFERING
- GEO_BLOCKED
- RATE_LIMITED
- TOKEN_EXPIRED
- REDIRECT_LOOP
- PLAYBACK_FAILED
- HOST_UNSUPPORTED

# ace-social-media

Temporary public hosting for social media assets ingested by Buffer/X. Each customer's files live under `{customerId}/...`. **Not for long-term storage** — files are cleaned up periodically (Buffer/X copy bytes to their own CDN within seconds of post creation, so we only need URLs to be live for ~1 minute).

## Layout

```
{customerId}/{post-slug}/{filename}
```

Example:
```
dataline-xyz/tearline-to-dataline-thread/thumb-animated.mp4
```

## Usage from ace-portal

`src/lib/social/media-host.ts` → `uploadMediaFile(customerId, localPath, options?)` returns a `raw.githubusercontent.com` URL.

## Cleanup

Files older than 14 days are deleted by a periodic job (not implemented yet — track via README TODO).

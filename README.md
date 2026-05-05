# EvilCast Test RSS Feed

Use `evilcast-test-feed.xml` as a fake podcast feed for testing refresh, new-episode detection, and public CloudKit episode indexing.

## Host On GitHub

1. Commit and push `evilcast-test-feed.xml` and `test-audio.mp3`.
2. Use the raw file URL as the feed URL:

```text
https://raw.githubusercontent.com/sotoole/evilcast-test-feeds/main/evilcast-test-feed.xml
```

If you host it in another repo or branch, use this pattern:

```text
https://raw.githubusercontent.com/<owner>/<repo>/<branch>/evilcast-test-feed.xml
```

## Force A New Episode

Add a new `<item>` at the top of the feed, or duplicate the top item and change these fields:

```xml
<title>Test Episode 004</title>
<pubDate>Tue, 28 Apr 2026 13:00:00 -0400</pubDate>
<guid isPermaLink="false">evilcast-test-episode-004</guid>
<link>https://example.com/evilcast-test-feed/episodes/004</link>
```

The important part is the `guid`: EvilCast treats a new GUID as a new episode.

The feed uses this tiny MP3 for every enclosure so download and playback testing work:

```text
https://raw.githubusercontent.com/sotoole/evilcast-test-feeds/main/test-audio.mp3
```

## Notes

GitHub raw URLs can be cached briefly. If an update does not appear immediately, wait a minute and pull to refresh again.

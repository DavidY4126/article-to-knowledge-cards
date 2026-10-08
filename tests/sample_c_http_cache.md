# How Browser Caching Works

When a browser loads a web page, downloading every resource on every visit is slow and wasteful. Browser caching lets the browser store a copy of a resource (an image, CSS file, or script) locally and reuse it on later visits instead of asking the server again.

The server controls caching with HTTP response headers. The `Cache-Control` header tells the browser how long a resource may be kept fresh, for example `max-age=31536000` means one year. During that time the browser uses its local copy without contacting the server at all.

Once the max-age passes, the browser must revalidate. It sends a request with an `ETag` or `If-Modified-Since` value that the server had given it earlier. If the file has not changed, the server replies with `304 Not Modified` and sends no body, which is a small, fast response. If the file has changed, the server sends `200 OK` with the new file.

A common mistake is caching HTML pages aggressively. Because HTML often changes when a new version ships, caching it too long can leave users on an old page. The recommended pattern is to cache content files (images, JS, CSS) for a long time, but give each file a content-based fingerprint in its filename, and keep the HTML itself either un-cached or very short-lived.

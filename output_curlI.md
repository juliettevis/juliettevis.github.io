# HTTP Best Practices Review

Based on the list given on slide 48, I wrote some comments out:

```http
HTTP/1.1 301 Moved Permanently
```
> **✅ Permanent URLs:** Your response includes a `301 Moved Permanently`, indicating that URLs are designed to be persistent and redirect correctly.

```http
Connection: keep-alive
Content-Length: 162
Server: GitHub.com
Content-Type: text/html
```
> **❌ Incorrect Content-Type:** The response includes `Content-Type: text/html`, but for RDF files, `application/ld+json` or another RDF-specific type should be used.

```http
permissions-policy: interest-cohort=()
Location: https://juliettevis.github.io/introduction.jsonld
```
> **✅ HTTPS:** The `Location` header confirms redirection to `https://`, ensuring secure connections.

```http
X-GitHub-Request-Id: 7F02:39F31E:B2BE35:B48057:67C768C2
Accept-Ranges: bytes
Age: 0
```
> **✅ Caching (Partial):** `Age: 0` indicates some caching mechanisms exist, but this response was not served from cache.

```http
Date: Tue, 04 Mar 2025 20:55:30 GMT
Via: 1.1 varnish
X-Served-By: cache-bru1480030-BRU
X-Cache: MISS
X-Cache-Hits: 0
X-Timer: S1741121731.703800,VS0,VE115
```
> **✅ Caching (Partial):** The presence of `X-Cache: MISS` means caching is enabled but this request wasn’t served from cache. GitHub Pages uses Fastly for caching.

```http
Vary: Accept-Encoding
```
> **✅ Compression:** The `Vary: Accept-Encoding` header suggests content compression could be supported if requested.

```http
X-Fastly-Request-ID: 8c93d2f59d98ad5146d685e2136c203e3035c466
```
> **❌ CORS Not Enabled:** There is no `Access-Control-Allow-Origin` header, which is needed for proper CORS support.


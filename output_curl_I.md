## Command
Below you find some remarks on the output of the command
```
curl -I https://juliettevis.github.io/introduction.jsonld
```
## Output
```
HTTP/2 200 
```
As shown in the output HTTP/2 is used which requires a HTTPS connection as stated on slide 41.

```
server: GitHub.com
```
This shows that GitHub.com hosts the webpage as it is a GitHub page.

```
content-type: application/ld+json
```
The content type is as expected `application/ld+json` as the webpage only contains a jsonld file.

```
permissions-policy: interest-cohort=()
last-modified: Tue, 04 Mar 2025 21:11:24 GMT
``` 

```
access-control-allow-origin: *
```
CORS is enabled as the `access-control-allow-origin` header is set to `*`, in other words the server allows access from any other website.

---
```
strict-transport-security: max-age=31556952
etag: "67c76c7c-d9e"
```
The `strict-transport-security`ensures HTTPS for 31556952 seconds such that users cannot access the website with HTTP.

```
expires: Thu, 06 Mar 2025 17:53:14 GMT
cache-control: max-age=600
```
This line states that caching using expiration is used. A bit further it is stated that the age is 0, meaning the expiration time = responese time + 600
```
x-proxy-cache: MISS
x-github-request-id: 9C97:686FD:14A65D:14CECC:67C9DEB1
accept-ranges: bytes
age: 0
date: Thu, 06 Mar 2025 17:43:14 GMT
via: 1.1 varnish
x-served-by: cache-bru1480064-BRU
x-cache: MISS
x-cache-hits: 0
x-timer: S1741282994.097675,VS0,VE124
vary: Accept-Encoding
x-fastly-request-id: 10bc7d312c7026dc7ef7d21ebc52bb5098dc823e
content-length: 3486
```
`x-proxy-cache: MISS`, `x-cache: MISS` and `x-cache-hits: 0`show that the request did not come from a cache. The fact that these lines are in the input indicate that there is a caching mechanism.

Nothing is stated on compression and `vary: Accept-Encoding` indicate that no compression was added.
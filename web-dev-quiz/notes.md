# script tag
default - stops parsing, downloads and executes
defer - download in parallel and execute after parsing
async - download in parallel and stop parsing to execute
async takes precedence unless browser does not support defer if both attributes are in tag

# rendering pipeline
get dom, get cssom, combine them to render tree (style calculation), calculate size and position (layout), convert to pixels, determine order of rendering (painting),
determine rendering layers (composite)

# dns resolving
browser - recursive DNS resolver
DNS resolver - root name server (gives ip for top)
DNS resolver - top level domin server (gives ip for authoritative server)
DNS resolver - authoritative server (gives ip for website)
begins TCP connection
starts fetching assets

# event loop
Call Stack
Web API
Macro Tasks (timeout, user events, network events)
Micro Tasks (promises)

# resources hints
<link rel="dns-prefetch" href="//example.com">
all resources are loaded first but you can change this
dns-prefetch - perform domain name resolution in the background
preconnect - proactively performs DNS resolution and TCP/TLS handshake
preload - prioritizes loading of asset for current navigation
prefetch - downloads asset when idle for the next navigation

Performance Navigation Timing
https://developer.mozilla.org/en-US/docs/Web/API/PerformanceNavigationTiming

# cache directives
no-cache - validates cached even if its still fresh (always validates with the origin server before using cache)
must-revalidate - validates staled cached before using it
no-store - does not store any cache
private - prevents caching on shared caches (prevents CDN/Proxy to cache)
state-while-revalidate - serves stale content while validating cache
ETag is used to identify resources

# animation cost
width change evokes layout, paint and composite
opacity change only evokes composite
transform change only evokes composite (very interesting)

# event propagation
capturing - down the dom tree
targeting - captures the element being clickled
bubblinh - goes up the dom tree

# weak map
Map that does not use strong references

# web vitals
Time To First Byte
First Input Delay
Time To Interactive
Total Blocking Time
Cumulate Layout Shift
Interaction to Next Paint

# content security policy
default-src script-src img-src font-src style-src media-src connect-src -frame-src

# refer policies
rel=noopener (new browser already apply this by default)
rel=noreferrer (also allies noopener)

# promise methods
all - resolved with all resolved or reject first reject (priority)
race - resolve with the first resolved or reject first reject (priority on first being declared)
any - waits for the first one to resolve, if no resolve, rejects any reject if there is any
allSettled - resolves with all promises resolved or rejected

# back forward cache

# front-end security
XSS - Cross Site Scripting - attackers inject malicious script into web pages
CSRF - Cross Site Request Forgery - tricks users into executing unwanted actions by exploiting their authenticated session
UI Redressing - Tricks users into interacting with disguised or hidden elements
MITM - Man-In-The-Middle - Intercepts connection and reads it

# font strategies
font-display: 
block, swap, fallback, optional, auto

# transport security
(Response Header) Strict-Transport-Security:

# image formats
JPEG - Lossy compression, supports progressive rendering, faster decoding
PNG - Losless compression, support transparency, larger file size
WebP - Both lossy and lossless, supports transparency, progressive rendering
AVIF - Both lossy and lossless, HDR Wide Color Gamut, Supports transparency

# http protocol
http 1.0 - Always requires a TCP connection
http 1.1 - Persisten same TCP connection, multiple requests and responses
http 2.0 - Multiple requests and responses on same connection in paralell
http 3.0 - Uses new protocol Quic
# ping_net
ping browser tool

How this works:

The JavaScript Timer: We use performance.now() right before initiating an HTTP request, and again right after the request finishes. The difference between these two numbers is the ping (latency).
The HTTP Request: We execute a fetch() call on the exact same page you are viewing using the HEAD method. This asks the server for the page headers without actually downloading the page body, making the request very small and fast. Cache Busting: Browsers are designed to load things from memory/cache whenever possible. To force the browser to actually go out to the internet every time, we append ?_t=123456789 (a timestamp) to the URL.

Note: If you just double-click the HTML file to open it locally (via a file:// URL), the latency will be essentially 0ms because it's pinging your own hard drive. To see realistic results, you'll need to host this file on a web server like Vercel, Netlify, GitHub Pages, or a basic local Node/Python server.

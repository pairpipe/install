# Network

The install downloads from **raw.githubusercontent.com**, **github.com** (and its download host objects.githubusercontent.com / release-assets.githubusercontent.com) and talks to **pairpipe.com** / **api.pairpipe.com**. All over HTTPS (port 443).

CHECK (each should print 200):
- PowerShell: `(Invoke-WebRequest https://pairpipe.com/healthz -UseBasicParsing -TimeoutSec 15).StatusCode`
- bash: `curl -s -o /dev/null -w "%{http_code}" --max-time 15 https://pairpipe.com/healthz`
Repeat with `https://raw.githubusercontent.com/pairpipe/install/main/marketplace.json`.

## Corporate proxy
Ask your user for the proxy address (their IT team has it). Set it before running Claude Code commands:
- PowerShell: `$env:HTTPS_PROXY = "http://proxy.example:8080"; $env:HTTP_PROXY = $env:HTTPS_PROXY`
- bash: `export HTTPS_PROXY=http://proxy.example:8080 HTTP_PROXY=http://proxy.example:8080`
In the desktop app, set them as user environment variables and restart the app.

## TLS inspection / certificate errors
Company networks that re-sign HTTPS cause `self signed certificate in certificate chain` or `unable to get local issuer certificate`. Ask your user for the company CA file and set `NODE_EXTRA_CA_CERTS=<path to .pem>`, then restart Claude. [Win] PowerShell 5.1 may also need `[Net.ServicePointManager]::SecurityProtocol = 'Tls12'` for the checks above.

## github.com blocked
The default route needs github.com downloads. If they're blocked, there is no workaround yet: send the report with `"outcome": "stuck"`.

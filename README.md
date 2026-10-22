# cal-image

cal.com (`calcom/cal.diy`) rebuilt on a patched Node runtime, published as `ghcr.io/steficzko/cal`.

Upstream stopped publishing Docker images after v6.2.0 and its Dockerfile still uses `node:20`
(end of life). This repo only holds the build workflow: it checks out an upstream tag, swaps the
Node base image, builds with the same build args as upstream's release action, checks the runtime
Node version, and pushes `ghcr.io/steficzko/cal:<tag>-node<version>`.

Rebuild for the next Node CVE: Actions → build → Run workflow, set `node_image` to the patched release.

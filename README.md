# Rootless Traefik

To be able to run this critical component as unprivileged and secure as possible, we had to be able to use custom Traefik image.

Approach here is to fetch the official image binary, and copy over the binary to a `scratch` based image with bare minimum of additions (*root certificates and zoneinfo* files from official image), running as unprivileged user (`1000:1000`) by default, all making it smaller and more secure.

Considering official image simplicity, this rootless image can be used across at least entire 3.x branch lifetime.

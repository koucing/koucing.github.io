## Run devel environment
```sh
    podman run -ti --rm -p4000:4000 -v .:/srv/jekyll:Z -e JEKYLL_ROOTLESS=1 docker.io/jekyll/jekyll jekyll serve
```
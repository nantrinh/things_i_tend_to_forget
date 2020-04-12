`docker build -t repo/tag .`

where tag can be `image_name:version`

- Order your layers from least likely to change to most likely to change in order to optimize the image size for pushing and pulling.
- Don't build containers with passwords baked in.
- Use multistage image builds to keep images small. (Kubernetes Up and Running 2019, Ch. 2, Multistage Image Builds)
- Use `--no-cache` option when running `apk add` on alpine images to avoid caching the index locally. Keeps containers small. 

# Considerations
- Use --memory and --memory-swap to limit memory usage per container at runtime. If the program in the container uses too much memory, it will be terminated. Beware!
- Use --cpu-shares to limit CPU usage. Beware units used and what they mean.

# Cleaning Up
- Unless you explicitly delete an image it will live on your system forever, even if you build a new image with an identical name. Building this new image simply moves the tag to the new image; it doesn't delete or replace the old image. As you iterate, you will often create many different images that end up take up unnecessary space on your computer.

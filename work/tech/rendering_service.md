# Rendering service

## Caching

- uses both redis and ram when writing, when reading, it prefers the ram cache
- puts EVERYTHING in ram cache as well, no selection there
- no memory limitation for the ram cache, the pod is killed when exceeds the memory limit

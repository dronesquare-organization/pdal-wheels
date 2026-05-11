# pdal-wheels

Pre-built PDAL python wheels (manylinux_2_28) for [dronesquare-backend](https://github.com/dronesquare-organization/dronesquare-backend).

Built via [cibuildwheel](https://github.com/pypa/cibuildwheel) + [auditwheel](https://github.com/pypa/auditwheel). The wheel bundles all native dependencies (libpdal, libgdal, libgeos, libproj, libgeotiff, libcurl, libssl, ...) so installation requires no system PDAL.

## Consumed by

```toml
[tool.uv.sources]
pdal = { url = "https://github.com/dronesquare-organization/pdal-wheels/releases/download/pdal-3.5.3-cp314/pdal-3.5.3-cp314-cp314-manylinux_2_28_x86_64.whl" }
```

## Versions

See [Releases](https://github.com/dronesquare-organization/pdal-wheels/releases).

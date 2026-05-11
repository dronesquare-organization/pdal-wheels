# pdal-wheels

Pre-built PDAL python wheels for [dronesquare-backend](https://github.com/dronesquare-organization/dronesquare-backend).

Built via [cibuildwheel](https://github.com/pypa/cibuildwheel). All native dependencies (libpdal, libgdal, libgeos, libproj, libgeotiff, libcurl, libssl, ...) are bundled inside the wheel so installation requires no system PDAL.

## Supported platforms

- **Linux x86_64** (manylinux_2_28) — source build of PROJ/GEOS/libgeotiff/GDAL/PDAL inside cibuildwheel docker, `auditwheel repair` bundles native deps. Used by backend amd64 docker image.
- **Linux aarch64** (manylinux_2_28) — same as x86_64. Used by backend prod (Graviton t4g.large) + CI (ubuntu-24.04-arm).
- **macOS arm64** (Apple Silicon) — `brew install pdal proj geos libgeotiff gdal`, `delocate-wheel` bundles brew dylibs. Used by macOS dev machines.

## Consumed by

```toml
[tool.uv.sources]
pdal = [
    { url = "https://github.com/dronesquare-organization/pdal-wheels/releases/download/pdal-3.5.3-cp314/pdal-3.5.3-cp314-cp314-manylinux_2_28_x86_64.whl",  marker = "sys_platform == 'linux' and platform_machine == 'x86_64'" },
    { url = "https://github.com/dronesquare-organization/pdal-wheels/releases/download/pdal-3.5.3-cp314/pdal-3.5.3-cp314-cp314-manylinux_2_28_aarch64.whl", marker = "sys_platform == 'linux' and platform_machine == 'aarch64'" },
    { url = "https://github.com/dronesquare-organization/pdal-wheels/releases/download/pdal-3.5.3-cp314/pdal-3.5.3-cp314-cp314-macosx_14_0_arm64.whl",      marker = "sys_platform == 'darwin' and platform_machine == 'arm64'" },
]
```

## Versions

See [Releases](https://github.com/dronesquare-organization/pdal-wheels/releases).

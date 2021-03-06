# Cadmus PURA API

Quick Docker image build:

```bash
docker build . -t vedph2020/cadmus_pura_api:1.0.6 -t vedph2020/cadmus_pura_api:latest
```

(replace with the current version).

This is a Cadmus API layer customized for the PURA project. Most of its code is derived from shared Cadmus libraries. See the [documentation](https://github.com/vedph/cadmus_doc/blob/master/guide/api.md) for more.

Note: as per current [NuGet issues](https://github.com/NuGet/Home/issues/10491), I temporarily changed the Docker image from `mcr.microsoft.com/dotnet/sdk:5.0-buster-slim AS build` to `mcr.microsoft.com/dotnet/sdk:5.0.102-ca-patch-buster-slim AS build`. I will revert as soon as the MS issue is resolved (see [status](https://status.nuget.org/)).

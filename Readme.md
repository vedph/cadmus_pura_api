# Cadmus PURA API

Quick Docker image build:

```bash
docker build . -t vedph2020/cadmus_pura_api:2.0.0 -t vedph2020/cadmus_pura_api:latest
```

(replace with the current version).

This is a Cadmus API layer customized for the PURA project. Most of its code is derived from shared Cadmus libraries. See the [documentation](https://github.com/vedph/cadmus_doc/blob/master/guide/api.md) for more.

## History

- 2021-11-29: updated packages.
- 2021-11-11: upgraded to NET 6.
- 2021-10-24: updated packages integrating graph SQL seeding.
- 2021-10-23: updated packages.
- 2021-10-16: refactored schema by lowering the structure level as requested.

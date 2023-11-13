# Cadmus PURA API

Quick Docker image build:

```bash
docker build . -t vedph2020/cadmus-pura-api:4.0.0 -t vedph2020/cadmus-pura-api:latest
```

(replace with the current version).

This is a Cadmus API layer customized for the PURA project. Most of its code is derived from shared Cadmus libraries. See the [documentation](https://github.com/vedph/cadmus_doc/blob/master/guide/api.md) for more.

## History

### 4.0.0

- ⚠️ 2023-11-13:
  - updated packages removing TGR dependencies.
  - refactored configuration:
    - changed flags.
    - added structured bibliography to lemma facet.
    - replaced all the TGR ms item parts with generic notes.
    - added new item for lexicons.
- 2023-11-08: updated packages.

### 3.0.1

- 2023-09-19: updated packages.
- 2023-05-19: updated packages and startup for index and graph.
- 2023-03-07: updated packages.

### 3.0.0

- 2023-02-06: migrated to new components factory. This is a breaking change for backend components, please see [this page](https://myrmex.github.io/overview/cadmus/dev/history/#2023-02-01---backend-infrastructure-upgrade). Anyway, in the end you just have to update your libraries and a single namespace reference. Benefits include:
  - more streamlined component instantiation.
  - more functionality in components factory, including DI.
  - dropped third party dependencies.
  - adopted standard MS technologies for DI.

### 2.2.0

- 2022-12-23: updated packages.
- 2022-11-10: upgraded to NET 7.
- 2022-10-11:
  - updated packages and injection in `Startup.cs` for new `IRepositoryProvider`.
  - added preview.

### 2.1.3

- 2022-06-13: updated packages.

### 2.1.2

- 2022-05-23: updated packages.

### 2.1.1

- 2022-05-13: added metadata part to all the items and upgraded packages.

### 2.1.0

- 2022-05-02: upgraded core to NET 6.0.

### 2.0.3

- 2021-12-22: updated `Cadmus.Api.Controller`.

### 2.0.2

- 2021-12-20: updated packages.

### 2.0.1

- 2021-11-29: updated packages and added graph support with these operations:

1. in `appsettings.json`, under `Indexing`, add `"IsGraphEnabled": true` to enable the graph. Currently this is set to false as we don't know it this feature will be used.
2. in `ConfigureServices.cs`, ensure that you configure the graph repository:

```cs
// graph repository
services.AddSingleton<IGraphRepository>(_ =>
{
    var repository = new MySqlGraphRepository();
    repository.Configure(new SqlOptions
    {
        ConnectionString = indexCS
    });
    return repository;
});
```

- 2021-11-11: upgraded to NET 6.
- 2021-10-24: updated packages integrating graph SQL seeding.
- 2021-10-23: updated packages.
- 2021-10-16: refactored schema by lowering the structure level as requested.

# Cadmus PURA API

Quick Docker image build:

```bash
docker build . -t vedph2020/cadmus_pura_api:2.1.0 -t vedph2020/cadmus_pura_api:latest
```

(replace with the current version).

This is a Cadmus API layer customized for the PURA project. Most of its code is derived from shared Cadmus libraries. See the [documentation](https://github.com/vedph/cadmus_doc/blob/master/guide/api.md) for more.

## History

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

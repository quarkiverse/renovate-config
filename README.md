# Quarkiverse Renovate Configuration

Shared [Renovate](https://docs.renovatebot.com/) configuration for [Quarkiverse](https://github.com/quarkiverse) repositories.

Renovate automatically discovers this configuration from any repository under the `quarkiverse` organization — no `extends` clause is needed in individual repositories.

## What's Included

- **`config:recommended`** — Renovate's recommended base configuration
- **Quarkus LTS updates** — A custom datasource that queries the [Quarkus Platform Registry](https://registry.quarkus.io/client/platforms) and proposes updates only to LTS versions. It matches `<quarkus.version>` in `pom.xml` files.
- **`io.quarkus` packages disabled** — Direct updates from Maven Central for `io.quarkus` artifacts are disabled, since they should follow the Quarkus platform version managed by each repository.

## Overriding Per Repository

Individual repositories can override any rule. For example, to re-enable `io.quarkus` updates from Maven Central:

```json
{
  "packageRules": [
    {
      "matchPackagePrefixes": ["io.quarkus"],
      "enabled": true
    }
  ]
}
```

## References

- [Renovate Shareable Config Presets](https://docs.renovatebot.com/config-presets/)
- [Renovate Custom Datasources](https://docs.renovatebot.com/modules/datasource/custom/)

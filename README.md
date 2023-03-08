# Renovate-20780

## What would you like Renovate to be able to do?

Renovate currently has the ability to update `.pre-commit-config.yaml` if the behaviour is opted into. At the moment renovate is only updating the declared `rev` (repo tag) dependencies.

It would be nice if renovate could also update any `additional_dependencies` if present, applying the supplied renovate configuration around pinning etc.

## What happens today?

For the given example `.pre-commit-config.yaml` file in this repository if ran with renovate today the `rev` for the prettier repo would be updated to `v3.0.0-alpha.6` however the `additional_dependencies` of prettier would remain at `v3.0.0-alpha.5` giving an inconcistency, and `eslint-config-prettier` would be unchanged.

## What would ideally happen?

Renovate would update the `additional_dependencies` to that `prettier` was updated to `v3.0.0-alpha.6` and `eslint-config-prettier` was updated to `@v8.7.0`.

## Further Considerations

As `pre-commit` hooks can be in a varianty of languages correctly identifying the upstream package manager of `additional_dependencies` will probably necessitate retrieving the `.pre-commit-hooks.yaml` file from the referenced repo to ascertain the `language` attribute.

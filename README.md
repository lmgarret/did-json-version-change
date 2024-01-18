# Did version change

An action that checks if the version in a pyproject.toml file has changed.
If it has, it will set the output variable `is_version_greater` to `true` otherwise it will set it to `false`. 
It will also set the output variable `version` to the current version.
It will only run if the `pyproject.toml` file has changed.

# Usage

See [action.yml](action.yml)

```yaml
steps:
- uses: raven-wing/did-version-change-action@v1
  id: did-version-change
- name: Your logic goes there
  if: steps.did-version-hange.outputs.is_version_greater == 'true'
  run: |
    <your logic>
```

# License

The scripts and documentation in this project are released under the [MIT License](LICENSE)

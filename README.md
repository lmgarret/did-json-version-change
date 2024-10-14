# Did version change

An action that checks if the version in a JSON file has changed.
If it has, it will set the output variable `is_version_greater` to `true` otherwise it will set it to `false`. 
It will also set the output variable `version` to the current version.
It will only run if the JSON file has changed.

# Usage

See [action.yml](action.yml)

The action has two inputs:
 - `json_file`: path to the JSON file. Defaults to `package.json`
 - `jq_expr`: the jq expression used to extract the version. Defaults to `.version`

```yaml
steps:
- uses: lmgarret/did-json-version-change-action@v1
  id: did-version-change
  with:
    json_file: nested/manifest.json
    jq_expr: .version
- name: Your logic goes there
  if: steps.did-version-hange.outputs.is_version_greater == 'true'
  run: |
    <your logic>
```

# License

The scripts and documentation in this project are released under the [MIT License](LICENSE)

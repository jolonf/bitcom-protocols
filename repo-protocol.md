# Repo Protocol
`14ncfV4MGFw7vQvkViPcJxKhUGABPVWVgt`
> Repo metadata

Contains metadata for on chain repositories. 

# Format

```
14ncfV4MGFw7vQvkViPcJxKhUGABPVWVgt
[name]
[description]
[version]
[website]
[github]
[hidden]
[...future fields]
```

- `name` - The name of the repository.
- `description` - A longer description of the respository, usually not longer than a sentence.
- `version` - A version string, e.g. '1.0.0'. There is no specific format for the version string, any characters are acceptible.
- `website` - A link to a website for the repo.
- `github` - A link to the GitHub repo.
- `hidden` - (`1` or `0`) If the value is `1` then it is requested that this repo is not returned in search results. This can not be enforced and is only a recommendation.

If information about the creator of the respository is required add one or more [Attribution Protocols](https://github.com/jolonf/bitcom-protocols/blob/master/attribution-protocol.md).

# Example

```
14ncfV4MGFw7vQvkViPcJxKhUGABPVWVgt
codeonchain-react
Website for viewing repositories
1.0.0
https://codeonchain.network
https://github.com/jolonf/codeonchain-react
0
```

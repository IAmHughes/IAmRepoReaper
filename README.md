# IAmRepoReaper
This script, `repo-reaper`, will grab every empty repository on a GitHub Enterprise Instance and list them. If given the `--execute=TRUE` option, will delete every repository that is empty.

## Pre-Requisites

#### AUTHENTICATION:
Before running this script, you must create a Personal Access Token (PAT) at https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/ with the permissions <repo> and <admin:org> scopes and <delete_repo>. Read more about scopes here: https://developer.github.com/apps/building-oauth-apps/scopes-for-oauth-apps/

Once created, you must export your PAT as an environment variable named <GITHUB_TOKEN>.
  - Exporting PAT as GITHUB_TOKEN
  $ export GITHUB_TOKEN=abcd1234efg567

#### API_ENDPOINT:
Additionally you will need to set the $API_ROOT at the top of the script to your instance of GitHub Enterprise.
 - _i.e._: https://MyGitHubEnterprise.com/api/v3

## Running the Script

#### NAME:
repo-reaper - For a GitHub Enterprise Instance, lists every empty repository in format <organization>:<repository> and deletes them if `--execute=TRUE` option is passed.

#### SYNOPSIS:

```
repo-reaper [--execute=TRUE]
```

#### DESCRIPTION:
For a GitHub Enterprise Instance, lists every empty repository in format <organization>:<repository> separated by new lines. Deleting them if passed the option `--execute=TRUE`
  - Example Output: List all empty repositories
    <organization1>:<repository1>
    <organization1>:<repository2>
    <organization3>:<repository1>

#### OPTIONS:

`--execute | -e`
When running the tool, this flag will delete every repo listed.
  * _NOTE:_ You should run the script without this option first, verifying that you want to delete every repository listed.

#### EXAMPLES:
  - Lists all empty repositories for each org that are empty.
  
```shell
$ bash repo-reaper
```

  - Lists all empty repositories for each org that are empty and deletes them.

```shell
$ bash repo-reaper --execute=TRUE
```

#### API DOCUMENTATION:
All documentation can be found at the [GitHub Developer Docs](https://developer.github.com/v3/) page.

## Contributing

Please read [CONTRIBUTING.md](https://github.com/IAmHughes/IAmRepoCleaner/blob/master/.github/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Authors

* **Thomas Hughes** - _Maintainer / On-Going Support_ - [@IAmHughes](https://GitHub.com/IAmHughes)

See also the list of [contributors](https://github.com/IAmHughes/IAmRepoReaper/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE](https://github.com/IAmHughes/IAmRepoReaper/blob/master/LICENSE) file for details.

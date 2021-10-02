# `gh stat` GitHub CLI extension

[GitHub CLI](https://github.com/cli/cli) extension for displaying various stats about organizations and repositories.

**⚠ This is a very first version based on a few quick experiments. I plan to improve it, but things might break. ⚠**


## Installation

```shell
gh extension install sagikazarmark/gh-stat
```

This extension depends on [jq](https://stedolan.github.io/jq/). To install using Homebrew:

```shell
brew install jq
```


## Usage

```shell
❯ gh stat
Display various stats about your organization and repositories
USAGE
  gh stat <stat> <resource> [flags]
AVAILABLE STATS
  stars:           Fetch data about stargazers
  forks:           Fetch data about forks
  issues:          Fetch data about issues
  pull-requests:   Fetch data about pull-requests
  commits:         Fetch data about commits
INHERITED FLAGS
  --help   Show help for command
ARGUMENTS
  An resource can be supplied as argument in any of the following formats:
  - organization or user, eg. "MY_USER"
  - repository, e.g. "MY_ORG/MY_REPO".
EXAMPLES
  $ gh stat stars MY_ORG/MY_REPO --group-by month
  $ gh stat forks MY_ORG/MY_REPO --group-by year
  $ gh stat issues MY_ORG/MY_REPO --csv
  $ gh stat commits MY_ORG/MY_REPO --branch master
LEARN MORE
  Use 'gh <command> <subcommand> --help' for more information about a command.
  Read the manual at https://cli.github.com/manual
```


## Improvement ideas

- Better validation
- Support org level stats (currently blocked: https://github.com/cli/cli/issues/4413)
- Rewrite in Go
    - Pros:
        - Better flexibility
        - Better parameter parsing/validation
        - GraphQL?
    - Cons:
        - Binary distribution might be less ideal (users can't read the code)
        - GraphQL?
- Come up with a GitHub CLI extension framework
    - Based on Go?
    - Based on Bash?
    - Rbenv style commands?
- More options for stats
    - Custom fields included?
    - Table output
    - Shell charts?


## License

The MIT License (MIT). Please see [License File](LICENSE) for more information.

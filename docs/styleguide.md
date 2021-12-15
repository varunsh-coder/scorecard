# Scorecard coding style guide.

NOTE: this is an evolving document that is expected to change over time. This
document does not signify the current state of the code rather the ideal state
Scorecard projects aims to be at. Feedback on the styleguide and PRs which
improve our code as per the styleguide are welcome!

Scorecard project follows the style guide specified by
https://go.dev/doc/effective_go and
https://github.com/golang/go/wiki/CodeReviewComments. The below guidelines are
assumed on top of the these existing styleguides. In case of a conflict, the
previous links take precedence.

The rule of thumb for contributors and code reviewers is that, someone
unfamiliar with the context in which the PR was written should be in a position
to understand the code.

## Code structure

*   Each struct or interface should belong to its own file. If there are nested
    structs that are mostly used by this struct, keep them in the same file.
*   Every file should have its equivalent `_test.go` file for unit testing.
*   If you made a bug fix, please add a corresponding unit test for the corner
    case.

## Code comments

*   Use `TODO(#<issue>): <details>` format for keeping track of any TODOs.
*   Comments should always start with a single space followed by a capital
    letter and end in a period.
*   Any `// nolint` comments should be for specific linters that you are trying
    to ignore. A blanket ignore should be avoided.

## Panic

*   Prefer log.Panic over panic or log.Fatal. See
    https://quasilyte.dev/blog/post/log-fatal-vs-log-panic/

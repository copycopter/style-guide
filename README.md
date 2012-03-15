Git
---

Choose a Github Issue.

Create a local feature branch off of master for development.

    git checkout master
    git pull
    git checkout -b 123-feature-xyz

Do work in your feature branch and commit the changes.

    git add -A
    git status
    git commit

Write a [good commit message](http://goo.gl/w11us).

    [#123] Summary of changes under 50 characters

    * More information about commit (under 72 characters)
    * More information about commit (under 72 characters)

A good commit message:

* Prefixes the subject line with a Github Issue number.
* Uses the present tense.

Share your feature branch

    git push origin [branch]

Rebase frequently to incorporate upstream changes.

    git checkout master
    git pull
    git checkout [branch]
    git rebase master
    <resolve conflicts>

Interactive rebase (squash) your commits (if necessary).

    git rebase -i master

Merge your branch back to master and push your changes.

    git checkout master
    git diff --stat master [branch]
    git merge [branch] --ff-only
    git push origin master

Delete your remote feature branch.

    git push origin :[branch]

Delete your local feature branch.

    git branch -d [branch]

Close Github Issue.

Programming
-----------

* Aggressively DRY code during development.
* Avoid comments.
* Avoid global variables.
* Avoid long parameter lists.
* Be consistent.
* Delete trailing whitespace.
* Don't duplicate the functionality of a built-in library.
* Don't over-design.
* Don't program defensively.
* Don't use an empty line at the beginning or end of methods, blocks or
  conditionals.
* Don't vertically align tokens on consecutive lines.
* Exceptions should be exceptional. Don't suppress them or use them for control
  flow.
* Guesses at future functionality should not be designed into the application.
* Keep methods small.
* Keep the code simple.
* Limit lines to a maximum of 80 characters.
* Make sure all tests pass before code is merged into a shared repository.
* No spaces after `(`, `[`. No spaces before `]`, `)`.
* Order variables and methods alphabetically when possible.
* Prefer single function exit points unless the complexity of the code is
  greatly reduced by multiple returns.
* Treat acronyms as words in names (`XmlHttpRequest` not `XMLHTTPRequest`),
  even if the acronym is the entire name (`class Html` not `class HTML`).
* Use 2 space indentation (no tabs) unless otherwise noted.
* Use an empty line between methods, blocks and conditionals.
* Use ASCII (or UTF-8, if you have to).
* Use default iterators for languages/types that support them.
* Use descriptive names that are both immediately obvious (to a new developer)
  and as short as possible without using abbreviations.
* Use implicit line joining where possible and indent continued lines.
* Use spaces around operators, after commas, colons and semicolons, around `{`
  and before `}`.
* Use standard language conventions for API documentation.
* Use Unix-style line endings (`\n`).

Ruby
----

* Avoid `%q`, `%Q`, `%x`, `%s`, and `%W`.
* Avoid conditional modifiers (lines that end with conditionals).
* Avoid hashes as optional parameters. Does the method do too much?
* Avoid meta-programming.
* Avoid monkey-patching core classes.
* Avoid return unless required.
* Avoid superfluous parentheses when calling methods, but keep them when you
  assign the return value.
        x = Math.sin(y)
        array.delete e
* Avoid ternary operators (`boolean ? true : false`). Use multi-line `if`
  instead to emphasize code branches.
* Don't use `unless` with `else`.
* Prefer `map` over `collect` and `reduce` over `inject` due to symmetry and
  familarity with mapping and reducing in other technologies.
* Prefer `detect` over `find` and `find_all` over `select` to avoid confusion
  with ActiveRecord and keep `select`/`reject` symmetry.
* Use `_` for unused block parameters.
        hash.map { |_, v| v + 1 }
* Use `%()` for single-line strings needing interpolation and double-quotes.
* Use `%w()` over `['', '']` for an array of words.
* Use `&&` and `||` for boolean expressions.
* Use `||=` freely.
* Use `{...}` over `do..end` for single-line blocks.
* Use `!` suffix for dangerous methods (modifies `self`).
* Use `?` suffix for predicate methods (return a boolean).
* Use `CamelCase` for classes and modules, `snake_case` for variables and
  methods, `SCREAMING_SNAKE_CASE` for constants.
* Use `def` with parentheses when there are arguments.
* Use `do..end` over `{...}` for multi-line blocks.
* Use heredocs for multi-line strings.
* Use `/(?:first|second)/` over `/(first|second)/` when you don't need the
  captured group.
* Use `private` over `protected` to indicate scope.
* Use `def self.method` over `def Class.method` or `class << self`.
* Use `Set` over `Array` for arrays with unique elements. The lookup is faster.
* Use single-quotes for strings unless variable interpolation is required.
* Use `unless boolean?` instead of `if !boolean?`.

Rails
-----

* Aim for skinny models and skinny controllers.
* Avoid Single Table Inheritance.
* Consider extracting `private` methods to their own object.
* Don't use SQL or SQL fragments (`where('inviter_id is not null')`) outside of
  models.
* Limit the number of instance variables shared between controller and view.
* Order controller contents: filters, public methods, `private` methods.
* Order model contents: constants, attributes, associations, nested attributes,
  named scopes, validations, callbacks, public methods, `private` methods.
* Prefer classes to modules when designing functionality that is shared by
  multiple models.
* Prefer gems to plugins.

Credit
------

This style guide was influenced by:

* [Bozhidar Batsov's Rails style guide](https://github.com/bbatsov/rails-style-guide)
* [Bozhidar Batsov's Ruby style guide](https://github.com/bbatsov/ruby-style-guide)
* [Christian Neukirchen's style guide](https://github.com/chneukirchen/styleguide)
* Debate at [thoughtbot](http://thoughtbot.com)
* [LevelUp](http://thelevelup.com)'s internal style guide

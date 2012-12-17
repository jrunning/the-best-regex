The Best Regular Expression For Everything
==========================================

There's a best regular expression for everything, except when there's not. This
project will (maybe) collect the best regular expressions for validating and
extracting the parts of common data, for example:

  * A U.K. postal code
  * A GitHub username
  * Currency
  * An email address (yes, [even that])

[even that]: http://stackoverflow.com/questions/201323/using-a-regular-expression-to-validate-an-email-address


Goals
-----

 1. Write good regular expressions.
 2. Use multi-line regular expressions and comments to thoroughly document each
    regular expression (also supplying a single-line version of each).
 3. Use automated testing best practices to verify correctness of each
    regular expression.
 4. Encourage pull requests (while enforcing testing best practices).
 5. Work toward the best* implementation of every regular expression.
 6. When the best* implementation relies on features not available in one or
    more common environments (say, named capture or Unicode properties),
    supplement it with additional best implementations which pass the
    same tests.
 7. Respect rightsholders when using, even just as a starting point, regular
    expressions originating elsewhere.

\* The definition of "best" is up for debate.


Project structure (draft)
-------------------------

The file structure of the project might look like this.

    ├─ test/
    │   ├─ javascript/
    │   │  └─ ...
    │   ├─ perl/
    │   │  └─ ...
    │   ├─ ruby/
    │   │  └─ ...
    │   └─ test-cases/
    │      ├─ email-address-html5.yml
    │      ├─ email-address-rfc5322.yml
    │      ├─ github-username.yml
    │      ├─ postal-code-ca.yml
    │      └─ postal-code-us.yml
    ├─ email-address-html5.yml
    ├─ email-address-rfc5322.yml
    ├─ github-username.yml
    ├─ postal-code-ca.yml
    ├─ postal-code-us.yml
    ├─ postal-code-ca.yml
    └─ Rakefile

### Implementation files

The root directory (`/`) contains one file for each type of datum we want
regular expressions for. They will be in a format that's machine-readable and
(especially) human-readable, such as YAML. Files should have descriptive names
that, when lexicographically sorted, have a logical order.

If a regular expression is country-specific then the last part of the filename
before the first `.` should be the country's ISO country code. Words in a
filename should be separated by hyphens. Other conventions or deeper hierarchy
in the event that the number of files grows prohibitively large will be
determined as necessary.

The internal structure of an implementation file itself is TBD. Among the
elements it will have are:

  * A very brief **title**
  * A **notes** section, formatted in Markdown, for further description,
    implementation notes, links to or excerpts from specifications or resources
    from which the implementations were derived, and any necessary license notes
    regarding same.
  * A **captures** section describing the capturing groups and their names
    and indices
  * An **implementations** section meeting the following requirements (to
    achieve the above Goals):
    * It must accommodate multiple implementations.
    * A simple method of "tagging" must be devised to indicate, both to human
      readers and to automated testing processes, what environments each
      implementation is expected to work in.
    * Each implementation must be expressed in two ways: A single-line regular
      expression, and a multi-line regular expression with comments.
    * Each implementation must have the same capturing groups. Named captures
      are strongly preferred for all environments that support them.

### Test suites

`/test` will be a subdirectory at the first level. It will contain a
subdirectory for each target environment (e.g. `/test/ruby`, `/test/javascript`,
etc.). Each of these will contain a file hierarchy matching the conventions or
requirements of the test methodology or framework chosen for that environment.

`/test/test-cases` will contain data files to be shared by all of the target
environments, so that only a single file need be edited to introduce a new test
for all environments. The structure of these files is TBD, but inspiration may
be taken from [twitter/twitter-text-conformance], which is shared among the
tests for twitter-text-rb, twitter-text-js, etc.

Each file in `/test/test-cases` will have the same name as the implementation
files it targets, e.g. `postal-code-ca.yml`.

[twitter/twitter-text-conformance]: https://github.com/twitter/twitter-text-conformance

### Automated testing

Ideally it will be possible to run tests for all environments with very little
fuss. Make, Rake, or a similar utility may be used to initiate tests across
environments.


Answers
-------

  * **"But this site over here already lists a regular expressions for all
    the things."**

    That site over there is great, but it doesn't achieve some or most of the
    stated goals of this project.
    
  * **"Who are you anyway?"**

    I'm just some guy. I'm not even that great at regular expressions. Hence
    this project, which will hopefully attract folks much better at them than I,
    whereupon I can remove this answer.


License
-------

TBD

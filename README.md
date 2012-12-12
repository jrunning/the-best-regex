The Best Regular Expression For Everything
==========================================

There's a best regular expression for everything, except when there's not. This
project will (maybe) collect the best regular expressions for validating and
extracting the parts of common entities, for example:

  * A U.K. postal code
  * A GitHub username
  * Currency
  * An email address (yes, [even that])

[even that]: http://stackoverflow.com/questions/201323/using-a-regular-expression-to-validate-an-email-address


Goals
-----

 1. Write good regular expressions.
 2. Use multi-line regular expressions and comments to thoroughly document each
    (also supplying a single-line version of each).
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


Project structure
-----------------

TBD


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

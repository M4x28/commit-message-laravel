# Commit Message Roules for Laravel Project
Here I'm going to specify the convention for the commit message in a Laravel project. <br>
This document was made to help organization and working group to provide more effective commit message and improve the workflow.
---
>By the way this document will be in continuous development to keep up with the framework changes.
---

### The commit message should be structured as follows:
```
<type>[optional scope]: [<branch>] <subject>

[optional body]

[optional footer(s)]
```

# Deep inside:
```
# Type: core, feat, fix, docs, style, refactor, test, chore, git, merge, composer
# Scope: controllers, models, repositories
# Subject: (This commit) <verb: 'add, fix, delete, modify'> subject 

# <body>
 

# [footer]
# Type should be one of the following:
# * core (improve core class)
# * feat (new feature)
# * fix (bug fix)
# * docs (changes to documentation)
# * style (formatting, missing semi colons, etc; no code change)
# * refactor (refactoring code)
# * test (adding missing tests, refactoring tests; no production code change)
# * git (changes about git, mainly .gitignore updates)
  
# Scope is just the scope of the change. Shold be one of the following:
# * Controller
# * Model
# Subject should use impertivite tone and say what you did.
# The body should go into detail about changes made.
# The footer should contain issue references or actions.
 ```

# Example

```
## ---------------------------------------------------------------------------------
#feat($browser): onUrlChange event (popstate/hashchange/polling)
#
#Added new event to $browser:
#- forward popstate event if available
#- forward hashchange event if popstate not available
#- do polling when neither popstate nor hashchange available
#
#Breaks $browser.onHashChange, which was removed (use onUrlChange instead)
## ---------------------------------------------------------------------------------

## ---------------------------------------------------------------------------------
#fix($compile): couple of unit tests for IE9
#
#Older IEs serialize html uppercased, but IE9 does not...
#Would be better to expect case insensitive, unfortunately jasmine does
#not allow to user regexps for throw expectations.
#
#Closes #392
#Breaks foo.bar api, foo.baz should be used instead
## ---------------------------------------------------------------------------------
#
## ---------------------------------------------------------------------------------
#feat(directive): ng:disabled, ng:checked, ng:multiple, ng:readonly, ng:selected
#
#New directives for proper binding these attributes in older browsers (IE).
#Added coresponding description, live examples and e2e tests.
#
#Closes #351
## ---------------------------------------------------------------------------------
#
## ---------------------------------------------------------------------------------
#style($location): add couple of missing semi colons
#
#docs(guide): updated fixed docs from Google Docs
#
#Couple of typos fixed:
#- indentation
#- batchLogbatchLog -> batchLog
#- start periodic checking
#- missing brace
## ---------------------------------------------------------------------------------
#
## ---------------------------------------------------------------------------------
#feat($compile): simplify isolate scope bindings
#
#Changed the isolate scope binding options to:
#  - @attr - attribute binding (including interpolation)
#  - =model - by-directional model binding
#  - &expr - expression execution binding
#
#This change simplifies the terminology as well as
#number of choices available to the developer. It
#also supports local name aliasing from the parent.
#
#BREAKING CHANGE: isolate scope bindings definition has changed and
#the inject option for the directive controller injection was removed.
#
#To migrate the code follow the example below:
#
#Before:
#
#scope: {
#  myAttr: 'attribute',
#  myBind: 'bind',
#  myExpression: 'expression',
#  myEval: 'evaluate',
#  myAccessor: 'accessor'
#}
#
#After:
#
#scope: {
#  myAttr: '@',
#  myBind: '@',
#  myExpression: '&',
#  // myEval - usually not useful, but in cases where the expression is assignable, you can use '='
#  myAccessor: '=' // in directive's template change myAccessor() to myAccessor
#}
#
#The removed `inject` wasn't generaly useful for directives so there should be no code using it.
## ---------------------------------------------------------------------------------
#
```

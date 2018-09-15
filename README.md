# codacy-hack

[![Codacy Badge](https://api.codacy.com/project/badge/Grade/bf79e02cbac845378498a6446bd88b9a)](https://app.codacy.com/app/cclauss/codacy-hack?utm_source=github.com&utm_medium=referral&utm_content=cclauss/codacy-hack&utm_campaign=Badge_Grade_Settings)

Hack on Codacy

> Codacy runs PyLint so we already have a linter in place.

_The ideal linter in a dynamic language should flag issues that the compiler would flag in a compiled language._  The linter should raise an alert if there is a syntax error or if an import is missing like a compiler would.  It should warn you that __basestring__, __cmp()__, __long__, __reload()__, __unicode__, __xrange()__ are not builtins in Python 3.

Codacy does none of these things that a compiler would.  It merely says that __async def func():__ is not valid Python.  (_Argh!?!_)  It seems to be ___tuned to Python 2___ and is therefor more legacy than the PyLint that it is based on.  In the hands of a strong practitioner, PyLint can catch many of the issues mentioned above but it requires configuration and usually a lot of __# pylint: disable=xyz__ directives in your code.

I prefer __flake8 . --count --select=E901,E999,F821,F822,F823 --show-source --statistics__

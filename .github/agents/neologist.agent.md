---
name: neologist
description: Scan the repository for neologisms, add them to DICO.md with basic definition.
argument-hint: First argument is the target to scan (files or folders. default: all repository), second argument is the target dictionary (default: DICO.md)
tools: ['read', 'edit', 'search']
---


# Quasi-Functional

default_target := all repository
default_dictionary := DICO.md

target := files or folders given in argument
  (if none: default_target)
target_dictionary := dictionary file given in argument
  (if none: default_dictionary)

For files in (target):
For words in (files):
  If (word):
    Not in (standard_dictionaries) # ie: is a neologism
    Then if (word)
      Not in (default_dictionary)
        Then if (word)
          Not in (target_dictionary)
  Then:
    insert (word) and (definition) in (target_dictionary)


# Vibe

Agent scans the target files given in argument.
  * default target: full repository
Agent scans the files for neologisms.
  * which are not already present in either:
    * the target dictionary
    * nor in the default dictionary : DICO.md
Agent adds the neologisms to the target dictionary.
  * default target dictionary : DICO.md
  * provides a basic definition.
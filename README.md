[![Stories in Ready](https://badge.waffle.io/melvincarvalho/vocab.png?label=ready&title=Ready)](https://waffle.io/melvincarvalho/vocab)
# vocab

[![Join the chat at https://gitter.im/melvincarvalho/vocab](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/melvincarvalho/vocab?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)


#vocab for SoLiD apps

Running live here: https://melvincarvalho.github.io/vocab/

Quick Start for contributors
----------------------------

```
$ git clone git://github.com/melvincarvalho/vocab
$ cd vocab
$ sudo npm -g install bower
$ bower install
```

# Tutorial

# Chapter 4 - Solid Words

![](https://melvincarvalho.gitbooks.io/solid-tutorials/content/words.png)


## Introduction

In this tutorial we will expand the previous tutorial video into a real world useful app, one for word training and vocabulary.

*What you will learn*

* How to structure JavaScript in several parts
* How to set up a turtle data file on github
* How to use localStorage to save state
* How to automatically remember a user and login
* How to prepare language files to be used in vocab training
* How to add audio to apps
* How to add an app to your desktop

## The App


The next tutorial is an app that is used to learn vocabulary in a foreign language.  A file is prepared containing the 10,000 most common words in a target language.  The source for word frequency was [wictionary](https://en.wiktionary.org/wiki/Wiktionary:Frequency_lists).  For this demo I have used the czech language with english, but any language pair is possible.

From a list of words it's possible to paste it into an online translator and get a list of translations.  For this I used google translate.  A simple program can change a 2 column text file into the needed turtle.  I used awk for this

```
awk -F $'\t' ' { print "<#" ++i "> <http://www.w3.org/2000/01/rdf-schema#label>" " \""  $2 "\"" "@en .\n" "<#" i ">  <http://www.w3.org/2000/01/rdf-schema#label>" " \""  $1 "\"" "@cz ." }'
```

Which should give you output something a bit like this:

```html
    <#1512> <http://www.w3.org/2000/01/rdf-schema#label> "žádost"@cs .
    <#1512> <http://www.w3.org/2000/01/rdf-schema#label> "application"@en .
````

One line is in Czech (cs) one in English (en).  This file can be conveniently stored as a .ttl in gh-pages on github so that it can be [loaded](https://github.com/melvincarvalho/data/blob/master/vocab/czech.ttl) into the app dynamically.  This is a great way to host all sorts of linked data content.




More coming soon ...


## See Also

* [Source Code](https://github.com/melvincarvalho/vocab/)
* [Live Demo](http://melvincarvalho.github.io/vocab/)
* [wictionary](https://en.wiktionary.org/wiki/Wiktionary:Frequency_lists)

# clojure-py

An implementation of Clojure in pure Python. [![Build Status](https://secure.travis-ci.org/halgari/clojure-py.png?branch=master)](http://travis-ci.org/halgari/clojure-py)

## Why Python? 

It is our belief that static virtual machines make very poor runtimes for dynamic languages. They constrain the languages to their view of what the "world should look like" and limit the options available to language implementors. We are attempting to prove this by writing an implementation of Clojure that runs on the Python VM. We believe that with a proper dynamic JIT (like pypy) a version of clojure running on a dynamic VM can outperform its JVM and CLR counterparts. 

Aside from that, there are many Python libraries like PySide (Qt GUI), numpy, scipy, and stackless that do not have JVM counterparts, or at least the Python implementations are easier to use and learn. clojure-py will integrate tightly with thy Python VM and will be able to use all of these libraries.

## Basic concepts

Python builtins are available under the py/ namespace. Actual python bytecodes can be injected via py.bytecodes/OP

Viewing the code at https://github.com/halgari/clojure-py/blob/master/clojure/core.clj is probably the best way to get a feeling of what is possible, and how clojure-py implements certain functions.

One note: clojure-py implements the new "property vs calling method" design used in ClojureScript:

      (.__name__ (module)) ; same as module.__name__() in python
   
      (.-__name__ (module)) ; same as module.__name__ in python
   

## How can I help?

At this point, find a need and fill it! Play around with clojure-py, start porting your favorite clojure lib, and see what is missing. Also feel free to join our [mailing list](http://groups.google.com/group/clojure-py-dev). We (the clojure-py devs) normally just send out a message either we plan on working on a certain aspect of clojure-py (either through a issue report or through the mailing list). Currently there are quite a few functions in clojure.core that need porting. Drop by the mailing list and let us know what your interests are, and we'll be glad to offer suggestions and help however we can. 

## Blog
   From time to time, we'll post status updates, ideas and plans to this blog http://clojure-py.blogspot.com/

## Installation
Install 0.1.0 release:

    easy_install clojure-py
    clojurepy

To run from GitHub checkout:

    python ./clojure.py
    
## Unit tests

    # (must 'easy_install nose' or 'pip install nose' first)
    nosetests

## Running

    clojurepy
    
## License
Not endorsed by Rich Hickey, but this project contains code based on his work

    Clojure-Py
    Copyright (c) Rich Hickey. All rights reserved.
    The use and distribution terms for this software are covered by the
    Eclipse Public License 1.0 (http://opensource.org/licenses/eclipse-1.0.php)
    which can be found in the file epl-v10.html at the root of this distribution.
    By using this software in any fashion, you are agreeing to be bound by
    the terms of this license.
    You must not remove this notice, or any other, from this software.

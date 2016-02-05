---
layout: post
title: ClojureScript in the Wild
author: dan
---

For the last few weeks, we've been building an application using a Clojure stack and despite the ups and downs it's been a positive experience. This post is going to cover the challenges we faced and the solutions that we eventually arrived at.

For anyone just joining this blog, our tech stack traditionally revolves around JS and where possible we opt to work only on the client side, reaching out to external services like Firebase for rapid prototyping and proof of concept ideas. As such, having a high velocity iteration environment is a _must have_. In the past this has meant livereloading with browser-sync and more recently hot-reloading with React.

{% highlight clojure %}
;; this function renders a rocket
;; it's a pretty wicked rocket
(defn rocket [{launched? :launched?}]
  [:div.rocket (if launched? "Y" "N")])

(defn rocket-list
  "This function is substantially more complex and therefore
   requires a proper docstring. Let's see whether it gets
   highlighted properly"
  [rockets]
  (map rocket rockets)
  (-> 42
      (+ 43)
      (/ 5)))

;; finally lets do some work with atoms
(inc (count []))

(def counter (atom false))
(def counter (atom nil))
(def counter (atom true))

(def next #(swap! counter inc))
{% endhighlight %}

When appropriate we take a functional approach to defining our views with React, opting for higher order components to help us keep our code declarative. Reagent takes this idea to the next level, __components are just functions__ — similar to React's stateless components.

We've been known to say this before.

> When appropriate we take a functional approach to defining our views with React, opting for higher order components to help us keep our code declarative. Reagent takes this idea to the next level, components are just functions — similar to React's stateless components

Sometimes the best thing to do is just to sit down and talk about `inline.code(snippets)` until the day is drawn and done.


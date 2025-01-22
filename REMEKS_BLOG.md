# Remek's Clojure Learning Blog

## Day 1
So I finally get to learn lisp that my friend Ivan Kelly bragged about loving so much. I still can't put my finger on what the Clojure symbols are. I am mildly impressed that Clojure does closed-open ranges like in here:
```
  "What if you only wanted to get part of a string?"
  (= "World" (subs "Hello World" 6 11))
```
I am mildly unimpressed that `string/index-of` returns a number or a `nil`
```
  "But when something doesn't exist, nothing is found"
  (= nil (string/index-of "hello world" "bob"))
```
Favouring the first element of the list seems familiar from Scala and I expect to become helpful when map/reducing and with recursion.
```
  "As well as the rest"
  (= '(2 3 4 5) (rest '(1 2 3 4 5)))
```
I still don't know how to add to the end of the list
```
  "Conjoining an element to a list isn't hard either"
  (= '(:e :a :b :c :d) (conj '(:a :b :c :d) :e))
```
Ah, going to vectors now and it became apparent that Clojure lists are linked lists. This is why conjoining prepends and why `rest` favours the first element (head).

Why does this work
```
  "You may create that mapping"
  (= [1 4 9 16 25] (map (fn [x] (* x x)) [1 2 3 4 5]))
```
but this doesn't?
```
  "You may create that mapping"
  (= [1 4 9 16 25] (map (fn [x] (square x)) [1 2 3 4 5]))
```
Ah, coz `square` isn't built-in.
I am stuck here:
```
Assertion failed!
Multimethods allow more complex dispatching
(= "Bambi eats veggies." (diet {:species "deer", :name "Bambi", :age 1, :eater :herbivore}))
```
And first impressions - a functional language with a lot of parentheses.
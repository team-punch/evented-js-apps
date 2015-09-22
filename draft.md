# Evented JavaScript Apps

This essay is aimed at people who for whatever reason cannot grasp events, and thus, insist on doing events incorrectly and telling all their friends about it.

## Why events

Events are the simplest mechanism for coordinating updates in a JavaScript application. They create less code, the structure is flat (so there’ll always be one event mapped to a callback), and all you really need are functions, a small set of rules, and you’re good to go.

## Vindicating callbacks

Callback examples are usually written like this:

    doSomething(foo => {
      let foo1 = 1
      let bar2 = 2

      doSomethingElse(foo1 => {
        let foo2 = foo1 + 1

        doSomethingElseElse(foo2 => {
          console.log('ERMAGEHRD CALLBACKS SUCK')
        })
      })
    })

The above is absolutely stupid code, but it’s also how a lot of people would write it. When they cower behind Promises, they’ll often still do that kind of thing but will conveniently pretend that the elephant isn’t in the room, when in fact it has its ass pressed hard against their faces.

A reasonable person would’ve done this instead:

    // Refactor callbacks into non-anonymous functions

The above example means that:

* Callbacks are now testable individually. Source the method into a test, run it with a value, boom, done.
* You can tell what the method does by its name.
* You don’t need to learn new stupid concepts. If it weren’t for the fact they’re comprehension workarounds, learning new stuff is generally a worthwhile endeavor.
* More importantly: **it’s all just functions**. If you stick to passing simple data structures around, testing this code is cake. But we’ll get to that further below.

## The data layer case

## Testing this stuff

## Comparisons

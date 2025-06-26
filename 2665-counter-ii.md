
## 2620. Counter II

- JavaScript
```JavaScript
/**
 * @param {integer} init
 * @return { increment: Function, decrement: Function, reset: Function }
 */
var createCounter = function(init) {
    let currentValue = init;
    return {
        increment: function() {
            return ++currentValue;
        },
        decrement: function() {
            return --currentValue;
        },
        reset: function() {
            currentValue = init;
            return currentValue;
        }
    };
};

/**
 * const counter = createCounter(5)
 * counter.increment(); // 6
 * counter.reset(); // 5
 * counter.decrement(); // 4
 */
```

- TypeScript
```TypeScript
type Counter = {
    increment: () => number,
    decrement: () => number,
    reset: () => number,
};

function createCounter(init: number): Counter {
    let currentValue = init;
    return {
        increment: () => ++currentValue,
        decrement: () => --currentValue,
        reset: () => (currentValue = init),
    };
}

/**
 * const counter = createCounter(5)
 * counter.increment(); // 6
 * counter.reset(); // 5
 * counter.decrement(); // 4
 */
```

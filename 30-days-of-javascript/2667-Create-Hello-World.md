## 2667. Create Hello World Function

#### TypeScript

```typescript
function createHelloWorld() {
    return function(...args: any[]): string {
        return "Hello World";
    };
}
```

#### Javascript

```javascript
/**
 * @return {Function}
 */
var createHelloWorld = function() {
    return function(...args) {
        return "Hello World";
    };
};
```

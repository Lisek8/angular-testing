# Helpers

## Get element by css

```ts
function getElementByCss(selector: string, element: DebugElement): DebugElement {
  return element.query(By.css(selector));
}
```

## Get elements by css

```ts
function getElementsByCss(selector: string, element: DebugElement): DebugElement[] {
  return element.queryAll(By.css(selector));
}
```

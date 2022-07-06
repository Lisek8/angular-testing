# Snippets

## Effect of the button click on the component

```ts
it('should do something correctly when button is pressed', fakeAsync(() => {
  const someElement = fixture.debugElement.query(By.css('[data-qa=some-button]'));

  someElement.nativeNode.dispatchEvent(new Event('click'));
  tick();
  fixture.detectChanges();

  // Expect whatever results you need
}));
```

## Test input - trigger validation messages

```ts
it('should display validation message', () => {
  const someElement = fixture.debugElement.query(By.css('[data-qa=some-input]'));

  someElement.nativeNode.value = 'banana';
  someElement.nativeNode.dispatchEvent(new Event('input'));
  component.someForm.get('someInput').touched = true;
  fixture.detectChanges();

  // Expect whatever results you need
});
```

## Test select input - trigger validation messages

```ts
it('should display validation message', () => {
  const someElement = fixture.debugElement.query(By.css('[data-qa=some-select-input]'));

  someElement.nativeNode.value = 'banana';
  someElement.nativeNode.dispatchEvent(new Event('change'));
  someElement.nativeNode.dispatchEvent(new Event('blur'));
  component.someForm.get('someSelectInput').touched = true; // Not sure if this is actually needed (TO_VERIFY)
  fixture.detectChanges();

  // Expect whatever results you need
});
```

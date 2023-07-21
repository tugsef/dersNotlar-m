```JavaScript
async function delay(ms){
  return new Promise((resolve) => setTimeout(resolve , ms));
}

// test
await delay(3000)
```

# DevSnap.js
DevSnap.js is a JavaScript library for collecting device, browser, and user data for security, analytics, and access control.

![DevSnap.js Overview](test/logo.png)

Hosted on GitHub: [https://github.com/asjayamal/DevSnapJs](https://github.com/asjayamal/DevSnapJs)

Live Preview : [https://asjayamal.github.io/DevSnapJS/test/](https://asjayamal.github.io/DevSnapJS/test/)

---

## Installation

```bash
git clone https://github.com/asjayamal/DevSnapJs.git
```
Copy `DevSnap.js` to your project or import as an ES6 module.

---

## Usage

### Import

```js
import { DevSnapJs } from './DevSnap.js';
// or if included via script tag, use window.DevSnapJs
```

### Basic Data Capture

```js
const result = await DevSnapJs.initSnap("snap", window.location.host, "Surface-Level", true);
console.log(result);
```

### Restriction Mode

```js
const result = await DevSnapJs.initSnap("restrict", window.location.host, "mobile");
console.log(result);
```

---

## Usage in Popular Frameworks

### Vanilla JS

```html
<script type="module">
import { DevSnapJs } from './DevSnap.js';

DevSnapJs.initSnap("snap", window.location.host, "Surface-Level", true)
  .then(result => console.log(result));
</script>
```

### React

```jsx
import React, { useEffect } from "react";
import { DevSnapJs } from "./DevSnap.js";

function App() {
  useEffect(() => {
    DevSnapJs.initSnap("snap", window.location.host, "Surface-Level", true)
      .then(result => console.log(result));
  }, []);
  return <div>Check console for DevSnapJs output</div>;
}
export default App;
```

### Vue 3

```vue
<script setup>
import { onMounted } from 'vue'
import { DevSnapJs } from './DevSnap.js'

onMounted(() => {
  DevSnapJs.initSnap("snap", window.location.host, "Surface-Level", true)
    .then(result => console.log(result))
})
</script>
<template>
  <div>Check console for DevSnapJs output</div>
</template>
```

### Angular

```typescript
// In your component
import { Component, OnInit } from '@angular/core';
import { DevSnapJs } from './DevSnap.js';

@Component({
  selector: 'app-root',
  template: '<div>Check console for DevSnapJs output</div>'
})
export class AppComponent implements OnInit {
  ngOnInit() {
    DevSnapJs.initSnap("snap", window.location.host, "Surface-Level", true)
      .then(result => console.log(result));
  }
}
```

### Svelte

```svelte
<script>
  import { onMount } from 'svelte';
  import { DevSnapJs } from './DevSnap.js';

  onMount(() => {
    DevSnapJs.initSnap("snap", window.location.host, "Surface-Level", true)
      .then(result => console.log(result));
  });
</script>
<div>Check console for DevSnapJs output</div>
```

---

## Data Levels

- **Surface-Level**: Minimal device info (screen, platform, user agent).
- **Interaction-Level**: Adds more device details (client hints, GPU, RAM, CPU, connection).
- **Profiling-Level**: Deep profiling (battery, geolocation, network, bridge API).

You can specify the level as `"Surface-Level"`, `"Interaction-Level"`, or `"Profiling-Level"`.

---

## Restrict Level

- **snap**: Normal data capture, optionally with geolocation.
- **restrict**: Restricts access based on device type (`"mobile"`, `"desktop"`, or `"untrusted"`).

Example:
```js
// Restrict to desktop only
await DevSnapJs.initSnap("restrict", window.location.host, "desktop");
```

---

## Step-by-Step Usage

1. **Clone the repository**
    ```bash
    git clone https://github.com/asjayamal/DevSnapJs.git
    ```
2. **Copy `DevSnap.js` to your project**
3. **Import and use as shown above**
4. **Choose data level and restrict mode as needed**

---

## License

MIT

---

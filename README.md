# GIF Play/Pause Library

A lightweight and accessible JavaScript library that allows you to toggle GIF play/pause with a button overlay.  
Supports **CDN (UMD)** and **ES Module (import)** usage.

---

## Features

- Pure JavaScript — no dependencies
- Play/Pause GIF with a single button
- Accessible (ARIA labels + dynamic alt text)
- Automatically loads FontAwesome icons
- Supports custom alt text
- Works with **CDN** or **NPM import**

---

## Installation

### **NPM**

```sh
npm install gif-library
```

### **CDN**

```html
<script src="https://cdn.jsdelivr.net/npm/gif-library@1.0.1/dist/gifLibrary.umd.js"></script>
```

---

## Usage

### Using CDN (UMD Version)

Global function name: GifLibrary

```html
<img src="example.gif" class="myGif" />

<script>
  GifLibrary(".myGif", "example.png");
</script>
```

### Using ES Module

```js
import gifPlay from "gif-library";
gifPlay(".myGif", "example.png");
```

---

## Parameters

```js
GifLibrary(selector, stillImage, altText);
```

| Parameter    | Type   | Required | Description                          |
| ------------ | ------ | -------- | ------------------------------------ |
| `selector`   | string | Yes      | CSS selector for the GIF image       |
| `stillImage` | string | Yes      | The static PNG/JPG shown when paused |
| `altText`    | object | No       | Custom alt text for accessibility    |

---

## Alt Text Example

```js
GifLibrary(".myGif", "still.png", {
  gifAlt: "GIF is playing",
  stillAlt: "GIF is paused",
});
```

---

## Full Example

```html
<img src="cat.gif" class="catGif" />

<script>
  GifLibrary(".catGif", "cat.png", {
    gifAlt: "Cat animation playing",
    stillAlt: "Cat image paused",
  });
</script>
```

---

## Optional CSS Override

```css
.gif-toggle-btn {
  background: black !important;
  border-radius: 5px !important;
}
```

---

## How It Works

- Wraps your <img> inside a positioned container
- Adds an accessible play/pause button
- Uses timestamp trick to restart GIF correctly
- Updates alt, aria-label, and aria-pressed dynamically

---

## License

MIT License.

---

## Contributing

Pull requests and issues are welcome.

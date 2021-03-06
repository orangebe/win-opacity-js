# win-opacity

Read and write the opacity values of windows on the Windows operating system.

## Example

```js
const winOpacity = require('win-opacity');
const windows = winOpacity.getWindows();
for (const win of windows) {
  console.log(win.title); // Title on the window
  const opacity = winOpacity.getOpacity(win);
  // Make the window slightly more transparent
  winOpacity.setOpacity(win, opacity - 10);
}
```

## Type Definitions

Definitions given in TypeScript format.

```typescript
type WindowHandle = number;
interface NativeWindow {
  string title;
  WindowHandle handle;
};
```

## API

- `getWindows() -> NativeWindow[]`
  - Gets all visible windows
- `getOpacity(window: WindowHandle | NativeWindow) -> number`
  - Returns the opacity of a window. The value will be in the range of [0-255]
- `setOpacity(window: WindowHandle | NativeWindow, opacity: number) -> void`
  - Sets the opacity of a window. `opacity` must be in the range of [0-255]
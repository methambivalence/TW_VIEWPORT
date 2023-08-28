# TW_VIEWPORT

Use the following method for fix how Tailwind CSS show websites on mobile devices.

## Usage

Add to main .css file:

```css
.h-screen {
  height: 100vh;
  height: calc(var(--vh, 1vh) * 100) !important;
}
```

Add to React/Next app:

```typescript
useEffect(() => {
  const handleResize = () => {
    document.documentElement.style.setProperty(
      "--vh",
      window.innerHeight * 0.01 + "px"
    );
  };

  window.addEventListener("resize", handleResize);
  handleResize();
  return () => {
    window.removeEventListener("resize", handleResize);
  };
});
```

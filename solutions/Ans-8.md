Good question! You only need to use `extend` **once** inside the `theme` object — and within that, you can extend **multiple properties**.

Here’s an example:

```javascript
module.exports = {
  theme: {
    extend: {
      colors: {
        primary: "#1E40AF",
        secondary: "#9333EA",
      },
      fontSize: {
        small: "0.875rem",
        large: "2rem",
      },
      spacing: {
        72: "18rem",
        84: "21rem",
      },
      borderRadius: {
        xl: "1rem",
      },
    },
  },
};
```

### ✅ **What This Does:**

- You only write `extend` **once**.
- Inside `extend`, you can add or override **any property** (like `colors`, `fontSize`, `spacing`, etc.).
- You don’t need to repeat `extend` for each property — just add whatever you want to customize under that single `extend`.

### 🎯 **Example Usage:**

```html
<div class="bg-primary text-white p-6 rounded-xl">
  <h1 class="text-large">Hello, Tailwind!</h1>
</div>
```

Would you like me to guide you through another example or help you organize your config better? Let me know! 🚀

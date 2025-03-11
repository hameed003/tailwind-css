### When Should You Use the `extend` Keyword in Tailwind CSS?

The `extend` keyword in Tailwind CSS is used inside the `theme` object in `tailwind.config.js` to **add custom styles while keeping Tailwind’s default styles intact**.

---

### **1️⃣ Without `extend` (Overrides Default Theme)**

If you define properties **without** `extend`, it **replaces** Tailwind’s default values. This means you **lose** access to Tailwind’s predefined values.

#### ❌ Example: Overriding the Default Colors (Not Recommended)

```js
module.exports = {
  theme: {
    colors: {
      primary: "#1E40AF", // Tailwind’s default colors are removed!
    },
  },
};
```

🔴 **Problem:** You can now **only** use `text-primary`, but `text-blue-500`, `bg-red-600`, etc., **will no longer work**.

---

### **2️⃣ Using `extend` (Adds Custom Values Without Removing Defaults)**

Using `extend` allows you to **add new values** while keeping Tailwind's existing styles.

#### ✅ Example: Extending Tailwind's Colors (Recommended)

```js
module.exports = {
  theme: {
    extend: {
      colors: {
        primary: "#1E40AF", // Custom color
      },
    },
  },
};
```

✅ **Now you can use**:

- `text-primary` for your new color.
- `text-blue-500`, `bg-green-400`, etc., from Tailwind’s default palette.

---

### **3️⃣ Example with Other Theme Properties**

The `extend` keyword is useful for customizing more than just colors.

#### ✅ Example: Extending Font Size and Spacing

```js
module.exports = {
  theme: {
    extend: {
      fontSize: {
        xxs: "0.65rem", // Add a tiny font size
      },
      spacing: {
        72: "18rem", // Add extra spacing utility
      },
    },
  },
};
```

Now you can use:

- `text-xxs` → A super small text size.
- `mt-72` → A margin of 18rem.

---

### **🔹 When to Use `extend`**

| **Scenario**                         | **Use `extend`?**       |
| ------------------------------------ | ----------------------- |
| Adding new colors, spacing, fonts    | ✅ Yes                  |
| Keeping default Tailwind values      | ✅ Yes                  |
| Completely replacing Tailwind values | ❌ No (Avoid)           |
| Changing only a few values           | ✅ Yes                  |
| Removing all default values          | ❌ No (Not recommended) |

---

### **📌 Summary**

✅ Use `extend` when you **want to add new styles** while keeping Tailwind’s defaults.  
❌ Avoid using `extend` if you need to **override Tailwind completely**—only do this if you're building a highly customized design system.

---

Would you like a **real-world example** of extending Tailwind for a project? 🚀

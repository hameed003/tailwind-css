**Q1:**

```js
// Without extend
tailwind.config = {
  theme: {
    colors: {
      mycolor: "#da373d",
    },
  },
};
```

and

```js
// With extend
tailwind.config = {
  theme: {
    extend: {
      colors: {
        mycolor: "#da373d",
      },
    },
  },
};
```

what is the difference between these two: [Ans-1]()

**Q2:** in the first one `without extend` you said we can not use `tailwind's` color pallet so how you are using `text-white` [Ans-2]()

**Q3:** list all the things that the `theme` object contains to customize tailwind css. [Ans-3]()

**Q4:** set up a complete tailwind.config.js OR walk through a real project. [Ans-4]()

**Q5:** build a small project with the above setup. [Ans-5]()

**Q6:** when should i use `extend` keyword in theme object in tailwind. [Ans-6]()

**Q7:** real-world example or usage of extend keyword in tailwind. [Ans-7]()

**Q8:** will i have to use `extend` for every property that i want to `extend` or i have to use it `once` and can extend any properties. [Ans-8]()

**Q9:** what i want to use `extend` as well as i want to `replace` or `override` a property. [Ans-9]()

**Q10:**

```js
tailwind.config = {
  theme: {
    screens: {
      //✅ Custom screen added ( new )
      xs: "475px",

      //✅ The below all the are default screens in Tailwind.
      sm: "640px",
      // => @media (min-width: 640px) { ... }

      md: "768px",
      // => @media (min-width: 768px) { ... }

      lg: "1024px",
      // => @media (min-width: 1024px) { ... }

      xl: "1280px",
      // => @media (min-width: 1280px) { ... }

      // Modified:
      "2xl": "1320px",
      // '2xl': '1536px',
      // => @media (min-width: 1536px) { ... }
    },
  },
};
```

,

```js
tailwind.config = {
  theme: {
    screens: {
      sm: "576px",
      // => @media (min-width: 576px) { ... }

      md: "960px",
      // => @media (min-width: 960px) { ... }

      lg: "1440px",
      // => @media (min-width: 1440px) { ... }
    },
  },
};
```

,

```js
tailwind.config = {
  theme: {
    extend: {
      screens: {
        "3xl": "1600px",
        // => @media (min-width: 1600px) { ... }
      },
    },
  },
};
```

,

```js
tailwind.config = {
  theme: {
    screens: {
      //✅ Custom screen added ( new )
      "4xl": "1900px",
    },
  },
};
```

what is the difference between all 4 of them explain detail with examples. [Ans-10]()

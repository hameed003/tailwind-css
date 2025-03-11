Awesome! Let’s build a small, responsive project using the Tailwind setup we created. 🚀

We’ll make a simple **Weather Card** with a header, input field, button, and animated weather info — perfect for practicing your React + Tailwind skills!

I’ll provide the file structure, component code, and a sample HTML page so you can run it locally or in your existing React app.

---

## 📂 **Project Structure (for React app):**

```
weather-app/
├── public/
├── src/
│   ├── App.js
│   ├── components/
│   │   ├── WeatherCard.js
│   │   └── Header.js
│   └── index.css
└── tailwind.config.js
```

---

## 📘 **App.js:**

```javascript
import React, { useState } from "react";
import WeatherCard from "./components/WeatherCard";
import Header from "./components/Header";

function App() {
  const [weather, setWeather] = useState(null);

  const handleSearch = (city) => {
    // Example weather data (you can replace this with an API call)
    const mockWeather = {
      city: city,
      temperature: 28,
      description: "Partly Cloudy",
      icon: "☁️",
    };
    setWeather(mockWeather);
  };

  return (
    <div className="min-h-screen bg-background p-8">
      <Header />
      <div className="flex flex-col items-center">
        <input
          type="text"
          placeholder="Enter city"
          className="input mb-4"
          onKeyDown={(e) => {
            if (e.key === "Enter") handleSearch(e.target.value);
          }}
        />
        <button className="btn-primary" onClick={() => handleSearch("Mumbai")}>
          Get Weather
        </button>

        {weather && <WeatherCard weather={weather} />}
      </div>
    </div>
  );
}

export default App;
```

---

## 🌤️ **WeatherCard.js:**

```javascript
import React from "react";

const WeatherCard = ({ weather }) => {
  return (
    <div className="card mt-8 animate-fadeIn">
      <h2 className="text-2xl font-heading">{weather.city}</h2>
      <p className="text-lg">{weather.icon}</p>
      <p className="text-xl">{weather.temperature}°C</p>
      <p className="text-secondary">{weather.description}</p>
    </div>
  );
};

export default WeatherCard;
```

---

## 🏷️ **Header.js:**

```javascript
import React from "react";

const Header = () => {
  return (
    <header className="w-full p-4 bg-primary text-white text-center shadow-deep">
      <h1 className="text-3xl font-heading">Weather App 🌤️</h1>
    </header>
  );
};

export default Header;
```

---

## 🎨 **index.css:**

```css
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer components {
  .btn-primary {
    @apply px-4 py-2 bg-primary text-white rounded-xl shadow-deep hover:bg-blue-700 transition;
  }

  .card {
    @apply p-6 bg-white shadow-lg rounded-2xl;
  }

  .input {
    @apply px-4 py-2 border border-secondary rounded-lg focus:outline-none focus:ring-2 focus:ring-primary;
  }
}
```

---

## ⚙️ **tailwind.config.js:**

```javascript
module.exports = {
  content: ["./src/**/*.{js,jsx,ts,tsx,html}"],
  theme: {
    extend: {
      colors: {
        primary: "#1E3A8A",
        secondary: "#64748B",
        accent: "#FF5733",
        background: "#F3F4F6",
      },
      animation: {
        fadeIn: "fadeIn 0.5s ease-in",
      },
      keyframes: {
        fadeIn: {
          "0%": { opacity: 0 },
          "100%": { opacity: 1 },
        },
      },
    },
  },
  plugins: [],
};
```

---

## 🚀 **Run the Project:**

1. Install Tailwind:

```bash
npm install tailwindcss
npx tailwindcss init
```

2. Add Tailwind to your `index.css`.

3. Start the app:

```bash
npm start
```

---

## 🎯 **Result:**

- **Header:** "Weather App 🌤️"
- **Input Field:** Type a city name and press **Enter**.
- **Button:** "Get Weather" (click to show mock weather).
- **Card:** Shows city name, temperature, and weather description.

👉 And all styled with Tailwind, using the utility-first approach and custom classes!

Would you like me to show how to integrate a live weather API instead of mock data? Let me know! 🌟

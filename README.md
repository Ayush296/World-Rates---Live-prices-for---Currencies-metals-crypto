World Rates 🌍
World Rates is a modern, premium, and fully responsive web application that serves as a universal financial dashboard. It allows users to track real-time global fiat currency exchange rates, live precious metal prices (Gold, Silver, Platinum), and top cryptocurrency market prices, all with interactive historical charts.

🚀 Overview & Features
1. Global Fiat Currency Converter
Instantly convert amounts between over 160+ global fiat currencies.
Generates dynamic country flags based on the ISO currency code (e.g., USD -> 🇺🇸, INR -> 🇮🇳).
Visualizes the exchange rate trend over 1 Week, 1 Month, 6 Months, 1 Year, or All-Time.
2. Precious Metals Tracker
A dedicated page (/metals) for live pricing of Gold (XAU), Silver (XAG), and Platinum (XPT).
Unit Conversion Engine: Precious metals are traded in Troy Ounces. The app mathematically converts this base rate into Grams, Kilograms, or Ounces based on user selection.
Features dynamic chart scaling, so historical data accurately plots the value of your chosen weight and unit.
3. Cryptocurrency Dashboard
A dedicated page (/crypto) tracking the Top 100 cryptocurrencies by market capitalization.
Universal Fiat Fallback System: While most crypto APIs only support ~50 major fiat currencies, World Rates uses a two-step conversion algorithm (Crypto -> USD -> Target Fiat) to guarantee that you can check Bitcoin's price in literally any fiat currency in the world.
4. Premium Design System
Glassmorphism UI: Built with custom CSS featuring frosted glass panels, smooth gradients, and glowing accents.
Light & Dark Mode: A fully integrated theme switch that dynamically alters shadows, text, gridlines, and backgrounds.
Context-Aware Animations: The background features floating symbols that dynamically change. If you are converting Fiat, you see $, €, ¥ floating. If you enter the Crypto section, they seamlessly transition to ₿, Ξ, Ɖ.
💻 Tech Stack & Architecture
Core Languages
HTML5 & Vanilla CSS3: Used for the underlying structure and all the premium styling, custom animations (rotating coins, floating symbols), and glassmorphic variables.
JavaScript (ES6+): The programming language driving all logic, API calls, and React components.
Frameworks & Libraries
React (v18): The core frontend library used for building the user interface, managing states (currencies, inputs, themes), and component architecture.
Vite: The blazing-fast build tool and development server powering the React environment.
React Router DOM: Used to transform the app into a Single Page Application (SPA), handling seamless client-side routing between the Home (/), Metals (/metals), and Crypto (/crypto) pages without refreshing the browser.
Chart.js & react-chartjs-2: The powerful data visualization libraries used to render the beautiful, responsive, and interactive line charts for historical data.
react-icons & lucide-react: Icon libraries used for the UI elements (Sun/Moon toggles, navigation arrows, social media brands, and the Bitcoin logo).
📡 APIs Used
The application achieves 100% free, real-time tracking without requiring API keys by orchestrating two powerful open-source APIs:

1. Frankfurter API (api.frankfurter.dev)
Purpose: Handles all Fiat currency and Precious Metal data.
Source: Data is published directly by the European Central Bank.
Usage in App:
GET /v2/currencies: Fetches the list of all supported fiat currencies.
GET /v2/rate/{from}/{to}: Fetches the live conversion rate between two currencies.
GET /v2/rates?base={from}&quotes={to}: Fetches historical time-series data for charting.
2. CoinGecko API (api.coingecko.com/api/v3)
Purpose: Handles Cryptocurrency data.
Usage in App:
GET /coins/markets: Fetches the current Top 100 coins (Bitcoin, Ethereum, Solana, etc.).
GET /simple/price: Fetches the live USD price of the selected cryptocurrency.
GET /coins/{id}/market_chart: Fetches the historical price array to render the crypto charts.

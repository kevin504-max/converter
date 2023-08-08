# 💵 Currency Converter App

This is a simple Currency Converter application built using Vue.js. The app allows you to convert currencies using real-time exchange rates fetched from a public API.

## 📌Prerequisites

To run this application, you'll need the following:

- Node.js (with npm)

## ⚙️ Setup

1. Clone the repository:

```bash
git clone https://github.com/your-username/currency-converter-app.git
```

2. Navigate to the project directory:

```bash
cd converter
```

3. Install the dependencies:

```bash
npm install
```

4. Run the development server:

```bash
npm run serve
```

5. Open your web browser and navigate to `http://localhost:8080` to see the app in action.

# How to Use

The Currency Converter app allows you to convert different currencies. 
The main page (`App.vue`) displays multiple `ConverterComponent` instances, each for a different currency conversion pair.

# 📖 ConverterComponent

The `ConverterComponent` is a reusable component responsible for converting currencies. 
It takes two props: `currencyA` and `currencyB`, which represent the source and target currencies, respectively.

1. Enter the amount you want to convert in the text input labeled with `currencyA`.

2. Click the "Converter" button to perform the conversion.

3. The converted amount will be displayed below the button.

# 🎲 Technologies Used

* Vue.js
* Fetch API 

# 🧠 Acknowledgements

This project was created as a learning exercise and is meant to demonstrate basic usage of Vue.js and making API calls using the Fetch API.
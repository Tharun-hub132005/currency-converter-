# Currency Converter App
# Requirements:
 * Input: amount, source currency, target currency
 * Conversion logic (use static values or dummy API)
 * Output: converted amount
 * Optional: Tkinter-based GUI with dropdowns
# Explanation and Features:
# HTML Structure:

* It's a single HTML file containing all the necessary code.

* Input field for the Amount.

* Two dropdown (<select>) elements for From Currency and To Currency. I've pre-populated these with common currencies.

* A "Convert" button.

* A div to display the Result.

* A div for errorMessage to provide user feedback.

# Tailwind CSS:

* The tailwind.config block is included directly in the <script> tag in the <head> to ensure the 'Inter' font is used globally.

* All styling is done using Tailwind CSS utility classes (e.g., bg-gray-100, flex, items-center, justify-center, rounded-xl, shadow-lg, p-8, text-indigo-600).

* Custom CSS is added for more specific styling, like border-radius values, box-shadows, and hover/active effects on the button, to give it a polished look.

* The design is responsive, adapting to different screen sizes.

# JavaScript Logic (<script> tag at the end of <body>):

* exchangeRates Object: This is a crucial part. For demonstration purposes, I've hardcoded a set of exchange rates relative to USD. In a real-world application, you would fetch these rates dynamically from a reliable currency exchange API (e.g., ExchangeRate-API, Open Exchange Rates, etc.).

* Element References: document.getElementById() is used to get references to all the interactive HTML elements.

* displayError() and clearError(): Functions to manage error messages displayed to the user.

* convertCurrency() Function (Conditional Logic):

* It first parses the amount input to a floating-point number.

* Input Validation: Checks if the amount is a valid positive number. If not, it displays an error.

* Same Currency Check: If the "From" and "To" currencies are the same, it simply displays the same amount.

# Conversion Calculation:

* It retrieves the exchange rates for the selected "From" and "To" currencies from the exchangeRates object.

* It converts the amount from the fromCurrency to the base USD (by dividing by its rate).

* Then, it converts the amountInUSD to the toCurrency (by multiplying by its rate).

* Display Result: The calculated convertedAmount is then formatted to two decimal places and displayed in the resultDiv.

# Event Listeners:

* convertButton.addEventListener('click', convertCurrency);: Triggers the convertCurrency function when the button is clicked.

* amountInput.addEventListener('keypress', ...);: Allows conversion when the "Enter" key is pressed in the amount input field.

* document.addEventListener('DOMContentLoaded', convertCurrency);: Performs an initial conversion when the page loads, using the default selected currencies and amount.

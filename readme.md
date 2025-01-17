# Shopping Basket Project

## Overview
This project is a simple shopping basket application that allows users to add items to their cart, update quantities, remove items, and view the total price. It is built using HTML, CSS, and JavaScript.

## Features
- Add items to the shopping cart.
- Update item quantities in the cart.
- Remove individual items from the cart.
- Clear the entire cart.
- View the total price of items in the cart.

## Technologies Used
- HTML
- CSS
- JavaScript


## Installation and Usage

1. Clone the repository:
    
bash
    git clone https://github.com/your-username/Shopping-Basket.git
    cd Shopping-Basket
   

2. Open `index.html` in your web browser:
    
bash
    open index.html
   

## Code Explanation

### HTML (`index.html`)
The HTML file sets up the structure of the shopping basket application, including the navigation menu, product display section, and shopping cart section.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Shopping Basket</title>
    <meta name="description" content="This is the description" />
    <link rel="stylesheet" href="css/styles.css" />
  </head>
  <body>
    <header class="main-header">
      <nav class="main-nav nav">
        <ul>
          <li><a href="#">HOME</a></li>
          <li><a href="#">STORE</a></li>
          <li><a href="#">ABOUT</a></li>
        </ul>
      </nav>
      <h1 class="band-name band-name-large">SabzLearn Shop</h1>
    </header>
    <section class="container content-section">
      <div class="shop-items"></div>
    </section>
    <section class="container content-section">
      <h2 class="section-header">CART</h2>
      <div class="cart-row">
        <span class="cart-item cart-header cart-column">ITEM</span>
        <span class="cart-price cart-header cart-column">PRICE</span>
        <span class="cart-quantity cart-header cart-column">QUANTITY</span>
      </div>
      <div class="cart-items"></div>
      <div class="cart-total">
        <strong class="cart-total-title">Total</strong>
        <span class="cart-total-price">$0</span>
      </div>
      <button class="btn btn-primary btn-purchase" id="remove-all-products" type="button">
        PURCHASE
      </button>
    </section>
    <footer class="main-footer">
      <div class="container main-footer-container">
        <h3 class="band-name">The Generics</h3>
        <ul class="nav footer-nav">
          <li>
            <a href="https://www.youtube.com" target="_blank">
              <img src="Images/YouTube Logo.png" />
            </a>
          </li>
          <li>
            <a href="https://www.spotify.com" target="_blank">
              <img src="Images/Spotify Logo.png" />
            </a>
          </li>
          <li>
            <a href="https://www.facebook.com" target="_blank">
              <img src="Images/Facebook Logo.png" />
            </a>
          </li>
        </ul>
      </div>
    </footer>
    <script src="js/store.js"></script>
  </body>
</html>
```
### CSS (`css/styles.css`)
The CSS file provides styling for the shopping basket application, including layout adjustments, font styles, and button appearances.

```css
/* General styles */
@import url('https://fonts.googleapis.com/css?family=Raleway:300,400,700');
@import url("https://fonts.googleapis.com/css?family=Metal+Mania");

@font-face {
    font-family: "Booter - Zero Zero";
    src: url("../Fonts/Booter - Zero Zero.woff") format("woff"),
         url("../Fonts/Booter - Zero Zero.woff2") format("woff2");
    font-weight: normal;
    font-style: normal;
}

* {
    box-sizing: border-box;
    font-family: Raleway;
    color: #777;
}

html, body {
    margin: 0;
    padding: 0;
    min-height: 100%;
}

.nav ul {
    margin: 0;
}

.nav li {
    display: inline;
}

.nav a {
    display: inline-block;
    padding: .5em;
    color: white;
    text-decoration: none;
}
.main-nav {
    text-align: center;
    font-size: 1.1em;
    font-weight: lighter;
    border-bottom: 1px solid rgba(255, 255, 255, .3)
}

.main-nav li {
    padding: 0 5%;
}

.nav a:hover {
    background-color: rgba(255, 255, 255, .3)
}

.main-header {
    background-color: rgba(0, 0, 0, .6);
    background-image: url("../Images/Header Background.jpg");
    background-blend-mode: multiply;
    background-size: cover;
    padding-bottom: 30px;
}

.band-name {
    text-align: center;
    margin: 0;
    font-size: 4em;
    font-family: "Booter - Zero Zero";
    font-weight: normal;
    color: white;
}

.band-name-large {
    font-size: 8em;
}

.content-section {
    margin: 1em;
}

.container {
    max-width: 900px;
    margin: 0 auto;
    padding: 0 1.5em;
}
.section-header {
    font-family: "Metal Mania";
    font-weight: normal;
    color: #333;
    text-align: center;
    font-size: 2.5em;
}

.main-footer {
    background-color: #56CCF2;
    color: white;
    padding: .25em 0;
}

.main-footer-container {
    display: flex;
    align-items: center;
}

.main-footer-container ul {
    flex-grow: 1;
    text-align: end;
}

.footer-nav li {
    padding: 0 .5em;
}

.footer-nav img {
    width: 30px;
    height: 30px;
}

/* Button styles */
.btn {
    text-align: center;
    vertical-align: middle;
    padding: .67em .67em;
    cursor: pointer;
}

.btn-primary {
    color: white;
    background-color: #56CCF2;
    border: none;
    border-radius: .3em;
    font-weight: bold;
}

.btn-primary:hover {
    background-color: #2D9CDB;
}

.btn-danger {
    color: white;
    background-color: #EB5757;
    border: none;
    border-radius: .3em;
    font-weight: bold;
}

.btn-danger:hover {
    background-color: #CC4C4C;
}

.btn-purchase {
    display: block;
    margin: 40px auto 80px auto;
    font-size: 1.75em;
}

/* Shop item styles */
.shop-item {
    margin: 30px;
}

.shop-item-title {
    display: block;
    width: 100%;
    text-align: center;
    font-weight: bold;
    font-size: 1.5em;
    color: #333;
    margin-bottom: 15px;
}

.shop-item-image {
    height: 250px;
}

.shop-item-details {
    display: flex;
    align-items: center;
    padding: 5px;
}

.shop-item-price {
    flex-grow: 1;
    color: #333;
}

.shop-items {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
}

/* Cart styles */
.cart-header {
    font-weight: bold;
    font-size: 1.25em;
    color: #333;
}

.cart-column {
    display: flex;
    align-items: center;
    border-bottom: 1px solid black;
    margin-right: 1.5em;
    padding-bottom: 10px;
    margin-top: 10px;
}

.cart-row {
    display: flex;
}

.cart-item {
    width: 45%;
}
.cart-price {
    width: 20%;
    font-size: 1.2em;
    color: #333;
}

.cart-quantity {
    width: 35%;
}

.cart-item-title {
    color: #333;
    margin-left: .5em;
    font-size: 1.2em;
}

.cart-item-image {
    width: 75px;
    height: auto;
    border-radius: 10px;
}

.cart-quantity-input {
    height: 34px;
    width: 50px;
    border-radius: 5px;
    border: 1px solid #56CCF2;
    background-color: #eee;
    color: #333;
    padding: 0;
    text-align: center;
    font-size: 1.2em;
    margin-right: 25px;
}

.cart-total {
    text-align: end;
    margin-top: 10px;
    margin-right: 10px;
}

.cart-total-title {
    font-weight
```

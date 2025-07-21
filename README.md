<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>ElectroShop Kenya</title>
  <link rel="stylesheet" href="style.css"/>
</head>
<body>
  <header>
    <h1>ElectroShop Kenya</h1>
    <nav>
      <a href="index.html">Home</a>
      <a href="cart.html">Cart</a>
    </nav>
  </header>

  <main>
    <h2>Featured Products</h2>
    <div class="products">
      <div class="product">
        <img src="images/phone.jpg" alt="Smartphone"/>
        <h3>Samsung Galaxy A14</h3>
        <p>Ksh 18,000</p>
        <button onclick="addToCart('Samsung Galaxy A14', 18000)">Add to Cart</button>
      </div>

      <div class="product">
        <img src="images/laptop.jpg" alt="Laptop"/>
        <h3>HP Laptop 14"</h3>
        <p>Ksh 45,000</p>
        <button onclick="addToCart('HP Laptop 14\"', 45000)">Add to Cart</button>
      </div>
    </div>
  </main>

  <footer>
    <p>&copy; 2025 ElectroShop Kenya</p>
  </footer>

  <script src="script.js"></script>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Your Cart - ElectroShop Kenya</title>
  <link rel="stylesheet" href="style.css"/>
</head>
<body>
  <header>
    <h1>Your Shopping Cart</h1>
    <nav>
      <a href="index.html">Home</a>
      <a href="checkout.html">Checkout</a>
    </nav>
  </header>

  <main>
    <h2>Items in Cart</h2>
    <div id="cart-items"></div>
    <h3 id="total">Total: Ksh 0</h3>
    <a href="checkout.html"><button>Proceed to Checkout</button></a>
  </main>

  <footer>
    <p>&copy; 2025 ElectroShop Kenya</p>
  </footer>

  <script>
    const cartItems = JSON.parse(localStorage.getItem("cart")) || [];
    const cartDiv = document.getElementById("cart-items");
    const totalDiv = document.getElementById("total");
    let total = 0;

    if (cartItems.length === 0) {
      cartDiv.innerHTML = "<p>Your cart is empty.</p>";
    } else {
      cartItems.forEach(item => {
        const itemDiv = document.createElement("div");
        itemDiv.classList.add("cart-item");
        itemDiv.innerHTML = `
          <p><strong>${item.name}</strong> - Ksh ${item.price}</p>
        `;
        cartDiv.appendChild(itemDiv);
        total += item.price;
      });

      totalDiv.textContent = `Total: Ksh ${total}`;
    }
  </script>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Checkout - ElectroShop Kenya</title>
  <link rel="stylesheet" href="style.css"/>
</head>
<body>
  <header>
    <h1>Checkout</h1>
    <nav>
      <a href="index.html">Home</a>
      <a href="cart.html">Cart</a>
    </nav>
  </header>

  <main>
    <h2>Customer Information</h2>
    <form id="checkout-form">
      <label for="name">Full Name:</label><br>
      <input type="text" id="name" name="name" required><br><br>

      <label for="phone">M-Pesa Phone Number:</label><br>
      <input type="tel" id="phone" name="phone" pattern="^07\d{8}$" placeholder="e.g. 0712345678" required><br><br>

      <label for="address">Delivery Address:</label><br>
      <textarea id="address" name="address" required></textarea><br><br>

      <h3 id="total">Total: Ksh 0</h3>

      <button type="submit">Pay with M-Pesa</button>
    </form>

    <div id="confirmation" style="margin-top: 20px; color: green;"></div>
  </main>

  <footer>
    <p>&copy; 2025 ElectroShop Kenya</p>
  </footer>

  <script>
    // Load total from cart
    const cartItems = JSON.parse(localStorage.getItem("cart")) || [];
    const total = cartItems.reduce((sum, item) => sum + item.price, 0);
    document.getElementById("total").textContent = `Total: Ksh ${total}`;

    // Handle form submission
    const form = document.getElementById("checkout-form");
    const confirmation = document.getElementById("confirmation");

    form.addEventListener("submit", function(e) {
      e.preventDefault();

      // Normally, here you'd send the payment request to a backend API
      const name = document.getElementById("name").value;
      const phone = document.getElementById("phone").value;
      const address = document.getElementById("address").value;

      confirmation.innerHTML = `Thank you <strong>${name}</strong>!<br>
        A payment request has been sent to <strong>${phone}</strong>.<br>
        Your items will be delivered to <strong>${address}</strong>.`;

      // Clear cart
      localStorage.removeItem("cart");
    });
  </script>
</body>
</html>
function addToCart(productName, productPrice) {
  // Get existing cart or initialize empty array
  let cart = JSON.parse(localStorage.getItem("cart")) || [];

  // Add new product to cart
  cart.push({ name: productName, price: productPrice });

  // Save back to localStorage
  localStorage.setItem("cart", JSON.stringify(cart));

  // Give user feedback
  alert(`${productName} has been added to your cart.`);
}

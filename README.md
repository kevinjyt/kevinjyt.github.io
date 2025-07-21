<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>ElectroShop Kenya</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <header>
    <h1>ElectroShop Kenya</h1>
    <nav>
      <a href="index.html">Home</a>
      <a href="products.html">Products</a>
      <a href="cart.html">Cart</a>
    </nav>
  </header>

  <main>
    <section class="hero">
      <h2>Welcome to the Best Electronics Shop in Kenya!</h2>
      <p>Shop phones, laptops, TVs, and more at affordable prices.</p>
      <a href="products.html" class="btn">Shop Now</a>
    </section>
  </main>

  <footer>
    <p>&copy; 2025 ElectroShop Kenya</p>
  </footer>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Products - ElectroShop</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <header>
    <h1>Our Products</h1>
    <nav>
      <a href="index.html">Home</a>
      <a href="cart.html">Cart</a>
    </nav>
  </header>

  <main>
    <section class="products">
      <div class="product-card">
        <img src="phone.jpg" alt="Smartphone" />
        <h3>Samsung Galaxy A14</h3>
        <p>Ksh 21,000</p>
        <a href="product.html" class="btn">View</a>
      </div>
      <!-- Add more products similarly -->
    </section>
  </main>

  <footer>
    <p>&copy; 2025 ElectroShop Kenya</p>
  </footer>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Product Details</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <header>
    <h1>Samsung Galaxy A14</h1>
    <nav>
      <a href="index.html">Home</a>
      <a href="cart.html">Cart</a>
    </nav>
  </header>

  <main>
    <div class="product-detail">
      <img src="phone.jpg" alt="Phone" />
      <div>
        <h2>Ksh 21,000</h2>
        <p>Awesome performance with long battery life.</p>
        <button>Add to Cart</button>
      </div>
    </div>
  </main>

  <footer>
    <p>&copy; 2025 ElectroShop Kenya</p>
  </footer>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
}
header, footer {
  background: #222;
  color: white;
  text-align: center;
  padding: 1rem;
}
nav a {
  color: white;
  margin: 0 10px;
  text-decoration: none;
}
.hero {
  text-align: center;
  padding: 2rem;
  background-color: #f4f4f4;
}
.btn {
  display: inline-block;
  background: green;
  color: white;
  padding: 10px 20px;
  text-decoration: none;
}
.products {
  display: flex;
  gap: 1rem;
  padding: 1rem;
  flex-wrap: wrap;
  justify-content: center;
}
.product-card {
  border: 1px solid #ccc;
  padding: 1rem;
  width: 200px;
  text-align: center;
}
.product-card img {
  max-width: 100%;
}

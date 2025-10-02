<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>EcoBin - Smart Waste Management</title>
  <style>
    body { font-family: 'Segoe UI', Arial, sans-serif; margin:0; padding:0; scroll-behavior: smooth; color:#333; }
    header {
      background: url('https://images.unsplash.com/photo-1581578017425-16c57c8c3a3a?ixlib=rb-4.0.3&auto=format&fit=crop&w=1350&q=80') no-repeat center center/cover;
      color:white; text-align:center; padding:120px 20px;
    }
    header h1 { font-size: 3rem; margin-bottom: 10px; text-shadow: 2px 2px 5px rgba(0,0,0,0.6);}
    header p { font-size: 1.3rem; max-width: 700px; margin:auto; text-shadow: 1px 1px 4px rgba(0,0,0,0.7);}
    nav { background:#228B22; padding:12px; text-align:center; position:sticky; top:0; z-index:100; }
    nav a { color:white; margin:0 15px; text-decoration:none; font-weight:bold; }
    nav a:hover { text-decoration:underline; }
    section { padding:60px 20px; text-align:center; }
    section h2 { color:#228B22; font-size:2rem; margin-bottom:20px; }
    .features { display:flex; justify-content:space-around; flex-wrap:wrap; margin-top:30px; }
    .feature { width:250px; padding:20px; border-radius:12px; background:#f0fff0; margin:10px; box-shadow:0 2px 6px rgba(0,0,0,0.1);}
    .feature img { width:60px; margin-bottom:15px; }
    #guide input { padding:10px; width:60%; margin-right:10px; border:1px solid #ccc; border-radius:6px;}
    #guide button { padding:10px 20px; background:#228B22; color:white; border:none; border-radius:6px; cursor:pointer; }
    #guide button:hover { background:#2e8b57; }
    #result { margin-top:20px; font-size:18px; font-weight:bold; }
    iframe { border-radius:10px; }
    footer { background:#2e8b57; color:white; text-align:center; padding:20px; margin-top:30px; }
  </style>
</head>
<body>
  <!-- Hero Section -->
  <header id="home">
    <h1>🌍 EcoBin</h1>
    <p>Smart Waste Management for a Cleaner, Greener Future</p>
  </header>

  <!-- Navigation -->
  <nav>
    <a href="#home">Home</a>
    <a href="#features">Features</a>
    <a href="#guide">Waste Guide</a>
    <a href="#map">Recycler Locator</a>
  </nav>

  <!-- Features Section -->
  <section id="features">
    <h2>Why Choose EcoBin?</h2>
    <div class="features">
      <div class="feature">
        <img src="https://cdn-icons-png.flaticon.com/512/3094/3094825.png" alt="Waste Guide">
        <h3>Waste Guide</h3>
        <p>Know where your waste belongs instantly using our smart search tool.</p>
      </div>
      <div class="feature">
        <img src="https://cdn-icons-png.flaticon.com/512/684/684908.png" alt="Map">
        <h3>Recycler Locator</h3>
        <p>Find nearby recycling centers to dispose of dry and e-waste responsibly.</p>
      </div>
      <div class="feature">
        <img src="https://cdn-icons-png.flaticon.com/512/1048/1048953.png" alt="Awareness">
        <h3>Eco Awareness</h3>
        <p>Learn easy tips & tricks to reduce waste and save the environment.</p>
      </div>
    </div>
  </section>

  <!-- Waste Guide Section -->
  <section id="guide" style="background:#f0fff0;">
    <h2>♻️ Check Your Waste Category</h2>
    <p>Type an item below to see if it’s Wet, Dry, or E-Waste.</p>
    <input type="text" id="wasteInput" placeholder="Enter waste item (e.g., banana peel)">
    <button onclick="checkWaste()">Check</button>
    <div id="result"></div>
  </section>

  <!-- Recycler Locator Section -->
  <section id="map">
    <h2>🗺️ Find Recycling Centers Near You</h2>
    <p>Locate nearby recycling bins and drop-off centers.</p>
    <iframe 
      src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d387144.00758324966!2d-74.258195745038!3d40.70583164041711!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zMzgnMjcuMiJOIDc0wrAwMy4wIlc!5e0!3m2!1sen!2sin!4v1632730190939!5m2!1sen!2sin" 
      width="100%" height="400" allowfullscreen="" loading="lazy">
    </iframe>
  </section>

  <!-- Footer -->
  <footer>
    <p>EcoBin Project © 2025 | Built for Environmental Studies 🌱</p>
  </footer>

  <script>
    function checkWaste() {
      let item = document.getElementById("wasteInput").value.toLowerCase();
      let result = document.getElementById("result");

      if (item.includes("banana") || item.includes("apple") || item.includes("food") || item.includes("vegetable")) {
        result.innerHTML = "🍌 This is <b>WET WASTE</b> – Put it in compost bin.";
      } else if (item.includes("plastic") || item.includes("bottle") || item.includes("paper") || item.includes("glass")) {
        result.innerHTML = "📦 This is <b>DRY WASTE</b> – Send for recycling.";
      } else if (item.includes("battery") || item.includes("bulb") || item.includes("charger") || item.includes("phone")) {
        result.innerHTML = "⚡ This is <b>E-WASTE</b> – Dispose safely at recycling center.";
      } else {
        result.innerHTML = "♻️ Please check guidelines – item not in database.";
      }
    }
  </script>
</body>
</html>

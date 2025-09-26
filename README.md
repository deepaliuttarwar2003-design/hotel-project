<!doctype html>
<html lang="en">

<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Ramayana — Full Menu</title>
  <style>
    :root {
      --accent: #b22222;
      --muted: #666;
      --card: #fff
    }

    body {
      font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial;
      margin: 0;
      background: #f4f4f5;
      color: #222
    }

    header {
      background: linear-gradient(90deg, #fff, #fff5f5);
      padding: 12px 18px;
      border-bottom: 1px solid #eee;
      display: flex;
      align-items: center;
      justify-content: space-between
    }

    header h1 {
      margin: 0;
      color: var(--accent);
      font-size: 20px
    }

    .top-controls {
      display: flex;
      gap: 8px;
      align-items: center
    }

    .btn {
      background: var(--accent);
      color: #fff;
      border: 0;
      padding: 8px 10px;
      border-radius: 6px;
      cursor: pointer
    }

    .btn.alt {
      background: #fff;
      color: var(--accent);
      border: 1px solid #f0a0a0
    }

    main {
      max-width: 1200px;
      margin: 18px auto;
      padding: 12px;
      display: grid;
      grid-template-columns: 1fr 360px;
      gap: 16px
    }

    .left {
      display: flex;
      flex-direction: column;
      gap: 12px
    }

    .filters {
      display: flex;
      gap: 8px;
      flex-wrap: wrap
    }

    .chip {
      padding: 6px 10px;
      border-radius: 999px;
      background: #fff;
      border: 1px solid #eee;
      cursor: pointer
    }

    .grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 12px
    }

    .card {
      background: var(--card);
      border-radius: 10px;
      padding: 10px;
      border: 1px solid #eee;
      display: flex;
      gap: 10px;
      align-items: flex-start
    }

    .thumb {
      width: 140px;
      height: 95px;
      border-radius: 8px;
      object-fit: cover;
      background: #eee
    }

    .meta {
      flex: 1
    }

    .title {
      font-weight: 700;
      margin: 0
    }

    .tags {
      font-size: 12px;
      color: var(--muted);
      margin: 6px 0
    }

    .price {
      color: var(--accent);
      font-weight: 800
    }

    .controls-row {
      display: flex;
      gap: 8px;
      align-items: center;
      margin-top: 8px
    }

    .qty {
      display: inline-flex;
      align-items: center;
      border: 1px solid #ddd;
      padding: 4px;
      border-radius: 6px
    }

    .qty button {
      background: #fafafa;
      border: 0;
      padding: 6px 8px;
      cursor: pointer
    }

    .note {
      padding: 6px;
      border-radius: 6px;
      border: 1px solid #ddd
    }

    aside {
      position: sticky;
      top: 18px
    }

    .cart {
      background: #fff;
      border-radius: 10px;
      padding: 12px;
      border: 1px solid #eee
    }

    .cart h3 {
      margin: 0 0 8px 0
    }

    .cart-list {
      max-height: 360px;
      overflow: auto
    }

    .cart-item {
      display: flex;
      justify-content: space-between;
      padding: 8px 0;
      border-bottom: 1px dashed #f2f2f2
    }

    .total {
      display: flex;
      justify-content: space-between;
      font-weight: 800;
      margin-top: 10px
    }

    .small {
      font-size: 13px;
      color: var(--muted)
    }

    .admin-panel {
      background: #fff;
      padding: 10px;
      border-radius: 8px;
      border: 1px solid #eee;
      margin-top: 12px
    }

    .category-title {
      margin: 6px 0 0 0;
      font-weight: 700
    }

    .search {
      padding: 8px;
      border-radius: 8px;
      border: 1px solid #ddd;
      width: 100%
    }

    .review-box {
      display: flex;
      gap: 8px;
      align-items: center;
      margin-top: 8px
    }

    .order-confirm {
      background: #e8f8f1;
      padding: 10px;
      border-radius: 8px;
      border: 1px solid #c8f0dd;
      margin-top: 10px
    }

    .small-link {
      font-size: 13px;
      color: var(--accent);
      cursor: pointer;
      text-decoration: underline;
      background: none;
      border: 0
    }

    .muted-note {
      font-size: 12px;
      color: #888;
      margin-top: 6px
    }

    footer {
      padding: 12px;
      text-align: center;
      color: #777;
      font-size: 13px;
      margin-top: 18px
    }

    /* responsive */
    @media (max-width:900px) {
      main {
        grid-template-columns: 1fr
      }

      .grid {
        grid-template-columns: 1fr
      }

      aside {
        position: static
      }
    }
  </style>
</head>

<body>
  <header>
    <h1>Ramayana — Full Dine-in Menu (Pure Veg)</h1>
    <div class="top-controls">
      <div class="small">Table: <strong id="tableNumber">—</strong></div>
      <button id="scanBtn" class="btn alt">Scan QR (simulate)</button>
      <button id="adminBtn" class="btn">Admin</button>
    </div>
  </header>

  <main>
    <div class="left">
      <div style="display:flex;gap:10px;align-items:center">
        <input id="search" class="search" placeholder="Search dishes or ingredient..." />
        <select id="categoryFilter" class="note">
          <option value="all">All Categories</option>
        </select>
      </div>

      <div class="filters" id="filtersRow">
        <!-- tags inserted here -->
      </div>

      <div id="menuArea" class="grid">
        <!-- menu items render here -->
      </div>

      <div class="admin-panel" id="adminPanel" style="display:none">
        <h3 style="margin-top:0">Admin Panel</h3>
        <div id="adminLoginArea">
          <input id="adminPass" placeholder="Enter admin password" class="note" />
          <button id="adminLoginBtn" class="btn">Login</button>
        </div>
        <div id="adminControls" style="display:none">
          <div style="display:flex;gap:8px;margin-top:8px">
            <button id="addItemBtn" class="btn alt">Add New Item</button>
            <button id="exportBtn" class="btn alt">Export Menu (console)</button>
            <button id="resetDataBtn" class="btn alt">Reset to Default</button>
          </div>
          <div id="adminMessage" class="muted-note"></div>
        </div>
      </div>

      <div style="background:#fff;padding:10px;border-radius:8px;border:1px solid #eee">
        <h3 style="margin:0">Reviews</h3>
        <div id="reviewsArea" style="min-height:80px;margin-top:8px"></div>
        <div style="margin-top:8px">
          <input id="reviewerName" placeholder="Your name"
            style="width:100%;padding:8px;border-radius:6px;border:1px solid #ddd;margin-bottom:6px" />
          <div class="review-box">
            <select id="rating" class="note" style="width:90px;padding:6px">
              <option value="5">5 ★</option>
              <option value="4">4 ★</option>
              <option value="3">3 ★</option>
              <option value="2">2 ★</option>
              <option value="1">1 ★</option>
            </select>
            <input id="reviewText" placeholder="Write a short review"
              style="flex:1;padding:8px;border-radius:6px;border:1px solid #ddd" />
            <button id="submitReview" class="btn">Submit</button>
          </div>
        </div>
      </div>

    </div>

    <aside>
      <div class="cart">
        <h3>Your Cart</h3>
        <div class="cart-list" id="cartList"></div>
        <div class="total">
          <div>Total</div>
          <div id="cartTotal">₹0</div>
        </div>

        <div style="margin-top:10px">
          <label class="small">Order note for kitchen</label>
          <textarea id="globalNote" class="note" placeholder="e.g., less oil, mild spice"
            style="width:100%;height:56px"></textarea>
        </div>

        <div style="display:flex;gap:8px;margin-top:10px">
          <button id="payBtn" class="btn">Pay (simulate)</button>
          <button id="placeOrderBtn" class="btn alt">Place Order</button>
        </div>

        <div style="margin-top:8px">
          <label class="small">Payment status</label>
          <div id="paymentStatus" class="muted-note">Not paid</div>
        </div>

        <div id="orderMessage"></div>
        <div style="margin-top:8px;display:flex;gap:8px">
          <button id="clearCartBtn" class="btn alt">Clear</button>
          <button id="downloadReceipt" class="btn alt">Download Receipt</button>
        </div>
        <div class="muted-note" style="margin-top:8px">Note: This is frontend-only demo. To make it real connect backend
          APIs.</div>
      </div>
    </aside>
  </main>

  <footer>Ramayana — Thank you for dining with us.</footer>

  <script>
    /* ------------------ DEFAULT MENU DATA (many items, all veg) ------------------ */
    const DEFAULT_MENU = [
      /* Sabji (8) */
      { id: 's1', cat: 'Sabji', name: 'Paneer Butter Masala', price: 220, cal: 420, gluten: false, vegan: false, allergens: ['Dairy'], prep: 12, photo: './assets/paneer_tikka_masala.jpeg' },
      { id: 's2', cat: 'Sabji', name: 'Mixed Vegetable Kurma', price: 200, cal: 360, gluten: false, vegan: true, allergens: [], prep: 10, photo: './assets/rajma_masala.jpeg' },
      { id: 's3', cat: 'Sabji', name: 'Aloo Gobhi', price: 150, cal: 310, gluten: false, vegan: true, allergens: [], prep: 8, photo: './assets/mixed_veg_kurma.jpeg' },
      { id: 's4', cat: 'Sabji', name: 'Methi Malai Paneer', price: 240, cal: 430, gluten: false, vegan: false, allergens: ['Dairy'], prep: 14, photo: './assets/methi_malai_paneer.jpeg' },
      { id: 's5', cat: 'Sabji', name: 'Bhindi Masala', price: 160, cal: 200, gluten: false, vegan: true, allergens: [], prep: 9, photo: './assets/Bhindi_Masala.jpeg' },
      { id: 's6', cat: 'Sabji', name: 'Navratan Korma', price: 230, cal: 400, gluten: false, vegan: false, allergens: ['Dairy', 'Nuts (maybe)'], prep: 15, photo: './assets/navratn_korma.jpeg' },
      { id: 's7', cat: 'Sabji', name: 'Chana Masala', price: 170, cal: 340, gluten: false, vegan: true, allergens: [], prep: 11, photo: './assets/chana_masala.jpeg' },
      { id: 's8', cat: 'Sabji', name: 'Paneer Tikka Masala', price: 250, cal: 450, gluten: false, vegan: false, allergens: ['Dairy'], prep: 16, photo: './assets/paneer_tikka_masala.jpeg' },

      /* Sweets (8) */
      { id: 'sw1', cat: 'Sweets', name: 'Gulab Jamun (2 pcs)', price: 90, cal: 260, gluten: false, vegan: false, allergens: ['Dairy'], prep: 6, photo: './assets/gulap_jamun.jpeg' },
      { id: 'sw2', cat: 'Sweets', name: 'Rasgulla (2 pcs)', price: 95, cal: 240, gluten: false, vegan: false, allergens: ['Dairy'], prep: 5, photo: './assets/rasgulla.jpeg' },
      { id: 'sw3', cat: 'Sweets', name: 'Kaju Katli (2 pcs)', price: 140, cal: 300, gluten: false, vegan: false, allergens: ['Nuts'], prep: 7, photo: './assets/kaju_katli.jpeg' },
      { id: 'sw4', cat: 'Sweets', name: 'Ras Malai (2 pcs)', price: 120, cal: 280, gluten: false, vegan: false, allergens: ['Dairy'], prep: 7, photo: './assets/rasmalai.jpeg' },
      { id: 'sw5', cat: 'Sweets', name: 'Jalebi (2 pcs)', price: 80, cal: 320, gluten: true, vegan: false, allergens: [], prep: 6, photo: './assets/jalebi.jpeg' },
      { id: 'sw6', cat: 'Sweets', name: 'Moong Dal Halwa', price: 130, cal: 360, gluten: false, vegan: false, allergens: ['Dairy'], prep: 15, photo: './assets/moong_daal_halawa.jpeg' },
      { id: 'sw7', cat: 'Sweets', name: 'Shrikhand', price: 110, cal: 220, gluten: false, vegan: false, allergens: ['Dairy'], prep: 5, photo: './assets/shrikhand.jpeg' },
      { id: 'sw8', cat: 'Sweets', name: 'Besan Ladoo (2 pcs)', price: 95, cal: 300, gluten: false, vegan: false, allergens: [], prep: 8, photo: './assets/besan_ladoo.jpeg' },

      /* Breads (8) */
      { id: 'b1', cat: 'Breads', name: 'Butter Naan', price: 40, cal: 200, gluten: true, vegan: false, allergens: ['Gluten', 'Dairy'], prep: 6, photo: './assets/tandoori_roti.jpeg' },
      { id: 'b2', cat: 'Breads', name: 'Tandoori Roti', price: 20, cal: 140, gluten: true, vegan: true, allergens: ['Gluten'], prep: 4, photo: './assets/tandoori_roti.jpeg' },
      { id: 'b3', cat: 'Breads', name: 'Garlic Naan', price: 55, cal: 230, gluten: true, vegan: false, allergens: ['Gluten', 'Dairy'], prep: 6, photo: './assets/Garlic_Naan.jpeg' },
      { id: 'b4', cat: 'Breads', name: 'Lachha Paratha', price: 35, cal: 260, gluten: true, vegan: false, allergens: ['Gluten'], prep: 7, photo: './assets/laccha_paratha.jpeg' },
      { id: 'b5', cat: 'Breads', name: 'Roomali Roti', price: 30, cal: 180, gluten: true, vegan: true, allergens: ['Gluten'], prep: 5, photo: './assets/rooamali.jpeg' },
      { id: 'b6', cat: 'Breads', name: 'Missi Roti', price: 45, cal: 210, gluten: true, vegan: false, allergens: ['Gluten'], prep: 6, photo: './assets/Missi_Roti.jpeg' },
      { id: 'b7', cat: 'Breads', name: 'Cheese Kulcha', price: 80, cal: 340, gluten: true, vegan: false, allergens: ['Gluten', 'Dairy'], prep: 8, photo: './assets/Cheese_Kulcha.jpeg' },
      { id: 'b8', cat: 'Breads', name: 'Naan Basket (3 pcs)', price: 110, cal: 600, gluten: true, vegan: false, allergens: ['Gluten', 'Dairy'], prep: 9, photo: './assets/Naan_basket.jpeg' },

      /* Starters (8) */
      { id: 'st1', cat: 'Starters', name: 'Paneer Tikka', price: 220, cal: 320, gluten: false, vegan: false, allergens: ['Dairy'], prep: 12, photo: './assets/paneer_tikka.jpeg'},
      { id: 'st2', cat: 'Starters', name: 'Hara Bhara Kebab', price: 180, cal: 260, gluten: false, vegan: true, allergens: [], prep: 10, photo: './assets/hara_bhara_kabab.jpeg' },
      { id: 'st3', cat: 'Starters', name: 'Veg Spring Rolls', price: 150, cal: 200, gluten: true, vegan: true, allergens: ['Gluten'], prep: 8, photo: './assets/Spring_Roll.jpeg' },
      { id: 'st4', cat: 'Starters', name: 'Crispy Corn', price: 140, cal: 220, gluten: false, vegan: true, allergens: [], prep: 7, photo: './assets/crispy_corn.jpeg' },
      { id: 'st5', cat: 'Starters', name: 'Cheese Balls', price: 160, cal: 300, gluten: true, vegan: false, allergens: ['Dairy', 'Gluten'], prep: 9, photo: './assets/cheese_balls.jpeg' },
      { id: 'st6', cat: 'Starters', name: 'Paneer 65', price: 210, cal: 340, gluten: true, vegan: false, allergens: ['Dairy'], prep: 11, photo: './assets/paneer_65.jpeg' },
      { id: 'st7', cat: 'Starters', name: 'Vegetable Manchurian (Dry)', price: 190, cal: 320, gluten: true, vegan: true, allergens: ['Gluten'], prep: 12, photo: './assets/veg_manchurian.jpeg' },
      { id: 'st8', cat: 'Starters', name: 'Samosa (2 pcs)', price: 80, cal: 260, gluten: true, vegan: true, allergens: ['Gluten'], prep: 6, photo: './assets/samosa.jpeg' },

      /* Drinks (8) */
      { id: 'd1', cat: 'Drinks', name: 'Masala Chai', price: 40, cal: 120, gluten: false, vegan: false, allergens: ['Dairy'], prep: 3, photo:'./assets/masala_chai.jpeg' },
      { id: 'd2', cat: 'Drinks', name: 'Lassi (Sweet)', price: 70, cal: 220, gluten: false, vegan: false, allergens: ['Dairy'], prep: 3, photo: './assets/lassi.jpeg'},
      { id: 'd3', cat: 'Drinks', name: 'Fresh Lime Soda', price: 50, cal: 60, gluten: false, vegan: true, allergens: [], prep: 2, photo: './assets/lime_soda.jpeg' },
      { id: 'd4', cat: 'Drinks', name: 'Mint Mojito (No Alcohol)', price: 90, cal: 80, gluten: false, vegan: true, allergens: [], prep: 3, photo: './assets/mint_mojito.jpeg' },
      { id: 'd5', cat: 'Drinks', name: 'Mango Shake', price: 120, cal: 250, gluten: false, vegan: false, allergens: ['Dairy'], prep: 4, photo: './assets/mango_shake.jpeg' },
      { id: 'd6', cat: 'Drinks', name: 'Cold Coffee', price: 110, cal: 220, gluten: false, vegan: false, allergens: ['Dairy'], prep: 4, photo: './assets/cold_coffee.jpeg' },
      { id: 'd7', cat: 'Drinks', name: 'Buttermilk', price: 45, cal: 80, gluten: false, vegan: false, allergens: ['Dairy'], prep: 2, photo: './assets/masala_chaas.jpeg' },
      { id: 'd8', cat: 'Drinks', name: 'Filter Coffee', price: 50, cal: 110, gluten: false, vegan: false, allergens: ['Dairy'], prep: 3, photo: './assets/filter_coffee.jpeg' },

      /* Chinese (8) */
      { id: 'c1', cat: 'Chinese', name: 'Veg Fried Rice', price: 160, cal: 420, gluten: true, vegan: true, allergens: ['Soy'], prep: 10, photo: './assets/veg_fried_rice.jpeg' },
      { id: 'c2', cat: 'Chinese', name: 'Veg Hakka Noodles', price: 150, cal: 400, gluten: true, vegan: true, allergens: ['Gluten', 'Soy'], prep: 10, photo: './assets/hakka_noodle.jpeg' },
      { id: 'c3', cat: 'Chinese', name: 'Chili Paneer (Dry)', price: 220, cal: 360, gluten: true, vegan: false, allergens: ['Dairy', 'Soy'], prep: 12, photo: './assets/chilli_paneer.jpeg' },
      { id: 'c4', cat: 'Chinese', name: 'Veg Manchow Soup', price: 120, cal: 90, gluten: false, vegan: true, allergens: [], prep: 6, photo: './assets/veg_manchaow_soup.jpeg' },
      { id: 'c5', cat: 'Chinese', name: 'Paneer Schezwan', price: 240, cal: 420, gluten: true, vegan: false, allergens: ['Dairy', 'Soy'], prep: 13, photo: './assets/paneer_sheswan.jpeg' },
      { id: 'c6', cat: 'Chinese', name: 'Veg Spring Rolls', price: 150, cal: 200, gluten: true, vegan: true, allergens: ['Gluten'], prep: 8, photo: './assets/spring_roll.jpeg' },
      { id: 'c7', cat: 'Chinese', name: 'Schezwan Fried Rice', price: 170, cal: 430, gluten: true, vegan: true, allergens: ['Soy'], prep: 10, photo: './assets/shejwan_fried_rice.jpeg' },
      { id: 'c8', cat: 'Chinese', name: 'Veg Manchurian Gravy', price: 200, cal: 380, gluten: true, vegan: true, allergens: ['Gluten'], prep: 12, photo: './assets/manchurian_gravy.jpeg' },

      /* Asian (8) */
      { id: 'a1', cat: 'Asian', name: 'Thai Veg Curry', price: 260, cal: 350, gluten: false, vegan: true, allergens: ['Coconut'], prep: 14, photo: './assets/thai_curry.jpeg' },
      { id: 'a2', cat: 'Asian', name: 'Vegetable Sukiyaki (Japanese-style)', price: 270, cal: 330, gluten: true, vegan: true, allergens: ['Soy'], prep: 16, photo: './assets/vegetable_sukiyaki.jpeg' },
      { id: 'a3', cat: 'Asian', name: 'Stir Fry Tofu & Veg', price: 230, cal: 300, gluten: true, vegan: true, allergens: ['Soy'], prep: 12, photo: './assets/thai_curry.jpeg' },
      { id: 'a4', cat: 'Asian', name: 'Veg Pad Thai', price: 240, cal: 420, gluten: true, vegan: true, allergens: ['Peanuts', 'Soy'], prep: 13, photo: './assets/veg_pad_thai.jpeg' },
      { id: 'a5', cat: 'Asian', name: 'Coconut Rice', price: 140, cal: 300, gluten: false, vegan: true, allergens: ['Coconut'], prep: 8, photo: './assets/coconut_rice.jpeg' },
      { id: 'a6', cat: 'Asian', name: 'Veg Sushi Platter (8 pcs)', price: 380, cal: 260, gluten: true, vegan: false, allergens: ['Gluten', 'Soy'], prep: 18, photo: './assets/veg_sushi_platter.jpeg' },
      { id: 'a7', cat: 'Asian', name: 'Miso Soup', price: 120, cal: 60, gluten: false, vegan: true, allergens: ['Soy'], prep: 5, photo: './assets/miso_soup.jpeg' },
      { id: 'a8', cat: 'Asian', name: 'Teriyaki Veg Skewers', price: 210, cal: 280, gluten: true, vegan: true, allergens: ['Soy'], prep: 12, photo: './assets/terriyaki_veg.jpeg' },

      /* Desi (8) */
      { id: 'dsi1', cat: 'Desi', name: 'Rajma Masala', price: 170, cal: 360, gluten: false, vegan: true, allergens: [], prep: 12, photo: './assets/rajma_masala.jpeg' },
      { id: 'dsi2', cat: 'Desi', name: 'Dal Makhani', price: 180, cal: 400, gluten: false, vegan: false, allergens: ['Dairy'], prep: 14, photo: './assets/dal_makhani.jpeg' },
      { id: 'dsi3', cat: 'Desi', name: 'Sarson ka Saag', price: 190, cal: 320, gluten: false, vegan: true, allergens: [], prep: 20, photo: './assets/sarso_ka_sag.jpeg' },
      { id: 'dsi4', cat: 'Desi', name: 'Kadhi Pakora', price: 160, cal: 330, gluten: true, vegan: false, allergens: ['Gluten', 'Dairy'], prep: 15, photo: './assets/kadhi_pakora.jpeg' },
      { id: 'dsi5', cat: 'Desi', name: 'Pav Bhaji', price: 150, cal: 420, gluten: true, vegan: false, allergens: ['Gluten'], prep: 12, photo: './assets/pav_bhaji.jpeg' },
      { id: 'dsi6', cat: 'Desi', name: 'Masala Papad', price: 60, cal: 80, gluten: false, vegan: true, allergens: [], prep: 3, photo: './assets/masala_papad.jpeg' },
      { id: 'dsi7', cat: 'Desi', name: 'Bhature (2 pcs)', price: 80, cal: 380, gluten: true, vegan: false, allergens: ['Gluten'], prep: 7, photo: './assets/bhature.jpeg' },
      { id: 'dsi8', cat: 'Desi', name: 'Methi Thepla', price: 70, cal: 220, gluten: true, vegan: false, allergens: ['Gluten'], prep: 6, photo: './assets/methi_thepla.jpeg' }
    ];

    /* ------------------ STATE ------------------ */
    let MENU = []; // loaded from localStorage or default
    let cart = []; // {id, qty, note, spice}
    const tableNumberEl = document.getElementById('tableNumber');

    /* ------------------ UTIL ------------------ */
    function uid() { return 'id' + Math.random().toString(36).slice(2, 9); }
    function formatR(n) { return '₹' + n.toFixed(0); }
    function saveMenu() { localStorage.setItem('ramayana_menu', JSON.stringify(MENU)); }
    function loadMenu() { const s = localStorage.getItem('ramayana_menu'); MENU = s ? JSON.parse(s) : JSON.parse(JSON.stringify(DEFAULT_MENU)); saveMenu(); }
    function saveCart() { localStorage.setItem('ramayana_cart', JSON.stringify(cart)); }
    function loadCart() { const s = localStorage.getItem('ramayana_cart'); cart = s ? JSON.parse(s) : []; renderCart(); }
    function escapeHtml(s = '') { return String(s).replace(/[&<>"']/g, c => ({ '&': '&amp;', '<': '&lt;', '>': '&gt;', '"': '&quot;', "'": '&#39;' }[c])); }

    /* ------------------ TABLE QR SIM ------------------ */
    function setTableFromURL() { const p = new URLSearchParams(location.search); const t = p.get('table'); if (t) { tableNumberEl.textContent = t; localStorage.setItem('ramayana_table', t); } else { const st = localStorage.getItem('ramayana_table'); tableNumberEl.textContent = st || '—'; } }
    setTableFromURL();
    document.getElementById('scanBtn').addEventListener('click', () => { const t = prompt('Enter table number (simulate QR):'); if (t) { tableNumberEl.textContent = t; localStorage.setItem('ramayana_table', t); alert('Table set to ' + t); } });

    /* ------------------ RENDER CATEGORIES & FILTERS ------------------ */
    const categoryFilter = document.getElementById('categoryFilter');
    const filtersRow = document.getElementById('filtersRow');
    function refreshFilters() {
      const cats = ['all', ...new Set(MENU.map(i => i.cat))];
      categoryFilter.innerHTML = cats.map(c => `<option value="${c}">${c}</option>`).join('');
      filtersRow.innerHTML = ['All', 'Vegan', 'Gluten-Free', 'Contains Dairy', 'High-Cal (<200 cal)'].map(t => `<div class="chip" data-filter="${t}">${t}</div>`).join('');
    }
    refreshFilters();

    /* ------------------ RENDER MENU ------------------ */
    const menuArea = document.getElementById('menuArea');
    function renderMenu(query = '', cat = 'all', customFilter = '') {
      menuArea.innerHTML = '';
      let items = MENU.slice();
      if (cat && cat !== 'all') items = items.filter(i => i.cat === cat);
      if (query) items = items.filter(i => (i.name + ' ' + i.tags).toLowerCase().includes(query.toLowerCase()));
      if (customFilter === 'Vegan') items = items.filter(i => i.vegan);
      if (customFilter === 'Gluten-Free') items = items.filter(i => !i.gluten);
      if (customFilter === 'Contains Dairy') items = items.filter(i => i.allergens && i.allergens.join(',').toLowerCase().includes('dairy'));
      if (customFilter === 'High-Cal (<200 cal)') items = items.filter(i => i.cal && i.cal < 200);
      if (items.length === 0) { menuArea.innerHTML = '<div class="small">No items match.</div>'; return; }
      items.forEach(it => {
        const div = document.createElement('div'); div.className = 'card';
        div.innerHTML = `
      <img class="thumb" src="${it.photo}" alt="${escapeHtml(it.name)}">
      <div class="meta">
        <div style="display:flex;justify-content:space-between">
          <div>
            <div class="title">${escapeHtml(it.name)}</div>
            <div class="tags small">${escapeHtml(it.cat)} • ${it.cal} kcal • Prep ${it.prep}m</div>
            <div class="tags">${it.vegan ? '<span class="chip">Vegan</span>' : ''} ${it.gluten ? '<span class="chip">Gluten</span>' : ''} ${it.allergens && it.allergens.length ? '<span class="chip">' + escapeHtml(it.allergens.join(', ')) + '</span>' : ''}</div>
          </div>
          <div style="text-align:right">
            <div class="price">${formatR(it.price)}</div>
            <div class="small">Est: ${it.prep} min</div>
          </div>
        </div>

        <div class="controls-row">
          <div class="qty" data-id="${it.id}">
            <button class="decrease">−</button>
            <div style="padding:0 8px" class="qty-val">1</div>
            <button class="increase">+</button>
          </div>

          <select class="note spice" data-id="${it.id}" style="padding:6px;border-radius:6px;border:1px solid #ddd">
            <option>Regular</option><option>Mild</option><option>Medium</option><option>Spicy</option><option>Extra Spicy</option>
          </select>

          <input placeholder="Instruction (e.g., no onion)" class="note item-note" data-id="${it.id}" style="width:140px"/>

          <button class="btn add-to-cart" data-id="${it.id}">Add</button>

          <button class="btn alt view-details" data-id="${it.id}">Details</button>
        </div>
      </div>
    `;
        menuArea.appendChild(div);
      });
      attachMenuEvents();
    }

    /* ------------------ MENU EVENTS ------------------ */
    function attachMenuEvents() {
      document.querySelectorAll('.qty').forEach(qel => {
        qel.querySelector('.increase').onclick = () => { const v = qel.querySelector('.qty-val'); v.textContent = (+v.textContent) + 1; };
        qel.querySelector('.decrease').onclick = () => { const v = qel.querySelector('.qty-val'); v.textContent = Math.max(1, (+v.textContent) - 1); };
      });
      document.querySelectorAll('.add-to-cart').forEach(btn => {
        btn.onclick = () => {
          const id = btn.dataset.id;
          const parent = btn.closest('.card');
          const qty = +parent.querySelector('.qty-val').textContent;
          const spice = parent.querySelector('.spice').value;
          const note = parent.querySelector('.item-note').value.trim();
          addToCart(id, qty, spice, note);
        }
      });
      document.querySelectorAll('.view-details').forEach(b => {
        b.onclick = () => showDetails(b.dataset.id);
      });
    }

    /* ------------------ CART ------------------ */
    const cartListEl = document.getElementById('cartList');
    const cartTotalEl = document.getElementById('cartTotal');
    function addToCart(id, qty, spice, note) {
      const key = id + '::' + spice + '::' + note;
      const existing = cart.find(c => c.key === key);
      if (existing) existing.qty += qty; else {
        const it = MENU.find(m => m.id === id);
        cart.push({ key, id, qty, spice, note, name: it.name, price: it.price });
      }
      saveCart(); renderCart(); showTemp('Added to cart');
    }
    function renderCart() {
      cartListEl.innerHTML = '';
      if (cart.length === 0) { cartListEl.innerHTML = '<div class="small">Cart is empty</div>'; cartTotalEl.textContent = formatR(0); return; }
      let total = 0;
      cart.forEach((c, idx) => {
        const line = c.price * c.qty; total += line;
        const div = document.createElement('div'); div.className = 'cart-item';
        div.innerHTML = `<div>
      <div style="font-weight:700">${escapeHtml(c.name)} <span class="small">x${c.qty}</span></div>
      <div class="small">Spice: ${escapeHtml(c.spice)} • Note: ${escapeHtml(c.note || '—')}</div>
    </div>
    <div style="text-align:right">
      <div>${formatR(line)}</div>
      <button class="small-link remove" data-idx="${idx}">Remove</button>
    </div>`;
        cartListEl.appendChild(div);
      });
      cartTotalEl.textContent = formatR(total);
      cartListEl.querySelectorAll('.remove').forEach(b => b.onclick = () => { cart.splice(+b.dataset.idx, 1); saveCart(); renderCart(); });
    }

    /* ------------------ ORDER & PAYMENT (simulate) ------------------ */
    document.getElementById('payBtn').addEventListener('click', () => {
      if (cart.length === 0) return alert('Cart is empty');
      document.getElementById('paymentStatus').textContent = 'Paid (simulated)';
      localStorage.setItem('ramayana_paid', 'true');
      showTemp('Payment received');
    });
    document.getElementById('placeOrderBtn').addEventListener('click', () => {
      if (cart.length === 0) return alert('Cart is empty');
      const table = localStorage.getItem('ramayana_table');
      if (!table) return alert('Set table number (Scan QR)');
      const order = { id: uid(), table, items: cart, globalNote: document.getElementById('globalNote').value, paid: !!localStorage.getItem('ramayana_paid'), time: new Date().toLocaleString() };
      // In real app send to backend. We'll save last order for demo.
      localStorage.setItem('ramayana_last_order', JSON.stringify(order));
      cart = []; saveCart(); renderCart();
      document.getElementById('orderMessage').innerHTML = `<div class="order-confirm">Order placed for table <strong>${table}</strong>. ${order.paid ? 'Payment received.' : 'Payment pending.'} Preparing — estimated 15-25 mins.</div>`;
      document.getElementById('paymentStatus').textContent = order.paid ? 'Paid' : 'Not paid';
    });
    document.getElementById('clearCartBtn').addEventListener('click', () => { if (confirm('Clear cart?')) { cart = []; saveCart(); renderCart(); } });
    document.getElementById('downloadReceipt').addEventListener('click', () => {
      const order = localStorage.getItem('ramayana_last_order');
      if (!order) return alert('No recent order');
      const blob = new Blob([order], { type: 'application/json' }); const url = URL.createObjectURL(blob);
      const a = document.createElement('a'); a.href = url; a.download = 'ramayana_order.json'; a.click(); URL.revokeObjectURL(url);
    });

    /* ------------------ DETAILS & REVIEWS ------------------ */
    function showDetails(id) {
      const it = MENU.find(m => m.id === id);
      if (!it) return;
      const existing = getReviewsForItem(id);
      const modalHtml = `
    <div style="position:fixed;inset:0;background:rgba(0,0,0,0.45);display:flex;align-items:center;justify-content:center;z-index:9999">
      <div style="background:#fff;padding:12px;border-radius:8px;max-width:720px;width:94%;max-height:90%;overflow:auto">
        <div style="display:flex;gap:12px">
          <img src="${it.photo}" style="width:220px;height:160px;object-fit:cover;border-radius:8px">
          <div style="flex:1">
            <h2 style="margin:0">${escapeHtml(it.name)}</h2>
            <div class="small">${escapeHtml(it.cat)} • ${it.cal} kcal • Prep ${it.prep} min</div>
            <div style="margin-top:8px">${it.allergens && it.allergens.length ? 'Allergens: ' + escapeHtml(it.allergens.join(', ')) : 'No common allergens listed.'}</div>
            <div style="margin-top:8px;font-weight:800;color:var(--accent)">${formatR(it.price)}</div>
          </div>
        </div>
        <div style="margin-top:10px">
          <h4 style="margin:0 0 6px 0">Reviews for ${escapeHtml(it.name)}</h4>
          <div id="itemRevArea" style="min-height:100px">${existing.length ? existing.map(r => `<div style="padding:6px 0;border-bottom:1px dashed #f2f2f2"><strong>${escapeHtml(r.name || 'Guest')}</strong> <span class="small">(${r.rating}★)</span><div class="small">${escapeHtml(r.text)}</div></div>`).join('') : '<div class="small">No reviews yet.</div>'}</div>
          <div style="margin-top:8px;display:flex;gap:8px">
            <input id="revName" placeholder="Name" class="note" />
            <select id="revRating" class="note"><option>5</option><option>4</option><option>3</option><option>2</option><option>1</option></select>
            <input id="revText" placeholder="Write review" class="note" style="flex:1" />
            <button id="revSubmit" class="btn">Submit</button>
          </div>
        </div>
        <div style="text-align:right;margin-top:10px"><button id="closeModal" class="btn alt">Close</button></div>
      </div>
    </div>
  `;
      const container = document.createElement('div'); container.innerHTML = modalHtml; document.body.appendChild(container);
      container.querySelector('#closeModal').onclick = () => container.remove();
      container.querySelector('#revSubmit').onclick = () => {
        const rname = container.querySelector('#revName').value.trim() || 'Guest';
        const rr = +container.querySelector('#revRating').value;
        const rt = container.querySelector('#revText').value.trim();
        if (!rt) return alert('Write review text');
        const rv = { id: uid(), itemId: id, name: rname, rating: rr, text: rt, time: Date.now() };
        const s = localStorage.getItem('ramayana_reviews'); const arr = s ? JSON.parse(s) : []; arr.unshift(rv); localStorage.setItem('ramayana_reviews', JSON.stringify(arr.slice(0, 200)));
        loadReviews(); showTemp('Review added'); container.remove();
      };
    }
    function getReviewsForItem(id) { const s = localStorage.getItem('ramayana_reviews'); const arr = s ? JSON.parse(s) : []; return arr.filter(r => r.itemId === id); }
    function loadReviews() { const s = localStorage.getItem('ramayana_reviews'); const arr = s ? JSON.parse(s) : []; const area = document.getElementById('reviewsArea'); area.innerHTML = arr.length ? arr.slice(0, 50).map(r => `<div style="padding:6px 0;border-bottom:1px dashed #f2f2f2"><strong>${escapeHtml(r.name || 'Guest')}</strong> <span class="small">(${r.rating}★)</span><div class="small">${escapeHtml(r.text)}</div></div>`).join('') : '<div class="small">No reviews yet. Be the first!</div>'; }

    /* ------------------ SEARCH & FILTER HOOKS ------------------ */
    let activeCustomFilter = '';
    document.getElementById('search').addEventListener('input', e => renderMenu(e.target.value, categoryFilter.value, activeCustomFilter));
    categoryFilter.addEventListener('change', () => renderMenu(document.getElementById('search').value, categoryFilter.value, activeCustomFilter));
    filtersRow.addEventListener('click', e => {
      const chip = e.target.closest('.chip'); if (!chip) return;
      const f = chip.dataset.filter;
      activeCustomFilter = f === 'All' ? '' : f;
      renderMenu(document.getElementById('search').value, categoryFilter.value, activeCustomFilter);
    });

    /* ------------------ MISC UI ------------------ */
    function showTemp(msg) { const om = document.getElementById('orderMessage'); om.innerHTML = `<div style="padding:8px;background:#fff7f7;border:1px solid #ffdddd;border-radius:6px">${msg}</div>`; setTimeout(() => om.innerHTML = '', 2400); }

    /* ------------------ ADMIN ------------------ */
    document.getElementById('adminBtn').addEventListener('click', () => {
      const panel = document.getElementById('adminPanel'); panel.style.display = panel.style.display === 'none' ? 'block' : 'block';
      window.scrollTo({ top: document.body.scrollHeight, behavior: 'smooth' });
    });
    document.getElementById('adminLoginBtn').addEventListener('click', () => {
      const pass = document.getElementById('adminPass').value;
      if (pass === 'admin123') { document.getElementById('adminLoginArea').style.display = 'none'; document.getElementById('adminControls').style.display = 'block'; document.getElementById('adminMessage').textContent = 'Logged in as admin.'; renderAdminList(); }
      else alert('Wrong password');
    });

    function renderAdminList() {
      let list = document.getElementById('adminItemsList');
      if (list) list.remove();
      const d = document.createElement('div'); d.id = 'adminItemsList'; d.style.marginTop = '10px';
      d.innerHTML = MENU.map((it, idx) => `<div style="display:flex;gap:8px;align-items:center;padding:6px;border-bottom:1px dashed #f2f2f2">
    <div style="flex:1"><strong>${escapeHtml(it.name)}</strong> <div class="small">${escapeHtml(it.cat)} • ${it.cal} kcal • ${it.prep}m</div></div>
    <div style="width:120px;text-align:right">${formatR(it.price)}</div>
    <div style="display:flex;gap:6px">
      <button class="small-link edit" data-idx="${idx}">Edit</button>
      <button class="small-link del" data-idx="${idx}">Delete</button>
    </div>
  </div>`).join('');
      document.getElementById('adminControls').appendChild(d);
      d.querySelectorAll('.del').forEach(b => b.onclick = () => {
        if (!confirm('Delete this item?')) return;
        MENU.splice(+b.dataset.idx, 1); saveMenu(); renderMenu(document.getElementById('search').value, categoryFilter.value, activeCustomFilter); renderAdminList(); showTemp('Item deleted');
      });
      d.querySelectorAll('.edit').forEach(b => b.onclick = () => {
        const it = MENU[+b.dataset.idx];
        const formHtml = `
      <div style="padding:10px;border-radius:8px;background:#fff;margin-top:8px;border:1px solid #eee">
        <div style="display:flex;gap:8px">
          <input id="admName" value="${escapeHtml(it.name)}" class="note" style="flex:1"/>
          <input id="admPrice" value="${it.price}" class="note" style="width:120px"/>
        </div>
        <div style="display:flex;gap:8px;margin-top:8px">
          <input id="admCal" value="${it.cal}" class="note" style="width:120px"/>
          <input id="admPrep" value="${it.prep}" class="note" style="width:120px"/>
          <input id="admPhoto" value="${it.photo}" class="note" style="flex:1"/>
        </div>
        <div style="display:flex;gap:8px;margin-top:8px">
          <input id="admAll" value="${escapeHtml((it.allergens || []).join(','))}" class="note" placeholder="Allergens comma"/>
          <select id="admVegan" class="note"><option value="true">Vegan</option><option value="false">Not Vegan</option></select>
          <select id="admGluten" class="note"><option value="true">Contains Gluten</option><option value="false">Gluten-Free</option></select>
        </div>
        <div style="margin-top:8px;display:flex;gap:8px">
          <button id="admSave" class="btn">Save</button>
          <button id="admCancel" class="btn alt">Cancel</button>
        </div>
      </div>
    `;
        const wrap = document.createElement('div'); wrap.innerHTML = formHtml; d.insertBefore(wrap, d.children[+b.dataset.idx + 1]);
        wrap.querySelector('#admCancel').onclick = () => wrap.remove();
        wrap.querySelector('#admSave').onclick = () => {
          it.name = wrap.querySelector('#admName').value.trim();
          it.price = +wrap.querySelector('#admPrice').value || it.price;
          it.cal = +wrap.querySelector('#admCal').value || it.cal;
          it.prep = +wrap.querySelector('#admPrep').value || it.prep;
          it.photo = wrap.querySelector('#admPhoto').value || it.photo;
          it.allergens = wrap.querySelector('#admAll').value.split(',').map(s => s.trim()).filter(Boolean);
          it.vegan = wrap.querySelector('#admVegan').value === 'true';
          it.gluten = wrap.querySelector('#admGluten').value === 'true';
          saveMenu(); renderMenu(document.getElementById('search').value, categoryFilter.value, activeCustomFilter); renderAdminList(); wrap.remove(); showTemp('Item updated');
        };
      });
    }

    /* Add item */
    document.getElementById('addItemBtn').addEventListener('click', () => {
      const nid = uid();
      const newItem = { id: nid, cat: 'Sabji', name: 'New Item', price: 120, cal: 200, gluten: false, vegan: true, allergens: [], prep: 10, photo: 'https://via.placeholder.com/400x300?text=New+Item' };
      MENU.unshift(newItem); saveMenu(); renderMenu(document.getElementById('search').value, categoryFilter.value, activeCustomFilter); renderAdminList(); showTemp('New item added (edit to update details)');
    });
    document.getElementById('exportBtn').addEventListener('click', () => { console.log('MENU EXPORT', MENU); alert('Menu printed to browser console'); });
    document.getElementById('resetDataBtn').addEventListener('click', () => { if (confirm('Reset menu to default?')) { localStorage.removeItem('ramayana_menu'); loadMenu(); refreshFilters(); renderMenu(); alert('Reset'); } });

    /* ------------------ BOOTSTRAP ------------------ */
    loadMenu(); refreshFilters();
    const cats = [...new Set(MENU.map(m => m.cat))]; // ensure categoryFilter filled
    categoryFilter.innerHTML = ['all', ...cats].map(c => `<option value="${c}">${c}</option>`).join('');
    renderMenu();
    loadCart(); loadReviews();

    /* ------------------ HELPER: show small message ------------------ */
    function showTempMsg(msg) { const om = document.getElementById('orderMessage'); om.innerHTML = `<div style="padding:8px;background:#fff7f7;border:1px solid #ffdddd;border-radius:6px">${msg}</div>`; setTimeout(() => om.innerHTML = '', 2500); }
  </script>
</body>

</html>

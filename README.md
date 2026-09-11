# ecommerce-website-on-cosmetic-
A 4-page e-commerce demo (Home, Shop, Product, Cart) built with vanilla HTML, CSS &amp; JS — products fetched from a local JSON file, cart powered by localStorage.
VERDANT MARKET - README
========================

Ye ek simple E-commerce website hai jo sirf HTML, CSS aur JavaScript
(Vanilla JS) se bani hai. Koi framework use nahi hua. Data ek JSON
file se fetch() karke load hota hai.

FOLDER STRUCTURE
-----------------
index.html          -> Home Page
products.html        -> Product Listing Page (Shop page)
product.html          -> Single Product Page
cart.html             -> Cart Page
css/style.css         -> Poori site ki styling (ek hi theme sab pages me)
js/app.js             -> Saari functionality (fetch, cart logic, product cards)
data/products.json    -> Product data (JSON format me), yahi se fetch hota hai

PAGES KI TAFSEEL
-----------------
1) Home Page (index.html)
   - Hero section
   - Categories grid
   - Featured products (JSON se fetch hoke aate hain)

2) Product Page (products.html)
   - Sare products ek grid me
   - Category filter chips (beauty, fragrances, furniture, groceries)
   - Sort option (price low-high, high-low, rating)
   - Search bar

3) Single Product Page (product.html)
   - URL me id parameter aata hai, jaise: product.html?id=5
   - Us product ki full detail: image, price, description, stock
   - Quantity ka + / - control
   - Add to Cart button
   - Related products (same category ke)

4) Cart Page (cart.html)
   - Cart me jo items add kiye gaye unki list
   - Har item ki quantity change ya remove kar saktay hain
   - Subtotal, shipping aur total ka summary

ADD TO CART FUNCTIONALITY (JS LOGIC)
--------------------------------------
- Cart ka data browser ke localStorage me store hota hai (key: "verdant_cart")
- Functions (js/app.js me):
    getCart()          -> localStorage se cart nikalta hai
    saveCart(cart)      -> cart ko localStorage me save karta hai
    addToCart(id, qty)  -> product ko cart me add karta hai (agar pehle se hai to quantity badha deta hai)
    removeFromCart(id)  -> product ko cart se hata deta hai
    updateCartQty(id,q) -> kisi item ki quantity update karta hai
    cartItemCount()     -> total items ka count return karta hai
    updateCartCount()   -> header wale cart badge ko update karta hai

- Har page load hone par header ka cart count JSON se nahi balke
  localStorage se calculate hokar dikhta hai.
- Jab bhi "Add to Cart" ya "+" button dabaya jata hai, ek chota
  toast message bhi show hota hai ("Added to cart").

DATA FETCH
-----------
- Poora product data data/products.json me hai.
- loadProducts() function fetch() use karke ye file load karta hai
  aur ek baar load hone ke baad cache kar leta hai (dobara fetch nahi karta).

KAISE CHALAYEN
---------------
Method 1 (Recommended):
   1. Terminal / cmd me project folder ke andar jayein
   2. Command chalayein:  python3 -m http.server
   3. Browser me kholein:  http://localhost:8000

Method 2:
   - index.html ko directly double-click karke browser me open karein
   - Note: kuch browsers file:// se fetch() block kar dete hain,
     is liye agar products load na hon to Method 1 use karein.

THEME
------
Color scheme: Deep forest green (#1f3a2e) + gold accent (#c9932b)
Fonts: Fraunces (headings) + Space Grotesk (body) - Google Fonts se load hote hain

NOTES
------
- Koi backend/server nahi hai, sab kuch frontend par hai.
- Cart sirf usi browser me save rehta hai jahan add kiya gaya ho
  (localStorage browser-specific hota hai).
- Checkout button sirf demo message dikhata hai, real payment
  process implement nahi kiya gaya.


<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flowerss Parfum - Wangi Bikin Menarik</title>
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@300;400;600&family=Pacifico&family=Quicksand:wght@400;600;700&display=swap" rel="stylesheet">
    
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>

    <!-- Custom Styles -->
    <style>
        body {
            font-family: 'Quicksand', sans-serif;
            background: linear-gradient(135deg, #fdfbfb 0%, #ebedee 100%);
            overflow-x: hidden;
        }
        
        h1, h2, h3, .brand-font {
            font-family: 'Fredoka', sans-serif;
        }

        .cursive-font {
            font-family: 'Pacifico', cursive;
        }

        /* Background Animation Wrapper */
        #canvas-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: linear-gradient(to bottom, #ffe4e1, #fff0f5, #e6e6fa);
        }

        .glass-card {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(10px);
            border: 2px solid rgba(255, 255, 255, 0.5);
            box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.15);
        }

        .product-card {
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(255, 105, 180, 0.3);
        }

        /* Floating Cart Animation */
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
        }
        .animate-float {
            animation: float 3s ease-in-out infinite;
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 10px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f1f1;
        }
        ::-webkit-scrollbar-thumb {
            background: #ff69b4;
            border-radius: 5px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #db2777;
        }
    </style>
</head>
<body class="text-gray-800">

    <!-- Background Falling Flowers -->
    <div id="canvas-container">
        <canvas id="flowerCanvas"></canvas>
    </div>

    <!-- Navbar -->
    <nav class="fixed top-0 w-full z-50 glass-card px-6 py-3 flex justify-between items-center shadow-sm">
        <div class="flex items-center gap-2">
            <i data-lucide="flower-2" class="text-pink-500 w-8 h-8 animate-spin-slow"></i>
            <span class="text-2xl font-bold text-pink-600 brand-font tracking-wide">Flowerss Parfum</span>
        </div>
        <button onclick="toggleCart()" class="relative p-2 bg-pink-100 rounded-full hover:bg-pink-200 transition">
            <i data-lucide="shopping-bag" class="text-pink-600"></i>
            <span id="cart-count" class="absolute -top-1 -right-1 bg-red-500 text-white text-xs font-bold w-5 h-5 flex items-center justify-center rounded-full">0</span>
        </button>
    </nav>

    <!-- Hero Section -->
    <header class="pt-32 pb-16 px-4 text-center relative overflow-hidden">
        <div class="max-w-4xl mx-auto relative z-10">
            <span class="inline-block py-1 px-3 rounded-full bg-purple-100 text-purple-600 text-sm font-bold mb-4 shadow-sm animate-bounce">
                ✨ Best Seller Roll On Perfume ✨
            </span>
            <h1 class="text-4xl md:text-6xl font-bold text-gray-800 mb-4 leading-tight">
                Wangi kan badan mu dengan <span class="text-pink-500 cursive-font">parfum roll</span>
            </h1>
            <p class="text-xl md:text-2xl text-gray-600 font-medium italic mb-8">
                "Parfum roll dengan wangi bikin menarik!!" 🌸
            </p>
            <a href="#produk" class="inline-block bg-gradient-to-r from-pink-500 to-purple-500 text-white font-bold py-4 px-8 rounded-full shadow-lg transform hover:scale-105 transition duration-300">
                Lihat Koleksi Wangi <i data-lucide="arrow-down" class="inline w-5 h-5 ml-2"></i>
            </a>
        </div>
    </header>

    <!-- Product Section -->
    <section id="produk" class="py-16 px-4">
        <div class="max-w-6xl mx-auto">
            <h2 class="text-3xl font-bold text-center text-gray-800 mb-12 brand-font">
                Pilih Varian Favoritmu 💖
            </h2>
            
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8" id="product-list">
                <!-- Products will be injected via JS -->
            </div>
        </div>
    </section>

    <!-- Features / Animasi Lucu Section -->
    <section class="py-12 bg-white/50 backdrop-blur-sm my-8">
        <div class="max-w-4xl mx-auto flex flex-wrap justify-center gap-8 text-center">
            <div class="flex flex-col items-center p-4 w-32 animate-float" style="animation-delay: 0s;">
                <div class="bg-pink-100 p-3 rounded-full mb-2">
                    <i data-lucide="droplets" class="text-pink-500 w-6 h-6"></i>
                </div>
                <span class="font-bold text-sm">Tahan Lama</span>
            </div>
            <div class="flex flex-col items-center p-4 w-32 animate-float" style="animation-delay: 0.5s;">
                <div class="bg-purple-100 p-3 rounded-full mb-2">
                    <i data-lucide="pocket" class="text-purple-500 w-6 h-6"></i>
                </div>
                <span class="font-bold text-sm">Travel Size</span>
            </div>
            <div class="flex flex-col items-center p-4 w-32 animate-float" style="animation-delay: 1s;">
                <div class="bg-yellow-100 p-3 rounded-full mb-2">
                    <i data-lucide="sparkles" class="text-yellow-500 w-6 h-6"></i>
                </div>
                <span class="font-bold text-sm">Non Alkohol</span>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-pink-500 text-white py-8 text-center relative overflow-hidden">
        <div class="relative z-10">
            <h3 class="text-3xl cursive-font mb-2">Isty parfum — Teman Wangi mu!</h3>
            <p class="text-pink-100 text-sm">© 2024 Flowerss Parfum. Dibuat dengan cinta 💖</p>
        </div>
        <!-- Decorative circles -->
        <div class="absolute top-0 left-0 w-24 h-24 bg-white opacity-10 rounded-full -translate-x-10 -translate-y-10"></div>
        <div class="absolute bottom-0 right-0 w-32 h-32 bg-white opacity-10 rounded-full translate-x-10 translate-y-10"></div>
    </footer>

    <!-- Cart Modal Overlay -->
    <div id="cart-modal" class="fixed inset-0 bg-black bg-opacity-50 z-[60] hidden flex items-center justify-center p-4">
        <div class="bg-white rounded-2xl shadow-2xl w-full max-w-md max-h-[90vh] overflow-y-auto relative animate-in fade-in zoom-in duration-300">
            
            <!-- Modal Header -->
            <div class="sticky top-0 bg-pink-50 p-4 border-b flex justify-between items-center rounded-t-2xl z-10">
                <h3 class="text-xl font-bold text-gray-800 flex items-center gap-2">
                    <i data-lucide="shopping-cart" class="text-pink-500"></i> Keranjang Wangi
                </h3>
                <button onclick="toggleCart()" class="text-gray-500 hover:text-red-500">
                    <i data-lucide="x"></i>
                </button>
            </div>

            <!-- Cart Items -->
            <div id="cart-items" class="p-4 space-y-4">
                <p class="text-center text-gray-500 py-8">Keranjangmu masih kosong nih, yuk isi! 🛍️</p>
            </div>

            <!-- Checkout Form -->
            <div id="checkout-form-container" class="p-4 bg-gray-50 border-t hidden">
                <h4 class="font-bold text-gray-800 mb-3 text-sm uppercase tracking-wider">Data Pemesan</h4>
                <form id="order-form" onsubmit="processOrder(event)" class="space-y-3">
                    <div>
                        <label class="block text-xs font-bold text-gray-600 mb-1">Nama Lengkap</label>
                        <input type="text" id="customer-name" required class="w-full border rounded-lg p-2 text-sm focus:ring-2 focus:ring-pink-400 outline-none" placeholder="Cth: Isty Cantik">
                    </div>
                    <div>
                        <label class="block text-xs font-bold text-gray-600 mb-1">Alamat Lengkap</label>
                        <textarea id="customer-address" required class="w-full border rounded-lg p-2 text-sm focus:ring-2 focus:ring-pink-400 outline-none" rows="2" placeholder="Jalan Mawar No. 12..."></textarea>
                    </div>
                    <div>
                        <label class="block text-xs font-bold text-gray-600 mb-1">Metode Pembayaran</label>
                        <select id="payment-method" class="w-full border rounded-lg p-2 text-sm focus:ring-2 focus:ring-pink-400 outline-none" onchange="checkPaymentMethod()">
                            <option value="DANA">DANA</option>
                            <option value="GoPay">GoPay</option>
                            <option value="OVO">OVO</option>
                            <option value="ShopeePay">ShopeePay</option>
                            <option value="QRIS">QRIS (Scan Barcode)</option>
                            <option value="COD">Cash / Bayar di Tempat</option>
                        </select>
                    </div>
                    
                    <!-- QRIS Info -->
                    <div id="qris-info" class="hidden p-3 bg-white border-2 border-dashed border-pink-300 rounded-lg text-center">
                        <p class="text-xs text-gray-600 mb-2">Klik link di bawah untuk membayar via QRIS DANA:</p>
                        <a href="https://link.dana.id/minta?full_url=https://qr.dana.id/v1/281012012024110773006713" target="_blank" class="block w-full bg-blue-500 text-white text-xs py-2 rounded font-bold hover:bg-blue-600">
                            Buka Link Pembayaran QRIS
                        </a>
                        <p class="text-[10px] text-gray-400 mt-1">*Lakukan pembayaran, lalu kirim bukti ke WA Admin setelah checkout.</p>
                    </div>

                    <!-- Total & Button -->
                    <div class="pt-2 border-t mt-4">
                        <div class="flex justify-between items-center mb-4">
                            <span class="font-bold text-gray-600">Total Pembayaran:</span>
                            <span id="cart-total" class="font-bold text-xl text-pink-600">Rp 0</span>
                        </div>
                        <button type="submit" class="w-full bg-green-500 hover:bg-green-600 text-white font-bold py-3 rounded-xl shadow-lg transform transition hover:-translate-y-1 flex justify-center items-center gap-2">
                            <i data-lucide="message-circle"></i> Pesan via WhatsApp
                        </button>
                    </div>
                </form>
            </div>
        </div>
    </div>

    <script>
        // --- Data Produk ---
        const products = [
            {
                id: 1,
                name: "Nagita Roll",
                price: 7000,
                desc: "Aroma elegan seperti selebriti! Campuran bunga mawar dan sentuhan musk yang mewah. Cocok buat kamu yang ingin tampil berkelas.",
                color: "bg-red-100",
                imgColor: "bg-red-200",
                imgSrc: "https://share.google/jyGikw7PzvbODmspY"
            },
            {
                id: 2,
                name: "Sweet Boo Roll",
                price: 7500,
                desc: "Wangi manis permen karet campur buah segar! Bikin hari-harimu ceria terus. Wangi favorit remaja masa kini.",
                color: "bg-pink-100",
                imgColor: "bg-pink-200",
                imgSrc: "https://share.google/kxRBuoCm7tpWclgSO"
            },
            {
                id: 3,
                name: "Vanilla Cake Roll",
                price: 8000,
                desc: "Hmm... Wangi kue vanilla yang baru matang! Lembut, creamy, dan bikin siapa aja pengen deket-deket sama kamu.",
                color: "bg-yellow-100",
                imgColor: "bg-yellow-200",
                imgSrc: "https://share.google/5O5o2hwCRe4qosL3n"
            }
        ];

        // --- State ---
        let cart = [];

        // --- Render Products ---
        const productList = document.getElementById('product-list');
        products.forEach(product => {
            const card = document.createElement('div');
            card.className = `glass-card rounded-2xl overflow-hidden p-6 flex flex-col items-center text-center product-card border-b-4 ${product.color.replace('bg-', 'border-')}`;
            
            // Format IDR
            const formattedPrice = new Intl.NumberFormat('id-ID', { style: 'currency', currency: 'IDR', minimumFractionDigits: 0 }).format(product.price);

            // Conditional image rendering
            const imageContent = product.imgSrc 
                ? `<img src="${product.imgSrc}" alt="${product.name}" class="w-full h-full object-cover">`
                : `<i data-lucide="spray-can" class="w-12 h-12 text-gray-700 opacity-50"></i>`;

            card.innerHTML = `
                <div class="w-24 h-24 ${product.imgColor} rounded-full flex items-center justify-center mb-4 shadow-inner overflow-hidden relative">
                    ${imageContent}
                </div>
                <h3 class="text-xl font-bold text-gray-800 mb-1">${product.name}</h3>
                <span class="text-pink-600 font-extrabold text-lg mb-3 block">${formattedPrice}</span>
                <p class="text-sm text-gray-600 mb-6 flex-grow leading-relaxed">${product.desc}</p>
                <button onclick="addToCart(${product.id})" class="w-full bg-gradient-to-r from-pink-500 to-purple-500 text-white font-bold py-2 rounded-full shadow hover:shadow-lg transition transform active:scale-95 flex items-center justify-center gap-2">
                    <i data-lucide="plus-circle" class="w-4 h-4"></i> Pesan Ini
                </button>
            `;
            productList.appendChild(card);
        });

        // --- Cart Functions ---
        function addToCart(productId) {
            const product = products.find(p => p.id === productId);
            const existingItem = cart.find(item => item.id === productId);

            if (existingItem) {
                existingItem.qty++;
            } else {
                cart.push({ ...product, qty: 1 });
            }
            updateCartUI();
            
            // Simple animation feedback
            const btn = event.currentTarget;
            const originalText = btn.innerHTML;
            btn.innerHTML = `<i data-lucide="check" class="w-4 h-4"></i> Masuk Keranjang!`;
            btn.classList.add('bg-green-500');
            setTimeout(() => {
                btn.innerHTML = originalText;
                btn.classList.remove('bg-green-500');
                lucide.createIcons();
            }, 1000);
        }

        function updateCartUI() {
            const cartCount = document.getElementById('cart-count');
            const cartItemsContainer = document.getElementById('cart-items');
            const cartTotalEl = document.getElementById('cart-total');
            const checkoutForm = document.getElementById('checkout-form-container');

            // Update Badge
            const totalQty = cart.reduce((acc, item) => acc + item.qty, 0);
            cartCount.innerText = totalQty;
            
            // Animation for badge
            cartCount.classList.remove('scale-125');
            void cartCount.offsetWidth; // trigger reflow
            if(totalQty > 0) cartCount.classList.add('scale-125', 'transition', 'transform');

            // Render Items
            cartItemsContainer.innerHTML = '';
            let grandTotal = 0;

            if (cart.length === 0) {
                cartItemsContainer.innerHTML = `<div class="text-center py-8 opacity-50"><i data-lucide="shopping-basket" class="w-16 h-16 mx-auto mb-2 text-pink-300"></i><p>Keranjang kosong</p></div>`;
                checkoutForm.classList.add('hidden');
            } else {
                checkoutForm.classList.remove('hidden');
                cart.forEach((item, index) => {
                    const itemTotal = item.price * item.qty;
                    grandTotal += itemTotal;
                    
                    const el = document.createElement('div');
                    el.className = 'flex justify-between items-center bg-white p-3 rounded-lg shadow-sm border border-gray-100';
                    el.innerHTML = `
                        <div>
                            <h4 class="font-bold text-sm text-gray-800">${item.name}</h4>
                            <p class="text-xs text-gray-500">Rp ${item.price.toLocaleString()} x ${item.qty}</p>
                        </div>
                        <div class="flex items-center gap-3">
                            <span class="font-bold text-pink-600 text-sm">Rp ${itemTotal.toLocaleString()}</span>
                            <div class="flex items-center bg-gray-100 rounded-full">
                                <button onclick="changeQty(${index}, -1)" class="w-6 h-6 flex items-center justify-center text-gray-600 font-bold hover:bg-gray-200 rounded-full">-</button>
                                <button onclick="changeQty(${index}, 1)" class="w-6 h-6 flex items-center justify-center text-pink-600 font-bold hover:bg-gray-200 rounded-full">+</button>
                            </div>
                        </div>
                    `;
                    cartItemsContainer.appendChild(el);
                });
            }

            cartTotalEl.innerText = 'Rp ' + grandTotal.toLocaleString('id-ID');
            lucide.createIcons();
        }

        function changeQty(index, delta) {
            cart[index].qty += delta;
            if (cart[index].qty <= 0) {
                cart.splice(index, 1);
            }
            updateCartUI();
        }

        function toggleCart() {
            const modal = document.getElementById('cart-modal');
            modal.classList.toggle('hidden');
        }

        function checkPaymentMethod() {
            const method = document.getElementById('payment-method').value;
            const qrisInfo = document.getElementById('qris-info');
            if (method === 'QRIS') {
                qrisInfo.classList.remove('hidden');
            } else {
                qrisInfo.classList.add('hidden');
            }
        }

        // --- WhatsApp Checkout ---
        function processOrder(e) {
            e.preventDefault();
            
            const name = document.getElementById('customer-name').value;
            const address = document.getElementById('customer-address').value;
            const payment = document.getElementById('payment-method').value;

            if (cart.length === 0) return alert("Keranjang kosong!");

            let message = `Halo Admin *Flowerss Parfum*! 🌸\n\n`;
            message += `Saya mau pesan nih:\n`;
            message += `--------------------------------\n`;
            
            let total = 0;
            cart.forEach(item => {
                const subtotal = item.price * item.qty;
                total += subtotal;
                message += `📦 *${item.name}* (${item.qty} pcs) - Rp ${subtotal.toLocaleString()}\n`;
            });
            
            message += `--------------------------------\n`;
            message += `💰 *TOTAL: Rp ${total.toLocaleString()}*\n\n`;
            message += `📋 *Data Penerima:*\n`;
            message += `👤 Nama: ${name}\n`;
            message += `🏠 Alamat: ${address}\n`;
            message += `💳 Pembayaran: ${payment}\n`;
            
            if(payment === 'QRIS') {
                 message += `(Saya akan melampirkan bukti transfer QRIS setelah ini)`;
            }

            message += `\nMohon diproses ya kak! Terima kasih ✨`;

            const encodedMessage = encodeURIComponent(message);
            const waNumber = "6285891693186";
            
            window.open(`https://wa.me/${waNumber}?text=${encodedMessage}`, '_blank');
        }

        // --- Animations: Falling Flowers (Canvas) ---
        const canvas = document.getElementById('flowerCanvas');
        const ctx = canvas.getContext('2d');
        
        let width, height;
        let flowers = [];

        function resize() {
            width = canvas.width = window.innerWidth;
            height = canvas.height = window.innerHeight;
        }
        window.addEventListener('resize', resize);
        resize();

        class Flower {
            constructor() {
                this.init();
            }

            init() {
                this.x = Math.random() * width;
                this.y = Math.random() * -height; // Start above screen
                this.size = Math.random() * 15 + 10;
                this.speedY = Math.random() * 1 + 0.5;
                this.speedX = Math.random() * 0.5 - 0.25;
                this.rotation = Math.random() * 360;
                this.rotationSpeed = Math.random() * 2 - 1;
                // Emoji flowers
                const types = ['🌸', '🌺', '🌹', '🌷', '💐']; 
                this.type = types[Math.floor(Math.random() * types.length)];
            }

            update() {
                this.y += this.speedY;
                this.x += this.speedX;
                this.rotation += this.rotationSpeed;

                if (this.y > height) {
                    this.init(); // Reset to top
                }
            }

            draw() {
                ctx.save();
                ctx.translate(this.x, this.y);
                ctx.rotate(this.rotation * Math.PI / 180);
                ctx.font = `${this.size}px serif`;
                ctx.fillText(this.type, -this.size/2, -this.size/2);
                ctx.restore();
            }
        }

        // Create flowers
        for (let i = 0; i < 25; i++) {
            flowers.push(new Flower());
        }

        function animate() {
            ctx.clearRect(0, 0, width, height);
            flowers.forEach(flower => {
                flower.update();
                flower.draw();
            });
            requestAnimationFrame(animate);
        }
        animate();

        // Init Icons
        lucide.createIcons();

    </script>
</body>
</html>

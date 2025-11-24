# klmpk5
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cemilan Nagih - By Adisty, Indyra, Rizka</title>
    
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Lucide Icons CDN -->
    <script src="https://unpkg.com/lucide@latest"></script>
    
    <!-- Google Font (Inter) -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;800&display=swap" rel="stylesheet">
    
    <script>
        // Konfigurasi Tailwind CSS
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        // Skema Warna: Orange, Merah, Cream
                        'brand-orange': '#F97316', // (Tailwind Orange-500)
                        'brand-red': '#EF4444',     // (Tailwind Red-500)
                        'brand-cream': '#FFF7ED',   // (Tailwind Orange-50)
                    },
                    fontFamily: {
                        inter: ['Inter', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    
    <style>
        /* Style tambahan untuk transisi halaman */
        .page-content {
            animation: fadeIn 0.5s ease-in-out;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        /* Style untuk tombol galeri gambar */
        .gallery-button {
            transition: all 0.3s;
        }
        /* Menyembunyikan scrollbar untuk thumbnail */
        .thumbnail-scroll::-webkit-scrollbar {
            display: none;
        }
        .thumbnail-scroll {
            -ms-overflow-style: none; /* IE dan Edge */
            scrollbar-width: none; /* Firefox */
        }
    </style>
</head>
<body class="bg-brand-cream font-inter text-gray-800">

    <!-- ===== HEADER / NAVBAR ===== -->
    <header class="bg-white shadow-md sticky top-0 z-50">
        <nav class="container mx-auto px-4 sm:px-6 lg:px-8 py-4 flex justify-between items-center">
            <!-- Brand Logo -->
            <a href="#" onclick="app.navigateTo('home')" class="text-2xl font-extrabold text-brand-orange">
                Cemilan Nagih
            </a>
            
            <!-- Navigation Links (Desktop) -->
            <div class="hidden md:flex space-x-6">
                <a href="#" onclick="app.navigateTo('home')" class="text-gray-600 hover:text-brand-orange font-medium">Home</a>
                <a href="#" onclick="app.navigateTo('about')" class="text-gray-600 hover:text-brand-orange font-medium">Tentang Kami</a>
                <a href="#" onclick="app.navigateTo('contact')" class="text-gray-600 hover:text-brand-orange font-medium">Kontak</a>
            </div>
            
            <!-- Cart Icon -->
            <button onclick="app.navigateTo('checkout')" class="relative flex items-center px-4 py-2 bg-brand-orange text-white rounded-full shadow-lg hover:bg-orange-600 transition-colors">
                <i data-lucide="shopping-cart" class="w-5 h-5"></i>
                <span class="ml-2 hidden sm:inline">Keranjang</span>
                <span id="cart-count-badge" class="absolute -top-2 -right-2 bg-brand-red text-white text-xs font-bold rounded-full w-5 h-5 flex items-center justify-center">0</span>
            </button>
            
            <!-- Mobile Menu Button -->
            <button id="mobile-menu-button" class="md:hidden ml-4">
                <i data-lucide="menu" class="w-6 h-6 text-gray-700"></i>
            </button>
        </nav>
        
        <!-- Mobile Menu (Hidden by default) -->
        <div id="mobile-menu" class="hidden md:hidden bg-white shadow-lg">
            <a href="#" onclick="app.navigateTo('home'); app.toggleMobileMenu();" class="block px-6 py-3 text-gray-600 hover:bg-brand-cream font-medium">Home</a>
            <a href="#" onclick="app.navigateTo('about'); app.toggleMobileMenu();" class="block px-6 py-3 text-gray-600 hover:bg-brand-cream font-medium">Tentang Kami</a>
            <a href="#" onclick="app.navigateTo('contact'); app.toggleMobileMenu();" class="block px-6 py-3 text-gray-600 hover:bg-brand-cream font-medium">Kontak</a>
        </div>
    </header>

    <!-- ===== MAIN CONTENT (DYNAMIC) ===== -->
    <main id="app-root" class="container mx-auto px-4 sm:px-6 lg:px-8 py-8 min-h-screen">
        <!-- Konten dinamis akan dimuat di sini oleh JavaScript -->
    </main>

    <!-- ===== FOOTER ===== -->
    <footer class="bg-gray-800 text-brand-cream mt-12 pt-12 pb-8">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <!-- Kolom 1: Brand -->
                <div>
                    <h3 class="text-2xl font-bold text-brand-orange mb-2">Cemilan Nagih</h3>
                    <p class="text-sm mb-4">by: Adisty, Indyra, Rizka.<br>Kelompok 5.</p>
                    <p class="text-sm">&copy; <span id="footer-year"></span> All rights reserved.</p>
                </div>
                
                <!-- Kolom 2: Tautan -->
                <div>
                    <h4 class="text-lg font-semibold text-white mb-3">Tautan</h4>
                    <ul class="space-y-2 text-sm">
                        <li><a href="#" onclick="app.navigateTo('home')" class="hover:text-brand-orange">Home</a></li>
                        <li><a href="#" onclick="app.navigateTo('about')" class="hover:text-brand-orange">Tentang Kami</a></li>
                        <li><a href="#" onclick="app.navigateTo('contact')" class="hover:text-brand-orange">Kontak</a></li>
                        <li><a href="#" onclick="app.navigateTo('checkout')" class="hover:text-brand-orange">Checkout</a></li>
                    </ul>
                </div>
                
                <!-- Kolom 3: Media Sosial -->
                <div>
                    <h4 class="text-lg font-semibold text-white mb-3">Ikuti Kami</h4>
                    <div class="flex space-x-4">
                        <a href="https://instagram.com/cemilanagih" target="_blank" rel="noopener noreferrer" class="p-2 bg-gray-700 rounded-full hover:bg-brand-orange transition-colors">
                            <i data-lucide="instagram" class="w-5 h-5"></i>
                        </a>
                        <a href="#" onclick="app.helpers.openWhatsApp(app.config.waAdmin)" class="p-2 bg-gray-700 rounded-full hover:bg-brand-orange transition-colors">
                            <i data-lucide="message-circle" class="w-5 h-5"></i>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </footer>
    
    <!-- ===== TOAST NOTIFICATION ===== -->
    <div id="toast" classs="hidden fixed bottom-10 right-10 bg-green-500 text-white px-6 py-3 rounded-lg shadow-xl z-50 transition-all duration-300 translate-y-20 opacity-0">
        Item ditambahkan ke keranjang!
    </div>

    <!-- ===== JAVASCRIPT LOGIC ===== -->
    <script>
        // Gunakan object `app` untuk menampung semua logika
        const app = {
            
            // Konfigurasi dan State
            config: {
                waAdmin: '083899569127',
                shopeeUser: 'cutecurate',
                payments: {
                    shopeepay: '083194373015',
                    dana: '085697272896',
                    seabank: '9013 4390 2999 (a/n Rizka Adinda)'
                }
            },
            
            state: {
                currentPage: 'home',
                currentProduct: null,
                currentImageIndex: 0,
                cart: [], // Format: { id, name, price, flavor, quantity, image }
                products: [
                    { 
                        id: 'p1', 
                        name: 'Makaroni Kering', 
                        price: 5000, 
                        desc: 'Makaroni kering renyah dengan bumbu melimpah. Gurih, pedas, dan bikin nagih!', 
                        images: [
                            'https://down-id.img.susercontent.com/file/id-11134207-7r992-lrjmd1resxfqeehttps://down-id.img.susercontent.com/file/id-11134207-7r992-lrjmd1resxfqee', 
                            
                    ], 
                        flavors: ['Pedas Daun Jeruk'] 
                    },
                    { 
                        id: 'p2', 
                        name: 'Basreng (Baso Goreng)', 
                        price: 5000, 
                        desc: 'Baso ikan goreng kering yang dipotong stik, renyah di luar dan gurih di dalam. Dicocol bumbu pedas makin mantap!', 
                        images: [
                            'https://www.static-src.com/wcsstore/Indraprastha/images/catalog/full//catalog-image/107/MTA-147168719/no_brand_-500gram-_basreng_stik_pedas_daun_jeruk_-_1-2kg_full01_ca6fff1b.jpg',
                        ], 
                        flavors: ['Pedas Daun Jeruk'] 
                    },
                    { 
                        id: 'p3', 
                        name: 'Usus Kering Crispy', 
                        price: 5000, 
                        desc: 'Usus ayam pilihan yang dibersihkan dan digoreng hingga kering dan crispy. Tanpa bau amis, dijamin renyah pol!', 
                        images: [
                            'https://ukhtiosaka.com/wp-content/uploads/2024/01/Usus-Crispy-Pedas-Premium.webp'
                        ], 
                        flavors: ['Original Gurih', 'Pedas Daun Jeruk',] 
                    },
                    { 
                        id: 'p4', 
                        name: 'Sosis Kering', 
                        price: 5000, 
                        desc: 'Sosis sapi berkualitas yang diiris tipis dan digoreng kering. Cemilan unik dengan rasa daging yang kuat.', 
                        images: [
                            'https://laz-img-sg.alicdn.com/p/8a9d9be50436a6f4684252d3216ceb67.jpg'
                        ], 
                        flavors: ['Gurih Pedas'] 
                    },
                    { 
                        id: 'p5', 
                        name: 'Citul (Aci Tulang)', 
                        price: 3000, 
                        desc: 'Cemilan aci kenyal dengan isian tulang rawan ayam yang gurih. Disajikan dengan bumbu chili oil dan bawang goreng.', 
                        images: [
                            'https://cf.shopee.co.id/file/id-11134207-7rbk7-ma2s0jru56grbe',
                        ], 
                        flavors: ['Isi Ayam Pedas'] 
                    }
                ]
            },
            
            // Elemen DOM
            elements: {
                appRoot: null,
                cartCountBadge: null,
                mobileMenu: null,
                mobileMenuButton: null,
                footerYear: null,
                toast: null,
            },

            // Inisialisasi Aplikasi
            init() {
                // Ikat elemen DOM
                this.elements.appRoot = document.getElementById('app-root');
                this.elements.cartCountBadge = document.getElementById('cart-count-badge');
                this.elements.mobileMenu = document.getElementById('mobile-menu');
                this.elements.mobileMenuButton = document.getElementById('mobile-menu-button');
                this.elements.footerYear = document.getElementById('footer-year');
                this.elements.toast = document.getElementById('toast');
                
                // Set Event Listeners
                this.elements.mobileMenuButton.addEventListener('click', this.toggleMobileMenu);
                
                // Set tahun di footer
                this.elements.footerYear.innerText = new Date().getFullYear();

                // Muat keranjang dari LocalStorage
                this.cart.load();
                
                // Render halaman awal
                this.renderPage();
            },
            
            // Toggle Menu Mobile
            toggleMobileMenu() {
                app.elements.mobileMenu.classList.toggle('hidden');
            },
            
            // Navigasi Halaman
            navigateTo(page, productId = null) {
                this.state.currentPage = page;
                
                if (page === 'detail' && productId) {
                    this.state.currentProduct = this.state.products.find(p => p.id === productId);
                    this.state.currentImageIndex = 0; // Reset index gambar
                } else {
                    this.state.currentProduct = null;
                }
                
                // Scroll ke atas
                window.scrollTo(0, 0);
                
                // Render halaman
                this.renderPage();
            },
            
            // Render Halaman Utama (Router)
            renderPage() {
                if (!this.elements.appRoot) return;
                
                let html = '';
                
                switch (this.state.currentPage) {
                    case 'home':
                        html = this.renderHomePage();
                        break;
                    case 'detail':
                        html = this.renderDetailPage();
                        break;
                    case 'checkout':
                        html = this.renderCheckoutPage();
                        break;
                    case 'about':
                        html = this.renderAboutPage();
                        break;
                    case 'contact':
                        html = this.renderContactPage();
                        break;
                    default:
                        html = this.renderHomePage();
                }
                
                this.elements.appRoot.innerHTML = html;
                
                // Inisialisasi ulang ikon setelah render
                lucide.createIcons();
                
                // Update hitungan keranjang
                this.cart.updateBadge();
            },
            
            // ===== RENDERER HALAMAN =====
            
            // Render Halaman Home
            renderHomePage() {
                const productCards = this.state.products.map(product => `
                    <div class="bg-white rounded-xl shadow-lg overflow-hidden transition-transform duration-300 hover:scale-105 group">
                        <img src="${product.images[0]}" alt="${product.name}" class="w-full h-48 object-cover">
                        <div class="p-5">
                            <h3 class="text-xl font-bold text-gray-800 mb-2">${product.name}</h3>
                            <p class="text-lg font-extrabold text-brand-orange mb-4">${this.helpers.formatRupiah(product.price)}</p>
                            <button onclick="app.navigateTo('detail', '${product.id}')" class="w-full bg-brand-orange text-white font-bold py-2 px-4 rounded-lg shadow-md hover:bg-orange-600 transition-colors duration-300">
                                Lihat Detail
                            </button>
                        </div>
                    </div>
                `).join('');
            
                return `
                    <div class="page-content">
                        <!-- Hero Section -->
                        <section class="bg-gradient-to-r from-brand-orange to-brand-red text-white rounded-xl shadow-2xl p-8 md:p-12 mb-12 flex flex-col items-center text-center">
                            <h1 class="text-4xl md:text-5xl font-extrabold mb-4">Cemilan Nagih!</h1>
                            <p class="text-lg md:text-xl mb-6 max-w-2xl">Lezat, murah, dan bikin nagih. Temukan aneka cemilan favoritmu di sini. Harga flat Rp 5.000,- aja!</p>
                            <a href="#produk" class="bg-white text-brand-orange font-bold py-3 px-6 rounded-full shadow-lg hover:scale-105 transition-transform">
                                Belanja Sekarang
                            </a>
                        </section>
                        
                        <!-- Product Grid -->
                        <section id="produk">
                            <h2 class="text-3xl font-bold text-center text-gray-800 mb-8">Produk Kami</h2>
                            <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
                                ${productCards}
                            </div>
                        </section>
                    </div>
                `;
            },
            
            // Render Halaman Detail Produk
            renderDetailPage() {
                const product = this.state.currentProduct;
                if (!product) return '<p>Produk tidak ditemukan.</p>';

                const flavorOptions = product.flavors.map(flavor => `<option value="${flavor}">${flavor}</option>`).join('');
                
                // Tombol thumbnail
                const thumbnails = product.images.map((img, index) => `
                    <img src="${img}" alt="Thumbnail ${index + 1}" 
                         class="w-16 h-16 object-cover rounded-md cursor-pointer border-2 ${index === this.state.currentImageIndex ? 'border-brand-orange' : 'border-transparent'} hover:border-brand-orange"
                         onclick="app.changeDetailImage(${index})">
                `).join('');
            
                return `
                    <div class="page-content bg-white p-6 md:p-10 rounded-xl shadow-xl">
                        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 lg:gap-12">
                            
                            <!-- Galeri Gambar -->
                            <div class="w-full">
                                <div class="relative rounded-lg overflow-hidden shadow-lg mb-4 aspect-square">
                                    <img id="main-product-image" src="${product.images[this.state.currentImageIndex]}" alt="${product.name}" class="w-full h-full object-cover transition-opacity duration-300">
                                    
                                    <!-- Tombol Navigasi Gambar (jika lebih dari 1 gambar) -->
                                    ${product.images.length > 1 ? `
                                        <button onclick="app.changeDetailImage(app.state.currentImageIndex - 1)" class="gallery-button absolute left-3 top-1/2 -translate-y-1/2 bg-white/70 p-2 rounded-full shadow-md hover:bg-white text-gray-800">
                                            <i data-lucide="chevron-left" class="w-6 h-6"></i>
                                        </button>
                                        <button onclick="app.changeDetailImage(app.state.currentImageIndex + 1)" class="gallery-button absolute right-3 top-1/2 -translate-y-1/2 bg-white/70 p-2 rounded-full shadow-md hover:bg-white text-gray-800">
                                            <i data-lucide="chevron-right" class="w-6 h-6"></i>
                                        </button>
                                    ` : ''}
                                </div>
                                
                                <!-- Thumbnails -->
                                ${product.images.length > 1 ? `
                                <div class="flex overflow-x-auto space-x-3 p-1 thumbnail-scroll">
                                    ${thumbnails}
                                </div>
                                ` : ''}
                            </div>
                            
                            <!-- Info Produk -->
                            <div>
                                <h1 class="text-4xl font-extrabold text-gray-900 mb-3">${product.name}</h1>
                                <p class="text-3xl font-bold text-brand-orange mb-6">${this.helpers.formatRupiah(product.price)}</p>
                                
                                <p class="text-gray-600 text-base leading-relaxed mb-6">${product.desc}</p>
                                
                                <!-- Form Opsi -->
                                <div class="space-y-4 mb-8">
                                    <!-- Pilihan Rasa -->
                                    <div>
                                        <label for="flavor-select" class="block text-sm font-medium text-gray-700 mb-1">Pilih Rasa:</label>
                                        <select id="flavor-select" class="w-full p-3 border border-gray-300 rounded-lg shadow-sm focus:ring-brand-orange focus:border-brand-orange">
                                            ${flavorOptions}
                                        </select>
                                    </div>
                                    
                                    <!-- Pilihan Jumlah -->
                                    <div>
                                        <label for="quantity-input" class="block text-sm font-medium text-gray-700 mb-1">Jumlah:</label>
                                        <input id="quantity-input" type="number" value="1" min="1" class="w-full p-3 border border-gray-300 rounded-lg shadow-sm focus:ring-brand-orange focus:border-brand-orange">
                                    </div>
                                </div>
                                
                                <!-- Tombol Aksi -->
                                <div class="space-y-4">
                                    <button onclick="app.cart.add('${product.id}')" class="w-full flex justify-center items-center bg-brand-orange text-white font-bold py-4 px-6 rounded-lg shadow-lg hover:bg-orange-600 transition-colors duration-300 text-lg">
                                        <i data-lucide="shopping-cart" class="w-5 h-5 mr-3"></i>
                                        Tambah ke Keranjang
                                    </button>
                                    <button onclick="app.orderViaWhatsApp()" class="w-full flex justify-center items-center bg-green-500 text-white font-bold py-4 px-6 rounded-lg shadow-lg hover:bg-green-600 transition-colors duration-300 text-lg">
                                        <i data-lucide="message-circle" class="w-5 h-5 mr-3"></i>
                                        Pesan via WhatsApp
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>
                `;
            },
            
            // Ubah Gambar di Halaman Detail
            changeDetailImage(index) {
                const product = this.state.currentProduct;
                if (!product) return;
                
                let newIndex = index;
                if (newIndex < 0) {
                    newIndex = product.images.length - 1;
                } else if (newIndex >= product.images.length) {
                    newIndex = 0;
                }
                
                this.state.currentImageIndex = newIndex;
                
                // Update gambar utama
                const mainImage = document.getElementById('main-product-image');
                if (mainImage) {
                    mainImage.src = product.images[newIndex];
                }
                
                // Update border thumbnail
                const thumbnails = document.querySelectorAll('.thumbnail-scroll img');
                thumbnails.forEach((thumb, i) => {
                    if (i === newIndex) {
                        thumb.classList.add('border-brand-orange');
                        thumb.classList.remove('border-transparent');
                    } else {
                        thumb.classList.remove('border-brand-orange');
                        thumb.classList.add('border-transparent');
                    }
                });
            },
            
            // Pesan via WA (dari Halaman Detail)
            orderViaWhatsApp() {
                const product = this.state.currentProduct;
                const flavorEl = document.getElementById('flavor-select');
                const quantityEl = document.getElementById('quantity-input');
                
                const flavor = flavorEl ? flavorEl.value : product.flavors[0];
                const quantity = quantityEl ? quantityEl.value : 1;
                
                let message = `Halo Cemilan Nagih, saya mau pesan:\n\n`;
                message += `Produk: ${product.name}\n`;
                message += `Rasa: ${flavor}\n`;
                message += `Jumlah: ${quantity} pcs\n\n`;
                message += `Terima kasih.`;
                
                this.helpers.openWhatsApp(this.config.waAdmin, message);
            },
            
            // Render Halaman Checkout
            renderCheckoutPage() {
                if (this.state.cart.length === 0) {
                    return `
                        <div class="page-content text-center bg-white p-10 rounded-xl shadow-xl">
                            <i data-lucide="shopping-cart" class="w-16 h-16 text-brand-orange mx-auto mb-4"></i>
                            <h2 class="text-3xl font-bold mb-4">Keranjang Kosong</h2>
                            <p class="text-gray-600 mb-6">Oops, keranjang belanjamu masih kosong. Yuk, cari cemilan favoritmu!</p>
                            <button onclick="app.navigateTo('home')" class="bg-brand-orange text-white font-bold py-3 px-6 rounded-lg shadow-md hover:bg-orange-600 transition-colors">
                                Kembali ke Home
                            </button>
                        </div>
                    `;
                }

                let cartItemsHtml = '';
                let subtotal = 0;
                
                this.state.cart.forEach((item, index) => {
                    const itemTotal = item.price * item.quantity;
                    subtotal += itemTotal;
                    
                    cartItemsHtml += `
                        <li class="flex items-center justify-between py-4 border-b border-gray-200">
                            <div class="flex items-center space-x-4">
                                <img src="${item.image}" alt="${item.name}" class="w-16 h-16 object-cover rounded-md shadow">
                                <div>
                                    <h4 class="font-semibold text-gray-800">${item.name}</h4>
                                    <p class="text-sm text-gray-500">${item.flavor}</p>
                                    <p class="text-sm text-gray-600">${item.quantity} x ${this.helpers.formatRupiah(item.price)}</p>
                                </div>
                            </div>
                            <div class="text-right">
                                <p class="font-semibold text-gray-800">${this.helpers.formatRupiah(itemTotal)}</p>
                                <button onclick="app.cart.remove(${index})" class="text-xs text-brand-red hover:underline mt-1">Hapus</button>
                            </div>
                        </li>
                    `;
                });

                return `
                    <div class="page-content">
                        <h1 class="text-3xl md:text-4xl font-extrabold text-gray-900 mb-8 text-center">Checkout</h1>
                        
                        <div class="grid grid-cols-1 lg:grid-cols-3 gap-8 lg:gap-12">
                            
                            <!-- Kolom Kiri: Form Data -->
                            <div class="lg:col-span-2 bg-white p-6 md:p-8 rounded-xl shadow-xl">
                                <form id="checkout-form" onsubmit="event.preventDefault(); app.submitOrder();">
                                    <!-- Data Pembeli -->
                                    <section class="mb-8">
                                        <h2 class="text-2xl font-bold text-gray-800 border-b-2 border-brand-orange pb-2 mb-4">Data Pembeli</h2>
                                        <div class="grid grid-cols-1 gap-4">
                                            <div>
                                                <label for="name" class="block text-sm font-medium text-gray-700 mb-1">Nama Lengkap</label>
                                                <input type="text" id="name" required class="w-full p-3 border border-gray-300 rounded-lg shadow-sm focus:ring-brand-orange focus:border-brand-orange">
                                            </div>
                                            <div>
                                                <label for="phone" class="block text-sm font-medium text-gray-700 mb-1">Nomor HP (WhatsApp)</label>
                                                <input type="tel" id="phone" required class="w-full p-3 border border-gray-300 rounded-lg shadow-sm focus:ring-brand-orange focus:border-brand-orange">
                                            </div>
                                            <div>
                                                <label for="address" class="block text-sm font-medium text-gray-700 mb-1">Alamat Lengkap</label>
                                                <textarea id="address" rows="3" required class="w-full p-3 border border-gray-300 rounded-lg shadow-sm focus:ring-brand-orange focus:border-brand-orange"></textarea>
                                            </div>
                                        </div>
                                    </section>
                                    
                                    <!-- Ekspedisi -->
                                    <section class="mb-8">
                                        <h2 class="text-2xl font-bold text-gray-800 border-b-2 border-brand-orange pb-2 mb-4">Pilih Ekspedisi</h2>
                                        <div class="flex flex-wrap gap-4">
                                            ${['JNT', 'JX', 'SPX'].map(kurir => `
                                                <div>
                                                    <input type="radio" name="shipping" id="ship-${kurir}" value="${kurir}" class="hidden peer" required>
                                                    <label for="ship-${kurir}" class="block cursor-pointer p-4 border border-gray-300 rounded-lg shadow-sm peer-checked:border-brand-orange peer-checked:ring-2 peer-checked:ring-brand-orange peer-checked:bg-brand-cream font-medium">
                                                        ${kurir}
                                                    </label>
                                                </div>
                                            `).join('')}
                                        </div>
                                    </section>
                                    
                                    <!-- Pembayaran -->
                                    <section>
                                        <h2 class="text-2xl font-bold text-gray-800 border-b-2 border-brand-orange pb-2 mb-4">Pilih Pembayaran</h2>
                                        <div class="space-y-3">
                                            ${this.renderPaymentOption('shopeepay', 'ShopeePay', this.config.payments.shopeepay)}
                                            ${this.renderPaymentOption('dana', 'DANA', this.config.payments.dana)}
                                            ${this.renderPaymentOption('seabank', 'SeaBank (Transfer)', this.config.payments.seabank)}
                                        </div>
                                    </section>
                                    
                                </form>
                            </div>
                            
                            <!-- Kolom Kanan: Ringkasan Pesanan -->
                            <div class="lg:col-span-1">
                                <div class="bg-white p-6 md:p-8 rounded-xl shadow-xl sticky top-28">
                                    <h2 class="text-2xl font-bold text-gray-800 border-b border-gray-300 pb-3 mb-4">Ringkasan Pesanan</h2>
                                    
                                    <ul class="divide-y divide-gray-200 mb-4 max-h-60 overflow-y-auto">
                                        ${cartItemsHtml}
                                    </ul>
                                    
                                    <div class="border-t border-gray-300 pt-4 space-y-2">
                                        <div class="flex justify-between text-lg font-semibold">
                                            <span>Subtotal</span>
                                            <span>${this.helpers.formatRupiah(subtotal)}</span>
                                        </div>
                                        <div class="flex justify-between text-sm text-gray-600">
                                            <span>Ongkir</span>
                                            <span>(Dihitung Admin)</span>
                                        </div>
                                        <div class="flex justify-between text-xl font-extrabold text-brand-orange pt-2">
                                            <span>Total</span>
                                            <span>${this.helpers.formatRupiah(subtotal)}</span>
                                        </div>
                                    </div>
                                    
                                    <div class="mt-6 space-y-3">
                                        <button type="submit" form="checkout-form" class="w-full bg-brand-red text-white font-bold py-4 px-6 rounded-lg shadow-lg hover:bg-red-600 transition-colors text-lg">
                                            Selesaikan Pesanan
                                        </button>
                                        <a href="https://shopee.co.id/${this.config.shopeeUser}" target="_blank" rel="noopener noreferrer" class="w-full flex justify-center items-center bg-orange-500 text-white font-bold py-4 px-6 rounded-lg shadow-lg hover:bg-orange-600 transition-colors text-lg">
                                            <i data-lucide="store" class="w-5 h-5 mr-3"></i>
                                            Bayar via Shopee
                                        </a>
                                    </div>
                                </div>
                            </div>
                            
                        </div>
                    </div>
                `;
            },
            
            // Helper untuk Render Opsi Pembayaran
            renderPaymentOption(id, name, detail) {
                return `
                    <div class="border border-gray-300 rounded-lg overflow-hidden">
                        <label for="pay-${id}" class="flex items-center p-4 cursor-pointer hover:bg-brand-cream">
                            <input type="radio" name="payment" id="pay-${id}" value="${id}" class="h-5 w-5 text-brand-orange focus:ring-brand-orange" required onchange="app.togglePaymentDetail(event)">
                            <span class="ml-3 font-medium text-gray-800">${name}</span>
                        </label>
                        <div id="detail-pay-${id}" class="payment-detail hidden p-4 bg-gray-100 border-t border-gray-200">
                            <p class="text-sm text-gray-700">Silakan lakukan pembayaran ke:</p>
                            <p class="text-lg font-bold text-gray-900">${detail}</p>
                            <img src="https://placehold.co/300x300/F97316/FFF?text=QR+${name}" alt="QR ${name}" class="w-1/2 mx-auto mt-2 rounded-md">
                        </div>
                    </div>
                `;
            },
            
            // Tampilkan detail pembayaran
            togglePaymentDetail(event) {
                // Sembunyikan semua
                document.querySelectorAll('.payment-detail').forEach(el => {
                    el.classList.add('hidden');
                });
                // Tampilkan yang dipilih
                const detailId = `detail-${event.target.id}`;
                document.getElementById(detailId).classList.remove('hidden');
            },
            
            // Submit Pesanan
            submitOrder() {
                // Simulasi submit order
                // Di aplikasi nyata, ini akan mengirim data ke server atau API
                
                // Ambil data form
                const orderData = {
                    name: document.getElementById('name').value,
                    phone: document.getElementById('phone').value,
                    address: document.getElementById('address').value,
                    shipping: document.querySelector('input[name="shipping"]:checked').value,
                    payment: document.querySelector('input[name="payment"]:checked').value,
                    cart: this.state.cart,
                    total: this.state.cart.reduce((sum, item) => sum + (item.price * item.quantity), 0)
                };
                
                // (Opsional) Kirim ke WhatsApp Admin sebagai ringkasan
                let waMessage = `*PESANAN BARU - CEMILAN NAGIH*\n\n`;
                waMessage += `*Data Pembeli:*\n`;
                waMessage += `Nama: ${orderData.name}\n`;
                waMessage += `HP: ${orderData.phone}\n`;
                waMessage += `Alamat: ${orderData.address}\n\n`;
                waMessage += `*Pesanan:*\n`;
                orderData.cart.forEach(item => {
                    waMessage += `- ${item.name} (${item.flavor}) x${item.quantity}\n`;
                });
                waMessage += `\n*Total: ${this.helpers.formatRupiah(orderData.total)}*\n`;
                waMessage += `*Pengiriman:* ${orderData.shipping}\n`;
                waMessage += `*Pembayaran:* ${orderData.payment}\n\n`;
                waMessage += `Mohon segera diproses, terima kasih.`;
                
                // Buka WA di tab baru
                this.helpers.openWhatsApp(this.config.waAdmin, waMessage);
                
                // Bersihkan keranjang dan tampilkan halaman terima kasih
                this.cart.clear();
                
                // Render halaman "Terima Kasih" (Simulasi)
                this.elements.appRoot.innerHTML = `
                    <div class="page-content text-center bg-white p-10 rounded-xl shadow-xl max-w-lg mx-auto">
                        <i data-lucide="check-circle" class="w-20 h-20 text-green-500 mx-auto mb-6"></i>
                        <h2 class="text-3xl font-bold mb-4">Pesanan Diterima!</h2>
                        <p class="text-gray-600 mb-6">Terima kasih telah memesan. Pesananmu akan segera kami proses. Salinan pesanan juga telah dikirimkan ke WhatsApp Admin kami.</p>
                        <button onclick="app.navigateTo('home')" class="bg-brand-orange text-white font-bold py-3 px-6 rounded-lg shadow-md hover:bg-orange-600 transition-colors">
                            Kembali ke Home
                        </button>
                    </div>
                `;
                lucide.createIcons(); // Re-init icons
            },
            
            // Render Halaman Tentang Kami
            renderAboutPage() {
                return `
                    <div class="page-content bg-white p-6 md:p-10 rounded-xl shadow-xl max-w-4xl mx-auto">
                        <h1 class="text-4xl font-extrabold text-gray-900 mb-6 text-center">Tentang Kami</h1>
                        
                        <img src="https://placehold.co/800x400/F97316/FFF?text=Tim+Cemilan+Nagih" alt="Tim Kami" class="w-full h-60 object-cover rounded-lg shadow-md mb-8">
                        
                        <section class="mb-8">
                            <h2 class="text-2xl font-bold text-brand-red mb-3">Cerita Kami</h2>
                            <p class="text-gray-600 leading-relaxed">
                                "Cemilan Nagih" lahir dari kecintaan kami (Adisty, Indyra, dan Rizka) terhadap makanan ringan yang lezat dan bisa dinikmati kapan saja. Kami percaya bahwa cemilan enak tidak harus mahal. Dari situlah kami berkomitmen untuk menciptakan produk-produk yang tidak hanya ramah di kantong tapi juga selalu bikin kangen.
                            </p>
                        </section>
                        
                        <section class="mb-8 bg-brand-cream p-6 rounded-lg">
                            <h2 class="text-2xl font-bold text-brand-red mb-3">Visi & Misi</h2>
                            <blockquote class="text-xl font-semibold text-gray-800 italic border-l-4 border-brand-orange pl-4">
                                "Menyajikan cemilan lezat, murah, dan bikin nagih untuk semua kalangan."
                            </blockquote>
                        </section>
                        
                        <section>
                            <h2 class="text-2xl font-bold text-brand-red mb-4">Tim Owner (Kelompok 5)</h2>
                            <ul class="space-y-3 text-gray-700 list-decimal list-inside ml-4">
                                <li class="text-lg font-medium">Adisty Bintang</li>
                                <li class="text-lg font-medium">Indyra Imaginesyah</li>
                                <li class="text-lg font-medium">Rizka Adinda</li>
                            </ul>
                        </section>
                    </div>
                `;
            },
            
            // Render Halaman Kontak
            renderContactPage() {
                return `
                    <div class="page-content bg-white p-6 md:p-10 rounded-xl shadow-xl max-w-4xl mx-auto">
                        <h1 class="text-4xl font-extrabold text-gray-900 mb-8 text-center">Hubungi Kami</h1>
                        
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                            <!-- Info Kontak -->
                            <div class="space-y-6">
                                <div>
                                    <h3 class="text-xl font-semibold text-brand-orange mb-2">Informasi Kontak</h3>
                                    <p class="text-gray-600">Punya pertanyaan atau ingin memesan langsung? Hubungi kami melalui:</p>
                                </div>
                                <a href="#" onclick="app.helpers.openWhatsApp(app.config.waAdmin)" class="flex items-center p-4 bg-gray-50 rounded-lg hover:shadow-md transition-shadow">
                                    <i data-lucide="message-circle" class="w-8 h-8 text-green-500"></i>
                                    <div class="ml-4">
                                        <span class="font-medium">WhatsApp Admin</span>
                                        <span class="block text-sm text-gray-500">${this.config.waAdmin}</span>
                                    </div>
                                </a>
                                <a href="https://instagram.com/cemilanagih" target="_blank" rel="noopener noreferrer" class="flex items-center p-4 bg-gray-50 rounded-lg hover:shadow-md transition-shadow">
                                    <i data-lucide="instagram" class="w-8 h-8 text-pink-500"></i>
                                    <div class="ml-4">
                                        <span class="font-medium">Instagram</span>
                                        <span class="block text-sm text-gray-500">@cemilanagih</span>
                                    </div>
                                </a>
                                <div class="flex items-center p-4 bg-gray-50 rounded-lg">
                                    <i data-lucide="mail" class="w-8 h-8 text-blue-500"></i>
                                    <div class="ml-4">
                                        <span class="font-medium">Email</span>
                                        <span class="block text-sm text-gray-500">info@cemilannagih.com</span>
                                    </div>
                                </div>
                                
                                <div class="pt-4 border-t border-gray-200">
                                    <h3 class="text-xl font-semibold text-brand-orange mb-2">Pembayaran</h3>
                                    <ul class="list-disc list-inside text-gray-600 space-y-1">
                                        <li>ShopeePay: ${this.config.payments.shopeepay}</li>
                                        <li>DANA: ${this.config.payments.dana}</li>
                                    </ul>
                                </div>
                            </div>
                            
                            <!-- Formulir Kontak -->
                            <div>
                                <h3 class="text-xl font-semibold text-brand-orange mb-2">Kirim Pesan</h3>
                                <form onsubmit="event.preventDefault(); app.helpers.showToast('Pesan terkirim (simulasi)', 'info');">
                                    <div class="space-y-4">
                                        <div>
                                            <label for="contact-name" class="block text-sm font-medium text-gray-700 mb-1">Nama Anda</label>
                                            <input type="text" id="contact-name" required class="w-full p-3 border border-gray-300 rounded-lg shadow-sm focus:ring-brand-orange focus:border-brand-orange">
                                        </div>
                                        <div>
                                            <label for="contact-email" class="block text-sm font-medium text-gray-700 mb-1">Email Anda</label>
                                            <input type="email" id="contact-email" required class="w-full p-3 border border-gray-300 rounded-lg shadow-sm focus:ring-brand-orange focus:border-brand-orange">
                                        </div>
                                        <div>
                                            <label for="contact-message" class="block text-sm font-medium text-gray-700 mb-1">Pesan</label>
                                            <textarea id="contact-message" rows="5" required class="w-full p-3 border border-gray-300 rounded-lg shadow-sm focus:ring-brand-orange focus:border-brand-orange"></textarea>
                                        </div>
                                        <div>
                                            <button type="submit" class="w-full bg-brand-orange text-white font-bold py-3 px-6 rounded-lg shadow-lg hover:bg-orange-600 transition-colors">
                                                Kirim Pesan
                                            </button>
                                        </div>
                                    </div>
                                </form>
                            </div>
                        </div>
                    </div>
                `;
            },
            
            // ===== LOGIKA KERANJANG =====
            cart: {
                // Tambah ke keranjang
                add(productId) {
                    const product = app.state.products.find(p => p.id === productId);
                    const flavorEl = document.getElementById('flavor-select');
                    const quantityEl = document.getElementById('quantity-input');
                    
                    const flavor = flavorEl ? flavorEl.value : product.flavors[0];
                    const quantity = quantityEl ? parseInt(quantityEl.value) : 1;
                    
                    // Cek jika sudah ada di keranjang (ID & Rasa yang sama)
                    const existingItemIndex = app.state.cart.findIndex(
                        item => item.id === productId && item.flavor === flavor
                    );
                    
                    if (existingItemIndex > -1) {
                        // Update jumlah
                        app.state.cart[existingItemIndex].quantity += quantity;
                    } else {
                        // Tambah item baru
                        app.state.cart.push({
                            id: product.id,
                            name: product.name,
                            price: product.price,
                            flavor: flavor,
                            quantity: quantity,
                            image: product.images[0]
                        });
                    }
                    
                    this.save();
                    this.updateBadge();
                    app.helpers.showToast('Sukses ditambah ke keranjang!', 'success');
                },
                
                // Hapus dari keranjang
                remove(index) {
                    app.state.cart.splice(index, 1);
                    this.save();
                    app.renderPage(); // Render ulang halaman (checkout)
                },
                
                // Bersihkan keranjang
                clear() {
                    app.state.cart = [];
                    this.save();
                    this.updateBadge();
                },
                
                // Simpan ke LocalStorage
                save() {
                    localStorage.setItem('cemilanNagihCart', JSON.stringify(app.state.cart));
                },
                
                // Muat dari LocalStorage
                load() {
                    const cartData = localStorage.getItem('cemilanNagihCart');
                    if (cartData) {
                        app.state.cart = JSON.parse(cartData);
                    }
                },
                
                // Update badge hitungan
                updateBadge() {
                    const totalItems = app.state.cart.reduce((sum, item) => sum + item.quantity, 0);
                    if (app.elements.cartCountBadge) {
                        app.elements.cartCountBadge.innerText = totalItems;
                    }
                }
            },
            
            // ===== FUNGSI HELPERS =====
            helpers: {
                // Format Rupiah
                formatRupiah(number) {
                    return new Intl.NumberFormat('id-ID', {
                        style: 'currency',
                        currency: 'IDR',
                        minimumFractionDigits: 0
                    }).format(number);
                },
                
                // Buka WhatsApp
                openWhatsApp(phone, message = '') {
                    // Pastikan nomor HP format internasional (ganti 08 jadi 628)
                    let formattedPhone = phone.replace(/^0/, '62');
                    const encodedMessage = encodeURIComponent(message);
                    window.open(`https://wa.me/${formattedPhone}?text=${encodedMessage}`, '_blank');
                },
                
                // Tampilkan Toast
                showToast(message, type = 'success') {
                    const toast = app.elements.toast;
                    if (!toast) return;
                    
                    toast.innerText = message;
                    toast.classList.remove('hidden', 'bg-green-500', 'bg-blue-500', 'bg-red-500', 'opacity-0', 'translate-y-20');
                    
                    if (type === 'success') {
                        toast.classList.add('bg-green-500');
                    } else if (type === 'info') {
                        toast.classList.add('bg-blue-500');
                    } else {
                        toast.classList.add('bg-red-500');
                    }
                    
                    toast.classList.add('opacity-100', 'translate-y-0');
                    
                    setTimeout(() => {
                        toast.classList.remove('opacity-100', 'translate-y-0');
                        toast.classList.add('opacity-0', 'translate-y-20');
                        setTimeout(() => toast.classList.add('hidden'), 500);
                    }, 3000);
                }
            }
        };

        // Inisialisasi aplikasi saat DOM siap
        document.addEventListener('DOMContentLoaded', () => {
            app.init();
        });
    </script>
</body>
</html>

# Grupo 1
Bem vindos 
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grupo 1 | Varejo de Elite</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
    <script src="https://unpkg.com/lucide@latest"></script>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Manrope:wght@300;500;700&display=swap" rel="stylesheet">
    
    <style>
        body { font-family: 'Manrope', sans-serif; background: #050505; color: white; overflow-x: hidden; }
        h1, h2, h3 { font-family: 'Playfair Display', serif; }
        .glass { background: rgba(255, 255, 255, 0.03); backdrop-filter: blur(15px); border: 1px solid rgba(255, 255, 255, 0.1); }
        .glass-dark { background: rgba(0, 0, 0, 0.95); backdrop-filter: blur(25px); border-left: 1px solid rgba(255, 255, 255, 0.1); }
        .bg-section { background-attachment: fixed; background-position: center; background-size: cover; position: relative; }
        .hide-scroll::-webkit-scrollbar { display: none; }
        .modal-blur { backdrop-filter: blur(40px) brightness(0.3); }
        input[type="radio"] { accent-color: #6366f1; }
    </style>
</head>
<body class="antialiased">

    <div class="fixed top-6 right-6 z-[70] flex gap-4">
        <div class="glass p-4 rounded-full cursor-pointer hover:bg-indigo-600 transition relative" onclick="toggleMenu()">
            <i data-lucide="more-vertical" class="w-6 h-6 text-white"></i>
            <span id="cart-count" class="absolute -top-1 -right-1 bg-red-500 text-[10px] w-5 h-5 flex items-center justify-center rounded-full font-bold">0</span>
        </div>
    </div>

    <div id="sidebar" class="fixed inset-y-0 right-0 w-full md:w-[450px] glass-dark z-[80] transform translate-x-full transition-transform duration-500 ease-in-out flex flex-col shadow-2xl">
        <div class="p-8 flex flex-col h-full overflow-y-auto hide-scroll">
            <div class="flex justify-between items-center mb-8">
                <h2 class="text-2xl font-serif italic text-indigo-400">Marketplace</h2>
                <button onclick="toggleMenu()" class="text-white/50 hover:text-white"><i data-lucide="x"></i></button>
            </div>

            <input type="text" id="search" onkeyup="filterItems()" placeholder="O que você procura hoje?" class="w-full bg-white/5 border border-white/10 rounded-2xl py-3 px-6 mb-6 focus:outline-none focus:border-indigo-500 text-sm text-white">

            <div id="product-list" class="space-y-4 mb-8"></div>

            <div class="mt-auto pt-6 border-t border-white/10">
                <div class="flex justify-between items-center mb-6">
                    <span class="text-gray-400">Total Estimado</span>
                    <span id="total-price" class="text-2xl font-bold text-indigo-400">R$ 0,00</span>
                </div>
                <button class="w-full py-4 bg-white text-black font-bold rounded-2xl hover:bg-indigo-500 hover:text-white transition mb-4">FINALIZAR SELEÇÃO</button>
                
                <button onclick="acessarRH()" class="w-full py-3 bg-transparent border border-indigo-500/50 text-indigo-400 font-bold rounded-2xl hover:bg-indigo-500 hover:text-white transition flex items-center justify-center gap-2 text-sm">
                    <i data-lucide="lock" class="w-4 h-4"></i> ÁREA DO RH (PRIVADO)
                </button>
            </div>
        </div>
    </div>

    <div id="rhPanel" class="fixed inset-0 z-[100] hidden flex items-center justify-center p-4">
        <div class="absolute inset-0 bg-black/95 modal-blur"></div>
        <div class="relative w-full max-w-4xl bg-black/80 border border-white/10 rounded-[3rem] p-8 md:p-12 h-[90vh] overflow-y-auto hide-scroll">
            <div class="flex justify-between items-center mb-10">
                <h2 class="text-3xl font-serif italic">Ficha de Avaliação de Candidato</h2>
                <button onclick="fecharRH()" class="text-white/50 hover:text-white"><i data-lucide="x"></i></button>
            </div>

            <div class="mb-10">
                <label class="text-xs text-gray-500 uppercase tracking-widest">Nome do Candidato ou Candidata</label>
                <input type="text" placeholder="Nome completo..." class="w-full bg-white/5 border border-white/10 rounded-xl py-4 px-6 mt-2 focus:border-indigo-500 outline-none text-white">
            </div>

            <div id="lista-perguntas" class="space-y-8"></div>

            <div class="mt-12">
                <label class="text-xs text-indigo-400 uppercase font-bold tracking-widest">Observações do Entrevistador</label>
                <textarea rows="4" placeholder="O que você achou desta pessoa?" class="w-full bg-white/5 border border-white/10 rounded-2xl py-4 px-6 mt-3 focus:border-indigo-500 outline-none text-white"></textarea>
            </div>

            <button onclick="window.print()" class="w-full mt-10 py-5 bg-white text-black font-bold rounded-2xl hover:bg-indigo-500 hover:text-white transition uppercase tracking-widest">Salvar Avaliação</button>
        </div>
    </div>

    <section class="h-screen bg-section flex items-center justify-center text-center px-6" style="background-image: url('https://images.unsplash.com/photo-1534723452862-4c874018d66d?q=80&w=1920');">
        <div class="absolute inset-0 bg-black/60"></div>
        <div class="z-10" data-aos="zoom-out">
            <h1 class="text-8xl md:text-[10rem] font-bold leading-tight">Grupo 1</h1>
            <p class="text-xl md:text-2xl italic text-gray-300">Excelência operacional em cada detalhe.</p>
        </div>
    </section>

    <section class="min-h-screen bg-section py-24 flex items-center" style="background-image: url('https://images.unsplash.com/photo-1510812431401-41d2bd2722f3?q=80&w=1920');">
        <div class="absolute inset-0 bg-black/80"></div>
        <div class="container mx-auto px-6 grid md:grid-cols-2 gap-12 items-center relative z-10">
            <div data-aos="fade-right">
                <h2 class="text-6xl italic mb-6">Adega <br><span class="text-red-600 font-bold not-italic">Exclusiva</span></h2>
                <p class="text-lg text-gray-300 mb-8">Vinhos selecionados com curadoria.</p>
                <img src="https://images.unsplash.com/photo-1584916201218-f4242ceb4809?w=400" class="rounded-[2rem] w-full max-w-xs shadow-2xl" alt="Vinho">
            </div>
            <div class="glass p-10 rounded-[3rem] border-r-4 border-red-600 text-right" data-aos="fade-left">
                <h3 class="text-3xl font-bold mb-4">Vinho Tinto Reserva</h3>
                <p class="text-4xl font-bold text-red-500 mb-8">R$ 189,90 <span class="text-sm text-gray-500">/ un</span></p>
                <button onclick="addToCart(6)" class="bg-red-600 px-8 py-4 rounded-2xl font-bold hover:bg-white hover:text-black transition">ADICIONAR</button>
            </div>
        </div>
    </section>

    <section class="min-h-screen bg-section py-24 flex items-center" style="background-image: url('https://images.unsplash.com/photo-1519708227418-c8fd9a32b7a2?q=80&w=1920');">
        <div class="absolute inset-0 bg-black/60"></div>
        <div class="container mx-auto px-6 grid md:grid-cols-2 gap-12 items-center relative z-10">
            <div class="order-2 md:order-1 glass p-10 rounded-[3rem] border-l-4 border-cyan-500" data-aos="fade-right">
                <h3 class="text-3xl font-bold mb-4">Salmão Chileno</h3>
                <p class="text-4xl font-bold text-cyan-400 mb-8">R$ 94,50 <span class="text-sm text-gray-500">/ kg</span></p>
                <button onclick="addToCart(4)" class="bg-cyan-600 px-8 py-4 rounded-2xl font-bold hover:bg-white hover:text-black transition">ADICIONAR</button>
            </div>
            <div class="order-1 md:order-2 text-right" data-aos="fade-left">
                <h2 class="text-6xl italic mb-6 text-cyan-400 font-bold">Frescor <span class="text-white">Marinho</span></h2>
                <img src="https://images.unsplash.com/photo-1485921325814-da976339d320?w=400" class="rounded-[2rem] w-full max-w-xs ml-auto" alt="Salmão">
            </div>
        </div>
    </section>

    <footer class="py-24 border-t border-white/5 text-center bg-black">
        <a href="mailto:efraimalmeida040@gmail.com" class="text-xl font-light underline">efraimalmeida040@gmail.com</a>
    </footer>

    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script>
        AOS.init();
        lucide.createIcons();

        const products = [
            { id: 1, name: "Leite Integral Itambé", price: 6.89, img: "https://images.unsplash.com/photo-1563636619-e9143da7973b?w=200", brand: "Unidade" },
            { id: 2, name: "Leite Piracanjuba", price: 7.45, img: "https://images.unsplash.com/photo-1550989460-0adf9ea622e2?w=200", brand: "Unidade" },
            { id: 4, name: "Salmão Chileno", price: 94.50, img: "https://images.unsplash.com/photo-1519708227418-c8fd9a32b7a2?w=200", brand: "kg" },
            { id: 6, name: "Vinho Tinto Reserva", price: 189.90, img: "https://images.unsplash.com/photo-1584916201218-f4242ceb4809?w=200", brand: "unidade" }
        ];

        let cart = [];
        function toggleMenu() { document.getElementById('sidebar').classList.toggle('translate-x-full'); }

        function renderProducts(items) {
            const list = document.getElementById('product-list');
            list.innerHTML = items.map(p => `
                <div class="glass p-4 rounded-2xl flex items-center gap-4 group">
                    <img src="${p.img}" class="w-16 h-16 rounded-xl object-cover">
                    <div class="flex-1">
                        <h4 class="text-sm font-bold">${p.name}</h4>
                        <p class="text-indigo-400 font-bold">R$ ${p.price.toFixed(2)}</p>
                    </div>
                    <button onclick="addToCart(${p.id})" class="bg-indigo-600 p-3 rounded-xl hover:bg-white hover:text-black transition">
                        <i data-lucide="shopping-cart" class="w-4 h-4"></i>
                    </button>
                </div>
            `).join('');
            lucide.createIcons();
        }

        function addToCart(id) {
            const p = products.find(x => x.id === id);
            cart.push(p);
            updateCart();
        }

        function updateCart() {
            const total = cart.reduce((s, i) => s + i.price, 0);
            document.getElementById('cart-count').innerText = cart.length;
            document.getElementById('total-price').innerText = `R$ ${total.toFixed(2)}`;
        }

        function acessarRH() {
            const senha = prompt("Senha do RH:");
            if (senha === "Salmos 1") {
                document.getElementById('rhPanel').classList.remove('hidden');
                document.getElementById('sidebar').classList.add('translate-x-full');
                montarPerguntas();
            } else { alert("Acesso negado."); }
        }

        function fecharRH() { document.getElementById('rhPanel').classList.add('hidden'); }

        function montarPerguntas() {
            const perguntas = [
                { cat: "Frequentes", q: "Fale um pouco sobre sua trajetória profissional." },
                { cat: "Frequentes", q: "Por que você quer trabalhar no Grupo 1?" },
                { cat: "Básicas", q: "Tem disponibilidade para escalas 6x1?" },
                { cat: "Situacionais", q: "O que faria ao ver um colega tratando um cliente mal?" }
            ];
            document.getElementById('lista-perguntas').innerHTML = perguntas.map((p, i) => `
                <div class="bg-white/5 p-5 rounded-2xl flex justify-between items-center">
                    <p class="text-sm">${p.q}</p>
                    <div class="flex gap-4">
                        <label><input type="radio" name="p${i}"> SIM</label>
                        <label><input type="radio" name="p${i}"> NÃO</label>
                    </div>
                </div>
            `).join('');
        }

        renderProducts(products);
    </script>
</body>
</html>


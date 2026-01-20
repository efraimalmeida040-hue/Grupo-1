# Grupo-1
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
    <style>
        body { font-family: 'sans-serif'; background: #050505; color: white; }
        .glass { background: rgba(255, 255, 255, 0.03); backdrop-filter: blur(15px); border: 1px solid rgba(255, 255, 255, 0.1); }
        .bg-section { background-size: cover; background-position: center; background-attachment: fixed; }
    </style>
</head>
<body>
    <div id="sidebar" class="fixed inset-y-0 right-0 w-72 bg-black/95 z-[100] transform translate-x-full transition-transform p-6 border-l border-white/10">
        <button onclick="toggleMenu()" class="mb-8">Fechar X</button>
        <button onclick="acessarRH()" class="w-full py-4 bg-indigo-600 rounded-xl font-bold">ÁREA DO RH (Senha)</button>
    </div>

    <button onclick="toggleMenu()" class="fixed top-5 right-5 z-[110] bg-white/10 p-3 rounded-full">Menu</button>

    <section class="h-screen flex items-center justify-center bg-section" style="background-image: url('https://images.unsplash.com/photo-1542838132-92c53300491e?q=80&w=1920');">
        <div class="absolute inset-0 bg-black/50"></div>
        <div class="text-center z-10" data-aos="fade-up">
            <h1 class="text-7xl font-bold">Grupo 1</h1>
            <p class="text-xl italic mt-4 text-gray-300">Excelência em cada detalhe.</p>
        </div>
    </section>

    <section class="py-20 px-6 container mx-auto grid md:grid-cols-2 gap-10">
        <div class="glass p-8 rounded-3xl" data-aos="fade-right">
            <img src="https://images.unsplash.com/photo-1584916201218-f4242ceb4809?w=500" class="rounded-2xl mb-6">
            <h3 class="text-2xl font-bold">Vinho Reserva Especial</h3>
            <p class="text-indigo-400 text-xl font-bold mt-2">R$ 189,90</p>
        </div>
        <div class="glass p-8 rounded-3xl" data-aos="fade-left">
            <img src="https://images.unsplash.com/photo-1519708227418-c8fd9a32b7a2?w=500" class="rounded-2xl mb-6">
            <h3 class="text-2xl font-bold">Salmão Fresco Chileno</h3>
            <p class="text-indigo-400 text-xl font-bold mt-2">R$ 94,50/kg</p>
        </div>
    </section>

    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script>
        AOS.init();
        function toggleMenu() { document.getElementById('sidebar').classList.toggle('translate-x-full'); }
        function acessarRH() {
            const senha = prompt("Digite a senha do RH:");
            if(senha === "Salmos 1") { alert("Acesso Autorizado! Carregando painel..."); }
            else { alert("Senha incorreta."); }
        }
    </script>
</body>
</html>

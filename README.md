<!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Passeios da Maria | Viagens com Alma</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600;700&family=Playfair+Display:wght@700;900&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #0f172a; 
            --accent: #ff6b6b;  
            --secondary: #0ea5e9; 
        }
        body { font-family: 'Montserrat', sans-serif; overflow-x: hidden; }
        h1, h2, h3, .font-serif { font-family: 'Playfair Display', serif; }
        
        .hero-bg {
            background: linear-gradient(rgba(15, 23, 42, 0.5), rgba(15, 23, 42, 0.5)), url('https://images.unsplash.com/photo-1476514525535-07fb3b4ae5f1?auto=format&fit=crop&w=1920&q=80');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
        }

        .glass-nav {
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
        }

        .destination-card img { transition: transform 0.7s cubic-bezier(0.4, 0, 0.2, 1); }
        .destination-card:hover img { transform: scale(1.1); }

        .btn-coral {
            background-color: var(--accent);
            transition: all 0.3s ease;
        }
        .btn-coral:hover {
            background-color: #fa5252;
            transform: translateY(-2px);
            box-shadow: 0 10px 20px -5px rgba(255, 107, 107, 0.4);
        }

        .testimonial-glow {
            box-shadow: 0 0 40px rgba(14, 165, 233, 0.1);
        }

        .hidden-page { display: none; }
        
        .logo-placeholder {
            background: #0ea5e9;
            color: white;
            font-weight: bold;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 8px;
        }

        #mobile-menu {
            transition: transform 0.3s ease-in-out;
            transform: translateX(100%);
        }
        #mobile-menu.active {
            transform: translateX(0);
        }

        /* Suavizar o scroll para o GitHub Pages */
        html { scroll-behavior: smooth; }
    </style>
</head>
<body class="bg-white text-slate-900">

    <!-- Navegação -->
    <nav class="fixed w-full z-50 glass-nav border-b border-slate-100 transition-all duration-300">
        <div class="max-w-7xl mx-auto px-6 h-20 flex justify-between items-center transition-all duration-300" id="nav-container">
            <a href="javascript:void(0)" onclick="showPage('home')" class="flex items-center">
                <!-- Fallback: Tenta carregar o LOGO.jpg que deve estar na mesma pasta no GitHub -->
                <img src="LOGO.jpg" alt="Passeios da Maria" class="h-12 w-auto" id="nav-logo" onerror="this.style.display='none'; document.getElementById('logo-text').style.display='block'">
                <span id="logo-text" class="hidden font-serif text-xl font-bold text-sky-600">Passeios da Maria</span>
            </a>
            
            <!-- Desktop Menu -->
            <div class="hidden lg:flex items-center space-x-8 font-semibold text-xs uppercase tracking-widest text-slate-700">
                <a href="javascript:void(0)" onclick="showPage('home')" class="hover:text-sky-500 transition-colors">Início</a>
                <a href="javascript:void(0)" onclick="showPage('7dias')" class="hover:text-sky-500 transition-colors">7 Dias</a>
                <a href="javascript:void(0)" onclick="showPage('cruzeiros')" class="hover:text-sky-500 transition-colors">Cruzeiros</a>
                <a href="#testemunhos" class="hover:text-sky-500 transition-colors">Testemunhos</a>
                <a href="#contacto" class="btn-coral text-white px-7 py-3 rounded-full shadow-lg">Planear com a Maria</a>
            </div>

            <!-- Mobile Toggle -->
            <button class="lg:hidden text-2xl p-2" onclick="toggleMenu(true)" aria-label="Abrir Menu">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7" />
                </svg>
            </button>
        </div>
    </nav>

    <!-- Mobile Menu Sidebar -->
    <div id="mobile-menu" class="fixed inset-0 z-[60] bg-white p-8 lg:hidden flex flex-col">
        <button class="self-end text-4xl mb-8" onclick="toggleMenu(false)">&times;</button>
        <div class="flex flex-col space-y-6 text-2xl font-bold text-slate-800">
            <a href="javascript:void(0)" onclick="showPage('home'); toggleMenu(false)">Início</a>
            <a href="javascript:void(0)" onclick="showPage('7dias'); toggleMenu(false)">Viagens 7 Dias</a>
            <a href="javascript:void(0)" onclick="showPage('cruzeiros'); toggleMenu(false)">Cruzeiros</a>
            <a href="#testemunhos" onclick="toggleMenu(false)">Testemunhos</a>
            <a href="#contacto" onclick="toggleMenu(false)" class="text-orange-500">Contactar Maria</a>
        </div>
    </div>

    <!-- PÁGINA INICIAL -->
    <main id="page-home" class="page-content">
        <!-- Hero Section -->
        <header class="hero-bg h-screen flex items-center justify-center text-center px-4">
            <div class="max-w-5xl text-white">
                <span class="inline-block px-4 py-1 mb-6 border border-white/30 rounded-full text-xs font-bold uppercase tracking-[0.3em] backdrop-blur-sm">Viagens Personalizadas</span>
                <h1 class="text-5xl md:text-8xl font-black mb-8 leading-tight">A Maria leva-te a <br><span class="italic text-sky-300">conhecer o mundo</span>.</h1>
                <p class="text-lg md:text-xl mb-12 font-light max-w-2xl mx-auto leading-relaxed opacity-90">Roteiros autênticos desenhados para viajantes que procuram a alma de cada destino.</p>
                
                <div class="bg-white p-2 rounded-2xl md:rounded-full shadow-2xl flex flex-col md:flex-row gap-2 items-center max-w-4xl mx-auto text-slate-800">
                    <div class="flex-1 w-full flex items-center px-6 py-3 border-b md:border-b-0 md:border-r border-slate-100">
                        <span class="mr-3 text-sky-500">📍</span>
                        <input type="text" placeholder="Para onde queres ir?" class="w-full focus:outline-none font-medium">
                    </div>
                    <div class="flex-1 w-full flex items-center px-6 py-3 border-b md:border-b-0 md:border-r border-slate-100">
                        <span class="mr-3 text-sky-500">📅</span>
                        <input type="text" placeholder="Quando?" onfocus="(this.type='date')" class="w-full focus:outline-none font-medium">
                    </div>
                    <button onclick="document.getElementById('contacto').scrollIntoView({behavior: 'smooth'})" class="w-full md:w-auto btn-coral text-white px-10 py-4 rounded-xl md:rounded-full font-bold">
                        Descobrir
                    </button>
                </div>
            </div>
        </header>

        <!-- Destinos Populares -->
        <section class="py-24 px-6 max-w-7xl mx-auto">
            <div class="flex flex-col md:flex-row justify-between items-end mb-16 gap-4">
                <div>
                    <span class="text-sky-500 font-bold tracking-widest text-xs uppercase">Sugestões da Maria</span>
                    <h2 class="text-4xl md:text-5xl font-bold mt-2 font-serif">Destaques do Mês</h2>
                </div>
                <button onclick="showPage('7dias')" class="text-sm font-bold text-sky-600 hover:underline">Ver todas as viagens →</button>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <!-- Azores -->
                <div class="destination-card relative group h-[450px] rounded-[2.5rem] overflow-hidden shadow-xl cursor-pointer">
                    <img src="https://images.unsplash.com/photo-1590001140517-7393439e6074?auto=format&fit=crop&w=800&q=80" class="w-full h-full object-cover" alt="Açores">
                    <div class="absolute inset-0 bg-gradient-to-t from-slate-900/90 via-transparent p-8 flex flex-col justify-end text-white">
                        <h3 class="text-2xl font-bold">Açores</h3>
                        <p class="text-sky-300">A Natureza em Estado Puro</p>
                    </div>
                </div>
                <!-- Vietnam -->
                <div class="destination-card relative group h-[450px] rounded-[2.5rem] overflow-hidden shadow-xl cursor-pointer">
                    <img src="https://images.unsplash.com/photo-1528127269322-539801943592?auto=format&fit=crop&w=800&q=80" class="w-full h-full object-cover" alt="Vietname">
                    <div class="absolute inset-0 bg-gradient-to-t from-slate-900/90 via-transparent p-8 flex flex-col justify-end text-white">
                        <h3 class="text-2xl font-bold">Vietname</h3>
                        <p class="text-sky-300">Cultura e Tradição</p>
                    </div>
                </div>
                <!-- Santorini -->
                <div class="destination-card relative group h-[450px] rounded-[2.5rem] overflow-hidden shadow-xl cursor-pointer">
                    <img src="https://images.unsplash.com/photo-1533105079780-92b9be482077?auto=format&fit=crop&w=800&q=80" class="w-full h-full object-cover" alt="Santorini">
                    <div class="absolute inset-0 bg-gradient-to-t from-slate-900/90 via-transparent p-8 flex flex-col justify-end text-white">
                        <h3 class="text-2xl font-bold">Santorini</h3>
                        <p class="text-sky-300">O Pôr do Sol Perfeito</p>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- PÁGINA: VIAGENS DE 7 DIAS -->
    <section id="page-7dias" class="page-content hidden-page pt-32 pb-24 px-6 max-w-7xl mx-auto">
        <div class="text-center mb-16">
            <span class="text-orange-500 font-bold tracking-widest text-xs uppercase">Itinerários Completos</span>
            <h2 class="text-4xl md:text-6xl font-bold mt-2 font-serif">Uma Semana de Magia</h2>
            <p class="text-slate-500 mt-4 max-w-2xl mx-auto">Experiências curadas para quem tem 7 dias para desligar e reconectar.</p>
        </div>

        <div class="grid gap-12">
            <div class="flex flex-col lg:flex-row bg-slate-50 rounded-[3rem] overflow-hidden shadow-sm border border-slate-100">
                <div class="lg:w-1/2 h-[450px]">
                    <img src="https://images.unsplash.com/photo-1520175480921-4edfa06830b1?auto=format&fit=crop&w=1200&q=80" class="w-full h-full object-cover" alt="Costa Amalfitana">
                </div>
                <div class="lg:w-1/2 p-12 flex flex-col justify-center">
                    <div class="flex items-center space-x-2 text-sky-500 font-bold text-sm mb-4 uppercase tracking-tighter">
                        <span>🗓️ 7 Dias / 6 Noites</span>
                        <span>•</span>
                        <span>Itália</span>
                    </div>
                    <h3 class="text-4xl font-bold mb-6 font-serif">Costa Amalfitana: O Sonho Italiano</h3>
                    <p class="text-slate-600 mb-8 leading-relaxed">Vilas coloridas, gastronomia autêntica e o azul infinito do Mediterrâneo num roteiro de luxo acessível.</p>
                    <div class="flex items-center justify-between border-t border-slate-200 pt-8">
                        <div class="flex flex-col">
                            <span class="text-slate-400 text-xs uppercase font-bold">Desde</span>
                            <span class="text-3xl font-black text-slate-900">1.850€</span>
                        </div>
                        <button onclick="document.getElementById('contacto').scrollIntoView({behavior: 'smooth'})" class="btn-coral text-white px-8 py-4 rounded-full font-bold">Ver Itinerário</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- PÁGINA: CRUZEIROS -->
    <section id="page-cruzeiros" class="page-content hidden-page pt-32 pb-24 px-6 bg-sky-50/50">
        <div class="max-w-7xl mx-auto">
            <div class="text-center mb-16">
                <span class="text-sky-600 font-bold tracking-widest text-xs uppercase">Experiência a Bordo</span>
                <h2 class="text-4xl md:text-6xl font-bold mt-2 font-serif">Cruzeiros Selecionados</h2>
                <p class="text-slate-500 mt-4 max-w-2xl mx-auto">Navios que são destinos em si mesmos, com as melhores rotas globais.</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-12">
                <div class="bg-white rounded-[3rem] overflow-hidden shadow-xl transition-all hover:shadow-2xl">
                    <div class="relative h-80">
                        <img src="https://images.unsplash.com/photo-1548574505-5e239809ee19?auto=format&fit=crop&w=1200&q=80" class="w-full h-full object-cover" alt="Cruzeiro">
                        <div class="absolute top-6 left-6 bg-white/95 backdrop-blur px-4 py-2 rounded-full text-xs font-bold text-sky-600 shadow-md">MEDITERRÂNEO</div>
                    </div>
                    <div class="p-10 text-center md:text-left">
                        <h3 class="text-3xl font-bold mb-4 font-serif">Tesouros do Adriático</h3>
                        <p class="text-slate-500 mb-8">Passe por Veneza, Dubrovnik e as Ilhas Gregas num navio de última geração.</p>
                        <div class="flex flex-col md:flex-row items-center justify-between gap-4">
                            <span class="text-3xl font-black text-sky-600">Desde 980€</span>
                            <button onclick="document.getElementById('contacto').scrollIntoView({behavior: 'smooth'})" class="bg-sky-600 text-white px-8 py-3 rounded-full font-bold hover:bg-sky-700 transition-colors">Mais Detalhes</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- SECÇÕES COMUNS -->
    <div id="common-sections">
        <!-- Testemunhos -->
        <section id="testemunhos" class="py-24 bg-white overflow-hidden">
            <div class="max-w-7xl mx-auto px-6 text-center">
                <span class="text-sky-500 font-bold tracking-widest text-xs uppercase">Comunidade Maria</span>
                <h2 class="text-4xl font-bold mt-2 mb-16 font-serif">Histórias de quem viajou</h2>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-10">
                    <div class="bg-slate-50 p-10 rounded-[2.5rem] testimonial-glow text-left">
                        <div class="flex items-center space-x-4 mb-6">
                            <div class="w-12 h-12 rounded-full bg-sky-200 flex items-center justify-center font-bold text-sky-700">AS</div>
                            <div><h4 class="font-bold">Ana Silva</h4><p class="text-xs text-slate-400">Açores</p></div>
                        </div>
                        <p class="text-slate-600 italic">"A organização foi impecável. Não tive de me preocupar com nada."</p>
                    </div>
                    <div class="bg-white p-10 rounded-[2.5rem] border border-slate-100 shadow-xl text-left scale-105 z-10">
                        <div class="flex items-center space-x-4 mb-6">
                            <div class="w-12 h-12 rounded-full bg-orange-200 flex items-center justify-center font-bold text-orange-700">RG</div>
                            <div><h4 class="font-bold">Ricardo G.</h4><p class="text-xs text-slate-400">Cruzeiros</p></div>
                        </div>
                        <p class="text-slate-600 italic">"A melhor experiência em família que já tivemos. Obrigado Maria!"</p>
                    </div>
                    <div class="bg-slate-50 p-10 rounded-[2.5rem] testimonial-glow text-left">
                        <div class="flex items-center space-x-4 mb-6">
                            <div class="w-12 h-12 rounded-full bg-emerald-200 flex items-center justify-center font-bold text-emerald-700">MC</div>
                            <div><h4 class="font-bold">Marta C.</h4><p class="text-xs text-slate-400">Itália</p></div>
                        </div>
                        <p class="text-slate-600 italic">"Recomendo a qualquer pessoa que procure uma viagem autêntica."</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Contacto -->
        <section id="contacto" class="py-24 px-6">
            <div class="max-w-6xl mx-auto flex flex-col lg:flex-row bg-slate-900 rounded-[3rem] overflow-hidden shadow-2xl">
                <div class="lg:w-1/3 p-12 bg-sky-900 text-white flex flex-col items-center text-center">
                    <div class="w-32 h-32 mb-8 rounded-full bg-white flex items-center justify-center p-4">
                         <img src="LOGO.jpg" alt="Maria" class="max-h-full max-w-full" onerror="this.outerHTML='<span class=\'text-sky-900 font-bold\'>PM</span>'">
                    </div>
                    <h2 class="text-3xl font-bold mb-6 font-serif">Fale com a Maria</h2>
                    <p class="opacity-80 mb-10 text-sm">Pronta para transformar o teu próximo destino numa memória eterna.</p>
                    <div class="text-left w-full space-y-6">
                        <div class="flex items-center">
                            <span class="w-10 h-10 rounded-full bg-white/10 flex items-center justify-center mr-4">📞</span>
                            <span class="text-sm">+351 912 345 678</span>
                        </div>
                        <div class="flex items-center">
                            <span class="w-10 h-10 rounded-full bg-white/10 flex items-center justify-center mr-4">✉️</span>
                            <span class="text-sm">bcsilva2003@gmail.com</span>
                        </div>
                    </div>
                </div>
                <div class="lg:w-2/3 p-12 bg-white">
                    <form action="https://formspree.io/f/xvgzvzvz" method="POST" id="budget-form" class="space-y-6">
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                            <div class="space-y-2">
                                <label class="text-xs font-bold uppercase text-slate-400">Nome Completo</label>
                                <input type="text" name="nome" placeholder="Seu nome aqui" class="w-full px-6 py-4 bg-slate-50 border border-slate-100 rounded-2xl focus:border-sky-500 outline-none" required>
                            </div>
                            <div class="space-y-2">
                                <label class="text-xs font-bold uppercase text-slate-400">Teu Email</label>
                                <input type="email" name="email" placeholder="email@exemplo.com" class="w-full px-6 py-4 bg-slate-50 border border-slate-100 rounded-2xl focus:border-sky-500 outline-none" required>
                            </div>
                        </div>
                        <div class="space-y-2">
                            <label class="text-xs font-bold uppercase text-slate-400">Detalhes do Pedido</label>
                            <textarea name="mensagem" placeholder="Para onde gostaria de ir?" rows="4" class="w-full px-6 py-4 bg-slate-50 border border-slate-100 rounded-2xl focus:border-sky-500 outline-none" required></textarea>
                        </div>
                        <button type="submit" class="btn-coral text-white w-full py-5 rounded-2xl font-bold text-lg shadow-xl">Enviar Pedido à Maria</button>
                    </form>
                </div>
            </div>
        </section>
    </div>

    <!-- Feedback Toast -->
    <div id="toast" class="fixed bottom-10 left-1/2 transform -translate-x-1/2 z-[100] opacity-0 translate-y-10 transition-all duration-500 pointer-events-none">
        <div class="bg-slate-900 text-white px-8 py-4 rounded-full shadow-2xl flex items-center space-x-3">
            <span class="text-sky-400">✨</span>
            <span id="toast-text" class="text-sm font-medium"></span>
        </div>
    </div>

    <!-- Rodapé -->
    <footer class="bg-slate-950 text-white pt-20 pb-10 px-6 text-center">
        <p class="text-slate-500 text-sm">© 2024 Passeios da Maria. Viagens com alma.</p>
    </footer>

    <script>
        function showToast(msg) {
            const toast = document.getElementById('toast');
            document.getElementById('toast-text').innerText = msg;
            toast.classList.replace('opacity-0', 'opacity-100');
            toast.classList.replace('translate-y-10', 'translate-y-0');
            setTimeout(() => {
                toast.classList.replace('opacity-100', 'opacity-0');
                toast.classList.replace('translate-y-0', 'translate-y-10');
            }, 4000);
        }

        function showPage(pageId) {
            document.querySelectorAll('.page-content').forEach(p => p.classList.add('hidden-page'));
            const target = document.getElementById('page-' + pageId);
            if(target) target.classList.remove('hidden-page');
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function toggleMenu(show) {
            const menu = document.getElementById('mobile-menu');
            if(show) menu.classList.add('active');
            else menu.classList.remove('active');
        }

        window.addEventListener('scroll', () => {
            const nav = document.querySelector('nav');
            const navContainer = document.getElementById('nav-container');
            if (window.scrollY > 50) {
                navContainer.classList.replace('h-20', 'h-16');
                nav.classList.add('shadow-lg');
            } else {
                navContainer.classList.replace('h-16', 'h-20');
                nav.classList.remove('shadow-lg');
            }
        });

        document.getElementById('budget-form').addEventListener('submit', function() {
            showToast('A enviar pedido para a Maria...');
        });
    </script>

🌍 Passeios da Maria - Agência de Viagens

Bem-vindo ao repositório oficial da Passeios da Maria. Este projeto contém o website institucional e os ativos visuais para uma agência de viagens focada em experiências personalizadas, cruzeiros e roteiros culturais.

🖼️ Ativos Visuais (Links Diretos)

Para garantir que as imagens carregam corretamente no website (contornando as restrições de visualização padrão do GitHub), utilizamos os links Raw.

Imagem

Finalidade

Link Direto (Raw)

LOGO.jpg

Logótipo da Marca

https://raw.githubusercontent.com/bcsilva2003/Agencia-De-Viagens/main/LOGO.jpg

DIA21.jpg

Cartaz Cruzeiro Douro

https://raw.githubusercontent.com/bcsilva2003/Agencia-De-Viagens/0c383296b277449571b3b7c4fa4a3473924044fc/DIA21.jpg

🚀 O Website (index.html)

O site foi desenvolvido como uma SPA (Single Page Application) moderna, utilizando:

Tailwind CSS: Design responsivo e premium.

JavaScript: Navegação dinâmica e lógica de pré-preenchimento de formulários.

Formspree: Integração para envio de formulários diretamente para o email de reservas.

Funcionalidades Implementadas:

Formulário de Orçamento Ativo: Sistema configurado para enviar pedidos para reservas.passeiosdamaria@gmail.com.

Página de Cruzeiros: Secção dedicada a ofertas sazonais com detalhe em modal.

Integração Inteligente: A barra de pesquisa inicial preenche automaticamente o formulário de contacto para facilitar a conversão.

Responsividade Total: Otimizado para telemóveis, tablets e desktop.

🚢 Oferta em Destaque: Cruzeiro no Douro 2026

Informações Principais:

📅 Data: 21 de Junho de 2026

💰 Preço: 119€ por pessoa

📍 Itinerário: Barca d’Alva → Peso da Régua

🚌 Saídas: Lisboa, Loures, Odivelas, Almada, Amadora, Sete Rios, Campo Grande, Alverca, Vila Franca de Xira, Carregado, Torres Novas, Leiria e Coimbra.

🛠️ Como Utilizar este Repositório

Ativação do Formulário: Na primeira submissão de teste através do site, o Formspree enviará um email de confirmação para o endereço de reservas. É necessário clicar no link desse email para ativar o envio automático de mensagens.

Edição: O ficheiro index.html contém todo o estilo e lógica. As secções estão identificadas com IDs (ex: page-home, page-cruzeiros).

📞 Contactos Oficiais

Telefones: 219 597 638 | 962 838 175 | 939 385 492

Emails: maria@passeiosdamaria.pt | reservas.passeiosdamaria@gmail.com

Licença: RNAVT 11763

Mantido por bcsilva2003

<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>INDUMAG | Autoridad y Confianza</title>
    <style>
        :root {
            --verde: #519a2e;
            --bezier-fluido: cubic-bezier(0.4, 0, 0.2, 1);
            --tiempo: 1s;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Segoe UI', Roboto, sans-serif; }
        body { background: #fff; height: 100vh; display: flex; flex-direction: column; overflow: hidden; }

        /* HEADER */
        .header { padding: 12px 15px; background: #fff; z-index: 100; border-bottom: 1px solid #eee; }
        .header-top { display: flex; justify-content: space-between; align-items: center; margin-bottom: 8px; }
        .logo { height: 35px; }
        .header-icons { display: flex; gap: 15px; color: #333; }
        
        .search-box { 
            width: 100%; border: 1px solid #ddd; border-radius: 10px; 
            padding: 8px 12px; display: flex; align-items: center; background: #f9f9f9;
        }
        .search-box input { border: none; background: none; outline: none; width: 100%; padding-left: 8px; font-size: 14px; }

        /* CONTENEDOR SPLIT */
        .split-container { flex: 1; display: flex; flex-direction: column; overflow: hidden; background: #000; }

        .section {
            position: relative; flex: 1; display: flex; align-items: center;
            padding: 0 35px; text-decoration: none;
            transition: flex var(--tiempo) var(--bezier-fluido);
            overflow: hidden; cursor: pointer; -webkit-tap-highlight-color: transparent;
        }

        .section.expanded { flex: 4; }

        /* ANIMACIÓN DE ENTRADA */
        @keyframes introExpand {
            0% { flex: 1; }
            40% { flex: 2.2; }
            100% { flex: 1; }
        }
        .hint-animation { animation: introExpand 2.2s var(--bezier-fluido) 0.5s; }

        .bg-img {
            position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            background-size: cover; background-position: center; z-index: 1;
            transition: transform 2s var(--bezier-fluido);
        }
        .section.expanded .bg-img { transform: scale(1.1); }

        .section::after {
            content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            background: linear-gradient(90deg, rgba(0,0,0,0.85) 0%, rgba(0,0,0,0.2) 100%);
            z-index: 2;
        }

        .content { position: relative; z-index: 10; color: white; }
        .title-group h2 { font-size: 26px; font-weight: 800; text-transform: uppercase; line-height: 1; }
        .line { width: 45px; height: 4px; background: var(--verde); margin: 10px 0 15px 0; }
        
        .btn-verde {
            background: var(--verde); color: white; padding: 12px 24px; border-radius: 8px;
            font-weight: 700; font-size: 12px; text-transform: uppercase;
            display: inline-flex; align-items: center; gap: 10px;
        }

        /* FOOTER DE CONFIANZA - AQUÍ EL CAMBIO */
        .brand-footer { 
            padding: 25px 0 30px; 
            background: #fff; 
            overflow: hidden; 
            border-top: 2px solid #f5f5f5; 
        }
        
        .brand-footer h3 { 
            font-size: 16px; /* Aumentado para mayor legibilidad */
            text-align: center; 
            color: #1a1a1a; /* Más oscuro para que destaque */
            margin-bottom: 20px; 
            letter-spacing: 0.5px; 
            text-transform: uppercase; 
            font-weight: 800; /* Super negrita */
        }
        
        .brand-footer h3 span { 
            color: var(--verde); 
            background: rgba(81, 154, 46, 0.1); /* Sutil fondo resaltador */
            padding: 2px 8px;
            border-radius: 4px;
        }
        
        .track { 
            display: flex; 
            width: 300%; 
            animation: scroll-logos 35s linear infinite; 
            align-items: center;
        }
        .logo-box { width: 120px; margin: 0 30px; flex-shrink: 0; }
        .logo-box img { width: 100%; height: 28px; object-fit: contain; filter: grayscale(1); opacity: 0.6; }

        @keyframes scroll-logos {
            from { transform: translateX(0); }
            to { transform: translateX(-50%); }
        }

        @media (min-width: 768px) {
            .split-container { flex-direction: row; }
            .section.expanded { flex: 2.5; }
            .title-group h2 { font-size: 42px; }
            .brand-footer h3 { font-size: 20px; }
        }
    </style>
</head>
<body>

    <header class="header">
        <div class="header-top">
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT3lHMukjCrCLrU_YlVaEyp_6mOCRm556gKSQ&s" class="logo">
            <div class="header-icons">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"></path><circle cx="12" cy="7" r="4"></circle></svg>
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="3" y1="12" x2="21" y2="12"></line><line x1="3" y1="6" x2="21" y2="6"></line><line x1="3" y1="18" x2="21" y2="18"></line></svg>
            </div>
        </div>
        <div class="search-box">
            <input type="text" placeholder="¿En qué podemos ayudarte hoy?">
        </div>
    </header>

    <div class="split-container">
        <!-- SECCIÓN ARRIBA con intro suave -->
        <div class="section hint-animation" onclick="toggleSplit(this)">
            <div class="bg-img" style="background-image: url('https://images.unsplash.com/photo-1504328345606-18bbc8c9d7d1?q=80&w=1000');"></div>
            <div class="content">
                <div class="title-group">
                    <h2>SERVICIO<br>TÉCNICO</h2>
                    <div class="line"></div>
                </div>
                <div class="btn-verde">Solicitar Asistencia ❯</div>
            </div>
        </div>

        <!-- SECCIÓN ABAJO -->
        <div class="section" onclick="toggleSplit(this)">
            <div class="bg-img" style="background-image: url('https://images.unsplash.com/photo-1581092160562-40aa08e78837?q=80&w=1000');"></div>
            <div class="content">
                <div class="title-group">
                    <h2>EQUIPOS Y<br>REPUESTOS</h2>
                    <div class="line"></div>
                </div>
                <div class="btn-verde">Ver Catálogo ❯</div>
            </div>
        </div>
    </div>

    <!-- FOOTER POTENCIADO -->
    <div class="brand-footer">
        <h3>SERVICIO TÉCNICO <span>AUTORIZADO</span></h3>
        <div class="track">
            <div class="logo-box"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/16/Lincoln_Electric_logo.svg/1280px-Lincoln_Electric_logo.svg.png"></div>
            <div class="logo-box"><img src="https://millerweldseurope.com/wp-content/uploads/2021/09/Miller-Logo-C-2.png"></div>
            <div class="logo-box"><img src="https://ujueta.com/assets/marca-elite-DVCMNE0a.svg"></div>
            <div class="logo-box"><img src="https://www.harrisproductsgroup.com/-/media/images/harris-logo.png"></div>
            <!-- Bucle Infinito -->
            <div class="logo-box"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/16/Lincoln_Electric_logo.svg/1280px-Lincoln_Electric_logo.svg.png"></div>
            <div class="logo-box"><img src="https://millerweldseurope.com/wp-content/uploads/2021/09/Miller-Logo-C-2.png"></div>
            <div class="logo-box"><img src="https://ujueta.com/assets/marca-elite-DVCMNE0a.svg"></div>
            <div class="logo-box"><img src="https://www.harrisproductsgroup.com/-/media/images/harris-logo.png"></div>
        </div>
    </div>

    <script>
        function toggleSplit(element) {
            const sections = document.querySelectorAll('.section');
            sections.forEach(s => s.style.animation = 'none');
            const isExpanded = element.classList.contains('expanded');
            sections.forEach(s => s.classList.remove('expanded'));
            if (!isExpanded) {
                element.classList.add('expanded');
            }
        }
    </script>

</body>
</html>

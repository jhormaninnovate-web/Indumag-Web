<!DOCTYPE html>
<html lang="es">
<head>
    <!-- ESTA LÍNEA ES LA QUE HACE QUE SE VEA BIEN EN CELULARES -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>INDUMAG | Oficial</title>
    <style>
        :root {
            --verde: #519a2e;
            --bezier: cubic-bezier(0.4, 0, 0.2, 1);
            --tiempo: 0.8s;
        }

        /* Ajustes básicos para móviles */
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif; }
        
        html, body { 
            height: 100%; 
            width: 100%;
            background: #fff; 
            overflow: hidden; /* Evita scrolls raros */
            display: flex;
            flex-direction: column;
        }

        /* HEADER RESPONSIVE */
        .header { padding: 10px 15px; background: #fff; z-index: 100; border-bottom: 1px solid #eee; flex-shrink: 0; }
        .header-top { display: flex; justify-content: space-between; align-items: center; margin-bottom: 10px; }
        .logo { height: 32px; width: auto; }
        .header-icons { display: flex; gap: 15px; color: #333; }
        
        .search-box { 
            width: 100%; border: 1px solid #ddd; border-radius: 10px; 
            padding: 10px; display: flex; align-items: center; background: #f9f9f9;
        }
        .search-box input { border: none; background: none; outline: none; width: 100%; padding-left: 10px; font-size: 16px; } /* 16px evita zoom automático en iPhone */

        /* CONTENEDOR SPLIT DINÁMICO */
        .split-container { 
            flex: 1; 
            display: flex; 
            flex-direction: column; /* Vertical en móvil */
            overflow: hidden; 
            background: #000;
        }

        .section {
            position: relative;
            flex: 1;
            display: flex;
            align-items: center;
            padding: 0 10%;
            text-decoration: none;
            transition: flex var(--tiempo) var(--bezier);
            overflow: hidden;
            cursor: pointer;
            -webkit-tap-highlight-color: transparent;
        }

        .section.expanded { flex: 3; }

        /* ANIMACIÓN DE ENTRADA SUAVE */
        @keyframes introHint {
            0% { flex: 1; }
            40% { flex: 1.8; }
            100% { flex: 1; }
        }
        .hint-animation { animation: introHint 2s var(--bezier) 0.5s; }

        .bg-img {
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            background-size: cover;
            background-position: center;
            z-index: 1;
            transition: transform 2s var(--bezier);
        }
        .section.expanded .bg-img { transform: scale(1.1); }

        .section::after {
            content: '';
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            background: linear-gradient(0deg, rgba(0,0,0,0.8) 0%, rgba(0,0,0,0.2) 100%);
            z-index: 2;
        }

        .content { position: relative; z-index: 10; color: white; }
        .title-group h2 { font-size: 24px; font-weight: 800; text-transform: uppercase; line-height: 1.1; }
        .line { width: 40px; height: 4px; background: var(--verde); margin: 10px 0; }
        
        .btn-verde {
            background: var(--verde); color: white;
            padding: 12px 20px; border-radius: 8px;
            font-weight: 700; font-size: 12px; text-transform: uppercase;
            display: inline-flex; align-items: center; gap: 8px;
            margin-top: 10px;
        }

        /* SECCIÓN DE CONFIANZA (Sello Autorizado) */
        .brand-footer { 
            padding: 20px 0; 
            background: #fff; 
            overflow: hidden; 
            flex-shrink: 0;
            border-top: 2px solid #f0f0f0;
        }
        .brand-footer h3 { 
            font-size: 15px; /* Tamaño legible */
            text-align: center; 
            color: #1a1a1a; 
            margin-bottom: 15px; 
            text-transform: uppercase; 
            font-weight: 800;
            letter-spacing: 0.5px;
        }
        .brand-footer h3 span { color: var(--verde); border-bottom: 2px solid var(--verde); }
        
        .track { 
            display: flex; 
            width: 200%; 
            animation: scroll-logos 25s linear infinite; 
            align-items: center; 
        }
        .logo-box { width: 100px; margin: 0 20px; flex-shrink: 0; }
        .logo-box img { width: 100%; height: 22px; object-fit: contain; filter: grayscale(1); opacity: 0.5; }

        @keyframes scroll-logos {
            0% { transform: translateX(0); }
            100% { transform: translateX(-50%); }
        }

        /* AJUSTES PARA COMPUTADORA */
        @media (min-width: 768px) {
            .split-container { flex-direction: row; }
            .section.expanded { flex: 2.5; }
            .section::after { background: linear-gradient(90deg, rgba(0,0,0,0.8) 0%, rgba(0,0,0,0) 100%); }
            .title-group h2 { font-size: 40px; }
            .logo { height: 45px; }
            .brand-footer h3 { font-size: 20px; }
        }
    </style>
</head>
<body>

    <header class="header">
        <div class="header-top">
            <!-- Logo oficial de la imagen -->
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT3lHMukjCrCLrU_YlVaEyp_6mOCRm556gKSQ&s" class="logo">
            <div class="header-icons">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"></path><circle cx="12" cy="7" r="4"></circle></svg>
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><line x1="3" y1="12" x2="21" y2="12"></line><line x1="3" y1="6" x2="21" y2="6"></line><line x1="3" y1="18" x2="21" y2="18"></line></svg>
            </div>
        </div>
        <div class="search-box">
            <input type="text" placeholder="Buscar equipos o repuestos...">
        </div>
    </header>

    <div class="split-container">
        <!-- Sección 1 con animación de pista visual -->
        <div class="section hint-animation" id="sec1" onclick="toggleSplit(this)">
            <div class="bg-img" style="background-image: url('https://images.unsplash.com/photo-1504328345606-18bbc8c9d7d1?q=80&w=1000');"></div>
            <div class="content">
                <div class="title-group">
                    <h2>SERVICIO<br>TÉCNICO</h2>
                    <div class="line"></div>
                </div>
                <div class="btn-verde">Solicitar Asistencia ❯</div>
            </div>
        </div>

        <!-- Sección 2 -->
        <div class="section" id="sec2" onclick="toggleSplit(this)">
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

    <!-- SELLO DE CONFIANZA REFORZADO -->
    <div class="brand-footer">
        <h3>SERVICIO TÉCNICO <span>AUTORIZADO</span></h3>
        <div class="track">
            <div class="logo-box"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/16/Lincoln_Electric_logo.svg/1280px-Lincoln_Electric_logo.svg.png"></div>
            <div class="logo-box"><img src="https://millerweldseurope.com/wp-content/uploads/2021/09/Miller-Logo-C-2.png"></div>
            <div class="logo-box"><img src="https://ujueta.com/assets/marca-elite-DVCMNE0a.svg"></div>
            <div class="logo-box"><img src="https://www.harrisproductsgroup.com/-/media/images/harris-logo.png"></div>
            <!-- Duplicados para el carrusel infinito -->
            <div class="logo-box"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/16/Lincoln_Electric_logo.svg/1280px-Lincoln_Electric_logo.svg.png"></div>
            <div class="logo-box"><img src="https://millerweldseurope.com/wp-content/uploads/2021/09/Miller-Logo-C-2.png"></div>
            <div class="logo-box"><img src="https://ujueta.com/assets/marca-elite-DVCMNE0a.svg"></div>
            <div class="logo-box"><img src="https://www.harrisproductsgroup.com/-/media/images/harris-logo.png"></div>
        </div>
    </div>

    <script>
        function toggleSplit(element) {
            const sections = document.querySelectorAll('.section');
            
            // Si el usuario interactúa, quitamos la animación de intro
            sections.forEach(s => s.style.animation = 'none');

            const isExpanded = element.classList.contains('expanded');
            
            // Limpiamos estados
            sections.forEach(s => s.classList.remove('expanded'));

            // Si no estaba expandido, lo expandimos. Si ya lo estaba, vuelve al 50/50.
            if (!isExpanded) {
                element.classList.add('expanded');
            }
        }
    </script>

</body>
</html>

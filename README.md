<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>INDUMAG | Oficial</title>
    <style>
        :root {
            --verde: #519a2e;
            --bezier: cubic-bezier(0.4, 0, 0.2, 1);
            --tiempo: 0.7s;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Segoe UI', sans-serif; }
        
        html, body { 
            height: 100%; 
            width: 100%;
            background: #fff; 
            display: flex;
            flex-direction: column;
            overflow: hidden;
        }

        .header { 
            padding: 12px 15px; 
            background: #fff; 
            z-index: 100; 
            border-bottom: 1px solid #eee;
            flex-shrink: 0;
        }
        .header-top { display: flex; justify-content: space-between; align-items: center; margin-bottom: 10px; }
        .logo { height: 35px; width: auto; }
        .header-icons { display: flex; gap: 15px; color: #333; }
        
        .search-box { 
            width: 100%; border: 1px solid #ddd; border-radius: 12px; 
            padding: 10px 15px; display: flex; align-items: center; background: #fdfdfd;
            box-shadow: inset 0 1px 3px rgba(0,0,0,0.05);
        }
        .search-box input { border: none; background: none; outline: none; width: 100%; padding-left: 10px; font-size: 16px; color: #666; }

        .split-container { 
            flex: 1; 
            display: flex; 
            flex-direction: column;
            background: #000;
        }

        .section {
            position: relative;
            flex: 1;
            display: flex;
            align-items: center;
            padding: 0 10%;
            transition: flex var(--tiempo) var(--bezier);
            overflow: hidden;
            cursor: pointer;
            -webkit-tap-highlight-color: transparent;
        }

        @keyframes introBounce {
            0% { flex: 1; }
            40% { flex: 2; }
            100% { flex: 1; }
        }
        .hint { animation: introBounce 2.5s var(--bezier) 0.5s; }

        .section.expanded { flex: 4; }

        .bg-img {
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            background-size: cover;
            background-position: center;
            z-index: 1;
            transition: transform 1.5s var(--bezier);
        }
        .section.expanded .bg-img { transform: scale(1.1); }

        .section::after {
            content: '';
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            background: linear-gradient(0deg, rgba(0,0,0,0.85) 0%, rgba(0,0,0,0.2) 100%);
            z-index: 2;
        }

        .content { position: relative; z-index: 10; color: white; width: 100%; }
        .title-group h2 { font-size: 28px; font-weight: 800; text-transform: uppercase; line-height: 1; letter-spacing: -1px; }
        .line { width: 50px; height: 5px; background: var(--verde); margin: 12px 0; border-radius: 2px; }
        
        .btn-verde {
            background: var(--verde); color: white;
            padding: 14px 25px; border-radius: 10px;
            font-weight: 700; font-size: 13px; text-transform: uppercase;
            display: inline-flex; align-items: center; gap: 10px;
            border: none;
            box-shadow: 0 4px 15px rgba(0,0,0,0.3);
        }

        .brand-footer { 
            padding: 20px 0 35px 0; 
            background: #fff; 
            flex-shrink: 0;
            border-top: 3px solid var(--verde);
        }
        .brand-footer h3 { 
            font-size: 18px;
            text-align: center; 
            color: #111; 
            margin-bottom: 20px; 
            text-transform: uppercase; 
            font-weight: 900;
            letter-spacing: 0.5px;
        }
        .brand-footer h3 span { color: var(--verde); }
        
        .track-container { overflow: hidden; width: 100%; }
        .track { 
            display: flex; 
            width: 200%; 
            animation: scroll 30s linear infinite; 
            align-items: center; 
        }
        .logo-box { width: 120px; margin: 0 25px; flex-shrink: 0; }
        .logo-box img { width: 100%; height: 25px; object-fit: contain; filter: grayscale(1); opacity: 0.6; }

        @keyframes scroll {
            0% { transform: translateX(0); }
            100% { transform: translateX(-50%); }
        }

        @media (min-width: 992px) {
            .split-container { flex-direction: row; }
            .section.expanded { flex: 2.5; }
            .section::after { background: linear-gradient(90deg, rgba(0,0,0,0.85) 0%, rgba(0,0,0,0) 100%); }
            .title-group h2 { font-size: 45px; }
            .brand-footer h3 { font-size: 22px; }
        }
    </style>
</head>
<body>

    <header class="header">
        <div class="header-top">
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT3lHMukjCrCLrU_YlVaEyp_6mOCRm556gKSQ&s" class="logo">
            <div class="header-icons">
                <svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"></path><circle cx="12" cy="7" r="4"></circle></svg>
                <svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="3" y1="12" x2="21" y2="12"></line><line x1="3" y1="6" x2="21" y2="6"></line><line x1="3" y1="18" x2="21" y2="18"></line></svg>
            </div>
        </div>
        <div class="search-box">
            <input type="text" placeholder="Buscar equipos, repuestos o marcas...">
        </div>
    </header>

    <div class="split-container">
        <div class="section hint" onclick="toggleSplit(this)">
            <!-- Imagen de soldadura/trabajo industrial que no bloquea -->
            <div class="bg-img" style="background-image: url('https://images.pexels.com/photos/1108101/pexels-photo-1108101.jpeg?auto=compress&cs=tinysrgb&w=1000');"></div>
            <div class="content">
                <div class="title-group">
                    <h2>SERVICIO<br>TÉCNICO</h2>
                    <div class="line"></div>
                </div>
                <div class="btn-verde">Solicitar Servicio ❯</div>
            </div>
        </div>

        <div class="section" onclick="toggleSplit(this)">
            <!-- Imagen de equipos industriales que no bloquea -->
            <div class="bg-img" style="background-image: url('https://images.pexels.com/photos/3846517/pexels-photo-3846517.jpeg?auto=compress&cs=tinysrgb&w=1000');"></div>
            <div class="content">
                <div class="title-group">
                    <h2>EQUIPOS Y<br>REPUESTOS</h2>
                    <div class="line"></div>
                </div>
                <div class="btn-verde">Ver Productos ❯</div>
            </div>
        </div>
    </div>

    <div class="brand-footer">
        <h3>SERVICIO TÉCNICO <span>AUTORIZADO</span></h3>
        <div class="track-container">
            <div class="track">
                <div class="logo-box"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/16/Lincoln_Electric_logo.svg/1280px-Lincoln_Electric_logo.svg.png"></div>
                <div class="logo-box"><img src="https://millerweldseurope.com/wp-content/uploads/2021/09/Miller-Logo-C-2.png"></div>
                <div class="logo-box"><img src="https://ujueta.com/assets/marca-elite-DVCMNE0a.svg"></div>
                <div class="logo-box"><img src="https://www.harrisproductsgroup.com/-/media/images/harris-logo.png"></div>
                <div class="logo-box"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/16/Lincoln_Electric_logo.svg/1280px-Lincoln_Electric_logo.svg.png"></div>
                <div class="logo-box"><img src="https://millerweldseurope.com/wp-content/uploads/2021/09/Miller-Logo-C-2.png"></div>
                <div class="logo-box"><img src="https://ujueta.com/assets/marca-elite-DVCMNE0a.svg"></div>
                <div class="logo-box"><img src="https://www.harrisproductsgroup.com/-/media/images/harris-logo.png"></div>
            </div>
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
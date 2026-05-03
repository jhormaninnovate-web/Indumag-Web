<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>INDUMAG | Oficial</title>

<style>
:root {
    --verde: #519a2e;
    --bezier: cubic-bezier(0.4, 0, 0.2, 1);
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Segoe UI', sans-serif;
}

body {
    background: #fff;
}

/* HEADER */
.header {
    padding: 12px 15px;
    background: #fff;
    border-bottom: 1px solid #eee;
}

.header-top {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 10px;
}

.logo { height: 35px; }

.header-icons { display: flex; gap: 15px; }

.search-box {
    border: 1px solid #ddd;
    border-radius: 12px;
    padding: 10px 15px;
    display: flex;
    align-items: center;
    background: #f9f9f9;
}

.search-box input {
    border: none;
    outline: none;
    width: 100%;
    padding-left: 10px;
    font-size: 16px;
}

/* SPLIT */
.split-container {
    display: flex;
    flex-direction: column;
    height: 60dvh;
}

.section {
    position: relative;
    flex: 1;
    display: flex;
    align-items: center;
    padding: 0 25px;
    cursor: pointer;
    overflow: hidden;
    transition: flex 0.6s var(--bezier);
    -webkit-tap-highlight-color: transparent;
}

.section.expanded { flex: 3; }

/* ANIMACIÓN HINT en la primera sección */
@keyframes introBounce {
    0%   { flex: 1; }
    40%  { flex: 2.2; }
    100% { flex: 1; }
}

.hint {
    animation: introBounce 2.5s var(--bezier) 0.5s both;
}

/* IMAGEN */
.bg-img {
    position: absolute;
    inset: 0;
    background-size: cover;
    background-position: center;
    transition: transform 1s var(--bezier);
}

.section.expanded .bg-img { transform: scale(1.1); }

/* OVERLAY */
.section::after {
    content: "";
    position: absolute;
    inset: 0;
    background: linear-gradient(0deg, rgba(0,0,0,0.8), rgba(0,0,0,0.2));
}

/* CONTENIDO */
.content {
    position: relative;
    color: white;
    z-index: 2;
}

h2 {
    font-size: 30px;
    font-weight: 800;
    line-height: 1;
}

.line {
    width: 50px;
    height: 4px;
    background: var(--verde);
    margin: 10px 0;
}

.btn {
    background: var(--verde);
    color: white;
    padding: 14px 24px;
    border-radius: 10px;
    font-size: 13px;
    font-weight: bold;
    display: inline-block;
    margin-top: 10px;
}

/* FOOTER */
.brand-footer {
    padding: 20px 0;
    border-top: 2px solid #eee;
    text-align: center;
}

.brand-footer h3 {
    font-size: 14px;
    margin-bottom: 15px;
}

.brand-footer span { color: var(--verde); }

.track-container {
    overflow: hidden;
    width: 100%;
}

.track {
    display: flex;
    width: max-content;
    animation: scrollLogos 25s linear infinite;
    align-items: center;
    will-change: transform;
}

body { overflow-x: hidden; }

.logo-box {
    width: 130px;
    margin: 0 30px;
    flex-shrink: 0;
}

.logo-box img {
    width: 100%;
    height: 25px;
    object-fit: contain;
    opacity: 0.6;
    filter: grayscale(1);
}

@keyframes scrollLogos {
    0%   { transform: translateX(0); }
    100% { transform: translateX(-50%); }
}

/* DESKTOP */
@media (min-width: 900px) {
    .split-container {
        flex-direction: row;
        height: 70dvh;
    }
    .section.expanded { flex: 2; }
    h2 { font-size: 42px; }
}
</style>

</head>

<body>

<header class="header">
    <div class="header-top">
        <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT3lHMukjCrCLrU_YlVaEyp_6mOCRm556gKSQ&s" class="logo">
        <div class="header-icons">☰</div>
    </div>
    <div class="search-box">
        <input type="text" placeholder="Buscar equipos o repuestos...">
    </div>
</header>

<div class="split-container">

```
<div class="section hint" onclick="toggle(this)">
    <div class="bg-img" style="background-image:url('https://images.unsplash.com/photo-1504328345606-18bbc8c9d7d1?auto=format&fit=crop&w=800&q=80')"></div>
    <div class="content">
        <h2>SERVICIO<br>TÉCNICO</h2>
        <div class="line"></div>
        <div class="btn">Reparar equipo</div>
    </div>
</div>

<div class="section" onclick="toggle(this)">
    <div class="bg-img" style="background-image:url('https://images.unsplash.com/photo-1581092160562-40aa08e78837?auto=format&fit=crop&w=800&q=80')"></div>
    <div class="content">
        <h2>EQUIPOS Y<br>REPUESTOS</h2>
        <div class="line"></div>
        <div class="btn">Comprar ahora</div>
    </div>
</div>
```

</div>

<div class="brand-footer">
    <h3>SERVICIO TÉCNICO <span>AUTORIZADO</span></h3>
    <div class="track-container">
        <div class="track">
            <div class="logo-box"><img src="https://upload.wikimedia.org/wikipedia/commons/1/16/Lincoln_Electric_logo.svg"></div>
            <div class="logo-box"><img src="https://millerweldseurope.com/wp-content/uploads/2021/09/Miller-Logo-C-2.png"></div>
            <div class="logo-box"><img src="https://ujueta.com/assets/marca-elite-DVCMNE0a.svg"></div>
            <div class="logo-box"><img src="https://www.harrisproductsgroup.com/-/media/images/harris-logo.png"></div>
            <!-- Duplicados para loop infinito -->
            <div class="logo-box"><img src="https://upload.wikimedia.org/wikipedia/commons/1/16/Lincoln_Electric_logo.svg"></div>
            <div class="logo-box"><img src="https://millerweldseurope.com/wp-content/uploads/2021/09/Miller-Logo-C-2.png"></div>
            <div class="logo-box"><img src="https://ujueta.com/assets/marca-elite-DVCMNE0a.svg"></div>
            <div class="logo-box"><img src="https://www.harrisproductsgroup.com/-/media/images/harris-logo.png"></div>
        </div>
    </div>
</div>

<script>
function toggle(el) {
    // Quitar animación hint al primer toque
    document.querySelectorAll('.section').forEach(s => s.style.animation = 'none');

    const isExpanded = el.classList.contains('expanded');

    // Quitar expanded de todos
    document.querySelectorAll('.section').forEach(s => s.classList.remove('expanded'));

    // Si no estaba expandido, expandir. Si ya estaba, vuelve al 50/50
    if (!isExpanded) {
        el.classList.add('expanded');
    }
}
</script>

</body>
</html>
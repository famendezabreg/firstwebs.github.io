<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Guía 1 - Ejercicios y Ejemplos Web</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            overflow: hidden;
        }

        header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 50px 40px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        header::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            animation: float 20s infinite linear;
        }

        @keyframes float {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        h1 {
            font-size: 3em;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
            position: relative;
            z-index: 1;
        }

        .subtitle {
            font-size: 1.3em;
            opacity: 0.95;
            position: relative;
            z-index: 1;
        }

        main {
            padding: 40px;
        }

        .sections-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin-bottom: 30px;
        }

        .section {
            background: #f8f9fa;
            border-radius: 15px;
            padding: 30px;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            border: 2px solid transparent;
        }

        .section:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(102,126,234,0.2);
            border-color: #667eea;
        }

        .section h2 {
            color: #667eea;
            margin-bottom: 25px;
            font-size: 1.8em;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .section h2 .icon {
            font-size: 1.2em;
        }

        .section h2::after {
            content: '';
            flex: 1;
            height: 2px;
            background: linear-gradient(90deg, #667eea, transparent);
            margin-left: 10px;
        }

        .links-list {
            list-style: none;
        }

        .links-list li {
            margin-bottom: 15px;
        }

        .links-list a {
            color: #333;
            text-decoration: none;
            padding: 12px 18px;
            background: white;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            transition: all 0.3s ease;
            border-left: 4px solid transparent;
            box-shadow: 0 2px 5px rgba(0,0,0,0.05);
        }

        .links-list a:hover {
            background: linear-gradient(90deg, rgba(102,126,234,0.1) 0%, rgba(118,75,162,0.1) 100%);
            border-left-color: #667eea;
            padding-left: 25px;
            box-shadow: 0 4px 10px rgba(102,126,234,0.2);
        }

        .file-info {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .file-icon {
            width: 24px;
            height: 24px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 18px;
        }

        .badge {
            display: inline-block;
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 3px 10px;
            border-radius: 15px;
            font-size: 0.75em;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .badge.css {
            background: linear-gradient(135deg, #3498db, #2980b9);
        }

        .badge.html {
            background: linear-gradient(135deg, #e74c3c, #c0392b);
        }

        .full-width-section {
            background: #f8f9fa;
            border-radius: 15px;
            padding: 30px;
            margin-bottom: 30px;
        }

        .full-width-section h2 {
            color: #667eea;
            margin-bottom: 20px;
            font-size: 1.8em;
        }

        .info-text {
            line-height: 1.8;
            color: #555;
            margin-bottom: 15px;
        }

        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .stat-card {
            background: white;
            padding: 15px;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 2px 5px rgba(0,0,0,0.05);
        }

        .stat-number {
            font-size: 2em;
            color: #667eea;
            font-weight: bold;
        }

        .stat-label {
            color: #666;
            font-size: 0.9em;
            margin-top: 5px;
        }

        footer {
            background: #f8f9fa;
            padding: 30px;
            text-align: center;
            color: #666;
            border-top: 2px solid #e9ecef;
        }

        footer a {
            color: #667eea;
            text-decoration: none;
            font-weight: 500;
        }

        footer a:hover {
            text-decoration: underline;
        }

        .github-link {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            margin-top: 10px;
        }

        @media (max-width: 768px) {
            h1 {
                font-size: 2em;
            }
            
            .sections-grid {
                grid-template-columns: 1fr;
            }

            main {
                padding: 20px;
            }
        }

        /* Animación de entrada */
        .fade-in {
            animation: fadeIn 0.5s ease-in;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>📘 Guía 1 - Desarrollo Web</h1>
            <p class="subtitle">Ejemplos y Ejercicios de HTML, CSS y JavaScript</p>
        </header>

        <main>
            <!-- Sección de Países -->
            <div class="sections-grid">
                <section class="section fade-in">
                    <h2><span class="icon">🌍</span> Países</h2>
                    <ul class="links-list">
                        <li>
                            <a href="Paises/paises.html">
                                <div class="file-info">
                                    <span class="file-icon">📄</span>
                                    <span>Página de Países</span>
                                </div>
                                <span class="badge html">HTML</span>
                            </a>
                        </li>
                        <li>
                            <a href="Paises/styles.css">
                                <div class="file-info">
                                    <span class="file-icon">🎨</span>
                                    <span>Estilos de Países</span>
                                </div>
                                <span class="badge css">CSS</span>
                            </a>
                        </li>
                    </ul>
                </section>

                <!-- Sección de Rápidos y Furiosos -->
                <section class="section fade-in">
                    <h2><span class="icon">🏎️</span> Rápidos y Furiosos</h2>
                    <ul class="links-list">
                        <li>
                            <a href="RapidosyFuriosos/Ryf.html">
                                <div class="file-info">
                                    <span class="file-icon">📄</span>
                                    <span>Página Principal R&F</span>
                                </div>
                                <span class="badge html">HTML</span>
                            </a>
                        </li>
                        <li>
                            <a href="RapidosyFuriosos/R-F.css">
                                <div class="file-info">
                                    <span class="file-icon">🎨</span>
                                    <span>Estilos R&F</span>
                                </div>
                                <span class="badge css">CSS</span>
                            </a>
                        </li>
                    </ul>
                </section>
            </div>

            <!-- Sección de Ejemplos y Ejercicios -->
            <div class="sections-grid">
                <section class="section fade-in">
                    <h2><span class="icon">💡</span> Ejemplos</h2>
                    <ul class="links-list">
                        <li>
                            <a href="ejemplo2.html">
                                <div class="file-info">
                                    <span class="file-icon">📝</span>
                                    <span>Ejemplo 2</span>
                                </div>
                                <span class="badge html">HTML</span>
                            </a>
                        </li>
                        <li>
                            <a href="estilos_embebidos.html">
                                <div class="file-info">
                                    <span class="file-icon">🎨</span>
                                    <span>Estilos Embebidos</span>
                                </div>
                                <span class="badge html">HTML</span>
                            </a>
                        </li>
                    </ul>
                </section>

                <section class="section fade-in">
                    <h2><span class="icon">✏️</span> Archivos CSS</h2>
                    <ul class="links-list">
                        <li>
                            <a href="estilos1.css">
                                <div class="file-info">
                                    <span class="file-icon">🎨</span>
                                    <span>Hoja de Estilos 1</span>
                                </div>
                                <span class="badge css">CSS</span>
                            </a>
                        </li>
                    </ul>
                </section>
            </div>

            <!-- Sección de Información -->
            <div class="full-width-section fade-in">
                <h2>📊 Información del Proyecto</h2>
                <p class="info-text">
                    Este repositorio contiene ejercicios y ejemplos prácticos de desarrollo web de la Guía 1. 
                    Incluye proyectos sobre países del mundo y la franquicia Rápidos y Furiosos, 
                    demostrando el uso de HTML5, CSS3 y buenas prácticas de desarrollo web.
                </p>
                
                <div class="stats">
                    <div class="stat-card">
                        <div class="stat-number">7</div>
                        <div class="stat-label">Archivos</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number">2</div>
                        <div class="stat-label">Proyectos</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number">HTML</div>
                        <div class="stat-label">Lenguaje Principal</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number">CSS</div>
                        <div class="stat-label">Estilos</div>
                    </div>
                </div>
            </div>
        </main>

        <footer>
            <p>© 2025 - Guía 1 de Desarrollo Web</p>
            <p>Creado para el curso de Desarrollo Web</p>
            <div class="github-link">
                <span>📁</span>
                <a href="https://github.com/tu-usuario/20245099_Guia1" target="_blank">
                    Ver código fuente en GitHub
                </a>
            </div>
        </footer>
    </div>

    <script>
        // Animación suave al cargar
        window.addEventListener('load', () => {
            const elements = document.querySelectorAll('.fade-in');
            elements.forEach((element, index) => {
                element.style.opacity = '0';
                element.style.transform = 'translateY(20px)';
                
                setTimeout(() => {
                    element.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
                    element.style.opacity = '1';
                    element.style.transform = 'translateY(0)';
                }, index * 100);
            });
        });

        // Mostrar fecha actual (opcional)
        const today = new Date();
        console.log('Página cargada:', today.toLocaleDateString('es-ES'));
    </script>
</body>
</html>

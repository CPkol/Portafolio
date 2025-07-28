<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio TACS - Jhosep Santiago Donis Canel</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --color-primary: #0a0a0a;
            --color-secondary: #ffffff;
            --color-accent: #6366f1;
            --color-accent-hover: #4f46e5;
            --color-accent-light: #8b5cf6;
            --color-text: #ffffff;
            --color-text-secondary: #e4e4e7;
            --color-text-muted: #a1a1aa;
            --color-background: #000000;
            --color-surface: #0f0f0f;
            --color-surface-hover: #1a1a1a;
            --color-surface-elevated: #171717;
            --color-border: #262626;
            --color-border-hover: #404040;
            --color-gradient-primary: linear-gradient(135deg, #000000 0%, #1a1a1a 50%, #2a2a2a 100%);
            --color-gradient-accent: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%);
            --color-gradient-surface: linear-gradient(145deg, #0f0f0f 0%, #1a1a1a 100%);
            --spacing-xs: 0.5rem;
            --spacing-sm: 1rem;
            --spacing-md: 1.5rem;
            --spacing-lg: 2rem;
            --spacing-xl: 3rem;
            --spacing-xxl: 4rem;
            --border-radius: 16px;
            --border-radius-lg: 20px;
            --border-radius-xl: 24px;
            --shadow-sm: 0 1px 3px 0 rgba(0, 0, 0, 0.3), 0 1px 2px 0 rgba(255, 255, 255, 0.05);
            --shadow-md: 0 4px 8px -2px rgba(0, 0, 0, 0.4), 0 2px 4px -2px rgba(255, 255, 255, 0.1);
            --shadow-lg: 0 10px 25px -5px rgba(0, 0, 0, 0.5), 0 4px 10px -6px rgba(255, 255, 255, 0.1);
            --shadow-xl: 0 20px 40px -12px rgba(0, 0, 0, 0.6), 0 8px 16px -8px rgba(255, 255, 255, 0.1);
            --transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            --transition-fast: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            background: var(--color-background);
            background-image: 
                radial-gradient(circle at 20% 20%, rgba(99, 102, 241, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(139, 92, 246, 0.08) 0%, transparent 50%),
                radial-gradient(circle at 40% 60%, rgba(99, 102, 241, 0.05) 0%, transparent 50%);
            color: var(--color-text);
            line-height: 1.6;
            font-weight: 400;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 var(--spacing-sm);
        }

        /* Header Styles */
        .header {
            padding: var(--spacing-xxl) 0;
            text-align: center;
            position: relative;
            overflow: hidden;
            background: var(--color-gradient-primary);
        }

        .header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: var(--color-gradient-surface);
            opacity: 0.9;
        }

        .header::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: 
                radial-gradient(circle at 30% 30%, rgba(99, 102, 241, 0.15) 0%, transparent 50%),
                radial-gradient(circle at 70% 70%, rgba(139, 92, 246, 0.1) 0%, transparent 50%);
            animation: float 20s ease-in-out infinite;
        }

        .header-content {
            position: relative;
            z-index: 3;
        }

        .header h1 {
            font-size: clamp(2.8rem, 8vw, 5rem);
            font-weight: 800;
            margin-bottom: var(--spacing-lg);
            background: var(--color-gradient-accent);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: -0.03em;
            text-shadow: 0 0 40px rgba(99, 102, 241, 0.3);
            position: relative;
        }

        .header h1::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: var(--color-gradient-accent);
            -webkit-background-clip: text;
            background-clip: text;
            filter: blur(20px);
            opacity: 0.7;
            z-index: -1;
        }

        .header-subtitle {
            font-size: 1.25rem;
            color: var(--color-text-secondary);
            max-width: 700px;
            margin: 0 auto;
            font-weight: 500;
            line-height: 1.8;
            text-shadow: 0 2px 8px rgba(0, 0, 0, 0.3);
        }

        .header-divider {
            width: 80px;
            height: 4px;
            background: var(--color-gradient-accent);
            margin: var(--spacing-xl) auto 0;
            border-radius: 2px;
            box-shadow: 0 0 20px rgba(99, 102, 241, 0.5);
        }

        /* Navigation */
        .nav-back {
            position: fixed;
            top: var(--spacing-lg);
            left: var(--spacing-lg);
            z-index: 1000;
            background: var(--color-gradient-surface);
            border: 1px solid var(--color-border);
            color: var(--color-text);
            padding: var(--spacing-sm) var(--spacing-lg);
            border-radius: var(--border-radius-lg);
            cursor: pointer;
            font-weight: 600;
            font-size: 0.95rem;
            transition: var(--transition);
            backdrop-filter: blur(20px);
            box-shadow: var(--shadow-lg);
            display: none;
        }

        .nav-back.active {
            display: flex;
            align-items: center;
            gap: var(--spacing-sm);
        }

        .nav-back:hover {
            background: var(--color-surface-elevated);
            border-color: var(--color-accent);
            transform: translateY(-2px) scale(1.05);
            box-shadow: var(--shadow-xl);
        }

        /* Grid Layout */
        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: var(--spacing-lg);
            margin: var(--spacing-xl) 0;
        }

        /* Card Styles */
        .portfolio-card {
            background: var(--color-gradient-surface);
            border: 1px solid var(--color-border);
            border-radius: var(--border-radius-xl);
            padding: var(--spacing-xl);
            cursor: pointer;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            min-height: 220px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            backdrop-filter: blur(20px);
            box-shadow: var(--shadow-md);
        }

        .portfolio-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: var(--color-gradient-accent);
            opacity: 0;
            transition: var(--transition);
            border-radius: var(--border-radius-xl);
        }

        .portfolio-card::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            background: radial-gradient(circle, rgba(99, 102, 241, 0.3) 0%, transparent 70%);
            transition: var(--transition);
            transform: translate(-50%, -50%);
            border-radius: 50%;
        }

        .portfolio-card:hover::before {
            opacity: 0.1;
        }

        .portfolio-card:hover::after {
            width: 200px;
            height: 200px;
        }

        .portfolio-card:hover {
            border-color: var(--color-accent);
            transform: translateY(-12px) scale(1.02);
            box-shadow: var(--shadow-xl);
        }

        .portfolio-card h3 {
            font-size: 1.3rem;
            font-weight: 700;
            margin-bottom: var(--spacing-sm);
            color: var(--color-text);
            position: relative;
            z-index: 3;
            letter-spacing: -0.01em;
        }

        .portfolio-card .card-icon {
            font-size: 2.5rem;
            margin-bottom: var(--spacing-lg);
            opacity: 0.9;
            transition: var(--transition);
            position: relative;
            z-index: 3;
            filter: drop-shadow(0 4px 8px rgba(0, 0, 0, 0.3));
        }

        .portfolio-card:hover .card-icon {
            opacity: 1;
            transform: scale(1.15) rotateY(5deg);
            filter: drop-shadow(0 8px 16px rgba(99, 102, 241, 0.4));
        }

        /* Content Sections */
        .content-section {
            display: none;
            margin: var(--spacing-xl) 0;
            animation: fadeInUp 0.6s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .content-section.active {
            display: block;
        }

        .content-wrapper {
            max-width: 900px;
            margin: 0 auto;
            background: var(--color-gradient-surface);
            border: 1px solid var(--color-border);
            border-radius: var(--border-radius-xl);
            padding: var(--spacing-xxl);
            box-shadow: var(--shadow-xl);
            backdrop-filter: blur(20px);
            position: relative;
            overflow: hidden;
        }

        .content-wrapper::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 1px;
            background: var(--color-gradient-accent);
            opacity: 0.6;
        }

        .content-section h2 {
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: var(--spacing-lg);
            color: var(--color-text);
            text-align: center;
            position: relative;
            padding-bottom: var(--spacing-md);
        }

        .content-section h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 3px;
            background: linear-gradient(90deg, var(--color-accent), var(--color-accent-hover));
            border-radius: 2px;
        }

        /* Media Containers */
        .media-container {
            margin: var(--spacing-lg) 0;
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--shadow-md);
            transition: var(--transition);
        }

        .media-container:hover {
            transform: translateY(-2px);
            box-shadow: var(--shadow-lg);
        }

        .media-container img,
        .media-container video {
            width: 100%;
            height: auto;
            display: block;
            border-radius: var(--border-radius);
        }

        .media-container audio {
            width: 100%;
            margin: var(--spacing-md) 0;
        }

        /* Content Text */
        .content-description {
            font-size: 1.125rem;
            line-height: 1.7;
            color: var(--color-text-secondary);
            text-align: center;
            margin-top: var(--spacing-lg);
        }

        /* Links */
        .presentation-links {
            display: flex;
            flex-direction: column;
            gap: var(--spacing-md);
            margin: var(--spacing-lg) 0;
        }

        .presentation-link {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: var(--spacing-sm);
            padding: var(--spacing-lg) var(--spacing-xl);
            background: var(--color-gradient-accent);
            color: var(--color-secondary);
            text-decoration: none;
            border-radius: var(--border-radius-lg);
            font-weight: 600;
            font-size: 1.1rem;
            transition: var(--transition);
            box-shadow: var(--shadow-lg);
            position: relative;
            overflow: hidden;
        }

        .presentation-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: var(--transition);
        }

        .presentation-link:hover::before {
            left: 100%;
        }

        .presentation-link:hover {
            transform: translateY(-4px) scale(1.02);
            box-shadow: var(--shadow-xl);
            filter: brightness(1.1);
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(40px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes pulse {
            0%, 100% {
                opacity: 1;
            }
            50% {
                opacity: 0.5;
            }
        }

        @keyframes float {
            0%, 100% {
                transform: rotate(0deg) translateX(0px) translateY(0px);
            }
            33% {
                transform: rotate(120deg) translateX(5px) translateY(-5px);
            }
            66% {
                transform: rotate(240deg) translateX(-5px) translateY(5px);
            }
        }

        @keyframes shimmer {
            0% {
                background-position: -200% 0;
            }
            100% {
                background-position: 200% 0;
            }
        }

        @keyframes glow {
            0%, 100% {
                opacity: 0.5;
                transform: scale(1);
            }
            50% {
                opacity: 0.8;
                transform: scale(1.05);
            }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .container {
                padding: 0 var(--spacing-sm);
            }

            .header {
                padding: var(--spacing-lg) 0;
            }

            .portfolio-grid {
                grid-template-columns: 1fr;
                gap: var(--spacing-md);
                margin: var(--spacing-lg) 0;
            }

            .portfolio-card {
                min-height: 160px;
                padding: var(--spacing-md);
            }

            .content-wrapper {
                padding: var(--spacing-lg);
                margin: var(--spacing-sm);
            }

            .nav-back {
                position: relative;
                top: auto;
                left: auto;
                margin-bottom: var(--spacing-md);
            }
        }

        @media (max-width: 480px) {
            .portfolio-grid {
                grid-template-columns: 1fr;
                gap: var(--spacing-sm);
            }

            .portfolio-card {
                min-height: 140px;
                padding: var(--spacing-sm);
            }

            .content-wrapper {
                padding: var(--spacing-md);
            }
        }

        /* Custom scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: var(--color-surface);
        }

        ::-webkit-scrollbar-thumb {
            background: var(--color-border);
            border-radius: 4px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: var(--color-border-hover);
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header -->
        <header class="header">
            <div class="header-content">
                <h1>PORTAFOLIOS TACS</h1>
                <p class="header-subtitle">
                    Página creada por <strong>Jhosep Santiago Donis Canel</strong>, un apasionado desarrollador con enfoque en tecnología, programación y la evolución de la inteligencia artificial.
                </p>
                <div class="header-divider"></div>
            </div>
        </header>

        <!-- Back Navigation -->
        <button class="nav-back" id="backButton">
            ← Volver a inicio
        </button>

        <!-- Portfolio Grid -->
        <div class="portfolio-grid" id="portfolioGrid">
            <div class="portfolio-card" data-section="infografia-uso-computadora">
                <div class="card-icon">💻</div>
                <h3>Infografía Uso de la Computadora</h3>
            </div>
            <div class="portfolio-card" data-section="infografia-virus-antivirus">
                <div class="card-icon">🛡️</div>
                <h3>Infografía Virus y Antivirus</h3>
            </div>
            <div class="portfolio-card" data-section="infografia-hacker-cracker">
                <div class="card-icon">🔐</div>
                <h3>Infografía Hacker vs Cracker</h3>
            </div>
            <div class="portfolio-card" data-section="presentacion-ia">
                <div class="card-icon">🧠</div>
                <h3>Presentación sobre la IA</h3>
            </div>
            <div class="portfolio-card" data-section="audio-ia">
                <div class="card-icon">🎵</div>
                <h3>Audio con IA</h3>
            </div>
            <div class="portfolio-card" data-section="imagen-ia">
                <div class="card-icon">🎨</div>
                <h3>Imagen con IA</h3>
            </div>
            <div class="portfolio-card" data-section="video-ia">
                <div class="card-icon">🎬</div>
                <h3>Video con IA</h3>
            </div>
            <div class="portfolio-card" data-section="presentacion-con-ia">
                <div class="card-icon">📊</div>
                <h3>Presentación con IA</h3>
            </div>
        </div>

        <!-- Content Sections -->
        <div class="content-section" id="infografia-uso-computadora">
            <div class="content-wrapper">
                <h2>Infografía Uso de la Computadora</h2>
                <div class="presentation-links">
                    <a href="https://online.flippingbook.com/view/930453343/" target="_blank" class="presentation-link">
                        📖 Ver Infografía - Uso de la Computadora
                    </a>
                </div>
                <p class="content-description">
                    Esta infografía presenta las mejores prácticas para el uso ergonómico de la computadora, incluyendo recomendaciones sobre postura, configuración del espacio de trabajo y hábitos saludables para prevenir lesiones y mejorar la productividad.
                </p>
            </div>
        </div>

        <div class="content-section" id="infografia-virus-antivirus">
            <div class="content-wrapper">
                <h2>Infografía Virus y Antivirus</h2>
                <div class="presentation-links">
                    <a href="https://online.flippingbook.com/view/930696297/" target="_blank" class="presentation-link">
                        🛡️ Ver Infografía - Virus y Antivirus
                    </a>
                </div>
                <p class="content-description">
                    Explora los conceptos fundamentales de la ciberseguridad moderna, incluyendo tipos de malware, métodos de protección y la importancia de mantener sistemas actualizados para una defensa efectiva contra amenazas digitales.
                </p>
            </div>
        </div>

        <div class="content-section" id="infografia-hacker-cracker">
            <div class="content-wrapper">
                <h2>Infografía Hacker vs Cracker</h2>
                <div class="presentation-links">
                    <a href="https://online.flippingbook.com/view/930684029/" target="_blank" class="presentation-link">
                        🔐 Ver Infografía - Hacker vs Cracker
                    </a>
                </div>
                <p class="content-description">
                    Análisis detallado de las diferencias entre hackers éticos y crackers maliciosos, explorando sus motivaciones, métodos y el papel crucial que desempeñan en el ecosistema de la ciberseguridad moderna.
                </p>
            </div>
        </div>

        <div class="content-section" id="presentacion-ia">
            <div class="content-wrapper">
                <h2>Presentación sobre la IA</h2>
                <div class="presentation-links">
                    <a href="https://heyzine.com/flip-book/46157b4f69.html" target="_blank" class="presentation-link">
                        📖 Ver Presentación sobre IA
                    </a>
                </div>
                <p class="content-description">
                    Presentación comprehensiva sobre los avances actuales en Inteligencia Artificial, sus aplicaciones en diferentes industrias y el impacto transformador en nuestra sociedad digital.
                </p>
            </div>
        </div>

        <div class="content-section" id="audio-ia">
            <div class="content-wrapper">
                <h2>Audio con IA</h2>
                <div class="presentation-links">
                    <a href="https://jumpshare.com/s/RphWfkitY21xpa2hBhUS" target="_blank" class="presentation-link">
                        🎵 Escuchar Audio generado con IA
                    </a>
                </div>
                <p class="content-description">
                    Demostración de las capacidades de síntesis de voz mediante tecnología de Inteligencia Artificial, utilizando herramientas avanzadas como ElevenLabs para crear contenido de audio realista y expresivo.
                </p>
            </div>
        </div>

        <div class="content-section" id="imagen-ia">
            <div class="content-wrapper">
                <h2>Imagen con IA</h2>
                <div class="presentation-links">
                    <a href="https://ibb.co/kgDMm9qX" target="_blank" class="presentation-link">
                        🎨 Ver Imagen generada con IA
                    </a>
                </div>
                <p class="content-description">
                    Ejemplo de generación de imágenes utilizando tecnología de IA avanzada. Esta imagen fue creada con herramientas de última generación que demuestran el potencial creativo de la inteligencia artificial.
                </p>
            </div>
        </div>

        <div class="content-section" id="video-ia">
            <div class="content-wrapper">
                <h2>Video con IA</h2>
                <div class="presentation-links">
                    <a href="https://www.flexclip.com/es/share/1341225695193a329ed7f2228ec70cd635a42b84.html" target="_blank" class="presentation-link">
                        🎬 Ver Video generado con IA
                    </a>
                </div>
                <p class="content-description">
                    Exploración de las capacidades de generación de video mediante IA, mostrando cómo la tecnología puede crear contenido audiovisual dinámico y atractivo de manera automatizada.
                </p>
            </div>
        </div>

        <div class="content-section" id="presentacion-con-ia">
            <div class="content-wrapper">
                <h2>Presentación con IA</h2>
                <div class="presentation-links">
                    <a href="https://heyzine.com/flip-book/b3754d0e63.html" target="_blank" class="presentation-link">
                        🤖 Ver Presentación con IA
                    </a>
                </div>
                <p class="content-description">
                    Presentación desarrollada con asistencia de Inteligencia Artificial, demostrando cómo las herramientas de IA pueden optimizar el diseño, contenido y estructura de materiales educativos.
                </p>
            </div>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const portfolioCards = document.querySelectorAll('.portfolio-card');
            const contentSections = document.querySelectorAll('.content-section');
            const portfolioGrid = document.getElementById('portfolioGrid');
            const backButton = document.getElementById('backButton');

            // Add smooth scroll behavior
            document.documentElement.style.scrollBehavior = 'smooth';

            // Function to show a specific content section
            function showSection(sectionId) {
                // Hide all sections
                contentSections.forEach(section => {
                    section.classList.remove('active');
                });
                
                // Hide the portfolio grid
                portfolioGrid.style.display = 'none';
                
                // Show the back button
                backButton.classList.add('active');
                
                // Show the selected section
                const targetSection = document.getElementById(sectionId);
                if (targetSection) {
                    targetSection.classList.add('active');
                    // Smooth scroll to the section
                    targetSection.scrollIntoView({ behavior: 'smooth', block: 'start' });
                }
            }

            // Function to return to portfolio view
            function returnToPortfolio() {
                // Hide all sections
                contentSections.forEach(section => {
                    section.classList.remove('active');
                });
                
                // Show the portfolio grid
                portfolioGrid.style.display = 'grid';
                
                // Hide the back button
                backButton.classList.remove('active');
                
                // Scroll to top
                window.scrollTo({ top: 0, behavior: 'smooth' });
            }

            // Add event listeners to portfolio cards
            portfolioCards.forEach(card => {
                card.addEventListener('click', function() {
                    const sectionId = this.getAttribute('data-section');
                    if (sectionId) {
                        showSection(sectionId);
                    }
                });

                // Add keyboard support
                card.addEventListener('keydown', function(e) {
                    if (e.key === 'Enter' || e.key === ' ') {
                        e.preventDefault();
                        this.click();
                    }
                });

                // Make cards focusable
                card.setAttribute('tabindex', '0');
            });

            // Add event listener to back button
            backButton.addEventListener('click', returnToPortfolio);

            // Add keyboard support for back button
            backButton.addEventListener('keydown', function(e) {
                if (e.key === 'Enter' || e.key === ' ') {
                    e.preventDefault();
                    this.click();
                }
            });

            // Add escape key support
            document.addEventListener('keydown', function(e) {
                if (e.key === 'Escape') {
                    const hasActiveSection = Array.from(contentSections).some(section => 
                        section.classList.contains('active')
                    );
                    if (hasActiveSection) {
                        returnToPortfolio();
                    }
                }
            });

            // Add intersection observer for smooth animations
            const observerOptions = {
                threshold: 0.1,
                rootMargin: '0px 0px -50px 0px'
            };

            const observer = new IntersectionObserver(function(entries) {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            }, observerOptions);

            // Observe portfolio cards for animations
            portfolioCards.forEach(card => {
                card.style.opacity = '0';
                card.style.transform = 'translateY(20px)';
                card.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
                observer.observe(card);
            });
        });
    </script>
</body>
</html>

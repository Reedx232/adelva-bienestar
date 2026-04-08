[adelva_completo.html](https://github.com/user-attachments/files/26561420/adelva_completo.html)
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ADELVA | Innovación y Salud</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        :root {
            --primary: #0077b6;
            --dark: #03045e;
            --accent: #2ecc71;
            --bg: #f4f7f9;
        }

        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Segoe UI', sans-serif; }
        body { background-color: var(--bg); color: #2d3436; line-height: 1.8; }

        header {
            background: linear-gradient(135deg, var(--dark), var(--primary));
            color: white; padding: 40px 20px; text-align: center; position: relative;
        }

        .lang-switch {
            position: absolute; top: 20px; right: 20px;
            background: rgba(255,255,255,0.2); border: 2px solid white;
            padding: 8px 16px; border-radius: 20px; cursor: pointer;
            color: white; font-weight: bold; transition: 0.3s; font-size: 16px;
        }

        .lang-switch:hover { background: rgba(255,255,255,0.3); }
        
        .contact-bar { 
            background: #fff; padding: 15px; text-align: center; 
            border-bottom: 2px solid #ddd; flex-wrap: wrap; 
            display: flex; justify-content: center; gap: 30px; 
        }
        .contact-bar a { 
            color: var(--primary); font-weight: bold; text-decoration: none; 
            font-size: 16px; display: flex; align-items: center; gap: 8px; 
        }
        .contact-bar a:hover { color: var(--dark); }

        nav {
            display: flex; overflow-x: auto; background: white; padding: 15px; gap: 10px;
            position: sticky; top: 0; z-index: 1000; box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            scrollbar-width: none;
        }
        nav button {
            padding: 10px 25px; border: none; background: #eee; border-radius: 30px;
            cursor: pointer; font-weight: bold; white-space: nowrap; transition: 0.3s; font-size: 14px;
        }
        nav button.active { background: var(--primary); color: white; }
        nav button:hover { background: #ccc; }
        nav button.active:hover { background: var(--primary); }

        .container { max-width: 900px; margin: 30px auto; padding: 0 20px; padding-bottom: 120px; }
        .tab-content { display: none; animation: fadeIn 0.5s ease; }
        .tab-content.active { display: block; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        /* INICIO */
        .hero-section {
            background: linear-gradient(135deg, rgba(0,119,182,0.1), rgba(46,204,113,0.1));
            border-radius: 20px; padding: 50px 30px; margin-bottom: 40px;
            border-left: 5px solid var(--primary);
        }

        .hero-section h2 { 
            color: var(--dark); margin-bottom: 20px; font-size: 36px; 
            text-align: center;
        }

        .features {
            display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-top: 30px;
        }

        .feature-box {
            background: white; padding: 20px; border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
            border-top: 4px solid var(--accent);
        }

        .feature-box h4 { color: var(--primary); margin-bottom: 10px; font-size: 18px; }
        .feature-box p { font-size: 15px; color: #555; }

        .inicio-box {
            background: white; border-radius: 20px; padding: 40px; 
            box-shadow: 0 10px 30px rgba(0,0,0,0.1); margin-bottom: 30px;
        }

        .inicio-box h3 { color: var(--dark); margin-bottom: 15px; font-size: 24px; }
        .inicio-box p { font-size: 17px; color: #555; margin-bottom: 15px; line-height: 1.8; text-align: justify; }

        /* PRODUCTOS */
        .card { 
            background: white; border-radius: 20px; overflow: hidden; 
            margin-bottom: 40px; box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .card:hover { transform: translateY(-5px); box-shadow: 0 15px 40px rgba(0,0,0,0.15); }

        .card-img-container {
            width: 100%; height: 300px; background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex; align-items: center; justify-content: center; color: white; font-size: 80px;
            overflow: hidden; position: relative;
        }

        .card-img-container.osmosis { background: linear-gradient(135deg, #0077b6 0%, #00d4ff 100%); }
        .card-img-container.descalcificador { background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); }
        .card-img-container.ozono { background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%); }
        .card-img-container.colchon { background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%); }

        .card-body { padding: 30px; }
        .card-body h3 { font-size: 28px; color: var(--dark); margin-bottom: 15px; }
        .card-body p { font-size: 17px; color: #555; margin-bottom: 15px; text-align: justify; }

        /* VISITA */
        .form-box {
            background: white; border-radius: 20px; padding: 40px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .form-group { margin-bottom: 20px; }
        .form-group label { display: block; margin-bottom: 8px; color: var(--dark); font-weight: bold; }
        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%; padding: 12px 15px; border: 2px solid #ddd; border-radius: 10px;
            font-size: 16px; font-family: inherit; transition: 0.3s;
        }

        .form-group input:focus,
        .form-group textarea:focus,
        .form-group select:focus {
            outline: none; border-color: var(--primary); box-shadow: 0 0 0 3px rgba(0,119,182,0.1);
        }

        .form-group textarea { resize: vertical; min-height: 120px; }

        .btn-submit {
            background: var(--primary); color: white; padding: 15px 40px;
            border: none; border-radius: 30px; font-size: 18px; font-weight: bold;
            cursor: pointer; transition: 0.3s; width: 100%;
        }

        .btn-submit:hover { background: var(--dark); transform: scale(1.02); }

        /* FAQ */
        .faq-item {
            background: white; border-radius: 15px; margin-bottom: 15px;
            overflow: hidden; box-shadow: 0 5px 15px rgba(0,0,0,0.08);
        }

        .faq-question {
            background: linear-gradient(135deg, var(--primary), #0077b6dd);
            color: white; padding: 20px; cursor: pointer; display: flex;
            justify-content: space-between; align-items: center; font-weight: bold;
            font-size: 18px; transition: 0.3s;
        }

        .faq-question:hover { background: var(--dark); }

        .faq-answer {
            padding: 0; max-height: 0; overflow: hidden; transition: max-height 0.3s ease, padding 0.3s ease;
            background: #f8f9fa;
        }

        .faq-answer.active {
            max-height: 500px; padding: 20px;
        }

        .faq-answer p { font-size: 16px; color: #555; line-height: 1.8; }

        /* IA */
        .chat-box { 
            background: white; border-radius: 20px; padding: 25px; 
            box-shadow: 0 10px 30px rgba(0,0,0,0.1); 
        }

        #chat-window { 
            height: 400px; overflow-y: auto; display: flex; flex-direction: column; 
            gap: 10px; padding: 15px; background: #f8fafc; border-radius: 15px; 
            margin-bottom: 15px; border: 1px solid #eee; 
        }

        .msg { 
            padding: 12px 18px; border-radius: 15px; font-size: 15px; 
            max-width: 80%; word-wrap: break-word; 
        }

        .msg.bot { background: #e3f2fd; align-self: flex-start; }
        .msg.user { background: var(--primary); color: white; align-self: flex-end; }

        .chat-input { display: flex; gap: 10px; }
        .chat-input input { 
            flex: 1; padding: 15px; border-radius: 30px; 
            border: 1px solid #ddd; outline: none; font-size: 16px;
        }
        .chat-input button { 
            background: var(--primary); color: white; border: none; 
            width: 50px; height: 50px; border-radius: 50%; 
            cursor: pointer; font-size: 20px; transition: 0.3s;
        }
        .chat-input button:hover { background: var(--dark); }

        /* BOTONES FLOTANTES */
        .floating { 
            position: fixed; right: 20px; bottom: 20px; 
            display: flex; flex-direction: column; gap: 10px; z-index: 2000; 
        }

        .btn-float { 
            padding: 18px 25px; border-radius: 50px; text-decoration: none; 
            color: white; font-weight: bold; display: flex; align-items: center; 
            gap: 10px; box-shadow: 0 5px 15px rgba(0,0,0,0.3); transition: 0.3s; 
            font-size: 15px;
        }

        .btn-float:hover { transform: scale(1.1); }
        .btn-ws { background: #25d366; }
        .btn-tel { background: var(--primary); }
        .btn-mail { background: #ea4335; }

        .success-message {
            background: #d4edda; color: #155724; padding: 15px 20px;
            border-radius: 10px; margin-top: 20px; display: none; border-left: 4px solid #28a745;
        }

        @media (max-width: 768px) {
            .features { grid-template-columns: 1fr; }
            nav { font-size: 12px; }
            nav button { padding: 8px 15px; font-size: 12px; }
            .btn-float { padding: 15px 20px; font-size: 13px; }
            .faq-question { font-size: 16px; }
        }

    </style>
</head>
<body>

<header>
    <button class="lang-switch" onclick="cambiarIdioma()">🌐 Català</button>
    <h1>ADELVA</h1>
    <p id="tagline">Empresa nueva con tecnología de vanguardia</p>
</header>

<div class="contact-bar">
    <a href="tel:+34614308378" title="Llamar"><i class="fas fa-phone"></i> <span id="call-text">Llámanos</span></a>
    <a href="mailto:serviceadelvatop@gmail.com" title="Enviar email"><i class="fas fa-envelope"></i> <span id="email-text">Email</span></a>
    <a href="https://www.adelva.com" target="_blank" title="Sitio web oficial"><i class="fas fa-globe"></i> <span id="web-text">Web Oficial</span></a>
</div>

<nav>
    <button class="t-btn active" onclick="tab(event, 'inicio')"><span id="nav-inicio">🏠 Inicio</span></button>
    <button class="t-btn" onclick="tab(event, 'productos')"><span id="nav-productos">💧 Productos</span></button>
    <button class="t-btn" onclick="tab(event, 'visita')"><span id="nav-visita">📅 Solicitar Visita</span></button>
    <button class="t-btn" onclick="tab(event, 'faq')"><span id="nav-faq">❓ FAQ</span></button>
    <button class="t-btn" onclick="tab(event, 'ia')"><span id="nav-ia">🤖 Asistente IA</span></button>
</nav>

<div class="container">

    <!-- INICIO -->
    <div id="inicio" class="tab-content active">
        <div class="hero-section">
            <h2 id="inicio-titulo">Bienvenidos a la nueva era del agua</h2>
            <p style="text-align: center; font-size: 18px; color: #555; margin-bottom: 30px;" id="inicio-subtitulo">
                Tecnología innovadora para mejorar tu calidad de vida
            </p>
        </div>

        <div class="inicio-box">
            <h3 id="sobre-adelva">¿Quiénes somos?</h3>
            <p id="inicio-p1">
                En <b>ADELVA</b> no somos una empresa antigua con métodos obsoletos. Somos una <b>empresa nueva</b>, joven y dinámica, nacida con la misión fundamental de aplicar la tecnología más avanzada de 2024 al bienestar y la salud de tu familia. Nuestro equipo está formado por expertos en tratamiento de agua y soluciones de hogar inteligente.
            </p>
        </div>

        <div class="inicio-box">
            <h3 id="nuestra-promesa">Nuestra Promesa</h3>
            <p id="inicio-p2">
                Nuestra frescura y modernidad es nuestra mayor garantía. Utilizamos sistemas de ósmosis inversa y descalcificación de última generación que consumen menos energía, purifican más eficientemente y cuestan menos a largo plazo. Si buscas calidad, innovación, sostenibilidad y un trato cercano y personalizado, ADELVA es definitivamente tu sitio.
            </p>
        </div>

        <div class="features">
            <div class="feature-box">
                <h4>💧 Agua Pura</h4>
                <p id="feat1">Ósmosis inversa de última generación para agua de manantial en tu hogar</p>
            </div>
            <div class="feature-box">
                <h4>🛡️ Protección</h4>
                <p id="feat2">Descalcificadores que protegen tu salud y tus electrodomésticos</p>
            </div>
            <div class="feature-box">
                <h4>🌍 Ecología</h4>
                <p id="feat3">Sistemas sostenibles que reducen consumo y residuos</p>
            </div>
            <div class="feature-box">
                <h4>🎯 Apoyo 24/7</h4>
                <p id="feat4">Equipo técnico disponible para cualquier consulta o soporte</p>
            </div>
        </div>
    </div>

    <!-- PRODUCTOS -->
    <div id="productos" class="tab-content">
        <div class="card">
            <div class="card-img-container osmosis">
                <i class="fas fa-droplet"></i>
            </div>
            <div class="card-body">
                <h3 id="prod1-titulo">💧 Ósmosis Inversa Premium</h3>
                <p id="prod1-desc">
                    Nuestra ósmosis es el sistema más avanzado para obtener agua pura en tu hogar. Olvida el sabor a cloro, los metales pesados y las impurezas. Disfruta de agua de manantial directamente en tu cocina con solo abrir el grifo. Es fundamental para la salud de tus riñones, para el sabor de tus comidas y para el bienestar de toda la familia. Instalación sencilla y mantenimiento mínimo.
                </p>
            </div>
        </div>

        <div class="card">
            <div class="card-img-container descalcificador">
                <i class="fas fa-shield"></i>
            </div>
            <div class="card-body">
                <h3 id="prod2-titulo">🛡️ Descalcificadores Inteligentes</h3>
                <p id="prod2-desc">
                    Protege tu hogar de la cal destructora. Nuestros equipos inteligentes eliminan el exceso de calcio y magnesio automáticamente, cuidando tu piel, tu cabello y alargando significativamente la vida de tu caldera y electrodomésticos. Ahorra dinero en reparaciones y sustituciones. Tecnología regenerable y eficiente energéticamente.
                </p>
            </div>
        </div>

        <div class="card">
            <div class="card-img-container ozono">
                <i class="fas fa-wind"></i>
            </div>
            <div class="card-body">
                <h3 id="prod3-titulo">🌀 Sistemas de Ozono y UV</h3>
                <p id="prod3-desc">
                    Desinfección total sin químicos nocivos. El ozono y la radiación UV eliminan virus, bacterias y patógenos del aire y el agua de forma ecológica y respetuosa con el medio ambiente. Es el complemento ideal para un hogar completamente saludable. Perfecto para familias con alergias o sistemas inmunológicos sensibles.
                </p>
            </div>
        </div>

        <div class="card">
            <div class="card-img-container colchon">
                <i class="fas fa-bed"></i>
            </div>
            <div class="card-body">
                <h3 id="prod4-titulo">🛏️ Descanso Ergonómico</h3>
                <p id="prod4-desc">
                    En ADELVA también cuidamos tu sueño y tu salud postural. Nuestros colchones de tecnología avanzada se adaptan perfectamente a tu cuerpo para garantizar un descanso reparador, profundo y saludable. Materiales de primera calidad que favorecen la circulación y alivian la presión corporal.
                </p>
            </div>
        </div>
    </div>

    <!-- SOLICITAR VISITA -->
    <div id="visita" class="tab-content">
        <div class="form-box">
            <h2 id="visita-titulo">Solicita tu Visita Técnica Gratuita</h2>
            <p id="visita-desc" style="margin-bottom: 30px; color: #555; font-size: 16px;">
                Nuestro equipo técnico visitará tu hogar para hacer un diagnóstico gratuito del agua y recomendarte la solución perfecta.
            </p>

            <form id="visitForm" onsubmit="enviarVisita(event)">
                <div class="form-group">
                    <label for="nombre" id="label-nombre">Nombre completo</label>
                    <input type="text" id="nombre" name="nombre" required>
                </div>

                <div class="form-group">
                    <label for="email" id="label-email">Correo electrónico</label>
                    <input type="email" id="email" name="email" required>
                </div>

                <div class="form-group">
                    <label for="telefono" id="label-telefono">Teléfono</label>
                    <input type="tel" id="telefono" name="telefono" required>
                </div>

                <div class="form-group">
                    <label for="ciudad" id="label-ciudad">Ciudad</label>
                    <input type="text" id="ciudad" name="ciudad" required>
                </div>

                <div class="form-group">
                    <label for="producto" id="label-producto">¿Qué te interesa?</label>
                    <select id="producto" name="producto" required>
                        <option value="">Selecciona un producto</option>
                        <option value="osmosis" id="opt-osmosis">Ósmosis Inversa</option>
                        <option value="descalcificador" id="opt-desc">Descalcificador</option>
                        <option value="ozono" id="opt-ozono">Ozono y UV</option>
                        <option value="colchon" id="opt-colchon">Colchón Ergonómico</option>
                        <option value="todos" id="opt-todos">Ver todos los productos</option>
                    </select>
                </div>

                <div class="form-group">
                    <label for="mensaje" id="label-mensaje">Mensaje (opcional)</label>
                    <textarea id="mensaje" name="mensaje"></textarea>
                </div>

                <button type="submit" class="btn-submit" id="btn-enviar">Solicitar Visita Gratuita</button>
                <div class="success-message" id="successMsg" style="display: none;">
                    <i class="fas fa-check-circle"></i> <span id="success-text">¡Solicitud enviada! Nos pondremos en contacto pronto.</span>
                </div>
            </form>
        </div>
    </div>

    <!-- FAQ -->
    <div id="faq" class="tab-content">
        <h2 id="faq-titulo" style="margin-bottom: 30px; color: var(--dark);">Preguntas Frecuentes</h2>

        <div class="faq-item">
            <div class="faq-question" onclick="toggleFaq(this)">
                <span id="faq1-q">¿Cuál es la diferencia entre ósmosis y descalcificación?</span>
                <i class="fas fa-chevron-down"></i>
            </div>
            <div class="faq-answer">
                <p id="faq1-a">
                    La ósmosis inversa purifica el agua eliminando prácticamente todas las impurezas, incluidos minerales, sales y contaminantes. El descalcificador elimina específicamente el calcio y magnesio que causan la cal, sin purificar completamente el agua. Lo ideal es combinar ambos sistemas.
                </p>
            </div>
        </div>

        <div class="faq-item">
            <div class="faq-question" onclick="toggleFaq(this)">
                <span id="faq2-q">¿Cuánto cuesta la instalación?</span>
                <span id="faq2-a-label" style="float: right;">
                    <i class="fas fa-chevron-down"></i>
                </span>
            </div>
            <div class="faq-answer">
                <p id="faq2-a">
                    El precio varía según el sistema elegido y la complejidad de la instalación. La visita técnica diagnóstica es completamente gratuita. En esa visita te haremos un presupuesto sin compromiso adaptado a tus necesidades.
                </p>
            </div>
        </div>

        <div class="faq-item">
            <div class="faq-question" onclick="toggleFaq(this)">
                <span id="faq3-q">¿Requiere mucho mantenimiento?</span>
                <i class="fas fa-chevron-down"></i>
            </div>
            <div class="faq-answer">
                <p id="faq3-a">
                    No. Nuestros sistemas son automáticos e inteligentes. Solo requieren cambios de filtros periódicos (aproximadamente cada 6-12 meses según uso). Nuestro equipo técnico puede encargarse del mantenimiento.
                </p>
            </div>
        </div>

        <div class="faq-item">
            <div class="faq-question" onclick="toggleFaq(this)">
                <span id="faq4-q">¿Es ecológico?</span>
                <i class="fas fa-chevron-down"></i>
            </div>
            <div class="faq-answer">
                <p id="faq4-a">
                    Absolutamente. Nuestros sistemas reducen el consumo de plástico (no más botellas), ahorran agua y energía, y utilizan tecnologías sostenibles. Es una inversión en tu salud y en el planeta.
                </p>
            </div>
        </div>

        <div class="faq-item">
            <div class="faq-question" onclick="toggleFaq(this)">
                <span id="faq5-q">¿Ofrecen garantía?</span>
                <i class="fas fa-chevron-down"></i>
            </div>
            <div class="faq-answer">
                <p id="faq5-a">
                    Sí. Todos nuestros equipos incluyen garantía de fabricante y soporte técnico gratuito durante el primer año. Además, ofrecemos planes de mantenimiento opcional.
                </p>
            </div>
        </div>
    </div>

    <!-- ASISTENTE IA -->
    <div id="ia" class="tab-content">
        <div class="chat-box">
            <h3 id="ia-titulo">🤖 Soporte IA Adelva</h3>
            <div id="chat-window">
                <div class="msg bot" id="msg-bienvenida">¡Hola! Soy la IA de ADELVA. Pregúntame sobre ósmosis, cal, ahorro o agendar una visita técnica. ¿En qué te ayudo?</div>
            </div>
            <div class="chat-input">
                <input type="text" id="chatIn" placeholder="Escribe tu duda aquí...">
                <button onclick="hablar()"><i class="fas fa-paper-plane"></i></button>
            </div>
        </div>
    </div>

</div>

<div class="floating">
    <a href="https://wa.me/34614308378" target="_blank" class="btn-float btn-ws" title="Contactar por WhatsApp"><i class="fab fa-whatsapp"></i> <span id="float-ws">WhatsApp</span></a>
    <a href="tel:+34614308378" class="btn-float btn-tel" title="Llamar"><i class="fas fa-phone"></i> <span id="float-tel">Llamar</span></a>
    <a href="mailto:serviceadelvatop@gmail.com" class="btn-float btn-mail" title="Enviar email"><i class="fas fa-envelope"></i> <span id="float-mail">Email</span></a>
</div>

<script>
    let idioma = 'es';

    const traducciones = {
        es: {
            'tagline': 'Empresa nueva con tecnología de vanguardia',
            'call-text': 'Llámanos',
            'email-text': 'Email',
            'web-text': 'Web Oficial',
            'nav-inicio': '🏠 Inicio',
            'nav-productos': '💧 Productos',
            'nav-visita': '📅 Solicitar Visita',
            'nav-faq': '❓ FAQ',
            'nav-ia': '🤖 Asistente IA',
            'inicio-titulo': 'Bienvenidos a la nueva era del agua',
            'inicio-subtitulo': 'Tecnología innovadora para mejorar tu calidad de vida',
            'sobre-adelva': '¿Quiénes somos?',
            'inicio-p1': 'En <b>ADELVA</b> no somos una empresa antigua con métodos obsoletos. Somos una <b>empresa nueva</b>, joven y dinámica, nacida con la misión fundamental de aplicar la tecnología más avanzada de 2024 al bienestar y la salud de tu familia. Nuestro equipo está formado por expertos en tratamiento de agua y soluciones de hogar inteligente.',
            'nuestra-promesa': 'Nuestra Promesa',
            'inicio-p2': 'Nuestra frescura y modernidad es nuestra mayor garantía. Utilizamos sistemas de ósmosis inversa y descalcificación de última generación que consumen menos energía, purifican más eficientemente y cuestan menos a largo plazo. Si buscas calidad, innovación, sostenibilidad y un trato cercano y personalizado, ADELVA es definitivamente tu sitio.',
            'feat1': 'Ósmosis inversa de última generación para agua de manantial en tu hogar',
            'feat2': 'Descalcificadores que protegen tu salud y tus electrodomésticos',
            'feat3': 'Sistemas sostenibles que reducen consumo y residuos',
            'feat4': 'Equipo técnico disponible para cualquier consulta o soporte',
            'prod1-titulo': '💧 Ósmosis Inversa Premium',
            'prod1-desc': 'Nuestra ósmosis es el sistema más avanzado para obtener agua pura en tu hogar. Olvida el sabor a cloro, los metales pesados y las impurezas. Disfruta de agua de manantial directamente en tu cocina con solo abrir el grifo. Es fundamental para la salud de tus riñones, para el sabor de tus comidas y para el bienestar de toda la familia. Instalación sencilla y mantenimiento mínimo.',
            'prod2-titulo': '🛡️ Descalcificadores Inteligentes',
            'prod2-desc': 'Protege tu hogar de la cal destructora. Nuestros equipos inteligentes eliminan el exceso de calcio y magnesio automáticamente, cuidando tu piel, tu cabello y alargando significativamente la vida de tu caldera y electrodomésticos. Ahorra dinero en reparaciones y sustituciones. Tecnología regenerable y eficiente energéticamente.',
            'prod3-titulo': '🌀 Sistemas de Ozono y UV',
            'prod3-desc': 'Desinfección total sin químicos nocivos. El ozono y la radiación UV eliminan virus, bacterias y patógenos del aire y el agua de forma ecológica y respetuosa con el medio ambiente. Es el complemento ideal para un hogar completamente saludable. Perfecto para familias con alergias o sistemas inmunológicos sensibles.',
            'prod4-titulo': '🛏️ Descanso Ergonómico',
            'prod4-desc': 'En ADELVA también cuidamos tu sueño y tu salud postural. Nuestros colchones de tecnología avanzada se adaptan perfectamente a tu cuerpo para garantizar un descanso reparador, profundo y saludable. Materiales de primera calidad que favorecen la circulación y alivian la presión corporal.',
            'visita-titulo': 'Solicita tu Visita Técnica Gratuita',
            'visita-desc': 'Nuestro equipo técnico visitará tu hogar para hacer un diagnóstico gratuito del agua y recomendarte la solución perfecta.',
            'label-nombre': 'Nombre completo',
            'label-email': 'Correo electrónico',
            'label-telefono': 'Teléfono',
            'label-ciudad': 'Ciudad',
            'label-producto': '¿Qué te interesa?',
            'opt-osmosis': 'Ósmosis Inversa',
            'opt-desc': 'Descalcificador',
            'opt-ozono': 'Ozono y UV',
            'opt-colchon': 'Colchón Ergonómico',
            'opt-todos': 'Ver todos los productos',
            'label-mensaje': 'Mensaje (opcional)',
            'btn-enviar': 'Solicitar Visita Gratuita',
            'success-text': '¡Solicitud enviada! Nos pondremos en contacto pronto.',
            'faq-titulo': 'Preguntas Frecuentes',
            'faq1-q': '¿Cuál es la diferencia entre ósmosis y descalcificación?',
            'faq1-a': 'La ósmosis inversa purifica el agua eliminando prácticamente todas las impurezas, incluidos minerales, sales y contaminantes. El descalcificador elimina específicamente el calcio y magnesio que causan la cal, sin purificar completamente el agua. Lo ideal es combinar ambos sistemas.',
            'faq2-q': '¿Cuánto cuesta la instalación?',
            'faq2-a': 'El precio varía según el sistema elegido y la complejidad de la instalación. La visita técnica diagnóstica es completamente gratuita. En esa visita te haremos un presupuesto sin compromiso adaptado a tus necesidades.',
            'faq3-q': '¿Requiere mucho mantenimiento?',
            'faq3-a': 'No. Nuestros sistemas son automáticos e inteligentes. Solo requieren cambios de filtros periódicos (aproximadamente cada 6-12 meses según uso). Nuestro equipo técnico puede encargarse del mantenimiento.',
            'faq4-q': '¿Es ecológico?',
            'faq4-a': 'Absolutamente. Nuestros sistemas reducen el consumo de plástico (no más botellas), ahorran agua y energía, y utilizan tecnologías sostenibles. Es una inversión en tu salud y en el planeta.',
            'faq5-q': '¿Ofrecen garantía?',
            'faq5-a': 'Sí. Todos nuestros equipos incluyen garantía de fabricante y soporte técnico gratuito durante el primer año. Además, ofrecemos planes de mantenimiento opcional.',
            'ia-titulo': '🤖 Soporte IA Adelva',
            'msg-bienvenida': '¡Hola! Soy la IA de ADELVA. Pregúntame sobre ósmosis, cal, ahorro o agendar una visita técnica. ¿En qué te ayudo?',
            'float-ws': 'WhatsApp',
            'float-tel': 'Llamar',
            'float-mail': 'Email',
            'placeholder': 'Escribe tu duda aquí...'
        },
        ca: {
            'tagline': 'Empresa nova amb tecnologia de punta',
            'call-text': 'Truca\'ns',
            'email-text': 'Correu',
            'web-text': 'Web Oficial',
            'nav-inicio': '🏠 Inici',
            'nav-productos': '💧 Productes',
            'nav-visita': '📅 Demanar Visita',
            'nav-faq': '❓ Preguntes',
            'nav-ia': '🤖 Assistent IA',
            'inicio-titulo': 'Benvinguts a la nova era de l\'aigua',
            'inicio-subtitulo': 'Tecnologia innovadora per millorar la teva qualitat de vida',
            'sobre-adelva': 'Qui som?',
            'inicio-p1': 'A <b>ADELVA</b> no som una empresa antiga amb mètodes obsolets. Som una <b>empresa nova</b>, jove i dinàmica, nascuda amb la missió fonamental d\'aplicar la tecnologia més avançada de 2024 al benestar i la salut de la teva família. El nostre equip està format per experts en tractament d\'aigua i solucions de llar intel·ligent.',
            'nuestra-promesa': 'La Nostra Promesa',
            'inicio-p2': 'La nostra frescor i modernitat és la nostra major garantia. Utilitzem sistemes d\'òsmosi inversa i descalcificació de darrera generació que consumeixen menys energia, purifiquen més eficientment i costen menys a llarg termini. Si busques qualitat, innovació, sostenibilitat i un tracte proper i personalitzat, ADELVA és definitivament el teu lloc.',
            'feat1': 'Òsmosi inversa de darrera generació per a aigua de font a la teva llar',
            'feat2': 'Descalcificadors que protegeixen la teva salut i els teus electrodomèstics',
            'feat3': 'Sistemes sostenibles que redueixen consum i residus',
            'feat4': 'Equip tècnic disponible per a qualsevol consulta o suport',
            'prod1-titulo': '💧 Òsmosi Inversa Premium',
            'prod1-desc': 'La nostra òsmosi és el sistema més avançat per obtenir aigua pura a la teva llar. Oblideu el sabor a clor, els metalls pesants i les impureses. Gaudeix de l\'aigua de font directament a la teva cuina només obrint el teu grifó. És fonamental per a la salut dels teus ronyons, per al sabor de les teves menges i per al benestar de tota la família. Instal·lació senzilla i manteniment mínim.',
            'prod2-titulo': '🛡️ Descalcificadors Intel·ligents',
            'prod2-desc': 'Protegeix la teva llar de la cal destructiva. Els nostres equips intel·ligents eliminen l\'excés de calci i magnesi automàticament, cuidant la teva pell, el teu cabell i allargant significativament la vida de la teva caldera i electrodomèstics. Estalvia diners en reparacions i substitucions. Tecnologia regenerable i eficient energèticament.',
            'prod3-titulo': '🌀 Sistemes d\'Ozó i UV',
            'prod3-desc': 'Desinfecció total sense químics nocius. L\'ozó i la radiació UV eliminen virus, bacteris i patògens de l\'aire i l\'aigua de forma ecològica i respectuosa amb el medi ambient. És el complement ideal per a una llar completament saludable. Perfecte per a famílies amb al·lèrgies o sistemes immunitaris sensibles.',
            'prod4-titulo': '🛏️ Descans Ergonòmic',
            'prod4-desc': 'A ADELVA també cuidem el teu son i la teva salut postural. Els nostres colchons de tecnologia avançada s\'adapten perfectament al teu cos per garantir un descans reparador, profund i saludable. Materials de primera qualitat que afavoreixen la circulació i alleugen la pressió corporal.',
            'visita-titulo': 'Demana la teva Visita Tècnica Gratuïta',
            'visita-desc': 'El nostre equip tècnic visitarà la teva llar per fer un diagnòstic gratuït de l\'aigua i recomanar-te la solució perfecta.',
            'label-nombre': 'Nom complet',
            'label-email': 'Adreça de correu electrònic',
            'label-telefono': 'Telèfon',
            'label-ciudad': 'Ciutat',
            'label-producto': 'Què t\'interessa?',
            'opt-osmosis': 'Òsmosi Inversa',
            'opt-desc': 'Descalcificador',
            'opt-ozono': 'Ozó i UV',
            'opt-colchon': 'Colchó Ergonòmic',
            'opt-todos': 'Veure tots els productes',
            'label-mensaje': 'Missatge (opcional)',
            'btn-enviar': 'Demanar Visita Gratuïta',
            'success-text': '¡Solicitud enviada! Ens posarem en contacte aviat.',
            'faq-titulo': 'Preguntes Freqüents',
            'faq1-q': 'Quina és la diferència entre òsmosi i descalcificació?',
            'faq1-a': 'L\'òsmosi inversa purifica l\'aigua eliminant pràcticament totes les impureses, inclosos minerals, sals i contaminants. El descalcificador elimina específicament el calci i el magnesi que causen la cal, sense purificar completament l\'aigua. L\'ideal és combinar ambdós sistemes.',
            'faq2-q': 'Quant costa la instal·lació?',
            'faq2-a': 'El preu varia segons el sistema escollit i la complexitat de la instal·lació. La visita tècnica de diagnòstic és completament gratuïta. En aquesta visita et farem un pressupost sense compromís adaptat a les teves necessitats.',
            'faq3-q': 'Requereix molt manteniment?',
            'faq3-a': 'No. Els nostres sistemes són automàtics i intel·ligents. Només requereixen canvis de filtres periòdics (aproximadament cada 6-12 mesos segons l\'ús). El nostre equip tècnic pot encarregar-se del manteniment.',
            'faq4-q': 'És ecològic?',
            'faq4-a': 'Absolutament. Els nostres sistemes redueixen el consum de plàstic (no més ampolles), estalvien aigua i energia, i utilitzen tecnologies sostenibles. És una inversió en la teva salut i en el planeta.',
            'faq5-q': 'Ofereixen garantia?',
            'faq5-a': 'Sí. Tots els nostres equips inclouen garantia del fabricant i suport tècnic gratuït durant el primer any. A més, oferim plans de manteniment opcionals.',
            'ia-titulo': '🤖 Suport IA Adelva',
            'msg-bienvenida': '¡Hola! Sóc l\'assistent de l\'IA d\'ADELVA. Pregunta\'m sobre òsmosi, cal, estalvi o agendar una visita tècnica. ¿Com t\'ajudo?',
            'float-ws': 'WhatsApp',
            'float-tel': 'Trucar',
            'float-mail': 'Correu',
            'placeholder': 'Escriu la teva dubte aquí...'
        }
    };

    function cambiarIdioma() {
        idioma = idioma === 'es' ? 'ca' : 'es';
        const btnLang = document.querySelector('.lang-switch');
        btnLang.textContent = idioma === 'es' ? '🌐 Català' : '🌐 Español';
        
        Object.keys(traducciones[idioma]).forEach(key => {
            const elem = document.getElementById(key);
            if (elem) {
                elem.innerHTML = traducciones[idioma][key];
            }
        });

        document.getElementById('chatIn').placeholder = traducciones[idioma]['placeholder'];
        document.documentElement.lang = idioma;
    }

    function tab(e, id) {
        document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('active'));
        document.querySelectorAll('.t-btn').forEach(b => b.classList.remove('active'));
        document.getElementById(id).classList.add('active');
        if(e) e.currentTarget.classList.add('active');
        window.scrollTo(0,0);
    }

    function toggleFaq(element) {
        const answer = element.nextElementSibling;
        answer.classList.toggle('active');
        element.querySelector('i').style.transform = answer.classList.contains('active') ? 'rotate(180deg)' : 'rotate(0)';
    }

    function enviarVisita(e) {
        e.preventDefault();
        const nombre = document.getElementById('nombre').value;
        const email = document.getElementById('email').value;
        const telefono = document.getElementById('telefono').value;
        const ciudad = document.getElementById('ciudad').value;
        const producto = document.getElementById('producto').value;
        const mensaje = document.getElementById('mensaje').value;

        // Simular envío (en producción, enviar a servidor)
        const textoMensaje = `Solicitud de visita:\nNombre: ${nombre}\nEmail: ${email}\nTeléfono: ${telefono}\nCiudad: ${ciudad}\nProducto interesado: ${producto}\nMensaje: ${mensaje}`;
        
        // Aquí se podría enviar por WhatsApp, email, etc.
        // Por ahora, mostrar mensaje de éxito
        document.getElementById('visitForm').reset();
        document.getElementById('successMsg').style.display = 'block';
        setTimeout(() => {
            document.getElementById('successMsg').style.display = 'none';
        }, 5000);
    }

    function hablar() {
        let input = document.getElementById('chatIn');
        let win = document.getElementById('chat-window');
        let val = input.value.toLowerCase();
        if(!val.trim()) return;

        win.innerHTML += `<div class="msg user">${input.value}</div>`;
        input.value = "";

        setTimeout(() => {
            let res = idioma === 'es' ? 
                "Es una excelente pregunta. Al ser una **empresa nueva**, tenemos la tecnología más moderna para solucionarlo. Lo mejor es que solicites una visita gratuita en nuestra sección 'Solicitar Visita' o nos contactes al 614308378 o serviceadelvatop@gmail.com." :
                "És una excel·lent pregunta. Al ser una **empresa nova**, tenim la tecnologia més moderna per solucionar-ho. El millor és que sol·licitis una visita gratuïta a la nostra secció 'Demanar Visita' o ens contactis al 614308378 o serviceadelvatop@gmail.com.";
            
            if(val.includes("cal")) {
                res = idioma === 'es' ? 
                    "Nuestros descalcificadores eliminan la cal al 100%. Ahorrarás dinero y protegerás tu piel. ¿Quieres agendar una prueba de dureza gratis? Llámanos: 614308378" :
                    "Els nostres descalcificadors eliminen la cal al 100%. Estalviaràs diners i protegiraàs la teva pell. ¿Vols agendar una prova de duresa gratis? Truca'ns: 614308378";
            }
            if(val.includes("osmosi")) {
                res = idioma === 'es' ? 
                    "La ósmosis ADELVA purifica el agua totalmente. Es fundamental para dejar de cargar botellas. ¡Se paga sola con el ahorro! Contáctanos: 614308378" :
                    "L'òsmosi ADELVA purifica l'aigua totalment. És fonamental per deixar de carregar ampolles. ¡Es paga sola amb l'estalvi! Contacta'ns: 614308378";
            }
            if(val.includes("hola")) {
                res = idioma === 'es' ? 
                    "¡Hola! Soy el asistente virtual de ADELVA. ¿Qué producto te interesa hoy?" :
                    "¡Hola! Sóc l'assistent virtual d'ADELVA. Quin producte t'interessa avui?";
            }
            if(val.includes("precio") || val.includes("preu")) {
                res = idioma === 'es' ? 
                    "Los precios varían según el sistema. La visita diagnóstica es GRATUITA. Nuestro técnico te hará un presupuesto personalizado. ¡Contáctanos!" :
                    "Els preus varien segons el sistema. La visita de diagnòstic és GRATUÏTA. El nostre tècnic et farà un pressupost personalitzat. ¡Contacta'ns!";
            }
            
            win.innerHTML += `<div class="msg bot">${res}</div>`;
            win.scrollTop = win.scrollHeight;
        }, 500);
    }

    // Permitir enviar mensaje con Enter
    document.addEventListener('DOMContentLoaded', function() {
        document.getElementById('chatIn').addEventListener('keypress', function(e) {
            if(e.key === 'Enter') hablar();
        });
    });
</script>

</body>
</html>

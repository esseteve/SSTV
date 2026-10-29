# SSTV
presentación de eseteve
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SSTV - Presentación Oficial</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
        }

        body {
            background-color: #0b0f19;
            color: #f3f4f6;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: space-between;
            padding: 20px;
        }

        header {
            text-align: center;
            margin-top: 20px;
        }

        h1 {
            font-size: 2.2rem;
            letter-spacing: 2px;
            color: #ffffff;
            margin-bottom: 8px;
        }

        p.subtitle {
            color: #9ca3af;
            font-size: 0.95rem;
        }

        .main-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            width: 100%;
            max-width: 480px;
            margin: 20px 0;
            gap: 20px;
        }

        .canvas-card {
            background: #111827;
            border: 1px solid #1f2937;
            border-radius: 16px;
            padding: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
            width: 100%;
            box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.3);
            position: relative;
        }

        canvas {
            background: #030712;
            border-radius: 12px;
            cursor: pointer;
            border: 1px solid #374151;
            box-shadow: inset 0 2px 4px rgba(0,0,0,0.6);
        }

        .mascot-status {
            margin-top: 12px;
            font-size: 0.85rem;
            color: #60a5fa;
            background: rgba(37, 99, 235, 0.1);
            padding: 4px 12px;
            border-radius: 20px;
            border: 1px solid rgba(37, 99, 235, 0.2);
            text-transform: uppercase;
            letter-spacing: 1px;
            font-weight: 600;
        }

        .controls-row {
            display: flex;
            gap: 8px;
            margin-top: 15px;
            width: 100%;
        }

        .btn-mode {
            flex: 1;
            background: #1f2937;
            color: #d1d5db;
            border: 1px solid #374151;
            padding: 8px 0;
            border-radius: 8px;
            font-size: 0.8rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s ease;
            text-align: center;
        }

        .btn-mode:hover, .btn-mode.active {
            background: #3b82f6;
            color: #ffffff;
            border-color: #60a5fa;
        }

        .terminal-box {
            width: 100%;
            background: #030712;
            border: 1px solid #1f2937;
            border-radius: 12px;
            padding: 12px;
            font-family: monospace;
            font-size: 0.8rem;
            color: #34d399;
            margin-top: 15px;
            display: flex;
            flex-direction: column;
            gap: 6px;
        }

        .terminal-header {
            color: #6b7280;
            font-size: 0.75rem;
            border-bottom: 1px solid #1f2937;
            padding-bottom: 4px;
            display: flex;
            justify-content: space-between;
        }

        .terminal-input-row {
            display: flex;
            gap: 6px;
            align-items: center;
        }

        .terminal-input-row span {
            color: #f472b6;
        }

        .terminal-input {
            background: transparent;
            border: none;
            color: #f3f4f6;
            font-family: monospace;
            font-size: 0.8rem;
            outline: none;
            flex: 1;
        }

        .cards-section {
            display: flex;
            flex-direction: column;
            gap: 12px;
            width: 100%;
        }

        .info-card {
            background: #111827;
            border: 1px solid #1f2937;
            border-radius: 12px;
            padding: 16px;
            display: flex;
            flex-direction: column;
            gap: 6px;
        }

        .info-card h3 {
            font-size: 0.95rem;
            color: #ffffff;
            font-weight: 600;
        }

        .info-card p {
            font-size: 0.85rem;
            color: #9ca3af;
            line-height: 1.4;
        }

        footer {
            text-align: center;
            font-size: 0.75rem;
            color: #4b5563;
            margin-top: 20px;
            padding-bottom: 10px;
        }
    </style>
</head>
<body>

    <header>
        <h1>SSTV</h1>
        <p class="subtitle">Estamos siempre al servicio.</p>
    </header>

    <div class="main-container">
        <!-- Canvas Interactivo con T -->
        <div class="canvas-card">
            <canvas id="mascotCanvas" width="260" height="260"></canvas>
            <div class="mascot-status" id="statusBadge">Modo: Normal</div>
            
            <div class="controls-row">
                <button class="btn-mode active" onclick="setMode('normal')">Normal</button>
                <button class="btn-mode" onclick="setMode('baile')">Baile</button>
                <button class="btn-mode" onclick="setMode('saludo')">Saludo Real</button>
                <button class="btn-mode" onclick="setMode('sorprendido')">Sorprendido</button>
            </div>

            <!-- Terminal interactiva -->
            <div class="terminal-box">
                <div class="terminal-header">
                    <span>SSTV-OS // Consola</span>
                    <span>12 FPS</span>
                </div>
                <div class="terminal-input-row">
                    <span>&gt;</span>
                    <input type="text" id="terminalInput" class="terminal-input" placeholder="Escribe 'baile', 'saludo', 'sorprendido'..." onkeydown="handleTerminal(event)">
                </div>
            </div>
        </div>

        <!-- Tarjetas de Contenido Limpias -->
        <div class="cards-section">
            <div class="info-card">
                <h3>Animaciones básicas</h3>
                <p>Animación por capas y otras muchas cosas.</p>
            </div>
            <div class="info-card">
                <h3>Creación de aplicaciones web sencillas e interactivas para presentar tus propios proyectos.</h3>
                <p>Enfoque minimalista y funcional para despliegues rápidos.</p>
            </div>
        </div>
    </div>

    <footer>
        SSTV &copy; 2026 // Arquitectura Interactiva
    </footer>

    <script>
        const canvas = document.getElementById('mascotCanvas');
        const ctx = canvas.getContext('2d');
        const statusBadge = document.getElementById('statusBadge');
        const terminalInput = document.getElementById('terminalInput');
        const buttons = document.querySelectorAll('.btn-mode');

        let currentMode = 'normal'; // 'normal', 'baile', 'saludo', 'sorprendido'
        let frameCount = 0;

        function setMode(mode) {
            currentMode = mode;
            statusBadge.innerText = `Modo: ${mode.charAt(0).toUpperCase() + mode.slice(1)}`;
            
            buttons.forEach(btn => btn.classList.remove('active'));
            if(mode === 'normal') buttons[0].classList.add('active');
            if(mode === 'baile') buttons[1].classList.add('active');
            if(mode === 'saludo') buttons[2].classList.add('active');
            if(mode === 'sorprendido') buttons[3].classList.add('active');
        }

        function handleTerminal(e) {
            if (e.key === 'Enter') {
                const val = terminalInput.value.trim().toLowerCase();
                if(val === 'baile' || val === 'saludo' || val === 'sorprendido' || val === 'normal') {
                    setMode(val);
                } else if(val === 'saludo real') {
                    setMode('saludo');
                }
                terminalInput.value = '';
            }
        }

        canvas.addEventListener('click', () => {
            if(currentMode === 'normal') setMode('baile');
            else if(currentMode === 'baile') setMode('saludo');
            else if(currentMode === 'saludo') setMode('sorprendido');
            else setMode('normal');
        });

        // Bucle de renderizado fijo a 12 FPS
        const fps = 12;
        const frameInterval = 1000 / fps;
        let lastTime = 0;

        function gameLoop(timestamp) {
            if (!lastTime) lastTime = timestamp;
            const elapsed = timestamp - lastTime;

            if (elapsed >= frameInterval) {
                lastTime = timestamp - (elapsed % frameInterval);
                frameCount++;
                updateAndDraw();
            }
            requestAnimationFrame(gameLoop);
        }

        function updateAndDraw() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);

            const cx = canvas.width / 2;
            const cy = canvas.height / 2 + 10;

            // Animación de flotación base
            let floatY = 0;
            if (currentMode === 'baile') {
                floatY = Math.sin(frameCount * 0.4) * 6;
            } else if (currentMode === 'normal') {
                floatY = Math.sin(frameCount * 0.2) * 3;
            }
            // En modo 'saludo' y 'sorprendido' se queda firme (sin flotar o flotación mínima)

            // Antena (Estática en modo sorprendido, sutil en los demás)
            let antennaWobble = (currentMode === 'sorprendido') ? 0 : Math.sin(frameCount * 0.3) * 2;
            ctx.strokeStyle = '#4b5563';
            ctx.lineWidth = 4;
            ctx.beginPath();
            ctx.moveTo(cx, cy - 45 + floatY);
            ctx.lineTo(cx + antennaWobble, cy - 75 + floatY);
            ctx.stroke();

            // Punta antena (roja brillante)
            ctx.fillStyle = '#ef4444';
            ctx.beginPath();
            ctx.arc(cx + antennaWobble, cy - 78 + floatY, 6, 0, Math.PI * 2);
            ctx.fill();

            // Cuerpo principal (Geométrico)
            ctx.fillStyle = '#1f2937';
            ctx.strokeStyle = '#374151';
            ctx.lineWidth = 3;
            ctx.beginPath();
            ctx.roundRect(cx - 45, cy - 45 + floatY, 90, 85, 14);
            ctx.fill();
            ctx.stroke();

            // Pixel-art "X" en el pecho
            ctx.strokeStyle = '#60a5fa';
            ctx.lineWidth = 3;
            ctx.beginPath();
            // Barra 1 de la X
            ctx.moveTo(cx - 12, cy - 15 + floatY);
            ctx.lineTo(cx + 12, cy + 9 + floatY);
            // Barra 2 de la X
            ctx.moveTo(cx + 12, cy - 15 + floatY);
            ctx.lineTo(cx - 12, cy + 9 + floatY);
            ctx.stroke();

            // Brazos y Manos según el modo
            if (currentMode === 'baile') {
                // Manos flotantes animadas del modo baile
                let handOffset1 = Math.sin(frameCount * 0.5) * 6;
                let handOffset2 = Math.cos(frameCount * 0.5) * 6;
                
                // Mano Izquierda
                ctx.fillStyle = '#374151';
                ctx.beginPath();
                ctx.arc(cx - 62, cy - 10 + floatY + handOffset1, 10, 0, Math.PI * 2);
                ctx.fill();
                
                // Mano Derecha
                ctx.beginPath();
                ctx.arc(cx + 62, cy - 10 + floatY + handOffset2, 10, 0, Math.PI * 2);
                ctx.fill();

            } else if (currentMode === 'saludo') {
                // SALUDO REAL: Mano izquierda abajo casi estática con su X, mano derecha arriba girando en semicircunferencia
                let staticLeftMicro = Math.sin(frameCount * 0.2) * 2;
                
                // Mano Izquierda (Abajo, estática con X en el centro)
                let lx = cx - 55;
                let ly = cy + 25 + staticLeftMicro;
                ctx.fillStyle = '#374151';
                ctx.beginPath();
                ctx.arc(lx, ly, 10, 0, Math.PI * 2);
                ctx.fill();
                // X dentro de la mano izquierda abajo
                ctx.strokeStyle = '#60a5fa';
                ctx.lineWidth = 2;
                ctx.beginPath();
                ctx.moveTo(lx - 4, ly - 4); ctx.lineTo(lx + 4, ly + 4);
                ctx.moveTo(lx + 4, ly - 4); ctx.lineTo(lx - 4, ly + 4);
                ctx.stroke();

                // Mano Derecha (Arriba, girando en semicircunferencia)
                let angle = (frameCount * 0.15) % Math.PI; // Semicircunferencia
                let rx = cx + 45 + Math.cos(angle) * 15;
                let ry = cy - 35 - Math.sin(angle) * 15;
                
                ctx.fillStyle = '#374151';
                ctx.beginPath();
                ctx.arc(rx, ry, 10, 0, Math.PI * 2);
                ctx.fill();

            } else if (currentMode === 'sorprendido') {
                // Brazos pegados o ligeramente alzados por la sorpresa, estáticos
                ctx.fillStyle = '#374151';
                ctx.beginPath();
                ctx.arc(cx - 55, cy - 5, 10, 0, Math.PI * 2);
                ctx.arc(cx + 55, cy - 5, 10, 0, Math.PI * 2);
                ctx.fill();
            } else {
                // Modo Normal (Brazos neutros)
                ctx.fillStyle = '#374151';
                ctx.beginPath();
                ctx.arc(cx - 55, cy, 10, 0, Math.PI * 2);
                ctx.arc(cx + 55, cy, 10, 0, Math.PI * 2);
                ctx.fill();
            }

            // Ojos / Pantalla frontal
            ctx.fillStyle = '#030712';
            ctx.beginPath();
            ctx.roundRect(cx - 28, cy - 30 + floatY, 56, 18, 6);
            ctx.fill();

            // Expresión facial según modo
            ctx.fillStyle = '#34d399'; // Verde terminal por defecto
            if (currentMode === 'sorprendido') {
                // Ojos bien abiertos / sorprendidos (círculos o puntos grandes)
                ctx.beginPath();
                ctx.arc(cx - 14, cy - 21 + floatY, 4, 0, Math.PI * 2);
                ctx.arc(cx + 14, cy - 21 + floatY, 4, 0, Math.PI * 2);
                ctx.fill();
            } else if (currentMode === 'baile' || currentMode === 'saludo') {
                // Ojos felices (^ ^)
                ctx.strokeStyle = '#34d399';
                ctx.lineWidth = 2;
                ctx.beginPath();
                ctx.moveTo(cx - 18, cy - 18 + floatY); ctx.lineTo(cx - 14, cy - 23 + floatY); ctx.lineTo(cx - 10, cy - 18 + floatY);
                ctx.moveTo(cx + 10, cy - 18 + floatY); ctx.lineTo(cx + 14, cy - 23 + floatY); ctx.lineTo(cx + 18, cy - 18 + floatY);
                ctx.stroke();
            } else {
                // Ojos normales (líneas horizontales o puntos)
                ctx.fillRect(cx - 16, cy - 23 + floatY, 8, 4);
                ctx.fillRect(cx + 8, cy - 23 + floatY, 8, 4);
            }
        }

        // Iniciar bucle
        requestAnimationFrame(gameLoop);
    </script>
</body>
</html>


<style>
    /* Estilos para el README */
    .readme-section {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        z-index: 20; /* Asegura que esté por encima del chat si lo quieres superpuesto */
        width: 85%;
        max-width: 550px;
        padding: 30px;
        background-color: var(--color-fondo-app); /* #283038 */
        border-radius: 16px;
        box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
        color: var(--color-texto-usuario);
        opacity: 0;
        visibility: hidden;
        transition: opacity 0.3s ease, visibility 0.3s ease;
    }

    .readme-section.active {
        opacity: 1;
        visibility: visible;
    }

    .readme-section h2 {
        color: var(--color-plomo-pastel); /* #BCC2C2 */
        text-align: center;
        margin-bottom: 25px;
        font-size: 1.8em;
    }

    .model-table {
        width: 100%;
        border-collapse: separate;
        border-spacing: 0;
        margin-top: 20px;
        overflow: hidden;
        border-radius: 8px;
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.4);
    }

    .model-table th, .model-table td {
        padding: 12px 15px;
        text-align: left;
        border-bottom: 1px solid rgba(255, 255, 255, 0.1);
    }

    .model-table th {
        background-color: var(--color-negro-pastel); /* #36454F */
        color: var(--color-plomo-pastel);
        font-weight: bold;
        text-transform: uppercase;
        font-size: 0.9em;
    }

    .model-table tr:nth-child(even) {
        background-color: var(--color-chat-fondo); /* #3E4E5A */
    }

    .model-table tr:nth-child(odd) {
        background-color: var(--color-fondo-app); /* #283038 */
    }

    .model-table td strong {
        color: #8be9fd; /* Un color de resaltado */
    }

    .model-table .status-ok {
        color: #50fa7b; /* Verde brillante */
        font-weight: bold;
    }

    .model-table .status-down {
        color: #ff5555; /* Rojo */
        font-weight: bold;
    }

    .readme-close {
        background: none;
        border: none;
        color: var(--color-plomo-pastel);
        font-size: 1.5em;
        position: absolute;
        top: 10px;
        right: 10px;
        cursor: pointer;
        padding: 10px;
        border-radius: 50%;
        transition: background-color 0.2s;
    }

    .readme-close:hover {
        background-color: rgba(255, 255, 255, 0.1);
    }
</style>

<div class="readme-section" id="readmeSection">
    <button class="readme-close" onclick="toggleReadme()">&#10005;</button>
    <h2>Acerca de ByKyvczz</h2>
    <p>Esta aplicación de chat utiliza potentes modelos de Inteligencia Artificial para ofrecer respuestas precisas y creativas, incluyendo análisis multimodal (texto e imagen).</p>

    <table class="model-table">
        <thead>
            <tr>
                <th>IA</th>
                <th>Modelo Principal</th>
                <th>Estado Actual</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>**Google Gemini**</td>
                <td><strong>gemini-2.5-flash</strong></td>
                <td class="status-ok">Activo y estable</td>
            </tr>
            <tr>
                <td>**AIModelProof**</td>
                <td><strong>gemini-2.5-flash (Proxy)</strong></td>
                <td class="status-ok">Activo</td>
            </tr>
            <tr>
                <td>**OpenAI**</td>
                <td>*Modelo no especificado*</td>
                <td class="status-down">Deshabilitado (Cuota Agotada)</td>
            </tr>
        </tbody>
    </table>

    <p style="margin-top: 20px; font-size: 0.9em; opacity: 0.7;">
        La disponibilidad de los modelos puede variar. Utilizamos la API de Google AI Studio para Gemini.
    </p>
</div>

<script>
    // Función JavaScript para mostrar/ocultar el README
    const readmeElement = document.getElementById('readmeSection');
    const chatApp = document.getElementById('chatAppContainer'); 

    function toggleReadme() {
        if (readmeElement.classList.contains('active')) {
            readmeElement.classList.remove('active');
            if (chatApp) {
                chatApp.style.opacity = 1; // Restaurar opacidad del chat
                chatApp.style.pointerEvents = 'auto'; // Habilitar interacciones
            }
        } else {
            readmeElement.classList.add('active');
            if (chatApp) {
                chatApp.style.opacity = 0.4; // Oscurecer/difuminar el chat
                chatApp.style.pointerEvents = 'none'; // Deshabilitar interacciones
            }
        }
    }
    
    // Opcional: Añade un botón a tu interfaz principal para llamar a toggleReadme()
    // Por ejemplo, puedes añadir un botón en el header del chat: 
    /*
        <button onclick="toggleReadme()" style="position: absolute; right: 20px; top: 15px; background: none; border: none; color: #BCC2C2; cursor: pointer;">
            i
        </button>
    */
</script>

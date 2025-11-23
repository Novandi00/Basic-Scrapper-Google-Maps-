🗺️ GMap Guerrilla Scraper (Console Edition)

Herramienta de extracción de datos ligera (Client-Side) para auditoría de mercados locales en Google Maps.
Sin API Keys. Sin Selenium. Sin Instalaciones complejas.

📖 Sobre el Proyecto

Este script fue diseñado para resolver un problema de fricción en la prospección B2B: La necesidad de obtener datos estructurados (Leads) de negocios locales sin configurar entornos complejos de Python/Selenium.

Funciona inyectando una clase JavaScript (GMapScraper) directamente en la consola del navegador, interactuando con el DOM de Google Maps en tiempo real para simular el comportamiento humano (scroll, espera) y extraer datos públicos.

Caso de Uso Principal:

Auditoría de presencia digital de PYMES.

Generación rápida de "Hitlists" para ventas B2B.

Investigación de mercado por nicho geográfico.

⚡ Características (Features)

Arquitectura OOP: Código estructurado en clases ES6 para fácil mantenimiento y escalabilidad.

Simulación Humana: Implementa scrollLoop con retardos aleatorios (Math.random) para evitar bloqueos por comportamiento robótico (Rate Limiting pasivo).

Extracción Heurística:

Detecta sitios web incluso si el botón está ofuscado.

Normaliza calificaciones y conteo de reseñas.

Exportación Nativa: Genera y descarga automáticamente un archivo .csv limpio y listo para Excel/Google Sheets.

Zero-Dependency: No requiere npm install ni librerías externas.

🚀 Instalación y Uso

Este es un script de Inyección en Consola. No requiere instalación en el sistema operativo.

Abre Google Maps en tu navegador (Chrome/Edge recomendado).

Realiza tu búsqueda. (Ej: "Mueblerías en Córdoba").

Abre las Herramientas de Desarrollador (F12 o Clic Derecho > Inspeccionar).

Ve a la pestaña Console.

Copia el código del archivo scraper.js de este repositorio.

Pégalo en la consola y presiona ENTER.

El script comenzará a hacer scroll automáticamente y descargará el archivo Leads_Maps_YYYY-MM-DD.csv al finalizar.

🛠️ Estructura del Código

El script opera bajo una única clase GMapScraper para encapsular el estado:

class GMapScraper {
    constructor() {
        this.config = { ... } // Configuración de Tiempos y Límites
        this.selectors = { ... } // Mapeo de selectores DOM (Resiliente a cambios)
    }

    async init() { ... } // Orquestador principal
    async scrollLoop() { ... } // Lógica de navegación y carga lazy-load
    extractData() { ... } // Parsing del DOM y limpieza de Strings
    downloadCSV() { ... } // Generación de Blob y descarga
}


⚙️ Configuración

Puedes modificar los parámetros directamente en el constructor de la clase antes de pegar el código:

this.config = {
    scrollDelay: 2500,    // Milisegundos entre scrolls
    maxScrolls: 50,       // Límite de seguridad
    minRating: 0.0,       // Filtrar negocios con bajo rating
    exportFileName: 'Mis_Leads.csv'
};


⚠️ Disclaimer Legal y Ético

Este software es para fines educativos y de investigación de mercado propia.

No abuse de las solicitudes a Google Maps.

Respete los Términos de Servicio de Google.

Los datos extraídos son información pública disponible en la web.

Author: [Novandi / Usuario GitHub]
Built for efficiency.
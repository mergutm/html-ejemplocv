# Curriculum Vitae Interactivo y Responsive con HTML5 y CSS3

---

## 1: Estructura HTML5 Semántica Bloque a Bloque

Comenzamos creando la estructura HTML5 paso a paso. Se emplean elementos semánticos que aportan significado al contenido antes de aplicar cualquier estilo visual.

### Paso 1.1: Configuración del Documento y Meta Viewport
Iniciamos con el esqueleto básico e incluimos la etiqueta `<meta name="viewport">` fundamental para habilitar el diseño adaptable en dispositivos móviles.

```html
<!DOCTYPE html>
<html lang="es">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CV - Ing. Sofía Sánchez Mendoza</title>
    <link rel="stylesheet" href="styles.css">
</head>

<body>
    <div class="cv-container">

    </div>

</body>

</html>
```

> **Explicación:**
> * `viewport`: Controla cómo se dimensiona la página en dispositivos móviles. `width=device-width` establece el ancho de la pantalla igual al ancho real del dispositivo, e `initial-scale=1.0` evita que el navegador móvil acerque o aleje la página por defecto.

---

### Paso 1.2: Cabecera del Perfil (`<header>`)
Cabecera con la fotografía del/la ingeniero, su nombre y su carrera.

```html
<header class="profile-header">
    <div class="avatar-wrapper">
        <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?q=80&w=400&auto=format&fit=crop" 
                alt="Fotografía de Sofía Sánchez Mendoza" 
                class="profile-avatar">
    </div>
    <div class="profile-title">
        <h1>Sofía Sánchez Mendoza</h1>
        <h2>Ingeniero en Desarrollo de Software</h2>
        <p class="tagline">Especialista en Arquitecturas Cloud, APIs RESTful y Sistemas Distribuidos</p>
    </div>
</header>
```

---

### Paso 1.3: Sección "Sobre Mí" (`<section class="about">`)
Descripción de la carrera del ingeniero.

```html
 <main>
    <section class="cv-section about-section">
        <h3 class="section-title">Perfil Profesional</h3>
        <p>
            Ingeniero en Desarrollo de Software con más de 5 años de experiencia en el diseño y despliegue de aplicaciones web de alto rendimiento. Apasionado por la optimización de código, desarrollo de APIs RESTful seguras y migración de servicios a la nube.
        </p>
    </section>
</main>
```

---

### Paso 1.4: Sección "Habilidades Técnicas" (`<section class="skills">`)
Competencias técnicas utilizando etiquetas semánticas y badges (`<span>`).

```html
<section class="cv-section skills-section">
    <h3 class="section-title">Habilidades de Software</h3>
    <div class="skills-grid">
        <span class="skill-badge">JavaScript (ES6+)</span>
        <span class="skill-badge">Python / Django</span>
        <span class="skill-badge">Node.js / Express</span>
        <span class="skill-badge">React.js</span>
        <span class="skill-badge">SQL (PostgreSQL)</span>
        <span class="skill-badge">Docker & Kubernetes</span>
        <span class="skill-badge">Git / GitHub</span>
        <span class="skill-badge">AWS / Cloud</span>
    </div>
</section>
```

---

### Paso 1.5: Sección "Proyectos Destacados" (`<section class="projects">`)
Proyectos de desarrollo utilizando tarjetas (`<article>`).

```html
<section class="cv-section projects-section">
    <h3 class="section-title">Proyectos Destacados</h3>
    <div class="projects-grid">
        <article class="project-card">
            <h4>EduControl - Plataforma Académica</h4>
            <p class="project-tech">Tecnologías: Python, Django, PostgreSQL, Docker</p>
            <p>Sistema integral de gestión de calificaciones y asistencia escolar con autenticación JWT y comunicación en tiempo real vía WebSockets.</p>
        </article>
        
        <article class="project-card">
            <h4>TechMarket - E-commerce Microservicios</h4>
            <p class="project-tech">Tecnologías: Node.js, Express, React, Redis, AWS</p>
            <p>Arquitectura distribuida de comercio electrónico con balanceo de carga, procesamiento de pagos con Stripe y caché distribuido.</p>
        </article>
    </div>
</section>
```

---

### Paso 1.6: Pie de Página y Contactos (`<footer>`)
Concluimos el marcado HTML con la sección de contacto.

```html
        <footer class="cv-footer">
            <address class="contact-info">
                <p>📧 Email: <a href="mailto:carlos.mendoza@devengine.com">carlos.mendoza@devengine.com</a></p>
                <p>📱 Teléfono: +52 (55) 8765-4321</p>
                <p>🌐 GitHub: <a href="https://github.com" target="_blank">github.com/carlos-dev</a></p>
            </address>
        </footer>
    </div> <!-- Cierre de .cv-container -->
</body>
</html>
```

---

## 2: Estilos Base, Variables CSS y Modelo de Caja

Archivo CSS (`styles.css`), con  un reset universal.

### Paso 2.1: Reset Universal
```css
/* Reset Básico de Márgenes y Rellenos */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```

> **Explicación:**
> * `box-sizing: border-box`: Por defecto, al usar  el modelo de caja tradicional (`content-box`), al añadir `padding` o `border` el tamaño total del elemento aumenta. Con `border-box`, el relleno y el borde se incluyen **dentro** del ancho y alto especificados, evitando descuadres inesperados en el maquetado.
---

https://developer.mozilla.org/es/docs/Web/CSS/Reference/Properties/box-sizing


### Paso 2.2: Variables CSS Globales (`:root`)
Paleta de colores moderna para reutilizar en todo el documento.

```css
:root {
    --primary-color: #1e293b;       /* Azul oscuro sobrio */
    --accent-color: #0284c7;        /* Azul brillante tecnológico */
    --accent-hover: #0369a1;        /* Azul al pasar el cursor */
    --bg-gradient: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
    --card-bg: #ffffff;
    --text-primary: #0f172a;
    --text-secondary: #475569;
    --shadow-soft: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
    --shadow-hover: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
    --transition-smooth: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}
```

> **Explicación:**
> * `:root`: Es la pseudo-clase de mayor nivel jerárquico en el documento. Al declarar variables con `--` dentro de `:root`, están disponibles globalmente en cualquier selector mediante la función `var(--nombre-variable)`.

---

### Paso 2.3: Fondo del Cuerpo y Contenedor Principal
Configuración del lienzo general de la página.

```css
body {
    font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
    background: var(--bg-gradient);
    color: var(--text-primary);
    line-height: 1.6;
    padding: 2rem 1rem;
    min-height: 100vh;
}

.cv-container {
    max-width: 900px;
    margin: 0 auto;
    background: var(--card-bg);
    border-radius: 16px;
    padding: 2.5rem;
    box-shadow: var(--shadow-soft);
}
```

---

## 3: Recorte y Enmarcado Ovalado de la Fotografía de Perfil

Para tener una imagen **redondeada en forma de óvalo**, aplicamos una relación de aspecto asimétrica combinada con `border-radius` y recorte limpio.

### Paso 3.1: Definición del Óvalo con CSS
```css
.avatar-wrapper {
    flex-shrink: 0;
}

.profile-avatar {
    /* Dimensiones asimétricas para forzar la forma de óvalo */
    width: 150px;
    height: 190px;
    
    /* El valor del 50% en una caja no cuadrada genera una elipse / óvalo perfecto */
    border-radius: 50%;
    
    /* Evita que la fotografía se deforme o estire */
    object-fit: cover;
    object-position: center top;
    
    /* Borde estético e iluminación */
    border: 4px solid var(--card-bg);
    outline: 3px solid var(--accent-color);
    box-shadow: 0 8px 16px rgba(2, 132, 199, 0.2);
    
    transition: var(--transition-smooth);
}
```

> **Explicación de los comandos:**
> * `border-radius: 50%`: Si un elemento es un cuadrado perfecto (`width == height`), `border-radius: 50%` genera un círculo. Sin embargo, cuando las dimensiones son asimétricas (en este caso `width: 150px` y `height: 190px`), el algoritmo de CSS calcula el radio de curvatura en forma de **elipse u óvalo**.
> * `object-fit: cover`: Cuando una imagen con una relación de aspecto nativa distinta se fuerza dentro de dimensiones fijas, tiende a distorsionarse. `object-fit: cover` hace que la imagen escale manteniendo sus proporciones para llenar completamente el contenedor, recortando los sobrantes.
> * `object-position: center top`: Centra el encuadre en la parte superior de la foto para asegurar que el rostro sea el punto focal.
> * `outline`: Dibuja un segundo contorno exterior por fuera del `border` sin alterar el modelo de caja.
> * `flex-shrink: 0:` Se ordena al navegador que respete el tamaño original de ese elemento (definido por su ancho, alto o flex-basis) y que nunca lo haga más pequeño, sin importar si falta espacio en la pantalla. https://www.youtube.com/watch?v=HySjMxQ6dTk
---

## 4: Maquetación Flexible y Grillas Adaptables (Flexbox & CSS Grid)

La alineación de componentes utilizando Flexbox para encabezados y CSS Grid para arreglos de habilidades y proyectos.

### Paso 4.1: Flexbox en el Header del Perfil
```css
.profile-header {
    display: flex;
    align-items: center;
    gap: 2rem;
    padding-bottom: 2rem;
    border-bottom: 2px solid #f1f5f9;
}

.profile-title h1 {
    font-size: 2.2rem;
    color: var(--primary-color);
    letter-spacing: -0.02em;
}

.profile-title h2 {
    font-size: 1.25rem;
    color: var(--accent-color);
    font-weight: 600;
    margin-top: 0.25rem;
}

.tagline {
    color: var(--text-secondary);
    font-size: 0.95rem;
    margin-top: 0.5rem;
}
```

---

### Paso 4.2: CSS Grid para Habilidades Técnicas
Utilizar la función `repeat(auto-fit, minmax(...))` para lograr un comportamiento adaptable automático.

```css
.skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
    gap: 0.75rem;
    margin-top: 1rem;
}

.skill-badge {
    background-color: #f1f5f9;
    color: var(--primary-color);
    padding: 0.6rem 1rem;
    border-radius: 8px;
    font-size: 0.875rem;
    font-weight: 600;
    text-align: center;
    border: 1px solid #e2e8f0;
    transition: var(--transition-smooth);
}
```

> **Explicación:**
> * `grid-template-columns: repeat(auto-fit, minmax(140px, 1fr))`:  CSS Grid.
>   * `minmax(140px, 1fr)`: Define que cada columna debe medir al menos `140px`, pero puede expandirse equitativamente (`1fr`) si hay espacio sobrante.
>   * `auto-fit`: Ajusta automáticamente el número de columnas según el ancho disponible de la pantalla sin requerir Media Queries adicionales para este bloque.  Le dice al navegador que cree tantas columnas como quepan en el ancho disponible. Si sobra espacio, las columnas se estiran para llenarlo.
>   * `repeat`: Duplica la estructura de columnas de forma automática.
---

### Paso 4.3: Grilla de Tarjetas de Proyectos
```css
.projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem;
    margin-top: 1rem;
}

.project-card {
    background: #f8fafc;
    border: 1px solid #e2e8f0;
    border-left: 4px solid var(--accent-color);
    padding: 1.25rem;
    border-radius: 8px;
    transition: var(--transition-smooth);
}

.project-card h4 {
    color: var(--primary-color);
    font-size: 1.1rem;
    margin-bottom: 0.4rem;
}

.project-tech {
    font-size: 0.8rem;
    color: var(--accent-color);
    font-weight: 600;
    margin-bottom: 0.6rem;
}
```

---

## 5: Efectos Visuales Avanzados (Hover, Transiciones y Sombras 3D)

Se anade profundidad e interactividad mediante transformaciones tridimensionales y cambios de elevación de sombra al pasar el cursor.

### Paso 5.1: Interactividad en la Foto Óvalada
```css
.profile-avatar:hover {
    /* Escalado e inclinación sutil al pasar el mouse */
    transform: scale(1.05) rotate(2deg);
    outline-color: var(--accent-hover);
    box-shadow: 0 12px 24px rgba(2, 132, 199, 0.35);
    cursor: pointer;
}
```

> **Explicación:**
> * `transform: scale(1.05) rotate(2deg)`: Aplica dos transformaciones simultáneas: amplía el tamaño del elemento un 5% y lo gira 2 grados en el sentido de las agujas del reloj.
> * `cursor: pointer`: Cambia el puntero del ratón a forma de mano indicando interactividad.

---

### Paso 5.2: Elevación 3D de las Tarjetas de Proyectos (`:hover`)
```css
.project-card:hover {
    /* Efecto de levitación vertical */
    transform: translateY(-6px);
    background-color: #ffffff;
    box-shadow: var(--shadow-hover);
    border-color: #cbd5e1;
    border-left-color: var(--accent-hover);
}
```

> **Explicación:**
> * `transform: translateY(-6px)`: Desplaza el elemento 6 píxeles hacia arriba en el eje Y. Al combinarse con `box-shadow`, simula que la tarjeta "flota" sobre la página alejándose del fondo.

---

### Paso 5.3: Resaltado de las Etiquetas de Habilidades
```css
.skill-badge:hover {
    background-color: var(--accent-color);
    color: #ffffff;
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(2, 132, 199, 0.3);
}
```

---

## 6: Pseudo-elementos Decorativos y Animaciones `@keyframes`

Detalles de diseño con pseudo-elementos (`::after`) y animación de entrada progresiva.

### Paso 6.1: Subrayado Animado en Títulos de Sección
```css
.section-title {
    font-size: 1.3rem;
    color: var(--primary-color);
    margin-bottom: 1rem;
    position: relative;
    display: inline-block;
}

/* Pseudo-elemento para crear una línea acentuada bajo el título */
.section-title::after {
    content: '';
    position: absolute;
    bottom: -4px;
    left: 0;
    width: 40%;
    height: 3px;
    background-color: var(--accent-color);
    border-radius: 2px;
    transition: var(--transition-smooth);
}

.cv-section:hover .section-title::after {
    width: 100%;
}
```

> **Explicación:**
> * `display: inline-block`: Si el título es un elemento de bloque estándar (como un <h2>), ocupará todo el ancho de la pantalla. Al usar inline-block, el 40% inicial y el 100% final se calcularán exactamente sobre el ancho de las palabras del título.
> * `::after`: Crea un elemento estético ficticio que no existe en el DOM HTML.
> * `content: ''`: Es obligatorio declarar la propiedad `content` para que el pseudo-elemento sea renderizado por el navegador.
> * `position: absolute` & `position: relative`: El título actúa como contenedor relativo, permitiendo al pseudo-elemento posicionarse exactamente en la base (`bottom: -4px`). https://developer.mozilla.org/es/docs/Web/CSS/Reference/Properties/position
> * `width: 40%` -> `100%`: Al pasar el cursor por la sección, la barra acentuada se expande fluidamente.

---

### Paso 6.2: Definición de la Animación de Entrada `@keyframes`
```css
/* Animación de entrada suave con desplazamiento vertical */
@keyframes fadeInUp {
    from {
        opacity: 0;
        transform: translateY(20px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.cv-container {
    /* Aplicación de la animación */
    animation: fadeInUp 0.8s cubic-bezier(0.16, 1, 0.3, 1) forwards;
}
```

> **Explicación:**
> * `@keyframes fadeInUp`: Define una secuencia de estados de animación. En la inicial (`from`), el contenedor es invisible (`opacity: 0`) y está desplazado 20px abajo. En el estado final (`to`), se vuelve completamente visible y recupera su posición natural.
> * `forwards`: Hace que el elemento conserve de forma permanente los estilos del último fotograma de la animación (`to`) al finalizar.

---

## 7: Diseño Adaptativo Completo (*Responsive Design* con Media Queries)

Para asegurar que el Curriculum Vitae se adapte a dispositivos móviles, tabletas y computadoras de escritorio, agregamos puntos de interrupción (*breakpoints*) mediante `@media`.

```css
/* Media Query para Tabletas y Dispositivos Medianos (Ancho máximo: 768px) */
@media (max-width: 768px) {
    body {
        padding: 1rem 0.5rem;
    }

    .cv-container {
        padding: 1.5rem;
        border-radius: 12px;
    }

    .profile-header {
        flex-direction: column;
        text-align: center;
        gap: 1.25rem;
    }

    .profile-avatar {
        /* Reducción proporcional del óvalo en pantallas medianas */
        width: 130px;
        height: 165px;
    }

    .profile-title h1 {
        font-size: 1.75rem;
    }

    .profile-title h2 {
        font-size: 1.1rem;
    }
}

/* Media Query para Teléfonos Móviles (Ancho máximo: 480px) */
@media (max-width: 480px) {
    .cv-container {
        padding: 1.25rem 1rem;
    }

    .projects-grid {
        /* Cambia a una única columna en pantallas pequeñas */
        grid-template-columns: 1fr;
    }

    .skills-grid {
        grid-template-columns: repeat(auto-fit, minmax(110px, 1fr));
    }

    .contact-info {
        font-size: 0.85rem;
    }
}
```

> **Explicación:**
> * `@media (max-width: 768px)`: Aplica las reglas CSS contenidas en su interior únicamente cuando la pantalla del usuario mide 768 píxeles de ancho o menos.
> * `flex-direction: column`: En pantallas pequeñas, reorganiza la foto de perfil y los textos de orientación horizontal a una disposición vertical centrada.

---

## 8: Documento Final Completo Ensamblado

A continuación se presenta el código completo integrado listo para ser guardado y probado en un navegador web.

### Archivo HTML (`index.html`):
```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Curriculum Vitae - Sofía Sánchez Mendoza</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="cv-container">
        <header class="profile-header">
            <div class="avatar-wrapper">
                <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?q=80&w=400&auto=format&fit=crop" 
                     alt="Fotografía de Sofía Sánchez Mendoza" 
                     class="profile-avatar">
            </div>
            <div class="profile-title">
                <h1>Sofía Sánchez Mendoza</h1>
                <h2>Ingeniero en Desarrollo de Software</h2>
                <p class="tagline">Especialista en Arquitecturas Cloud, APIs RESTful y Sistemas Distribuidos</p>
            </div>
        </header>

        <section class="cv-section about-section">
            <h3 class="section-title">Perfil Profesional</h3>
            <p>
                Ingeniero en Desarrollo de Software con más de 5 años de experiencia en el diseño y despliegue de aplicaciones web de alto rendimiento. Apasionado por la optimización de código, desarrollo de APIs RESTful seguras y migración de servicios a la nube.
            </p>
        </section>

        <section class="cv-section skills-section">
            <h3 class="section-title">Habilidades de Software</h3>
            <div class="skills-grid">
                <span class="skill-badge">JavaScript (ES6+)</span>
                <span class="skill-badge">Python / Django</span>
                <span class="skill-badge">Node.js / Express</span>
                <span class="skill-badge">React.js</span>
                <span class="skill-badge">SQL (PostgreSQL)</span>
                <span class="skill-badge">Docker & Kubernetes</span>
                <span class="skill-badge">Git / GitHub</span>
                <span class="skill-badge">AWS / Cloud</span>
            </div>
        </section>

        <section class="cv-section projects-section">
            <h3 class="section-title">Proyectos Destacados</h3>
            <div class="projects-grid">
                <article class="project-card">
                    <h4>EduControl - Plataforma Académica</h4>
                    <p class="project-tech">Tecnologías: Python, Django, PostgreSQL, Docker</p>
                    <p>Sistema integral de gestión de calificaciones y asistencia escolar con autenticación JWT y comunicación en tiempo real vía WebSockets.</p>
                </article>
                
                <article class="project-card">
                    <h4>TechMarket - E-commerce Microservicios</h4>
                    <p class="project-tech">Tecnologías: Node.js, Express, React, Redis, AWS</p>
                    <p>Arquitectura distribuida de comercio electrónico con balanceo de carga, procesamiento de pagos con Stripe y caché distribuido.</p>
                </article>
            </div>
        </section>

        <footer class="cv-footer">
            <address class="contact-info">
                <p>📧 Email: <a href="mailto:carlos.mendoza@devengine.com">carlos.mendoza@devengine.com</a></p>
                <p>📱 Teléfono: +52 (55) 8765-4321</p>
                <p>🌐 GitHub: <a href="https://github.com" target="_blank">github.com/carlos-dev</a></p>
            </address>
        </footer>
    </div>
</body>
</html>
```

### Archivo CSS (`styles.css`):
```css
/* Reset Básico */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Variables Globales */
:root {
    --primary-color: #1e293b;
    --accent-color: #0284c7;
    --accent-hover: #0369a1;
    --bg-gradient: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
    --card-bg: #ffffff;
    --text-primary: #0f172a;
    --text-secondary: #475569;
    --shadow-soft: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
    --shadow-hover: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
    --transition-smooth: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

body {
    font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
    background: var(--bg-gradient);
    color: var(--text-primary);
    line-height: 1.6;
    padding: 2rem 1rem;
    min-height: 100vh;
}

.cv-container {
    max-width: 900px;
    margin: 0 auto;
    background: var(--card-bg);
    border-radius: 16px;
    padding: 2.5rem;
    box-shadow: var(--shadow-soft);
    animation: fadeInUp 0.8s cubic-bezier(0.16, 1, 0.3, 1) forwards;
}

/* Header y Fotografía Óvalada */
.profile-header {
    display: flex;
    align-items: center;
    gap: 2rem;
    padding-bottom: 2rem;
    border-bottom: 2px solid #f1f5f9;
}

.avatar-wrapper {
    flex-shrink: 0;
}

.profile-avatar {
    width: 150px;
    height: 190px;
    border-radius: 50%;
    object-fit: cover;
    object-position: center top;
    border: 4px solid var(--card-bg);
    outline: 3px solid var(--accent-color);
    box-shadow: 0 8px 16px rgba(2, 132, 199, 0.2);
    transition: var(--transition-smooth);
}

.profile-avatar:hover {
    transform: scale(1.05) rotate(2deg);
    outline-color: var(--accent-hover);
    box-shadow: 0 12px 24px rgba(2, 132, 199, 0.35);
    cursor: pointer;
}

.profile-title h1 {
    font-size: 2.2rem;
    color: var(--primary-color);
    letter-spacing: -0.02em;
}

.profile-title h2 {
    font-size: 1.25rem;
    color: var(--accent-color);
    font-weight: 600;
    margin-top: 0.25rem;
}

.tagline {
    color: var(--text-secondary);
    font-size: 0.95rem;
    margin-top: 0.5rem;
}

/* Secciones Generales */
.cv-section {
    margin-top: 2rem;
}

.section-title {
    font-size: 1.3rem;
    color: var(--primary-color);
    margin-bottom: 1rem;
    position: relative;
    display: inline-block;
}

.section-title::after {
    content: '';
    position: absolute;
    bottom: -4px;
    left: 0;
    width: 40%;
    height: 3px;
    background-color: var(--accent-color);
    border-radius: 2px;
    transition: var(--transition-smooth);
}

.cv-section:hover .section-title::after {
    width: 100%;
}

/* Grilla de Habilidades */
.skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
    gap: 0.75rem;
    margin-top: 1rem;
}

.skill-badge {
    background-color: #f1f5f9;
    color: var(--primary-color);
    padding: 0.6rem 1rem;
    border-radius: 8px;
    font-size: 0.875rem;
    font-weight: 600;
    text-align: center;
    border: 1px solid #e2e8f0;
    transition: var(--transition-smooth);
}

.skill-badge:hover {
    background-color: var(--accent-color);
    color: #ffffff;
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(2, 132, 199, 0.3);
}

/* Grilla de Proyectos */
.projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem;
    margin-top: 1rem;
}

.project-card {
    background: #f8fafc;
    border: 1px solid #e2e8f0;
    border-left: 4px solid var(--accent-color);
    padding: 1.25rem;
    border-radius: 8px;
    transition: var(--transition-smooth);
}

.project-card:hover {
    transform: translateY(-6px);
    background-color: #ffffff;
    box-shadow: var(--shadow-hover);
    border-color: #cbd5e1;
    border-left-color: var(--accent-hover);
}

.project-card h4 {
    color: var(--primary-color);
    font-size: 1.1rem;
    margin-bottom: 0.4rem;
}

.project-tech {
    font-size: 0.8rem;
    color: var(--accent-color);
    font-weight: 600;
    margin-bottom: 0.6rem;
}

/* Pie de Página */
.cv-footer {
    margin-top: 3rem;
    padding-top: 1.5rem;
    border-top: 2px solid #f1f5f9;
}

.contact-info {
    font-style: normal;
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    gap: 1rem;
    color: var(--text-secondary);
    font-size: 0.9rem;
}

.contact-info a {
    color: var(--accent-color);
    text-decoration: none;
    font-weight: 600;
}

.contact-info a:hover {
    text-decoration: underline;
}

/* Keyframes de Animación */
@keyframes fadeInUp {
    from {
        opacity: 0;
        transform: translateY(20px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

/* Responsive Design (Media Queries) */
@media (max-width: 768px) {
    body {
        padding: 1rem 0.5rem;
    }

    .cv-container {
        padding: 1.5rem;
        border-radius: 12px;
    }

    .profile-header {
        flex-direction: column;
        text-align: center;
        gap: 1.25rem;
    }

    .profile-avatar {
        width: 130px;
        height: 165px;
    }

    .profile-title h1 {
        font-size: 1.75rem;
    }

    .profile-title h2 {
        font-size: 1.1rem;
    }
}

@media (max-width: 480px) {
    .cv-container {
        padding: 1.25rem 1rem;
    }

    .projects-grid {
        grid-template-columns: 1fr;
    }

    .skills-grid {
        grid-template-columns: repeat(auto-fit, minmax(110px, 1fr));
    }

    .contact-info {
        flex-direction: column;
        align-items: center;
        gap: 0.5rem;
    }
}
```

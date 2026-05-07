# Mundo del Desarrollador

Portafolio interactivo 3D estilo juego, construido como una experiencia Next.js + React Three Fiber + Rapier + Zustand.

## Instalación

Abre un terminal en la raíz del proyecto y ejecuta:

```bash

npm install
```

Si necesitas limpiar dependencias anteriores, ejecuta:

```bash
npm install --force

si se te cae la señal del internet y sale error hacer : 

npm cache clean --force
npm install --force
```

## Comandos

```bash
npm run dev
npm run build
npm run start
```

- `npm run dev`: inicia el servidor de desarrollo en `http://localhost:3000`
- `npm run build`: crea la versión optimizada de producción
- `npm run start`: ejecuta la versión de producción

## Estructura principal

- `app/page.tsx`: punto de entrada que renderiza el lienzo 3D.
- `components/Experience.tsx`: contenedor de `<Canvas>`, `<Physics>`, escena 3D y componentes de audio.
- `components/Player.tsx`: controlador del jugador, movimiento WASD/Flechas y cámara tercera persona.
- `components/Environment.tsx`: suelo, flores instanciadas y placeholders de NPCs.
- `components/Zones.tsx`: sensores físicos que abren cada habitación (8 zonas configuradas).
- `components/UI.tsx`: overlay HTML que renderiza los paneles según la zona activa.
- `components/Audio.tsx`: manejo de música de fondo con autoplay inteligente.
- Paneles modulares: `HeroPanel.tsx`, `AboutPanel.tsx`, `SkillsPanel.tsx`, `ServicesPanel.tsx`, `ProjectsPanel.tsx`, `Panels.tsx`.
- `store/useGameStore.ts`: estado global con `currentZone`, `isUIOpen` y navegación de proyectos.

## ¿Dónde agregar tu contenido?

1. `components/UI.tsx` y paneles individuales
   - Los paneles están modularizados en archivos separados: `HeroPanel.tsx`, `AboutPanel.tsx`, `SkillsPanel.tsx`, `ServicesPanel.tsx`, `ProjectsPanel.tsx`, `Panels.tsx` (TestimonialsPanel, ContactPanel, FooterPanel).
   - Actualiza los textos, datos y enlaces en cada panel según tu información real.

2. `public/cv/GiseellaSanchez_CV.pdf`
   - Coloca tu hoja de vida en esta ruta para activar el botón de descarga.

3. `public/images/`
   - `giseella.jpg`: Tu foto para el panel Hero (descomenta el código en HeroPanel.tsx).
   - `projects/glowcode.jpg`, `projects/terrasoft.jpg`, etc.: Imágenes de tus proyectos para ProjectsPanel.

4. `public/audio/background.mp3` (y opcionalmente `background.ogg`)
   - Coloca tu archivo de música de fondo. El componente Audio.tsx ya está configurado para reproducirlo automáticamente.

5. Si agregas nuevos proyectos, actualiza el array `PROJECTS` en `components/ProjectsPanel.tsx`.

## Música y audio

La música de fondo ya está implementada en el componente `Audio.tsx`:

1. Copia tu archivo de audio a `public/audio/background.mp3` (y opcionalmente `background.ogg` para compatibilidad).
https://pixabay.com/es/music/search/lofi%20chill%20background/ 

2. El audio se reproduce automáticamente al cargar la página (puede estar bloqueado por políticas de autoplay del navegador).
3. Si el autoplay falla, se activa al primer click en la página.
4. El volumen está configurado al 30% y se reproduce en loop.

Para sonidos adicionales (pasos, ambientales), puedes extender el componente Audio o crear nuevos componentes de sonido.

## Mapa y habitaciones

La experiencia actúa como una mansión-jardín completa con estas zonas:

- `home`: sala de bienvenida / hero con avatar y descripción personal.
- `about`: habitación de Sobre mí con filosofía, intereses y descarga de CV.
- `skills`: sala de habilidades técnicas con barras de progreso animadas.
- `services`: habitación de servicios ofrecidos con tarjetas interactivas.
- `projects`: galería de proyectos estilo carrusel con navegación por puntos.
- `testimonials`: sala de testimonios con reseñas de colaboradores.
- `contact`: buzón mágico con información de contacto completa.
- `footer`: sala de despedida con agradecimiento y enlaces finales.

Cada zona tiene su propio panel UI con animaciones de entrada/salida usando Framer Motion.

## Mejora del proyecto

- Añade modelos `.glb` en `public/models/` y reemplaza los placeholders geométricos.
- Sustituye los paneles HTML por componentes más ricos usando Framer Motion.
- Agrega sonidos ambientales y pasos con la API `Audio`.
- Crea nuevas zonas físicas en `components/Zones.tsx` para más habitaciones.

> No puedo generar el ZIP directamente desde aquí, pero toda la estructura necesaria ya está lista en el proyecto.

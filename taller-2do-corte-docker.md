# Taller del 2do Corte — Docker

*Arquitectura de Software · Semana 10 · Entrega individual*

---

Este documento reúne las **dos partes** del taller de Docker del 2do corte:

1. [**Parte 1 — Investigativa**](#parte-1--investigativa): fundamentos de Docker (investigación individual).
2. [**Parte 2 — Práctica**](#parte-2--práctica): seguir la guía del [`README.md`](https://github.com/carrenoutb/biblioteca-api/blob/main/README.md) del repositorio y evidenciar la ejecución.
3. [**Entrega y fecha**](#entrega-del-taller-github): cómo subir los 2 archivos a GitHub y cuándo entregar.

Ambas partes se entregan juntas: **2 archivos (PDF o Markdown)** — el informe de investigación (Parte 1) y el informe de práctica (Parte 2) — subidos a un repositorio de GitHub compartido.

---
---

# Parte 1 — Investigativa

## Contexto

Docker se volvió una herramienta estándar en la industria del software: casi todos los proyectos reales empaquetan sus aplicaciones en **contenedores** para poder llevarlas de una máquina a otra sin sorpresas. En este curso, Docker es más que una herramienta práctica: es la base concreta de muchos de los estilos arquitectónicos que hemos visto — un microservicio, un broker de eventos o una base de datos corren como contenedores.

Este taller tiene **dos partes**: esta primera parte es **investigativa** (por tu cuenta, antes de la clase práctica), y más adelante tendrá una **parte práctica** donde correrás contenedores reales en tu máquina.

Para esta parte puedes apoyarte en la diapositiva de la clase (`diapo-docker.html`), en la documentación oficial de Docker y en las fuentes que tú mismo encuentres.

## Objetivo

Que el estudiante investigue los fundamentos de Docker —qué es, cómo está compuesto, qué resuelve— y explique con sus propias palabras por qué esta tecnología es relevante dentro de la Arquitectura de Software.

---

## Instrucciones — Qué debes investigar y desarrollar

Tu informe debe incluir los siguientes puntos, desarrollados **con tus propias palabras** (no copiar y pegar de internet):

### 1. ¿Qué es Docker?

Define qué es Docker de forma clara y sencilla. Tu respuesta debe incluir:
- Una **definición** con tus propias palabras.
- Una breve explicación de **cómo funciona a alto nivel**: ¿qué es un contenedor y por qué comparte el sistema operativo del host?
- La diferencia básica entre un **contenedor** y una **máquina virtual** (¿por qué un contenedor es más ligero?).

### 2. ¿Cuáles son sus componentes?

Explica cada uno de los siguientes componentes y cómo se relacionan entre sí. Puedes ayudarte de un esquema o diagrama en texto:

- **CLI** (cliente `docker`)
- **Daemon** (`dockerd`, el motor)
- **Imagen**
- **Contenedor**
- **Dockerfile**
- **Registro** (ej. Docker Hub)

Debes explicar claramente la cadena: **Dockerfile → Imagen → Contenedor**, y en qué punto entra el registro (descargar/publicar imágenes).

### 3. ¿Cuáles son sus principales funcionalidades?

Explica al menos **4 funcionalidades** importantes de Docker. Algunas sugerencias (puedes usar estas u otras):
- **Portabilidad** (la misma imagen corre en cualquier máquina con Docker).
- **Aislamiento** entre aplicaciones.
- **Versionado de imágenes** (etiquetas como `mysql:8`, `node:18`).
- **Reproducibilidad del entorno** (todos los del equipo usan lo mismo).
- **Escalabilidad** (arrancar varias instancias de un contenedor).
- Base para **CI/CD** (construir y desplegar de forma automatizada).

Cada funcionalidad debe tener una breve explicación de **para qué sirve** y un ejemplo concreto.

### 4. ¿Cuáles son sus principales comandos?

a) Completa una tabla como la siguiente (puedes agregar más filas):

| Comando | ¿Qué hace? | Ejemplo |
|---|---|---|
| `docker pull` | | |
| `docker run` | | |
| `docker ps` | | |
| `docker ps -a` | | |
| `docker logs` | | |
| `docker exec` | | |
| `docker stop` / `start` | | |
| `docker rm` | | |
| `docker images` | | |
| `docker rmi` | | |
| `docker build` | | |
| `docker compose up` | | |

b) Elige **3 de esos comandos** y explica en detalle: qué parámetros comunes usan (ej. `-d`, `-p`, `-e`, `-v`, `--name`) y en qué situación los usarías.

### 5. ¿Qué problema resuelve?

Explica el problema clásico que motivó la aparición de Docker. Tu respuesta debe incluir:
- El escenario *"en mi máquina funciona"*: ¿por qué una app funciona en una máquina y falla en otra?
- Las causas típicas: **versiones de dependencias, sistema operativo, configuración, instalación manual**.
- Un ejemplo concreto de **antes vs después** de usar Docker (puedes inventar una situación sencilla).

### 6. ¿Por qué es importante dentro de una Arquitectura de Software?

Relaciona Docker con lo visto en el curso. Tu respuesta debe incluir, al menos:
- Por qué conviene que **cada servicio de una arquitectura** (API, base de datos, broker de eventos) corra en su propio contenedor.
- Cómo ayuda Docker al **despliegue consistente**: el mismo entorno pasa de desarrollo → pruebas → producción.
- Cómo facilita la **escalabilidad** (más instancias de un servicio) y la **portabilidad a la nube**.
- Su relación con los estilos arquitectónicos que hemos visto (microservicios, SOA, orientada a eventos).

---

## Estructura esperada del informe (Parte 1)

Tu documento entregado debe tener, como mínimo, estas secciones:

1. **Portada** — nombre del curso, tema del trabajo, tu nombre.
2. **Introducción** — breve, presentando el tema y por qué es relevante.
3. **Desarrollo** — los 6 puntos de la sección de instrucciones.
4. **Conclusión** — tu reflexión personal (por ejemplo: ¿en qué proyecto tuyo usarías Docker y por qué?).
5. **Referencias** — las fuentes que consultaste (documentación oficial, artículos, etc.). Mínimo **3 fuentes**.

> 📄 **Formato del archivo:** el informe se entrega en **PDF o Markdown** (ej. `informe-investigacion-docker.md` o `.pdf`).

## Extensión sugerida (Parte 1)

Entre **2 y 3 páginas** (sin contar portada y referencias). No es necesario extenderse más — se valora más la claridad que la extensión.

---

## Rúbrica de evaluación (Parte 1)

| Criterio | Descripción | Porcentaje |
|---|---|---|
| **Claridad conceptual** | Temas 1 y 2: la definición de Docker, el funcionamiento de los contenedores y los componentes están bien explicados, con palabras propias. | 30% |
| **Funcionalidades y comandos** | Temas 3 y 4: al menos 4 funcionalidades justificadas, tabla de comandos completa y 3 comandos explicados a detalle. | 25% |
| **Problema y relevancia arquitectónica** | Temas 5 y 6: el problema "en mi máquina funciona" y la importancia de Docker en la arquitectura de software están bien argumentados. | 25% |
| **Estructura y presentación** | El informe sigue la estructura solicitada, está bien organizado y usa buena redacción. | 15% |
| **Referencias** | Se incluyen al menos 3 fuentes consultadas. | 5% |
| **Total** | | **100%** |

---
---

# Parte 2 — Práctica

## Contexto

Esta es la **segunda parte** del taller de Docker del 2do corte (en la primera parte investigaste los fundamentos: qué es, componentes, comandos, problemas que resuelve).

Ahora trabajamos con un proyecto real del curso: **biblioteca-api** (la API en Go + Gin + MySQL de **Arquitectura de Software**, que implementa una arquitectura por capas: `handler` → `service` → `repository`). El proyecto está publicado en GitHub: **[github.com/carrenoutb/biblioteca-api](https://github.com/carrenoutb/biblioteca-api)**. Está **dockerizado** (trae su `Dockerfile` y su `docker-compose.yml`) y su **`README.md` contiene una guía completa, paso a paso y explicada** — [ver el README en línea](https://github.com/carrenoutb/biblioteca-api/blob/main/README.md) — para levantar la API en cualquier computador limpio (sin saber nada de Docker y sin instalar Go ni MySQL).

## Objetivo

Que el estudiante **siga la guía del `README.md` del repositorio** ([guía en GitHub](https://github.com/carrenoutb/biblioteca-api/blob/main/README.md)) de principio a fin, en su propia máquina, y demuestre que la ejecución funcionó mediante **evidencias**, además de **responder unas preguntas de comprensión** que demuestran que entendió cada paso.

**Regla de oro:** la práctica solo se considera lograda si **tú mismo ejecutaste cada paso** y lo demostraste con capturas o la salida real de los comandos.

---

## Qué debes hacer

El proyecto **`biblioteca-api`** — [github.com/carrenoutb/biblioteca-api](https://github.com/carrenoutb/biblioteca-api) — ya incluye un **`README.md`** ([ver la guía](https://github.com/carrenoutb/biblioteca-api/blob/main/README.md)) que es una guía completa y detallada. **La guía de inicio son las secciones 0 a 3** (requisitos, instalación de Docker por sistema operativo, las piezas del proyecto y el paso a paso con verificación); el resto del documento (comandos útiles, problemas comunes, glosario y referencia de la API) está en los **anexos**, que **no forman parte de la guía** y se usan solo como material de consulta.

**No tienes que escribir una guía nueva**: tu trabajo es **ejecutar** la del `README.md` en tu máquina y **documentar** el proceso.

### Pasos (sigue el orden del `README.md` del repositorio)

1. **Clonar el repositorio** (es el paso 3.1 de la guía):

   ```bash
   git clone https://github.com/carrenoutb/biblioteca-api.git
   cd biblioteca-api
   ```

2. **Sección 1 — Instalar Docker** según tu sistema operativo y verificar con `docker --version` y `docker compose version`. 📸 Captura como evidencia.
3. **Sección 2 — Leer y entender las piezas del proyecto**: `Dockerfile`, `docker-compose.yml`, `.env.example` y `migrations/` (¿qué aporta cada uno?).
4. **Sección 3 — Ejecutar el paso a paso**:
   - Crear tu config: `cp .env.example .env` y explicar en tu informe **cada variable** (`DB_HOST`, `DB_PORT`, `DB_USER`, `DB_PASSWORD`, `DB_NAME`, `JWT_SECRET`, `JWT_EXPIRATION_HOURS`, `APP_PORT`).
   - Levantar todo: `docker compose up --build`. 📸 Captura del **inicio** (descarga/construcción) y del **final** (ambos servicios corriendo).
   - Verificar: `docker compose ps` → ambos `up` (MySQL `healthy`) · abrir Swagger en `http://localhost:8080/swagger/index.html` · probar el flujo **registrar → iniciar sesión → usar el token → listar libros** siguiendo el tutorial de la sección 3.4 c) del README (con la extensión **REST Client** de VS Code, Swagger UI o `curl`). 📸 Evidencia de cada verificación.
5. **Anexos (consulta)**: revisa los **anexos** del `README.md` (comandos útiles y problemas comunes — no forman parte de la guía) y menciona en tu informe al menos **2 problemas** que hayas resuelto (o que podrían ocurrir) con su solución.

### Preguntas de comprensión (responde en tu informe)

1. ¿Qué diferencia hay entre una **imagen** y un **contenedor**? Usa un ejemplo de este proyecto.
2. ¿Qué hace `docker compose` que no harías con `docker run` por separado?
3. ¿Por qué la API encuentra la base de datos con `DB_HOST=mysql` y no con `127.0.0.1`?
4. ¿Qué borra exactamente `docker compose down -v` y cuándo lo usarías?
5. ¿Qué pasaría si cambias `DB_PASSWORD` en el `.env` pero **no** en el `docker-compose.yml`? ¿Y al revés?

> 💡 Conecta tus respuestas con lo que investigaste en la **Parte 1** (componentes, la cadena Dockerfile → imagen → contenedor, el registro, Compose…).

---

## Evidencias (obligatorias)

Anexa en tu informe, organizadas por fase:

- **Fase 1 (instalación):** salida de `docker --version` y `docker compose version`.
- **Fase 2 (puesta en marcha):** salida de `cp .env.example .env` y de `docker compose up --build` (el **inicio** descargando/construyendo y el **final** con ambos servicios corriendo).
- **Fase 3 (verificación):** salida de `docker compose ps`, captura de la página de Swagger respondiendo, y el flujo register → login → books (con **REST Client**, Swagger UI o `curl`).

Organízalas en una carpeta `evidencias/` junto a tu informe, o embebidas directamente en el documento.

## Formato de entrega

- El **informe de práctica** (Parte 2): la narración del proceso seguido (fase por fase) + las respuestas a las **5 preguntas de comprensión**, en **PDF o Markdown** (ej. `informe-practica-docker.md` o `.pdf`).
- Carpeta **`evidencias/`** con las capturas (o imágenes embebidas), dentro del mismo repositorio.

> 📦 **Ambos informes (investigación de la Parte 1 + práctica de la Parte 2), en PDF o Markdown, se suben a un repositorio de GitHub** y se comparte el enlace del repositorio como única forma de entrega.

## Extensión sugerida (Parte 2)

Sin límite de páginas, pero se valora **precisión sobre extensión**: un informe claro, organizado por fases y con evidencias completas vale más que muchas páginas de relleno.

---

## Rúbrica de evaluación (Parte 2)

| Criterio | Descripción | Porcentaje |
|---|---|---|
| **Ejecución completa de la guía** | Siguió los pasos del `README.md` en orden: instalación y verificación de Docker, creación del `.env`, `docker compose up --build`, y verificación (ps, Swagger, flujo register→login→books). | 30% |
| **Comprensión (preguntas)** | Respuestas claras y correctas a las 5 preguntas de comprensión, conectadas con la teoría de la Parte 1. | 25% |
| **Precisión técnica** | Comandos ejecutados tal cual (correctos) y explicaciones correctas del funcionamiento interno (imágenes, Compose, volúmenes). | 20% |
| **Evidencias** | Capturas/salidas reales por fase que demuestran que realmente ejecutó la guía. | 15% |
| **Estructura y presentación** | Informe organizado por fases, bien redactado y con buena presentación. | 10% |
| **Total** | | **100%** |

---
---

## Entrega del taller (GitHub)

### Entregables — 2 archivos

| # | Archivo | Contenido | Formato |
|---|---|---|---|
| 1 | **Informe de investigación** (Parte 1) | El desarrollo de los 6 temas (con su estructura: portada, introducción, desarrollo, conclusión, referencias) | **PDF o Markdown** |
| 2 | **Informe de práctica** (Parte 2) | La narración del proceso seguido al ejecutar la guía del `README.md` del repositorio, las respuestas a las 5 preguntas de comprensión y la carpeta `evidencias/` | **PDF o Markdown** |

Los **dos informes** se suben a un **repositorio de GitHub** y se comparte el **enlace del repositorio** como única forma de entrega.

### Proceso de entrega paso a paso

1. **Crea una cuenta en GitHub** (si aún no tienes): [github.com/signup](https://github.com/signup).
2. **Crea un repositorio nuevo** (para **entregar tus informes** — no confundir con el repositorio de `biblioteca-api`, que ya existe en GitHub): en tu perfil, botón **New** (o `github.com/new`). Nombre sugerido: `taller-2do-corte-docker`. Puedes dejarlo **público** (más fácil de revisar) o privado si prefieres.
3. **Sube los dos informes** (tienes dos opciones):
   - **Opción web (recomendada si no sabes git):** dentro del repositorio, botón **Add file → Upload files** → arrastra el informe de investigación y el informe de práctica (y la carpeta `evidencias/` con las capturas) → botón verde **Commit changes**.
   - **Opción terminal (si ya sabes git):**

     ```bash
     git init
     git add informe-investigacion-docker.md informe-practica-docker.md evidencias/
     git commit -m "Taller 2do corte — Docker"
     git branch -M main
     git remote add origin https://github.com/TU_USUARIO/taller-2do-corte-docker.git
     git push -u origin main
     ```

4. **Comparte el enlace**: copia la URL del repositorio (botón verde **Code**) — tiene esta forma: `https://github.com/TU_USUARIO/taller-2do-corte-docker` — y compártela por la vía que indique el docente (plataforma del curso, formulario o correo), **antes de la fecha límite**.
5. **Autochequeo final**: abre el enlace en una ventana de incógnito y confirma que se ven **los 2 informes** (investigación + práctica). Si se ven, tu entrega está completa. ✅

---

## Fecha de entrega (Partes 1 y 2)

📅 **Viernes 16 de octubre de 2026 · 11:59 pm (23:59)** — los dos archivos deben estar subidos al repositorio y el enlace compartido antes de esa hora.
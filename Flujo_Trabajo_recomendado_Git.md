Sí, es correcto, pero hay un flujo mejor para reutilizarlo sin arrastrar el historial.

Recomendado

Template de GitHub: Marca este repo como “Template repository” y crea cada proyecto con “Use this template”.
Ventajas: no arrastra commits/branches del esqueleto, mantiene el esqueleto versionado.
CLI: gh repo create <org/nuevo-proyecto> --template <owner/este-repo> --public
Alternativas

Clonar y reinicializar Git: copia limpia sin historial.
git clone <url> nuevo-proyecto && cd nuevo-proyecto && rm -rf .git && git init && git add -A && git commit -m "init from skeleton"
degit (muy rápido): copia archivos sin .git.
npx degit <owner/este-repo>#main nuevo-proyecto
Plantillas parametrizadas y actualizables: usar Cookiecutter o Copier si quieres:
Pedir nombres/puertos/paths al crear el proyecto.
Posibilidad de “pull de updates” del esqueleto (Copier lo soporta mejor que Cookiecutter).
Cuándo elegir cada uno

Proyectos independientes sin necesidad de actualizar desde el esqueleto: Template de GitHub o degit.
Necesitas aplicar mejoras del esqueleto a proyectos ya creados: Copier (o mantén el esqueleto como submódulo, aunque es más complejo).
Monorepo multi‑app: si planeas muchos servicios juntos, considera un monorepo con workspaces (npm/pnpm) y un backend Python separado por carpeta, pero eso es otra decisión de arquitectura.
Sugerencias prácticas para tu starter

Publica tags del esqueleto (v0.1, v0.2) y un CHANGELOG; facilita saber qué versión usó cada proyecto.
Incluye un script init que renombre nombres de app/puertos/envs.
Documenta el flujo: “Crear desde template → frontend/ npm i && npm run dev → backend python -m venv/poetry install → variables de entorno”.
Si quieres, puedo marcar este repo como Template (o darte los comandos) y preparar un script init básico para personalización. ¿Te interesa que lo deje listo?
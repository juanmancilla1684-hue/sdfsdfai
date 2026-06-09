# AI Chat — GitHub Pages

App de chat con IA estilo Instagram DM. Un solo archivo HTML, sin dependencias.

## 🚀 Deploy en GitHub Pages

### Pasos

1. **Crea un repositorio** en GitHub (puede ser público o privado con plan pro).

2. **Sube los archivos** al repositorio:
   ```bash
   git init
   git add .
   git commit -m "first commit"
   git branch -M main
   git remote add origin https://github.com/TU_USUARIO/TU_REPO.git
   git push -u origin main
   ```

3. **Activa GitHub Pages** en tu repositorio:
   - Ve a `Settings` → `Pages`
   - En **Source**, selecciona **GitHub Actions**
   - Guarda los cambios

4. El workflow se ejecuta automáticamente. En ~1 minuto tu app estará en:
   ```
   https://TU_USUARIO.github.io/TU_REPO/
   ```

### Deploy manual (alternativa sin Actions)

Si prefieres no usar GitHub Actions:
- Ve a `Settings` → `Pages`
- En **Source** elige **Deploy from a branch**
- Selecciona `main` y carpeta `/ (root)`
- Guarda — GitHub Pages servirá `index.html` directamente

## 📁 Estructura

```
/
├── index.html          ← toda la app (HTML + CSS + JS)
├── README.md
└── .github/
    └── workflows/
        └── deploy.yml  ← GitHub Actions (deploy automático)
```

## 🔑 API Keys

Las keys se guardan en `localStorage` del navegador (nunca salen del dispositivo).
Configúralas dentro de la app en **⚙️ → Modelos**.

| Proveedor | Dónde obtener la key | ¿Gratis? |
|-----------|----------------------|----------|
| Groq | console.groq.com | ✅ Sí |
| Gemini | aistudio.google.com | ✅ Con límites |
| Claude | console.anthropic.com | 💳 De pago |
| OpenAI | platform.openai.com | 💳 De pago |
| Grok | console.x.ai | 💳 De pago |
| Mistral | console.mistral.ai | 💳 De pago |

## ⚠️ CORS

- **Groq y Claude** funcionan directo desde el navegador (CORS habilitado).
- **OpenAI, Grok, Gemini, Mistral** requieren proxy local para evitar errores CORS.
  Ejecuta `node proxy.js` si los usas desde desktop.

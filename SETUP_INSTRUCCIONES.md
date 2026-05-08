# Danz Studio - Guía de Setup e Instalación

## 📱 ¿Qué tienes?

Una app web completa que:
- ✅ Funciona en móvil, tablet y desktop
- ✅ Gratis para siempre
- ✅ Sin instalación complicada
- ✅ Datos guardados en tu navegador (privado, sin servicios externos)
- ✅ Acceso diferenciado (tú admin, coreógrafos ven solo su info)

---

## 🚀 OPCIÓN 1: Deploy Rápido en Vercel (Recomendado)

### Paso 1: Preparar el proyecto

1. **Crea una carpeta en tu computadora:**
   ```bash
   mkdir danz-studio
   cd danz-studio
   ```

2. **Inicia un proyecto Next.js:**
   ```bash
   npx create-next-app@latest . --typescript --tailwind --no-eslint
   ```
   (Elige "No" en la mayoría de opciones)

3. **Instala dependencias:**
   ```bash
   npm install lucide-react
   ```

### Paso 2: Agregar el código

1. **Reemplaza el contenido de `app/page.tsx`** con el código de `danz-studio-app.jsx` (renómbralo como `.tsx`)

2. **Crea `app/layout.tsx`:**
   ```tsx
   import type { Metadata } from "next";
   import "./globals.css";

   export const metadata: Metadata = {
     title: "Danz Studio",
     description: "Gestión de Montajes Coreográficos",
   };

   export default function RootLayout({
     children,
   }: {
     children: React.ReactNode;
   }) {
     return (
       <html lang="es">
         <body className="antialiased">{children}</body>
       </html>
     );
   }
   ```

### Paso 3: Deploy en Vercel

1. **Sube a GitHub:**
   - Crea cuenta en [github.com](https://github.com)
   - Crea repo llamado "danz-studio"
   - Sube tu carpeta:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/TU_USUARIO/danz-studio.git
   git push -u origin main
   ```

2. **Deploy en Vercel:**
   - Ve a [vercel.com](https://vercel.com)
   - Click en "New Project"
   - Conecta tu GitHub
   - Selecciona el repo "danz-studio"
   - Click en Deploy
   - **¡Listo!** Tu app está online en `https://danz-studio.vercel.app`

---

## 💻 OPCIÓN 2: Ejecutar Localmente (Sin deploy)

Si solo quieres usarlo en tu computadora:

### Windows/Mac/Linux:

1. **Instala Node.js** desde [nodejs.org](https://nodejs.org)

2. **Descarga los archivos** del proyecto

3. **Abre terminal/CMD en la carpeta del proyecto y ejecuta:**
   ```bash
   npm install
   npm run dev
   ```

4. **Abre tu navegador en:** `http://localhost:3000`

---

## 🔐 Configuración Inicial

### Primer acceso:

1. **Email admin:** `admin@danzsudio.com`
2. **Cualquier otro email:** Acceso de coreógrafo

### Cambiar email admin:

En la app, cuando loguees como admin, ve a Configuración y cambia el email autorizado.

---

## 📋 ¿Cómo usar la app?

### Dashboard (Admin):
- Ver eventos próximos
- Alertas de grupos sin coreógrafo
- Alertas de música faltante
- Pagos pendientes

### Gestión de Colegios:
- Nombre, fecha de graduación, ubicación
- Monto total del acuerdo
- Contacto principal

### Gestión de Coreógrafos:
- Nombre, email, teléfono
- Tarifa por grupo (la que pagás a cada uno)

### Gestión de Grupos:
- Colegio, nombre, cantidad alumnos
- Asignar coreógrafo
- Agregar música (separar con comas)
- Turno (matutino/vespertino)
- Maestro responsable

### Registrar Pagos:
- Pagos recibidos de colegios
- Pagos hechos a coreógrafos
- La app calcula automáticamente lo que falta cobrar/pagar

---

## 🔗 Integración Google Calendar (PRÓXIMA FASE)

Para sincronizar automáticamente los ensayos a tu Google Calendar:

1. Voy a agregarte un botón "Sincronizar con Google Calendar"
2. Autorizas una sola vez
3. Se crean eventos automáticamente con:
   - Fecha y hora del ensayo
   - Coreógrafos asignados como invitados
   - Ubicación del colegio
   - Detalles del grupo

**Recordatorios:** Google Calendar te notifica automáticamente por email.

---

## 💾 Dónde se guardan los datos

- **Localmente:** En tu navegador (localStorage)
- **Privado:** Nadie ve tus datos
- **Respaldo:** Descargá un JSON con tus datos regularmente

Para descargar tus datos:
- En la app, panel admin → "Descargar Respaldo"

---

## 🚨 Problemas Comunes

### "No carga la app"
- Limpia el caché del navegador (Ctrl+Shift+Del)
- Reinicia el navegador

### "Perdí mis datos"
- Están en localStorage. Si borraste los datos del navegador, se pierden.
- **Solución:** Hacer respaldos regulares en JSON

### "Coreógrafos no ven su info"
- Verifica que el email del coreógrafo sea exacto
- El email que usan para login debe coincidir con el registrado

---

## 📧 Próximas Mejoras (Sin costo adicional)

- ✅ Notificaciones por email (cambios de ensayo, pagos pendientes)
- ✅ Integración Google Calendar automática
- ✅ Reportes de ingresos/egresos
- ✅ Recordatorios automáticos a coreógrafos
- ✅ Exportar datos a Excel

---

## ❓ Soporte

Si algo no funciona:
1. Verifica que estés usando un navegador moderno (Chrome, Firefox, Safari)
2. Usa la misma sesión del navegador (no private/incognito)
3. Contactame si persiste el problema

---

**Tu app está lista. Siguiente paso: ¿Quieres que agregue la integración Google Calendar?**

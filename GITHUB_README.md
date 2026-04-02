# TCheers Games Configuration

Repositorio centralizado para la gestión de juegos de la aplicación TCheers.

## 📋 ¿Qué es esto?

Este repositorio contiene el archivo `games.lang` que la aplicación TCheers descarga para mostrar la lista de juegos disponibles.

### ✨ Nuevo: Lenguaje Intermedio

Ahora usamos un formato **mucho más simple** que JSON. No necesitas saber programar.

**Antes (JSON complicado):**
```json
{
  "games": [
    {
      "title": "Multiplicaciones",
      "icon": "dangerous_outlined",
      "url": "https://ejemplo.com/"
    }
  ]
}
```

**Ahora (Simple):**
```
juego: Multiplicaciones | multiplicar | https://ejemplo.com/
```

¡Eso es todo! Sin comas, sin comillas, sin corchetes.

## 🚀 Cómo Añadir un Juego

### Desde la Web de GitHub (Recomendado)

1. Ve al archivo [`games.lang`](games.lang)
2. Haz click en el lápiz ✏️ (Edit)
3. Añade una línea nueva siguiendo el formato:

```
juego: NOMBRE_DEL_JUEGO | ICONO | https://url-del-juego.com/
```

4. Haz click en **"Commit changes..."** abajo
5. Escribe un mensaje como "Añadido juego: Nombre"
6. Click en **"Commit changes"**

### Iconos Disponibles (Nombres Amigables)

| Icono | Para qué usarlo |
|-------|----------------|
| `multiplicar` | Juegos de multiplicar |
| `restar` | Juegos de restas |
| `sumar` | Juegos de sumas |
| `dinero` | Juegos de dinero/euros |
| `musica` | Juegos de música/canciones |
| `mapa` | Juegos de mapas/lugares |
| `emocion` | Caritas, emociones |
| `ahorcado` | Juego del ahorcado |
| `deletrear` | Juegos de letras |
| `libro` | Lectura, libros |
| `pregunta` | Trivias, preguntas |
| `sopa` | Sopas de letras |
| `comida` | Juegos de comida |
| `memoria` | Memoria visual |
| `juego` | Genérico (por defecto) |
| `estrella` | Destacados, favoritos |
| `futbol` | Deportes |
| `casino` | Azar, cartas |
| `puzzle` | Rompecabezas |
| `escuela` | Educativos |
| `pincel` | Arte, dibujar |
| `microfono` | Voz, cantar |
| `avion` | Viajes, transporte |
| `coche` | Coches, vehículos |
| `mascota` | Animales |
| `pastel` | Cumpleaños, fiestas |
| `fiesta` | Celebraciones |

## 📝 Formato Completo

```
# Esto es un comentario (se ignora)
version: 1.0
descripcion: Lista de juegos

juego: Multiplicaciones | multiplicar | https://ejemplo1.com/
juego: Adivina el Cantante | musica | https://ejemplo2.com/
juego: Sopa de Letras | sopa | https://ejemplo3.com/
```

### Reglas Simples

1. **Cada juego en una línea** que empieza con `juego:`
2. **Separa con tubos** `|` (la tecla al lado del 1)
3. **La URL debe empezar** por `https://` o `http://`
4. **Los comentarios** empiezan con `#`

## ⚠️ Errores Comunes

| ❌ Mal | ✅ Bien |
|-------|--------|
| `juego: Mi Juego` | `juego: Mi Juego | estrella | https://ejemplo.com/` |
| `juego: Mi Juego | estrella | ejemplo.com` | `juego: Mi Juego | estrella | https://ejemplo.com/` |
| `juego: Mi Juego | unicornio | ...` | `juego: Mi Juego | juego | ...` |

## 🔗 URL de GitHub Pages

Una vez configurado, la app descargará los juegos desde:

```
https://TU-USUARIO.github.io/tcheers-games/games.lang
```

## 🛠️ Configuración Inicial

### 1. Crear el Repositorio

1. Ve a [github.com/new](https://github.com/new)
2. Nombre: `tcheers-games`
3. Hazlo **Público**
4. Click en **"Create repository"**

### 2. Subir el Archivo

1. Click en **"uploading an existing file"**
2. Arrastra el archivo `games.lang`
3. Click en **"Commit changes"**

### 3. Activar GitHub Pages

1. Ve a **Settings** → **Pages**
2. En **Source**, selecciona:
   - Branch: `main`
   - Folder: `/ (root)`
3. Click en **Save**
4. Espera 1-2 minutos

### 4. Actualizar la App

Edita `lib/services/games_service.dart` y cambia la URL:

```dart
static const String _defaultGamesUrl = 
    'https://TU-USUARIO.github.io/tcheers-games/games.lang';
```

## 📱 Para Usuarios de la App

### Añadir Juegos desde la App

1. Abre la app
2. Toca el **logo 5 veces** rápidamente
3. Se abrirá el menú de configuración
4. Añade juegos manualmente o cambia la URL del JSON

### ¿Cuándo se ven los cambios?

- **Inmediato**: Si el usuario pulsa refresh (botón 🔄)
- **Automático**: La app actualiza cada 24 horas
- **Offline**: Usa la última versión cacheada

## 📄 Archivos

| Archivo | Para qué sirve |
|---------|---------------|
| `games.lang` | Archivo principal con los juegos |
| `games_plantilla.lang` | Plantilla vacía para empezar |
| `GESTION_JUEGOS.md` | Guía completa en español |

## ❓ Solución de Problemas

| Problema | Solución |
|----------|----------|
| La app no muestra juegos | Verifica que GitHub Pages esté activo |
| Error al cargar | Revisa que las URLs empiecen por `https://` |
| Juegos no actualizan | Toca el botón refresh en la app |
| Icono no se ve | Usa un nombre de icono de la lista |

## 🆘 Ayuda

Para más información, lee [`GESTION_JUEGOS.md`](GESTION_JUEGOS.md)

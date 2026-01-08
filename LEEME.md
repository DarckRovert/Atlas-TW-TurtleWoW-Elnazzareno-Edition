# Atlas-TW — Documentación (WoW 1.12)

Descripción: Atlas-TW es un navegador de mapas de mazmorras con un panel de botín integrado y módulo de misiones. Es compatible con World of Warcraft 1.12 e incluye soporte de localización.

![main](https://github.com/user-attachments/assets/fb4b69fc-158c-4f55-a0dd-bfd0a7967170)

## 1) Compatibilidad y Requisitos
- Cliente: WoW 1.12 (Interface: 11200)
- Carpeta del addon: Interface\AddOns\Atlas-TW
- Variables guardadas:
  - A nivel de cuenta: AtlasTWOptions
  - Por personaje: AtlasTWCharDB
- Dependencias opcionales (detectadas si están instaladas): LootLink, ItemSync, EquipCompare, EQCompare, pfQuest, pfUI

## 2) Instalación
- Copia la carpeta Atlas-TW a Interface\AddOns
- Activa el addon en la pantalla de selección de personaje

## 3) Inicio Rápido y Controles
- Abrir/Cerrar Atlas-TW: /atlas
- Abrir opciones: /atlas options (o /atlas opt)
- Botón del minimapa (si está activado):
  - Clic izquierdo — abrir Atlas-TW
  - Clic central — abrir opciones de Atlas-TW
  - Clic derecho + arrastrar — mover el botón
- La ventana de AtlasTW se puede arrastrar cuando está desbloqueada (botón de bloqueo en el marco)
- Clic derecho en la ventana de AtlasTW (si está activado) — cerrar AtlasTW y abrir el Mapa del Mundo

## 4) Características Principales
- Mapas de instancias con menús desplegables:
  - Arriba a la izquierda: selección de categoría (tipo de mapa)
  - Al lado: lista de instancias
- Selección automática de mapa basada en la zona actual (opción Auto-Select)
- Escala y Transparencia ajustables para la ventana de AtlasTW
- Fijar ventana a la pantalla
- Panel de botín (panel inferior):
  - Secciones: Mazmorras y Bandas, Colecciones, Facciones, Recompensas JcJ, Profesiones, Eventos Mundiales, Mobs Raros
  - Búsqueda, preajustes, navegación rápida
  - **Integración con pfQuest**:
    - Clic derecho en un objeto para buscarlo en la base de datos de pfQuest
- Módulo de misiones:
  - Panel lateral con misiones de instancia
  - Panel de detalles dentro de Atlas con historia/recompensas
  - Alternador de facción (Alianza/Horda), filtrado básico de disponibilidad
  - **Integración con pfQuest**:
    - Clic derecho en una misión de la lista para mostrar su ubicación inicial en el mapa
    - Clic derecho en una recompensa de misión para buscarla en la base de datos de pfQuest
- Tooltips mejorados de objetos: añade la fuente del botín al final del tooltip e integra con addons de comparación si están activados
- Opcional: superposición de coordenadas del cursor en el Mapa del Mundo predeterminado (activar en opciones)

## 5) Ventana y Elementos de UI
- Marco principal: AtlasTWFrame
- Menús desplegables:
  - Tipo de Mapa (categoría)
  - Selección de instancia
- Botones superiores:
  - Bloquear/Desbloquear — alternar movimiento de ventana
  - Opciones — abrir opciones de Atlas-TW
  - Misiones — mostrar/ocultar panel de misiones
  - Panel de Botín — mostrar/ocultar panel de botín inferior
- Panel de botín: botones de sección y área de objetos con desplazamiento
- Panel de misiones: contador de misiones, entradas de misiones, botones de facción, botón "Historia"

## 6) Opciones (destacadas)
- Mostrar Botón en Minimapa — mostrar el botón del minimapa
- Selección Automática de Mapa de Instancia — seleccionar automáticamente el mapa de instancia por zona actual
- Clic Derecho para Mapa del Mundo — el clic derecho cierra Atlas y abre el Mapa del Mundo
- Mostrar Acrónimos — mostrar acrónimos de instancias
- Fijar ventana a la pantalla — mantener la ventana dentro de la pantalla
- Transparencia — transparencia de la ventana de Atlas
- Escala — escala de la ventana de Atlas
- Mostrar Panel de Botín con AtlasTW — mostrar el panel de botín inferior
- Misiones — incrustar el panel de misiones en la ventana de Atlas
- Modos de tooltip (LootDefaultTT / LootlinkTT / LootItemSyncTT) — elegir integración de tooltip
- Mostrar coordenadas del cursor en el Mapa del Mundo — alternar AtlasTWOptions.AtlasCursorCoords

## 7) Comandos
- /atlastw — alternar ventana de Atlas-TW
- /atlastw options (o /atlastw opt) — abrir opciones
- /atlastw ver — imprimir tu versión local de Atlas-TW en el chat
- /atlastw ver check — publicar inmediatamente tu versión en LFT e imprimir confirmación

## 8) Primera Ejecución
- En la primera ejecución, puede mostrarse un mensaje de configuración una vez
- AtlasTWCharDB.FirstTime controla el comportamiento del saludo único

## 9) Preguntas Frecuentes
- La ventana es invisible
  - Verifica Escala/Transparencia en opciones
  - Escribe /atlastw
- Falta el botón del minimapa
  - Activa "Mostrar Botón en Minimapa" en opciones
- El clic derecho abre el Mapa del Mundo
  - Desactiva "Clic Derecho para Mapa del Mundo"
- No hay misiones para la instancia
  - Verifica tu facción (Alianza/Horda)
  - Algunas instancias pueden no tener misiones

## 10) Consejos
- La selección automática es útil cuando farmeas: el mapa correcto se abre automáticamente cuando entras en una instancia
- Para comparación de objetos, activa la integración de tooltip apropiada (ItemSync/LootLink/EquipCompare)
- Oculta el panel de botín temporalmente para ahorrar espacio dentro de la ventana de Atlas

## 11) Localización
- Atlas-TW usa un sistema de localización modular basado en espacios de nombres
- Estructura:
  - `Locales/LocalizationFramework.lua` — Sistema central de localización
  - `Locales/[locale]/` — Archivos específicos de idioma (enUS, deDE, esES, ptBR, zhCN)
  - Cada locale tiene 9 módulos: Core, Zones, Bosses, Classes, Factions, Spells, ItemSets, MapData, QuestData
- Fallback automático a inglés para traducciones faltantes
- Para añadir/actualizar traducciones: edita el archivo correspondiente en `Locales/[locale]/`

## 12) Detalles Técnicos
- No se requieren librerías Babble externas (reemplazadas por sistema modular)
- Todos los datos de localización se cargan a través de `Locales/locales.xml`

## Correcciones de Compatibilidad para Turtle WoW (Enero 2026)

Esta versión incluye correcciones y mejoras específicamente para Turtle WoW:

**Corregido por**: DarckRovert (Elnazzareno - El Sequito del Terror)

### Correcciones Realizadas:
- Reemplazadas las librerías Babble externas con sistema modular de localización
- Corregidos todos los errores de localización para español (esES)
- Mejorada la compatibilidad con contenido custom de Turtle WoW
- Mejorada la integración con pfQuest

Para información detallada sobre las correcciones, consulta:
- **CHANGELOG_TURTLEWOW.md** - Changelog completo (Inglés)
- **CREDITOS_ES.md** - Changelog completo (Español)
- **LEEME.md** - README en español

## Comentarios
- Reporta bugs y solicitudes: qué mapas/misiones/recompensas son incorrectos, tu idioma de cliente y versión de cliente

---

## Características Específicas de Turtle WoW

### Zonas Custom Soportadas
- **The Black Morass** (Morass Oscuro)
- **Emerald Sanctum** (Santuario Esmeralda)
- **Tower of Karazhan** (Torre de Karazhan)
- Todas las demás instancias custom de Turtle WoW

### Integración Mejorada con pfQuest
- Clic derecho en objetos del panel de botín para buscar en pfQuest
- Clic derecho en misiones para ver ubicación del NPC que la da
- Clic derecho en recompensas de misiones para buscar en pfQuest
- Funciona perfectamente con el addon pfQuest

### Sistema de Localización Modular
- Sin dependencias de librerías Babble externas
- Traducciones completas en 5 idiomas
- Fallback automático a inglés si falta una traducción
- Fácil de mantener y actualizar

## Créditos

### Equipo de Desarrollo Original de Atlas
- CFM
- Otari98
- Dan Gilbert
- Daviesh
- pepopo
- Y muchos otros contribuidores

### Correcciones para Turtle WoW
**Autor**: DarckRovert  
**Personaje**: Elnazzareno  
**Clan**: El Sequito del Terror  
**Fecha**: Enero 2026  

Estas correcciones fueron realizadas para eliminar todos los errores de Babble y mejorar la compatibilidad con el contenido custom de Turtle WoW.

## Soporte

Si encuentras algún error o tienes sugerencias, por favor contacta a:
- **Discord de Turtle WoW**: Busca a Elnazzareno
- **En el juego**: Envía un mensaje a Elnazzareno

## Licencia

Este addon mantiene la licencia original de Atlas. Las correcciones para Turtle WoW son de código abierto y pueden ser utilizadas libremente.

---

**¡Disfruta de tus mazmorras sin errores!** 🐢✨

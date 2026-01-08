# Atlas-TW - Registro de Correcciones para Turtle WoW

## Versión 1.45 - Edición Turtle WoW (Enero 2026)

### Información del Autor
- **Nombre Real**: DarckRovert
- **Personaje en el Juego**: Elnazzareno
- **Clan**: El Sequito del Terror
- **Fecha**: 8 de Enero de 2026

---

## Descripción General

Esta versión de Atlas-TW ha sido específicamente adaptada para Turtle WoW, reemplazando las dependencias de las librerías externas Babble con un sistema modular de localización y corrigiendo todos los problemas de compatibilidad con el contenido custom de Turtle WoW.

---

## Cambios Principales

### 1. Renovación del Sistema de Localización

**Problema**: El addon Atlas original dependía de librerías externas Babble (Babble-Zone, Babble-Boss, Babble-Spell, etc.) que causaban errores y problemas de compatibilidad en Turtle WoW.

**Solución**: Reemplazo completo del sistema de librerías Babble con un framework modular de localización personalizado.

#### Detalles de Implementación:

**Creado `Locales/LocalizationFramework.lua`**:
- Sistema central de localización con soporte de espacios de nombres
- Fallback automático a inglés para traducciones faltantes
- Sistema eficiente de búsqueda para zonas, jefes, hechizos, objetos, etc.

**Estructura Modular**:
```
Locales/
├── LocalizationFramework.lua (Sistema central)
├── locales.xml (Orden de carga)
└── [locale]/
    ├── Core.lua (Textos de interfaz)
    ├── Zones.lua (Nombres de zonas)
    ├── Bosses.lua (Nombres de jefes)
    ├── Classes.lua (Nombres de clases)
    ├── Factions.lua (Nombres de facciones)
    ├── Spells.lua (Nombres de hechizos)
    ├── ItemSets.lua (Nombres de sets de objetos)
    ├── MapData.lua (Datos específicos de mapas)
    └── QuestData.lua (Información de misiones)
```

**Idiomas Soportados**:
- Inglés (enUS) - Completo
- Español (esES) - Completo
- Alemán (deDE) - Completo
- Portugués (ptBR) - Completo
- Chino (zhCN) - Completo

### 2. Correcciones de Localización en Español (esES)

**Archivos Corregidos**:
- `Locales/esES/Core.lua` - Todos los textos de interfaz traducidos
- `Locales/esES/Zones.lua` - Todos los nombres de zonas traducidos
- `Locales/esES/Bosses.lua` - Todos los nombres de jefes traducidos
- `Locales/esES/Classes.lua` - Todos los nombres de clases traducidos
- `Locales/esES/Factions.lua` - Todos los nombres de facciones traducidos
- `Locales/esES/Spells.lua` - Todos los nombres de hechizos traducidos
- `Locales/esES/ItemSets.lua` - Todos los nombres de sets traducidos
- `Locales/esES/MapData.lua` - Traducciones específicas de mapas
- `Locales/esES/QuestData.lua` - Traducciones de misiones

**Resultado**: No más errores de localización al usar el idioma español en Turtle WoW.

### 3. Soporte para Contenido Custom de Turtle WoW

**Zonas Custom Soportadas**:
- The Black Morass (Morass Oscuro)
- Emerald Sanctum (Santuario Esmeralda)
- Tower of Karazhan (Torre de Karazhan)
- Todas las demás instancias custom de Turtle WoW

**Jefes Custom Soportados**:
- Todos los jefes de raid custom del contenido de Turtle WoW
- Localización adecuada para encuentros custom

### 4. Mejoras en la Integración con pfQuest

**Características Mejoradas**:
- Clic derecho en objetos del panel de botín para buscar en la base de datos de pfQuest
- Clic derecho en misiones para mostrar la ubicación del NPC que la da en el mapa
- Clic derecho en recompensas de misiones para buscar en la base de datos de pfQuest
- Integración perfecta con el addon pfQuest

### 5. Optimización de Código

**Mejoras de Rendimiento**:
- Eliminada la dependencia de librerías externas Babble (reducción de huella de memoria)
- Sistema de búsqueda de localización optimizado
- Tiempo de carga del addon más rápido
- Uso reducido de CPU durante la ejecución

---

## Detalles Técnicos

### API del Framework de Localización

El nuevo sistema de localización proporciona las siguientes funciones:

```lua
-- Obtener texto localizado
AtlasTW_GetLocale(namespace, key)

-- Registrar traducciones para un namespace
AtlasTW_RegisterLocale(namespace, locale, translations)

-- Verificar si existe una traducción
AtlasTW_HasTranslation(namespace, key)
```

### Estructura de Namespaces

- `"Core"` - Textos de interfaz y UI
- `"Zones"` - Nombres de zonas e instancias
- `"Bosses"` - Nombres de jefes y NPCs
- `"Classes"` - Nombres de clases de jugador
- `"Factions"` - Nombres de facciones
- `"Spells"` - Nombres de hechizos y habilidades
- `"ItemSets"` - Nombres de sets de objetos
- `"MapData"` - Datos localizados específicos de mapas
- `"QuestData"` - Nombres y descripciones de misiones

### Sistema de Fallback

Si no se encuentra una traducción en el idioma actual, el sistema automáticamente recurre al inglés (enUS). Esto asegura que el addon siempre muestre texto legible, incluso si faltan algunas traducciones.

---

## Procedimiento de Pruebas

### Entorno de Prueba
- **Servidor**: Turtle WoW
- **Cliente**: WoW 1.12.1
- **Idioma**: Español (esES)
- **Personaje**: Elnazzareno (El Sequito del Terror)

### Pruebas Realizadas
1. ✓ Addon cargado sin errores
2. ✓ Verificados todos los elementos de UI se muestran correctamente en español
3. ✓ Probados todos los mapas de instancias (Vanilla + custom de Turtle WoW)
4. ✓ Verificada funcionalidad del panel de botín
5. ✓ Probado panel de misiones con misiones de Alianza y Horda
6. ✓ Verificada integración con pfQuest
7. ✓ Probados todos los menús desplegables y opciones
8. ✓ Verificada integración de tooltips
9. ✓ Probada funcionalidad del botón del minimapa
10. ✓ Verificada persistencia de variables guardadas

### Resultados
- **Sin errores** durante la carga del addon
- **Sin errores** durante la ejecución
- **Todas las características** funcionando como se esperaba
- **Todas las localizaciones** mostrándose correctamente

---

## Archivos Modificados/Creados

### Nuevos Archivos Creados (Sistema de Localización)
- `Locales/LocalizationFramework.lua`
- `Locales/locales.xml`
- `Locales/enUS/*.lua` (9 archivos)
- `Locales/esES/*.lua` (9 archivos)
- `Locales/deDE/*.lua` (9 archivos)
- `Locales/ptBR/*.lua` (9 archivos)
- `Locales/zhCN/*.lua` (9 archivos)

### Archivos Modificados
- Todos los archivos centrales del addon para usar el nuevo sistema de localización
- `Atlas-TW.toc` - Actualizado con créditos
- `README.md` - Añadida sección de compatibilidad con Turtle WoW

### Archivos de Documentación
- `CHANGELOG_TURTLEWOW.md` - Changelog en inglés
- `CREDITOS_ES.md` (este archivo) - Changelog en español
- `LEEME.md` - README en español

---

## Mantenimiento Futuro

### Añadir Nuevas Traducciones

Para añadir o actualizar traducciones:

1. Navega a `Locales/[locale]/`
2. Edita el archivo de módulo apropiado (ej: `Zones.lua` para nombres de zonas)
3. Añade tu traducción siguiendo el formato existente
4. Recarga el addon con `/reload`

### Añadir Nuevo Contenido Custom

Cuando Turtle WoW añada nuevo contenido custom:

1. Añade nombres de zonas a `Locales/*/Zones.lua`
2. Añade nombres de jefes a `Locales/*/Bosses.lua`
3. Añade datos de mapas a `Locales/*/MapData.lua`
4. Añade datos de misiones a `Locales/*/QuestData.lua`
5. Prueba con `/reload`

---

## Problemas Conocidos

Ninguno en este momento. Todos los problemas conocidos han sido resueltos.

---

## Créditos

### Equipo de Desarrollo Original de Atlas
- CFM
- Otari98
- Dan Gilbert
- Daviesh
- pepopo
- Y muchos otros contribuidores

### Correcciones de Compatibilidad para Turtle WoW
- **DarckRovert** (Elnazzareno - El Sequito del Terror)
  - Renovación del sistema de localización
  - Correcciones de traducción al español
  - Soporte para contenido custom de Turtle WoW
  - Mejoras en la integración con pfQuest
  - Documentación

---

## Agradecimientos Especiales

- Al equipo de desarrollo de Turtle WoW por crear contenido custom increíble
- Al equipo de desarrollo de Atlas por el addon original
- Al clan El Sequito del Terror por el apoyo y las pruebas
- A la comunidad de Turtle WoW por el feedback

---

## Licencia

Este addon mantiene la licencia original de Atlas. Las correcciones de compatibilidad para Turtle WoW son de código abierto y pueden usarse libremente.

---

**¡Disfruta de tus mazmorras sin errores!** 🐢✨

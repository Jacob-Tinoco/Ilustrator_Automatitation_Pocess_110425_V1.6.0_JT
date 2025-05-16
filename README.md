# 🖋️ ILUSTRATOR_ASSETS_EXPORT_MAC_V1.6.0_JT

> **Versión:** V1.6.0  
> **Script actual:** `export_assets_mac_70525_V1.6.0_JT.py`  
> **Fecha de última actualización:** 09-05-2025  
> **Estado:** ✅ En uso productivo (macOS), en espera de validaciones y feedback por elqeuipo de Design

---

## 📘 Descripción General

Este launcher en macOS automatiza la ejecución de un ExtendScript en Adobe Illustrator para:

1. **Renombrado de grupos**  
   • Convierte los grupos de capas `"FRONT" → "F"` y `"BACK" → "B"`  
   • Mantiene intactos subgrupos secundarios  
2. **Detección y asociación de IDs**  
   • Busca `TextFrames` que coincidan con el patrón dinámico `XXXXXXXXX-XXX`  
   • Asocia cada grupo `F`, `B`, `S1`, `S2` o `IN` al ID más cercano (cuadrantes y distancia)  
3. **Limpieza y exportación de Assets**  
   • Limpia el panel **Assets for Export**  
   • Añade cada grupo renombrado como asset exportable  
   • Renombra automáticamente cada asset como `ID-F`, `ID-B`, `ID-S1`, etc.  
4. **Registro y notificaciones**  
   • Guarda un log detallado en `~/Downloads/export_assets_log.txt`  
   • Muestra una alerta final con el conteo de assets procesados  

> 🔁 Versión macOS equivalente a la edición Windows, usando `osascript` para inyección de ExtendScript.

---

## 🚀 Cómo Ejecutar

1. Abre Adobe Illustrator con un documento activo.  
2. En una terminal macOS, ve al directorio del script y ejecuta:

```bash
python3 export_assets_mac_70525_V1.6.0_JT.py
````

El script generará un archivo temporal de ExtendScript, lo inyectará en Illustrator y luego mostrará:

* Un log en `~/Downloads/export_assets_log.txt`
* Un mensaje de confirmación con el número de assets agregados

---

## 📁 Estructura del Proyecto

```bash
ILUSTRATOR_AUTOMATITATION_POCESS_110425/
├── backup/                            
├── build/                             
├── data/                              
├── dist_arm/                          
├── dist_x86/                         
├── dist_universal/                   
├── Documentation/                     
├── Downloads/                         
├── export/                            
├── exports/                          
├── respaldo/                         
├── src/
│   ├── export_assets_mac_70525_V1.6.0_JT.py    # Script principal V1.6.0
│   ├── gorup_view.py                           
│   └── script_exploratoreo_de_api.py           
├── añadir_assets_export.jsx           
├── añadir_assets_export.py            
├── ExportAssets.spec                  
├── README.md                          # Documento principal
├── notas.txt                          
├── draft_documentación.docx           
├── exploración_elementos_*.txt        
├── Reporte_Exportacion_Masiva_Illustrator_JT.docx 
├── Reporte_Exportacion_Masiva_Illustrator_JT.pdf  
└── Analisis_exploratorio_notas.txt    
```

---

## 📦 Dependencias

* **macOS** (con `osascript`)
* **Python ≥ 3.10**
* **Adobe Illustrator 2023+** (recomendado 2025)
* **No** requiere módulos adicionales en Python (solo `subprocess`, `tempfile`, `os`, `sys`)

---

## 📊 Impacto Operativo

Este script optimiza un flujo altamente manual:

* **Antes:** \~3.5 h por archivo
* **Equipo:** 5 personas
* **Ahorro semanal:** \~87.5 h (más de 11 jornadas)
* **Escalabilidad:** aplica a cualquier `.ai` con la estructura de capas correcta

---

## 📝 Notas Finales

* Asegúrate de que las capas estén nombradas exactamente `"FRONT"`, `"BACK"`, `"S1"`, `"S2"` o `"INSIDE"`
* El patrón ID es alfanumérico con guion (7–11 caracteres + `-` + 2–3 caracteres)
* Si no se detecta ID válido, el grupo se etiqueta como `DESCONOCIDO`
* Verifica permisos de automatización en **Seguridad y Privacidad** de macOS

---

## ✍️ Autor

**Jacob Tinoco**
📧 [jtinoco@maximaapparel.com](mailto:jtinoco@maximaapparel.com)
📆 Última actualización: 09-05-2025
Departamento de AI, Maxima Apparel&#x20;

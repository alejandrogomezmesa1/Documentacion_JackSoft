---
title: "00 MOC — Casos de Uso y Módulos del Sistema (JackSoft)"
type: MOC
tags:
  - moc
  - casos-de-uso
  - modulos
  - uml
aliases:
  - MOC Casos de Uso
  - Mapa Casos de Uso
related:
  - "[[00_INDICE_GENERAL]]"
  - "[[00_MOC_Manual_Tecnico]]"
  - "[[CU_01_Configuracion_y_Seguridad]]"
  - "[[CU_02_Compras_e_Inventario]]"
  - "[[CU_03_Produccion_y_Recetas]]"
  - "[[CU_04_Servicios_y_Operacion]]"
  - "[[CU_05_Clientes_y_Ventas]]"
  - "[[CU_06_Logistica_y_Domicilios]]"
  - "[[CU_07_Analitica_y_Metricas]]"
---

# 🎯 00 MOC — Casos de Uso y Módulos del Sistema (CU)

Este Mapa de Contenido consolida la especificación funcional detallada de los 7 macro-procesos del sistema **JackSoft**, desglosados en subprocesos, diagramas PlantUML/Mermaid y listados de casos de uso por rol.

---

## 🗺️ Mapa de Módulos del Sistema

```mermaid
graph TD
    MOC_CU["[[00_MOC_Casos_de_Uso]]"] --> CU01["[[CU_01_Configuracion_y_Seguridad]]"]
    MOC_CU --> CU02["[[CU_02_Compras_e_Inventario]]"]
    MOC_CU --> CU03["[[CU_03_Produccion_y_Recetas]]"]
    MOC_CU --> CU04["[[CU_04_Servicios_y_Operacion]]"]
    MOC_CU --> CU05["[[CU_05_Clientes_y_Ventas]]"]
    MOC_CU --> CU06["[[CU_06_Logistica_y_Domicilios]]"]
    MOC_CU --> CU07["[[CU_07_Analitica_y_Metricas]]"]

    CU01 -. Soporta Acceso .-> CU05
    CU02 -. Abastece Insumos .-> CU03
    CU03 -. Genera Pedidos .-> CU06
    CU05 -. Genera Ventas .-> CU06
    CU06 -. Emite KPIs .-> CU07
```

---

## 📚 Catálogo de Módulos Funcionales

1. **[[CU_01_Configuracion_y_Seguridad]]**: Administración de Roles (7 CUs), Permisos (6 CUs), Usuarios (6 CUs) y Mecanismos de Autenticación/Acceso (6 CUs).
2. **[[CU_02_Compras_e_Inventario]]**: Categorías de Insumos (5 CUs), Gestión de Insumos (7 CUs), Categorías de Productos (5 CUs), Productos (6 CUs), Proveedores (6 CUs) y Compras (6 CUs).
3. **[[CU_03_Produccion_y_Recetas]]**: Fichas Técnicas (6 CUs), Órdenes de Producción (6 CUs) y Producto Terminado (5 CUs).
4. **[[CU_04_Servicios_y_Operacion]]**: Planes de Servicio (6 CUs), Categorías de Servicio (5 CUs) y Agenda de Festivos (4 CUs).
5. **[[CU_05_Clientes_y_Ventas]]**: Registro de Clientes (6 CUs), Suscripciones / Ventas (8 CUs), Renovaciones (4 CUs) y Validación de Comprobantes (5 CUs).
6. **[[CU_06_Logistica_y_Domicilios]]**: Zonas de Cobertura (5 CUs), Asignación de Rutas (6 CUs), Tracking GPS en Tiempo Real (4 CUs), Gestión de Incidencias (6 CUs) y App Domiciliarios (6 CUs).
7. **[[CU_07_Analitica_y_Metricas]]**: Panel Dashboard (5 CUs), Reportes de Ventas (4 CUs), Reportes de Producción (4 CUs) y Reportes Logísticos (4 CUs).

---

## 🎨 Recursos y Diagramas del Módulo

- **Diagramas Editables:** `05_Casos_de_Uso/Diagramas_DrawIO/Casos_de_usos.drawio` (24 carriles, con Permisos).
- **Código y Exportaciones:**
  - `05_Casos_de_Uso/Diagramas_PUML/` (24 archivos en PlantUML).
  - `05_Casos_de_Uso/Diagramas_SVG/` (24 archivos vectoriales).
  - `05_Casos_de_Uso/Diagramas_PNG/` (24 diagramas de alta resolución).
- **Documento Oficial de Fichas:** `05_Casos_de_Uso/Especificaciones/Documentacion_Word/v2_2026-09-14/Documentacion_Casos_de_Uso_JackSoft.docx` (243 fichas funcionales).
- **Subprocesos v3:** `05_Casos_de_Uso/casos_de_uso_v3/` (desglose minucioso por cada subproceso).
- **Arquitectura C4 (Niveles 1 al 4):** `05_Casos_de_Uso/Arquitectura_C4/v2_2026-10-30/Arquitectura_C4_JackSoft.md` (Contexto, Contenedores, Componentes, Clases).
- **Visor Interactivo Web:** `05_Casos_de_Uso/Visor_Interactivo/mapa_interactivo.html` (el SVG multifase anterior está en `_Historial/Obsoletos/`).
- **Integración con el Manual Técnico:** La versión vigente consolidada de estos casos de uso se encuentra documentada en `10_Manual_Tecnico/Documentos_Word/v3_2026-09-25/Manual_Tecnico_v2.1_Jacksoft.docx` y auditada en [[Correcciones_Manual_Tecnico_v1]] dentro de [[00_MOC_Manual_Tecnico]].

## 🔄 Cambio de alcance 2026-11-02
* **Eliminado:** subproceso Empleados (sus diagramas quedan en `05_Casos_de_Uso/_Historial/`).
* **Nuevo:** Configuraciones del sistema (8 CU) en [[CU_01_Configuracion_y_Seguridad]] y Menú (9 CU, 2 de ellos en la app móvil) en [[CU_05_Clientes_y_Ventas]].
* Total: **23 subprocesos**. Documentación de CU v3: 248 fichas renumeradas HU_001–HU_248 en orden del documento. Roles queda sin "Asignar permisos" y Suscripciones suma "Aprobar solicitud fuera de límite".

## 🔄 Ajuste con el frontend 2026-11-03 (bd.uml v3.7)
Documentación de CU v4: 245 fichas renumeradas. Se retiran "Seleccionar menú personalizado", "Aplicar recargo por menú personalizado" y "Consultar impacto del menú personalizado"; "Aprobar solicitud fuera de límite" pasa a "Gestionar suscripciones con pago vencido"; "Cambiar estado del menú" pasa a "Publicar menú semanal"; los estados Pendiente y Vencida pasan a Pendiente de pago y Finalizada.

Documentación de CU v5 (2026-11-17): vuelve el subproceso **Permisos** antes de Roles (bd.uml v4.6, acuerdo G2). Total: **24 subprocesos** y 253 fichas; las de Permisos son HU_246 a HU_253 (listar, ver detalle, asignar a un rol, consultar los del rol, quitar, cambiar estado, buscar/filtrar y reporte por rol). Ruta: `Especificaciones/Documentacion_Word/v5_2026-11-17/`.

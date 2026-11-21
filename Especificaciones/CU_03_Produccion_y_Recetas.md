---
title: "CU-03: Módulo de Producción, Recetas y Fichas Técnicas"
type: Caso_de_Uso
tags:
  - casos-de-uso
  - produccion
  - cocina
  - fichas-tecnicas
  - recetas
aliases:
  - Modulo de Produccion
  - CU Produccion y Recetas
related:
  - "[[00_MOC_Casos_de_Uso]]"
  - "[[PROC_Planeacion_Cocina_y_Recetas]]"
  - "[[DB_Tablas_Inventario_Compras]]"
  - "[[RN_Suspensiones_Voluntarias]]"
---
# 📌 CU-03: Módulo de Producción y Recetas

## 📌 Descripción General
Categorías y catálogo de productos, fichas técnicas (recetas), órdenes de producción y producto terminado. El personal de cocina se gestiona como usuarios con rol.

---

## 📋 Subprocesos y Especificación Funcional

### Subproceso 1: CATEGORIA PRODUCTOS (6 Casos de Uso)
* **Actor Principal:** `Jefe de Cocina`
* **Nodo Principal:** `Gestión de categorías de productos`

![Diagrama de Casos de Uso - CATEGORIA PRODUCTOS](../Diagramas_PNG/CATEGORIA_PRODUCTOS.png)

#### Casos de Uso Oficiales:
1. **Crear categoría de productos**
2. **Listar categorías de productos**
3. **Ver detalle de la categoría de productos**
4. **Editar categoría de productos**
5. **Cambiar estado de la categoría de productos**
6. **Buscar/Filtrar categorías de productos**

---

### Subproceso 2: PRODUCTOS (6 Casos de Uso)
* **Actor Principal:** `Jefe de Cocina`
* **Nodo Principal:** `Gestión de productos`

![Diagrama de Casos de Uso - PRODUCTOS](../Diagramas_PNG/PRODUCTOS.png)

#### Casos de Uso Oficiales:
1. **Crear producto**
2. **Listar productos**
3. **Ver detalle del producto**
4. **Editar producto**
5. **Cambiar estado del producto**
6. **Buscar productos**

---

### Subproceso 3: PRODUCCION (9 Casos de Uso)
* **Actor Principal:** `Jefe de Cocina`
* **Nodo Principal:** `Gestión de producción`

![Diagrama de Casos de Uso - PRODUCCION](../Diagramas_PNG/PRODUCCION.png)

#### Casos de Uso Oficiales:
1. **Generar orden de producción desde el menú publicado**
2. **Listar órdenes de producción**
3. **Ver detalle de la orden de producción**
4. **Editar orden de producción**
5. **Cambiar estado de la orden de producción**
6. **Programar producción**
7. **Buscar producción**
8. **Reportar faltantes de insumos**
9. **Reporte de producción por período**

---

### Subproceso 4: FICHA TECNICA "PRODUCTO" (6 Casos de Uso)
* **Actor Principal:** `Jefe de Cocina`
* **Nodo Principal:** `Gestión de fichas técnicas`

![Diagrama de Casos de Uso - FICHA TECNICA "PRODUCTO"](../Diagramas_PNG/FICHA_TECNICA__PRODUCTO_.png)

#### Casos de Uso Oficiales:
1. **Crear ficha técnica de producto**
2. **Listar fichas técnicas de producto**
3. **Ver detalle de la ficha técnica de producto**
4. **Editar ficha técnica de producto**
5. **Buscar fichas técnicas de producto**
6. **Generar reporte de fichas técnicas**

---

### Subproceso 5: PRODUCTO TERMINADO (6 Casos de Uso)
* **Actor Principal:** `Jefe de Cocina`
* **Nodo Principal:** `Gestión de producto terminado`

![Diagrama de Casos de Uso - PRODUCTO TERMINADO](../Diagramas_PNG/PRODUCTO_TERMINADO.png)

#### Casos de Uso Oficiales:
1. **Registrar producto terminado desde la orden**
2. **Listar productos terminados**
3. **Ver detalle del producto terminado**
4. **Corregir cantidad producida desde la orden**
5. **Buscar productos terminados**
6. **Generar reporte de producto terminado**

---

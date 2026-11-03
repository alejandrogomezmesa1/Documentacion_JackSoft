---
title: "CU-01: Módulo de Configuración y Seguridad"
type: Caso_de_Uso
tags:
  - casos-de-uso
  - seguridad
  - roles
  - permisos
  - usuarios
  - autenticacion
aliases:
  - Modulo de Seguridad
  - CU Configuracion y Seguridad
related:
  - "[[00_MOC_Casos_de_Uso]]"
  - "[[DB_Tablas_Usuarios_Permisos]]"
  - "[[RN_QA_y_Auditoria]]"
---
# 📌 CU-01: Módulo de Configuración y Seguridad

## 📌 Descripción General
Gestión de roles, usuarios, mecanismos de autenticación y acceso al sistema, y configuraciones generales (valores del negocio y funcionalidades activables).

---

## 📋 Subprocesos y Especificación Funcional

### Subproceso 1: ROLES (6 Casos de Uso)
* **Actor Principal:** `Administrador`
* **Nodo Principal:** `Gestión de roles`

![Diagrama de Casos de Uso - ROLES](../Diagramas_PNG/ROLES.png)

#### Casos de Uso Oficiales:
1. **Crear rol**
2. **Listar roles**
3. **Ver detalle del rol**
4. **Editar rol**
5. **Cambiar estado**
6. **Eliminar rol**

---

### Subproceso 2: USUARIOS (8 Casos de Uso)
* **Actor Principal:** `Administrador`
* **Nodo Principal:** `Gestión de usuarios`

![Diagrama de Casos de Uso - USUARIOS](../Diagramas_PNG/USUARIOS.png)

#### Casos de Uso Oficiales:
1. **Crear usuario**
2. **Listar usuarios**
3. **Generar reporte**
4. **Ver detalle del usuario**
5. **Editar usuario**
6. **Cambiar estado**
7. **Eliminar usuario**
8. **Filtrar/Buscar usuario**

---

### Subproceso 3: ACCESO (5 Casos de Uso)
* **Actor Principal:** `Usuario / Admin`
* **Nodo Principal:** `Acceso al sistema`

![Diagrama de Casos de Uso - ACCESO](../Diagramas_PNG/ACCESO.png)

#### Casos de Uso Oficiales:
1. **Iniciar sesión**
2. **Recuperar/Restablecer contraseña**
3. **Consultar estado de la cuenta**
4. **Cerrar sesión**
5. **Generar reporte**

---

### Subproceso 4: CONFIGURACIONES DEL SISTEMA (8 Casos de Uso)
* **Actor Principal:** `Administrador`
* **Nodo Principal:** `Gestión de configuraciones`

![Diagrama de Casos de Uso - CONFIGURACIONES DEL SISTEMA](../Diagramas_PNG/CONFIGURACIONES_DEL_SISTEMA.png)

#### Casos de Uso Oficiales:
1. **Registrar configuración**
2. **Listar configuraciones**
3. **Ver detalle de la configuración**
4. **Editar valor de configuración**
5. **Activar/desactivar funcionalidad**
6. **Consultar historial de cambios**
7. **Restablecer valor por defecto**
8. **Buscar/Filtrar configuraciones**

---

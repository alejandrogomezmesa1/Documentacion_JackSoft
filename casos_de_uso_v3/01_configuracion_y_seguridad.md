# Macro-Proceso: Configuración y Seguridad

Gestión de permisos (matriz módulo × acción por rol), roles, usuarios, mecanismos de autenticación y acceso al sistema, y configuraciones generales (valores del negocio y funcionalidades activables).

## Subprocesos Integrados

### Subproceso: PERMISOS
- **Total de Casos de Uso / Acciones:** 8
- **Actor Principal:** Administrador
- **Nodo Principal:** Gestión de permisos

#### Listado de Casos de Uso
1. Listar permisos
2. Ver detalle del permiso
3. Asignar permisos a un rol
4. Consultar permisos del rol
5. Quitar permisos a un rol
6. Cambiar estado del permiso
7. Buscar/Filtrar permisos
8. Generar reporte de permisos por rol

#### Diagrama PlantUML
```plantuml
@startuml
left to right direction
skinparam packageStyle rectangle
skinparam nodesep 50
skinparam ranksep 70
skinparam shadowing true
skinparam defaultFontName "Inter, Arial, sans-serif"

skinparam actor {
  BorderColor #0f172a
  BackgroundColor #fff7ed
}

skinparam usecase {
  BackgroundColor #ffffff
  BorderColor #0f172a
  ArrowColor #ea580c
}

skinparam usecase<<hub>> {
  BackgroundColor #fff7ed
  BorderColor #ea580c
}

actor "Administrador" as actor_user

rectangle "SISTEMA JACKSOFT — SEGURIDAD Y ACCESO (PERMISOS)" {
  usecase "Gestión de permisos" as UC_Hub <<hub>>
  usecase "Listar permisos" as UC_Central <<hub>>
  usecase "Generar reporte de permisos por rol" as UC_Top1
  usecase "Buscar/Filtrar permisos" as UC_Bot1
  usecase "Ver detalle del permiso" as UC_R1
  usecase "Asignar permisos a un rol" as UC_R2
  usecase "Consultar permisos del rol" as UC_R3
  usecase "Quitar permisos a un rol" as UC_R4
  usecase "Cambiar estado del permiso" as UC_R5
}

actor_user --> UC_Hub
UC_Hub .> UC_Central : <<include>>
UC_Top1 ..> UC_Hub : <<extend>>
UC_Top1 .> UC_Central : <<include>>
UC_Bot1 ..> UC_Hub : <<extend>>
UC_Bot1 .> UC_Central : <<include>>
UC_R1 ..> UC_Central : <<extend>>
UC_R2 ..> UC_Central : <<extend>>
UC_R3 ..> UC_Central : <<extend>>
UC_R4 ..> UC_Central : <<extend>>
UC_R5 ..> UC_Central : <<extend>>
@enduml
```

---

### Subproceso: ROLES
- **Total de Casos de Uso / Acciones:** 5
- **Actor Principal:** Administrador
- **Nodo Principal:** Gestión de roles

#### Listado de Casos de Uso
1. Crear rol
2. Listar roles
3. Ver detalle del rol
4. Editar rol
5. Cambiar estado

#### Diagrama PlantUML
```plantuml
@startuml
left to right direction
skinparam packageStyle rectangle
skinparam nodesep 50
skinparam ranksep 70
skinparam shadowing true
skinparam defaultFontName "Inter, Arial, sans-serif"

skinparam actor {
  BorderColor #0f172a
  BackgroundColor #fff7ed
}

skinparam usecase {
  BackgroundColor #ffffff
  BorderColor #0f172a
  ArrowColor #ea580c
}

skinparam usecase<<hub>> {
  BackgroundColor #fff7ed
  BorderColor #ea580c
}

actor "Administrador" as actor_user

rectangle "SISTEMA JACKSOFT — SEGURIDAD Y ACCESO (ROLES)" {
  usecase "Gestión de roles" as UC_Hub <<hub>>
  usecase "Listar roles" as UC_Central <<hub>>
  usecase "Crear rol" as UC_Top1
  usecase "Ver detalle del rol" as UC_R1
  usecase "Editar rol" as UC_R2
  usecase "Cambiar estado" as UC_R3
}

actor_user --> UC_Hub
UC_Hub .> UC_Central : <<include>>
UC_Top1 ..> UC_Hub : <<extend>>
UC_Top1 .> UC_Central : <<include>>
UC_R1 ..> UC_Central : <<extend>>
UC_R2 ..> UC_Central : <<extend>>
UC_R3 ..> UC_Central : <<extend>>
@enduml
```

---

### Subproceso: USUARIOS
- **Total de Casos de Uso / Acciones:** 7
- **Actor Principal:** Administrador
- **Nodo Principal:** Gestión de usuarios

#### Listado de Casos de Uso
1. Crear usuario
2. Listar usuarios
3. Generar reporte
4. Ver detalle del usuario
5. Editar usuario
6. Cambiar estado
7. Filtrar/Buscar usuario

#### Diagrama PlantUML
```plantuml
@startuml
left to right direction
skinparam packageStyle rectangle
skinparam nodesep 50
skinparam ranksep 70
skinparam shadowing true
skinparam defaultFontName "Inter, Arial, sans-serif"

skinparam actor {
  BorderColor #0f172a
  BackgroundColor #fff7ed
}

skinparam usecase {
  BackgroundColor #ffffff
  BorderColor #0f172a
  ArrowColor #ea580c
}

skinparam usecase<<hub>> {
  BackgroundColor #fff7ed
  BorderColor #ea580c
}

actor "Administrador" as actor_user

rectangle "SISTEMA JACKSOFT — SEGURIDAD Y ACCESO (USUARIOS)" {
  usecase "Gestión de usuarios" as UC_Hub <<hub>>
  usecase "Listar usuarios" as UC_Central <<hub>>
  usecase "Crear usuario" as UC_Top1
  usecase "Generar reporte" as UC_Top2
  usecase "Filtrar/Buscar usuario" as UC_Bot1
  usecase "Ver detalle del usuario" as UC_R1
  usecase "Editar usuario" as UC_R2
  usecase "Cambiar estado" as UC_R3
}

actor_user --> UC_Hub
UC_Hub .> UC_Central : <<include>>
UC_Top1 ..> UC_Hub : <<extend>>
UC_Top1 .> UC_Central : <<include>>
UC_Top2 .> UC_Central : <<include>>
UC_Bot1 ..> UC_Hub : <<extend>>
UC_Bot1 .> UC_Central : <<include>>
UC_R1 ..> UC_Central : <<extend>>
UC_R2 ..> UC_Central : <<extend>>
UC_R3 ..> UC_Central : <<extend>>
@enduml
```

---

### Subproceso: ACCESO
- **Total de Casos de Uso / Acciones:** 7
- **Actor Principal:** Usuario / Admin
- **Nodo Principal:** Acceso al sistema

#### Listado de Casos de Uso
1. Iniciar sesión
2. Recuperar/Restablecer contraseña
3. Consultar estado de la cuenta
4. Cerrar sesión
5. Generar reporte
6. Iniciar sesión con Google o Apple
7. Iniciar sesión con código por WhatsApp

#### Diagrama PlantUML
```plantuml
@startuml
left to right direction
skinparam packageStyle rectangle
skinparam nodesep 50
skinparam ranksep 70
skinparam shadowing true
skinparam defaultFontName "Inter, Arial, sans-serif"

skinparam actor {
  BorderColor #0f172a
  BackgroundColor #fff7ed
}

skinparam usecase {
  BackgroundColor #ffffff
  BorderColor #0f172a
  ArrowColor #ea580c
}

skinparam usecase<<hub>> {
  BackgroundColor #fff7ed
  BorderColor #ea580c
}

actor "Usuario / Admin" as actor_user

rectangle "SISTEMA JACKSOFT — SEGURIDAD Y ACCESO (ACCESO)" {
  usecase "Acceso al sistema" as UC_Hub <<hub>>
  usecase "Iniciar sesión" as UC_Login <<hub>>
  usecase "Recuperar/Restablecer contraseña" as UC_Recup
  usecase "Consultar estado de la cuenta" as UC_Estado
  usecase "Cerrar sesión" as UC_Logout
  usecase "Generar reporte" as UC_Reporte
  usecase "Iniciar sesión con Google o Apple" as UC_Social
  usecase "Iniciar sesión con código por WhatsApp" as UC_Codigo
}

actor_user --> UC_Hub
UC_Hub .> UC_Login : <<include>>
UC_Recup ..> UC_Hub : <<extend>>
UC_Estado ..> UC_Login : <<extend>>
UC_Logout ..> UC_Login : <<extend>>
UC_Reporte ..> UC_Hub : <<extend>>
UC_Reporte .> UC_Login : <<include>>
UC_Social ..> UC_Login : <<extend>>
UC_Codigo ..> UC_Login : <<extend>>
@enduml
```

---

### Subproceso: CONFIGURACIONES DEL SISTEMA
- **Total de Casos de Uso / Acciones:** 8
- **Actor Principal:** Administrador
- **Nodo Principal:** Gestión de configuraciones

#### Listado de Casos de Uso
1. Registrar configuración
2. Listar configuraciones
3. Ver detalle de la configuración
4. Editar valor de configuración
5. Activar/desactivar funcionalidad
6. Consultar historial de cambios
7. Restablecer valor por defecto
8. Buscar/Filtrar configuraciones

#### Diagrama PlantUML
```plantuml
@startuml
left to right direction
skinparam packageStyle rectangle
skinparam nodesep 50
skinparam ranksep 70
skinparam shadowing true
skinparam defaultFontName "Inter, Arial, sans-serif"

skinparam actor {
  BorderColor #0f172a
  BackgroundColor #fff7ed
}

skinparam usecase {
  BackgroundColor #ffffff
  BorderColor #0f172a
  ArrowColor #ea580c
}

skinparam usecase<<hub>> {
  BackgroundColor #fff7ed
  BorderColor #ea580c
}

actor "Administrador" as actor_user

rectangle "SISTEMA JACKSOFT — SEGURIDAD Y ACCESO (CONFIGURACIONES DEL SISTEMA)" {
  usecase "Gestión de configuraciones" as UC_Hub <<hub>>
  usecase "Listar configuraciones" as UC_Central <<hub>>
  usecase "Registrar configuración" as UC_Top1
  usecase "Buscar/Filtrar configuraciones" as UC_Bot1
  usecase "Ver detalle de la configuración" as UC_R1
  usecase "Editar valor de configuración" as UC_R2
  usecase "Activar/desactivar funcionalidad" as UC_R3
  usecase "Consultar historial de cambios" as UC_R4
  usecase "Restablecer valor por defecto" as UC_R5
}

actor_user --> UC_Hub
UC_Hub .> UC_Central : <<include>>
UC_Top1 ..> UC_Hub : <<extend>>
UC_Top1 .> UC_Central : <<include>>
UC_Bot1 ..> UC_Hub : <<extend>>
UC_Bot1 .> UC_Central : <<include>>
UC_R1 ..> UC_Central : <<extend>>
UC_R2 ..> UC_Central : <<extend>>
UC_R3 ..> UC_Central : <<extend>>
UC_R4 ..> UC_Central : <<extend>>
UC_R5 ..> UC_Central : <<extend>>
@enduml
```

---

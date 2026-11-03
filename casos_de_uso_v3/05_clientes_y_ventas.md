# Macro-Proceso: Clientes y Ventas

Gestión de clientes, cotización, registro y administración de suscripciones, y programación del menú que reciben los clientes (consultable desde la app móvil).

## Subprocesos Integrados

### Subproceso: CLIENTES
- **Total de Casos de Uso / Acciones:** 7
- **Actor Principal:** Gestor Comercial
- **Nodo Principal:** Gestión de clientes

#### Listado de Casos de Uso
1. Crear cliente
2. Listar clientes
3. Generar reporte de clientes
4. Ver detalle del cliente
5. Editar cliente
6. Cambiar estado del cliente
7. Buscar/Filtrar clientes

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

actor "Gestor Comercial" as actor_user

rectangle "SISTEMA JACKSOFT — CLIENTES Y VENTAS (CLIENTES)" {
  usecase "Gestión de clientes" as UC_Hub <<hub>>
  usecase "Listar clientes" as UC_Central <<hub>>
  usecase "Crear cliente" as UC_Top1
  usecase "Generar reporte de clientes" as UC_Top2
  usecase "Buscar/Filtrar clientes" as UC_Bot1
  usecase "Ver detalle del cliente" as UC_R1
  usecase "Editar cliente" as UC_R2
  usecase "Cambiar estado del cliente" as UC_R3
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

### Subproceso: SUSCRIPCIONES
- **Total de Casos de Uso / Acciones:** 10
- **Actor Principal:** Gestor Comercial
- **Nodo Principal:** Gestión de suscripciones

#### Listado de Casos de Uso
1. Cotizar suscripción
2. Registrar suscripción
3. Listar suscripciones
4. Ver detalle de la suscripción
5. Editar suscripción
6. Cambiar estado de la suscripción
7. Subir comprobante de suscripción
8. Consultar comprobante de suscripción
9. Buscar/Filtrar suscripciones
10. Aprobar solicitud fuera de límite

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

actor "Gestor Comercial" as actor_user

rectangle "SISTEMA JACKSOFT — CLIENTES Y VENTAS (SUSCRIPCIONES)" {
  usecase "Gestión de suscripciones" as UC_Hub <<hub>>
  usecase "Listar suscripciones" as UC_Central <<hub>>
  usecase "Cotizar suscripción" as UC_Top1
  usecase "Registrar suscripción" as UC_Top2
  usecase "Buscar/Filtrar suscripciones" as UC_Bot1
  usecase "Ver detalle de la suscripción" as UC_R1
  usecase "Editar suscripción" as UC_R2
  usecase "Cambiar estado de la suscripción" as UC_R3
  usecase "Subir comprobante de suscripción" as UC_R4
  usecase "Consultar comprobante de suscripción" as UC_R5
  usecase "Aprobar solicitud fuera de límite" as UC_R6
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
UC_R4 ..> UC_Central : <<extend>>
UC_R5 ..> UC_Central : <<extend>>
UC_R6 ..> UC_Central : <<extend>>
@enduml
```

---

### Subproceso: MENU
- **Total de Casos de Uso / Acciones:** 9
- **Actor Principal:** Administrador / Cliente
- **Nodo Principal:** Gestión de menú

#### Listado de Casos de Uso
1. Crear menú
2. Listar menús
3. Ver detalle del menú
4. Editar menú
5. Cambiar estado del menú
6. Programar menú semanal
7. Buscar/Filtrar menús
8. Consultar menú de la semana (app móvil)
9. Ver detalle del almuerzo del día (app móvil)

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

actor "Administrador / Cliente" as actor_user

rectangle "SISTEMA JACKSOFT — CLIENTES Y VENTAS (MENU)" {
  usecase "Gestión de menú" as UC_Hub <<hub>>
  usecase "Listar menús" as UC_Central <<hub>>
  usecase "Crear menú" as UC_Top1
  usecase "Buscar/Filtrar menús" as UC_Bot1
  usecase "Ver detalle del menú" as UC_R1
  usecase "Editar menú" as UC_R2
  usecase "Cambiar estado del menú" as UC_R3
  usecase "Programar menú semanal" as UC_R4
  usecase "Consultar menú de la semana (app móvil)" as UC_R5
  usecase "Ver detalle del almuerzo del día (app móvil)" as UC_R6
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
UC_R6 ..> UC_Central : <<extend>>
@enduml
```

---

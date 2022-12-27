# Domain, Subdomain And Bounded Context

- Dominio: Lo que una organizacion hace y el mundo en que lo hace
- Bounded context > subdomain
- Subdomain: Un pedazo de dominio. Ej: Facturacion.
- Core domain: El corazon del dominio ?
- Subdominio: Puede ser un conjunto de algoritmos que si bien son escenciales no son parte del core domain
- Bounded context: Es una frontera explicita en donde existe un modelo de dominio

## Actividad

_Ejemplificar en nuestro proyecto_

* **Dominio:**
* **Bounded context:**
* **Subdomain:**
* **Core domain:**

# Context Maps

- Mapeo entre dos bounded context
- Sobre el presente y no sobre un futuro imaginario
- Dinamica de equipos/developers

| Nombre | Descripción | 
| -- | -- |
| Partnership | Dos equipos que trabajan en BC diferentes van a triunfar o fallar juntos. Cooperan en la elaboración de interfaces, para acordar nececidades de diseño de ambos |
| Shared kernel | Expliictar lo compartido. Un subset del dominio se mantiene en un pequeño kernel. Este kernel compartido tiene un status especial, no se puede cambiar sin acuerdo previo. CI para mantner el shared kernel. SK alineado con el lenguaje ubicuo|
|Customer-supplier dependent| Los equipos estan en una relación cliente/proveedor donde el equipo clinete necesita tener exito independientemnte del equipo proveedor. Negociacion|
|Comformista| Equipos con una relación asimetrica, donde el equipo de arriba no tiene ninguna motivacion para satisfacer las nececidades del de abajo. El equipo de abajo temrina adhiriendo al protolocol del de arriba|
|Anticorruption Layer| Cuando no todo es color de rosas en la comunicación aparece el tono defensivo. Utilizas funcionalidad del equipo de arriba en terminos de tu dominio. Tu sistema habla con el de arriba a traves de un interface. La interfaz puede ser unidireccional o bidireccional|
|Open host serive| Define un protocolo que da acceso a tu sistema como una serie de servicios. Abris el protocolo para que todos los que quieren integrarse puedan hacerlo|
|Published langauge| La traduccion entre dos modelos de un BC requiere de un lenguaje. Usar un lenguaje computado bien definido, que puede expresar la informacion de dominio necesaria como un medio comun de interpretación|
| Separate ways| Si un conjunto de funcionalidades que parecen estar relacionadas no tienen un relacion lo suficientemente significativa, podemos evitar los costos de integracion innecesarios (tradeoff)|
| Big Ball of Mud| Fronteras inconsistentes y modelos mezcaldos. Encerrarlo en un contrato y no hacerse el loco inventando cosas raras|

## Actividad

* Analizar que context maps se dan entre servicios de nuestro proyecto

# Architecture

- Por su naturaleza DDD no requiere una arquitectura en particular
- Debe haber un motivo detras de la arquitectura, meter por meter nos puede llevar a fallos inecesarios
- Evans plantea mas una arquitectura de capas, Vernon hexagonal. Podria ser cualquier cosa

---
### Capas

- Diseño del sistema en capas por responsabilidad. 
- En la version estricta cada capa se relaciona solo con su capa adyacente. 
- El dominio reside en una unica capa. 
- Es probable que evolucione a una arq hexagonal. 
- Ports and adapters. 
- Ej: UI - app - Dominio - infra

---
SOA 
- Service contract: El servicio expresa su proposito y capacidad
- Bajo acoplamiento: Los servicios minimizan dependencias y no tienen conociencia de otros servicios
- Abstraccion: Solo exponen su contrato
- Re uso
- Autonomia: Controlan su entorno subyacente y recursos. 
- Stateless: El manjeo del estado se delega al cliente
- Descubribles: Metadata
- Composicion: Pueden componerse con otros servicios}

--- 
REST

---
CQRS

---
Event driven

# Entities

- Unica y subceptible a ser modificada 
- Ciclo de vida
- Mantener la clase simple y centrarse en la continuidad del ciclo de vida y de la identidad
- Tiene un identidad univoca

# Value Objects

- Cuando es posible debemos usarlos en lugar de las entidades (mindset)
- Cuando lo unico que me importa son los atributos --> Value object
- Tratarlo como inmutable

# Services

# Domain Events

# Modules

# Aggregates

# Factories

# Repositories

# Integrating bounded contexts

# Aplication
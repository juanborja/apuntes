1. Domain, Subdomain And Bounded Context

- Dominio: Lo que una organizacion hace y el mundo en que lo hace
- Bounded context > subdomain
- Subdomain: Un pedazo de dominio. Ej: Facturacion.
- Core domain: El corazon del dominio ?
- Subdominio: Puede ser un conjunto de algoritmos que si bien son escenciales no son parte del core domain
- Bounded context: Es una frontera explicita en donde existe un modelo de dominio

2. Context Maps

- Mapeo entre dos bounded context
- Sobre el presente y no sobre un futuro imaginario
- Dinamica de equipos/developers

3. Architecture

- Por su naturaleza DDD no requiere una arquitectura en particular
- Debe haber un motivo detras de la arquitectura, meter por meter nos puede llevar a fallos inecesarios
- Evans plantea mas una arquitectura de capas, Vernon hexagonal. Podria ser cualquier cosa

4. Entities

- Unica y subceptible a ser modificada 
- Ciclo de vida
- Mantener la clase simple y centrarse en la continuidad del ciclo de vida y de la identidad
- Tiene un identidad univoca

5. Value Objects

- Cuando es posible debemos usarlos en lugar de las entidades (mindset)
- Cuando lo unico que me importa son los atributos --> Value object
- Tratarlo como inmutable

6. Services

7. Domain Events

8. Modules

9. Aggregates

10. Factories

11. Repositories

12. Integrating bounded contexts

13. Aplication
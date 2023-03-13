# Que es blockchain?
 ## Ethereum vs bitcoin
 Desde la perspectiva de las ciencias de la computación es una determinista y prácticamente ilimitada maquina de estados, que consiste en un único estado global que puede ser modificado a través de una maquina virtual.
 Desde la perspectiva practica es una infraestructura de computación descentralizada que ejecuta programadas denominados contratos inteligentes.
 Ethereum tiene varios puntos en común con otras blockchains (como bitcoin)
  - Se conectan a través de una red P2P
  - Un algoritmo de consenso resistente a fallos
  - Uso de primitivas criptográficas como firmas digitales y hashes 
  - Y un moneda digital (ether)

El propósito principal de ethereum no es la moneda en si, aunque es necesaria para pagar por el funcionamiento de Ethereum como la computadora mundial. A diferencia de bitcoin que tiene un lenguaje de scripting muy limitado, Ethereum esta diseñada para ser una blockchain programable de uso general que corre un maquina virtual capaz de ejecutar código arbitrario y prácticamente sin limitaciones. Mientras el lenguaje de bitcoin esta pensado para evaluar simplemente verdadero|falso sobre condiciones de pago el lenguaje de Ethereum es Turing computable  
      
 ## POW vs POS



Los creadores de bitcoin inventaron un algoritmo de consenso llamado prueba de trabajo (POW), el objetivo de este algoritmo es mantener la red segura a la vez que descentralizada, y consiste en descubrir un hash a través de una prueba de trabajo en la que se invierten recursos computacionales y energía y se obtiene un recompensa.  
Otro algoritmo de consenso es prueba de participación (PoS) en donde el consenso es respaldado por una suma de dinero en la moneda d ela blockchain en vez de por un gasto de recursos (trabajo), para volverse un validador la persona interesada envía una transacción que deja su ehter bloqueado como deposito. Los validadores votan para determinar los próximos bloques a incluir en la blockchain con el deposito como garantía y reciben una recompensa cuando el bloque es incluido.


Ethereum comenzó utilizando POW y luego del merge en 2022 funciona bajo POS

## Wallets

La palabra "wallet" es utilizada para describir diferentes cosas en Ethereum, a alto nivel la billetera es un software que funciona como principal interfaz del usuario con la red. La billetera controla el acceso al dinero del usuario, maneja las claves y direcciones. Hilando mas fino, desde la perspectiva del programador la billetera se refiere al sistema usado para almacenar y gestionar las claves de los usuarios. No hay un limite clave para lo que es o no una billetera, pero vamos a verlo como como un contenedor de claves privadas y un sistema para manejar esas claves.



## Transctions

Las transacciones son mensajes firmados y originado por una EOA, que son transmitido y almacenados por la red de Ethereum. Son lo único que puede disparar un cambio de estado o causar la ejecución de un contrato.

### Estructura de una transacción

- **nonce:** Número secuencial emitido por la EOA utilizado para prevenir la duplicación del mensaje.
- **gas price:** El precio de gas en wai que el originador de la transacción esta dispuesto a pagar
- **gas limit:** Cantidad máxima de gas que quien envía la transacción esta dispuesto a comprar
- **recipient:** La dirección de destino
- **value:** La cantidad de ether a enviar al destino
- **data:** Payload de la transacción en formato binario
- **v,r,s:** Los tres componentes en formato ECDSA que se utilizan para verificar la firma de la transacción

La creación de un contrato es una transacción especial que se envía a la dirección 0x00

ECDSA: Elliptic curve digital signature algorithm. Es el algoritmo de de firmado de transacciones en Ethereum, basado en un algoritmo de curva elíptica para pares de llaves publico-privada. Permite 3 cosas:
- La firma prueba que que el dueño de la clave privada que es por implicación el dueño de la EOA eue emitió la transacción ha autorizado el gasto de ether o ejecución de un contrato
- Garantiza no repudiable: la prueba de autorización es innegable
- garantiza que la información de la transacción (data) no fue y no puede ser modificada por nadie luego de que fue firmada

## Smart contracts
    - ERC 20
    - ERC 721
En Ethereum existen dos tipos de cuentas EOA y contratos. Las EOA son controladas por los usuarios, mientras que los contratos son un programa que corre sobre la EVM.
Un contrato inteligente es basicamente un programa que corre sobre la blockchain y tiene las siguientes caracteristicas:
- Es un programa de computadora
- Inmutable
- Deterministico
- Tiene el contexto d ela EVM
- Computadora mundial desentralizada

Se escrib en Solidity o Viper (LLL, Serpent, Bamboo) y se traduce a codigo maquina de EVM. Es deployado utilizando una transaccion que tiene como destino el address 0x00. Se crea una direccion de etherum asociada al contrato que no tiene llave privada.

- Solo corren si son invocados por una transaccion. 
- Un contrato puede llamar a otros

### ABI

Application binary interface. Define las funciones que pueden ser invocadas en el contrato, expone que argumento pueden recibir las funciones y en que formato responderan. En la practica es una array de JSON con la descripcion de cada funcion. Esta descripcion consiste en: type: name, inputs, ouputs, constant and payable. Un evento es descripto con: type, name, inputs and anoynmus. 
# Seguridad en la blockchain (aspectos basicos)

- Defensive programming: 
    - Minimalismo- Simplicidad: La complejidad es el enemigo de la seguridad. Mientras mas simple y menos haga un contrato menos probable es que tenga un bug. 
    - Rehuso de codigo: no reinventar la rueda. Si ya existe un contrato que lo haga, usalo sino asegurate que tu codigo siga DRY
    - Calidad de codigo: Clave no se puede tratar como codigo regular, cada error puede llevar a que se pierda dinero. Ingeniera y metodologias de software rigurosas, como si estuvieras en la industria aero espacial.
    - Legibilidad- que sea auditable: Tu codigo deberia ser facil de leer 
    - Test coverage. Testear codigo, como el codigo es publico y cualquiera puede leerlo y ejecutarlo deberias asumir la pero de las intenciones en las variables de entrada.

# Tokens

Abstracciones basadas en Blockchain que pueden ser obtenidas y representan activos, monedas o derechos a acceso. 

El uso mas obvio es el de una moneda digital
# Oraculos
# Aplicaciones desentralizadas (DApps)
# EVM
# Ecosistema JS

--- 
## Proyectos

1. [Simple NFT Example](https://speedrunethereum.com/challenge/simple-nft-example)
2. [Desentralized staking](https://speedrunethereum.com/challenge/decentralized-staking)
3. [Token vendor](https://speedrunethereum.com/challenge/token-vendor)
4. Build a DEX Challenge
5. Multisig Wallet Challenge
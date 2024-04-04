# CryptoZombies

Este proyecto lo arme a modo de practica con con el lenguaje Solidity, consiste en un contrato inteligente (smart contract) para crear y manejar zombies en una blockchain.

## Archivo 1: ZombieFactory.sol

Este archivo contiene la implementación de un contrato llamado `ZombieFactory`, que permite a los usuarios crear zombies de manera aleatoria. Aquí hay algunas características clave:

- **Eventos:**
  - `NewZombie`: Este evento se emite cada vez que se crea un nuevo zombie, proporcionando información sobre el ID del zombie, su nombre y su ADN.

- **Variables:**
  - `dnaDigits`: Un entero que representa la cantidad de dígitos en el ADN del zombie.
  - `dnaModulus`: El módulo utilizado para asegurar que el ADN generado tenga la longitud adecuada.
  - `zombies`: Una matriz pública que contiene todos los zombies creados.
  - `zombieToOwner`: Un mapeo que asigna el ID de un zombie a su propietario.
  - `ownerZombieCount`: Un mapeo que cuenta la cantidad de zombies que un usuario posee.

- **Funciones:**
  - `_createZombie`: Una función privada que crea un nuevo zombie y emite el evento `NewZombie`.
  - `_generateRandomDna`: Una función privada que genera un número aleatorio basado en una cadena de entrada.
  - `createRandomZombie`: Una función pública que permite a los usuarios crear un zombie aleatorio, siempre que no posean ningún otro zombie.

## Archivo 2: ZombieFactoryV2.sol

Este archivo presenta una versión simplificada del contrato `ZombieFactory`, eliminando la contabilidad del propietario del zombie. Aquí están las principales diferencias:

- Se ha eliminado la contabilidad del propietario y la restricción de crear solo un zombie por usuario.

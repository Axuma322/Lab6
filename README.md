# Sistema de Gestión de Eventos y Actualizaciones en Tiempo Real

## Descripción General
Este es un sistema de gestión de eventos y actualizaciones de datos en tiempo real utilizando el patrón de diseño de callbacks. El sistema se compone de tres módulos principales: `EventManager`, `RealTimeDataManager`, y un módulo ejecutable `main.py`.

## Módulos

### `eventos.py`
Este módulo define la clase `EventManager`, que es responsable de manejar los eventos y las suscripciones de los callbacks. Las principales funcionalidades incluyen:
- **Suscripción a Eventos:** Permite que los callbacks se registren para eventos específicos.
- **Cancelación de Suscripción:** Elimina los callbacks de la lista de suscriptores.
- **Notificación:** Informa a todos los suscriptores registrados cuando ocurre un evento específico.

### `datamanager.py`
Contiene la clase `RealTimeDataManager`, la cual simula la generación y actualización de datos en tiempo real. Sus características son:
- **Generación de Datos:** Actualiza valores de `temperatura` y `humedad` aleatoriamente cada 3 segundos.
- **Integración con EventManager:** Notifica a los suscriptores del `EventManager` cada vez que los datos se actualizan.

### `main.py`
Este es el módulo ejecutable que integra los módulos `EventManager` y `RealTimeDataManager`. En él se realizan las siguientes acciones:
- **Creación de Instancias:** Inicializa `EventManager` y `RealTimeDataManager`.
- **Suscripción de Callbacks:** Registra una función callback que imprime los datos actualizados.
- **Ejecución del Bucle de Actualización:** Inicia un hilo para las actualizaciones de datos en tiempo real y mantiene el programa en ejecución.

## Ejemplo de Resultados
Al ejecutar `main.py`, el programa produce una salida en la consola que muestra los datos actualizados en tiempo real. Un ejemplo de salida podría ser:
Datos en tiempo real actualizados: {'temperatura': 25.135503724540715, 'humedad': 58.72619213938574}
Datos en tiempo real actualizados: {'temperatura': 25.152980007970235, 'humedad': 58.54094853821499}
Datos en tiempo real actualizados: {'temperatura': 25.47714880639016, 'humedad': 58.48333141193844}
Datos en tiempo real actualizados: {'temperatura': 25.06320128795558, 'humedad': 57.34698595121229}
Datos en tiempo real actualizados: {'temperatura': 25.83796669326286, 'humedad': 58.91154070212184}
Datos en tiempo real actualizados: {'temperatura': 25.633820355546508, 'humedad': 57.92364213595421}


Cada línea representa una actualización de los valores de `temperatura` y `humedad`, que ocurre aproximadamente cada 3 segundos.

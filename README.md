# Prueba
uwu

[Ver el documento PDF](Netlogo/DiscreteEventSimulationQueuesandServers.pdf)

# Prueba 2

# Discrete Event Simulation: Queues and Servers

## Descripción del modelo
Este modelo simula un sistema de colas M/M/n, donde los clientes llegan y esperan en una cola hasta que uno de los servidores esté disponible para atenderlos. El número de servidores (hasta 10) y las tasas de llegada y servicio de los clientes son configurables. El modelo permite recopilar estadísticas agregadas sobre el tiempo promedio en la cola y en el sistema.

## Propósito del modelo
El propósito del modelo es analizar el comportamiento de un sistema de colas y servidores, midiendo cómo factores como el número de servidores o la tasa de llegada afectan el tiempo de espera de los clientes.

## Tipos de agentes

1. **Clientes (customers)**: Los clientes son las entidades que llegan al sistema y esperan en la cola para ser atendidos. Cada cliente registra su tiempo de llegada y el tiempo en que comienza el servicio.

2. **Servidores (servers)**: Los servidores atienden a los clientes en orden de llegada. Cada servidor registra el cliente que está atendiendo y el tiempo estimado para finalizar el servicio.

## Propiedades de los agentes

### Propiedades de los clientes (customers):
- `time-entered-queue`: Tiempo en que el cliente ingresó al sistema (cola).
- `time-entered-service`: Tiempo en que el cliente comenzó a ser atendido por un servidor.

### Propiedades de los servidores (servers):
- `customer-being-served`: El cliente que el servidor está atendiendo.
- `service-completion-time`: Tiempo estimado de finalización del servicio para el cliente actual.

## Dinámica del modelo
Los clientes llegan al sistema a intervalos de tiempo definidos por una tasa de llegada (`lambda`). Cuando llegan, entran a una cola si no hay servidores disponibles. Si hay un servidor disponible, el cliente pasa directamente a ser atendido. Los servidores atienden a los clientes en el orden en que llegaron (primero en entrar, primero en ser servido). Cada cliente tiene un tiempo de servicio, tras el cual el servidor se libera y puede atender a otro cliente. 

Las estadísticas sobre el tiempo que los clientes pasan en la cola y en el sistema completo se recopilan para calcular promedios.

## Parámetros del modelo
- **Número de servidores (n)**: Puedes configurar hasta 10 servidores.
- **Tasa de llegada (lambda)**: Define el intervalo de tiempo entre la llegada de clientes al sistema.
- **Tasa de servicio (mu)**: Determina cuánto tiempo tarda cada servidor en atender a un cliente.

## Estadísticas y gráficos
El modelo recopila las siguientes estadísticas:
- **Tiempo promedio en la cola**: El tiempo que los clientes esperan en la cola antes de ser atendidos.
- **Tiempo promedio en el sistema**: El tiempo total que los clientes pasan en el sistema (cola + servicio).
- **Número de clientes en la cola**: La cantidad de clientes que esperan para ser atendidos en un momento dado.

Estas estadísticas se visualizan en gráficos a lo largo del tiempo, lo que permite observar el comportamiento del sistema bajo diferentes configuraciones.

## Cálculo teórico y comparación con simulación
Se calculó el promedio y la probabilidad mediante ecuaciones para comparar con los resultados de la simulación. Estas ecuaciones siguen la lógica del sistema con su tasa de cambio (`lambda`) y tasa de servicio (`mu`), ajustando el tamaño de la cola y las probabilidades correspondientes. Los valores obtenidos en las pruebas fueron comparados con los resultados simulados para validar la precisión del modelo.

### Ejemplos de comparación de resultados (Teórico vs Simulado):

| Intento | Teórico | Simulado |
|---------|---------|----------|
| 1       | 184.784 | 164.141  |
| 2       | 151.106 | 148.232  |
| 3       | 131.014 | 140.681  |
| ...     | ...     | ...      |
| 10      | 151.393 | 150.271  |
| **Promedio** | 149.208 | 148.895 |

Se utilizaron diferentes valores para `lambda` y `mu`, incluyendo casos donde `lambda` es mayor, menor e igual a `mu`.

## Conclusión
Se realizó una simulación de un sistema de colas M/M/n, donde se compararon los resultados teóricos y simulados para analizar el comportamiento del sistema. Los resultados mostraron una coherencia general, pero se encontraron diferencias en las escalas de los valores teóricos y simulados. Estas discrepancias probablemente se deben a diferencias en las unidades de tiempo utilizadas o a pequeños errores de precisión en la simulación.

A lo largo del proceso, se aprendió que la correcta configuración de parámetros, como las tasas de llegada (`lambda`) y servicio (`mu`), es fundamental para obtener resultados consistentes. También se evidenció la importancia de tener en cuenta la aleatoriedad en las simulaciones.

El trabajo permitió reforzar el entendimiento del funcionamiento de los sistemas de colas y su aplicación en la simulación de eventos discretos.

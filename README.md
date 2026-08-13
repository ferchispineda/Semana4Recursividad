# Práctica 4: Implementación Segura de Recursividad en C#

## Descripción

En esta práctica se implementaron y compararon algoritmos iterativos y recursivos para calcular el factorial y la serie de Fibonacci en C#. El objetivo principal fue analizar las diferencias de rendimiento entre ambos enfoques y comprender la importancia del caso base para evitar problemas de Stack Overflow.

## Algoritmos implementados

Se desarrollaron los siguientes métodos:

* Factorial iterativo.
* Factorial recursivo.
* Fibonacci iterativo.
* Fibonacci recursivo.

Los métodos recursivos incluyen casos base explícitos para detener correctamente la recursión.

## Pruebas de rendimiento

Para medir el tiempo de ejecución de cada algoritmo se utilizó `System.Diagnostics.Stopwatch`.

Los valores utilizados fueron:

* Factorial: `n = 20`
* Fibonacci: `n = 40`

## Resultados obtenidos

| Algoritmo           |           Resultado |         Tiempo |
| ------------------- | ------------------: | -------------: |
| Factorial Iterativo | 2432902008176640000 |    0.673900 ms |
| Factorial Recursivo | 2432902008176640000 |    0.310300 ms |
| Fibonacci Iterativo |           102334155 |    0.308000 ms |
| Fibonacci Recursivo |           102334155 | 2128.684600 ms |

## Salida de la ejecución

```text
╔═══════════════════════════════════════════════════╗
║       COMPARATIVA: ITERATIVO vs RECURSIVO        ║
╚═══════════════════════════════════════════════════╝

--- FACTORIAL(20) ---
[Iterativo] Resultado:       2432902008176640000 Tiempo: 0.673900 ms
[Recursivo] Resultado:       2432902008176640000 Tiempo: 0.310300 ms

--- FIBONACCI(40) ---
[Iterativo] Resultado:                 102334155 Tiempo: 0.308000 ms
[Recursivo] Resultado:                 102334155 Tiempo: 2128.684600 ms

[OK] Prueba completada. Registra los tiempos en tu bitácora.
```

## Análisis

Los resultados muestran que ambos enfoques producen correctamente los mismos valores. En el caso del factorial, la diferencia de tiempo es pequeña para `n = 20`.

La diferencia más importante se observa en Fibonacci. El método iterativo calculó `Fibonacci(40)` en `0.308000 ms`, mientras que el método recursivo necesitó `2128.684600 ms`.

Esto demuestra el elevado costo computacional del algoritmo Fibonacci recursivo naïve, ya que realiza una gran cantidad de llamadas repetidas. En contraste, el algoritmo iterativo realiza el cálculo mediante un ciclo y utiliza espacio constante.

## Caso base y Stack Overflow

El caso base es fundamental en un algoritmo recursivo porque establece la condición que detiene las llamadas sucesivas al método. Si el caso base no existe o nunca puede alcanzarse, las llamadas continúan acumulándose en el Call Stack hasta provocar un Stack Overflow.

En esta práctica se utilizaron casos base explícitos tanto para Factorial como para Fibonacci, garantizando que la recursión pueda finalizar correctamente.

## Conclusión

Esta práctica permitió comprobar experimentalmente las diferencias entre los algoritmos iterativos y recursivos. Aunque la recursividad puede producir código claro y fácil de comprender, debe utilizarse de manera controlada y considerando su impacto en memoria y rendimiento.

La comparación de Fibonacci mostró especialmente la importancia de analizar la complejidad algorítmica antes de seleccionar una solución. El uso de `Stopwatch` permitió respaldar esta comparación con resultados obtenidos directamente durante la ejecución del programa.

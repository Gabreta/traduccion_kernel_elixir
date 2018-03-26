# Nucleo
Este Modulo es el punto de entrada del lenguaje de programacion Elixir.
Este ofrece las funciones por defecto y los macros que eloxor importa en su entorno. Estos pueden ser invocados directamente en el codigo sin el nombre del modulo:
```elixir
iex> is_number(13)
true
```
Estas funciones y macros pueden ser omitidas o seleccionadas mediante la macro `Kernel.SpecialForms.import/2`. Para instanciar, si quieres que Elixir no importe la macro `if/2`, tu puedes hacer:
```elixir
import Kernel, expect: [if: 2]
```
Elixir tiene formas especiales que siempre se importen y no se puedan omitir. Estos se describen en `Kernel.SpecialForms`.

Este modulo proveé una variante de definicion de codigo, control de flujo y funcionalidad de tipo de datos. Por ejemplo, nuevos procesos pueden ser creados con `spawn/1`, los modulos pueden ser definidos con `defmodules/2`, los operadores logicos cortos son `&&/2` y `||/2`, los numeros pueden ser sumados con `+/2`, y mas. Este modulo tambien tiene guardas incorporados, que son un conjunto de funciones que enfocan hacia la coincidencia de patrones con verificacion compleja. Para mas informacion acerca de los guardas pueden ser encontrados en la [pagina de guardas](https://hexdocs.pm/elixir/guards.html).

# La libreria estandar
`Kernel` provee las funcionalidades basicas de elixir que estan construidas encima de la libreria estandar. Es recomendado explorar la libreria estandar para funcionalidades avanzadas. Aqui estan los principales grupos de modulos en la libreria estandar (esta lista no es una completa referencia, vea la documentacion en la barra lateral para todas las entradas).

## Modulos incorporados
Los siguientes modulos manejan los tipos de datos integrados en Elixir:
* `Atom` - Constantes literales con nombre (`true`, `false` y `nil` son atomos)
* `Float` - Numeros con precision de punto flotante
* `Integer` - Numero enteros (No fracciones)
* `List` - Coleccion de un numero de elementos variable (Listas vinculadas)
* `Map` - Colecciones por pares llave-valor
* `Process` - Hilos ligeros de ejecucion
* `Port` - Mecanismos para relacionarse con el mundo externo
* `Tuple` - Colecciones de un numero fijo de elementos

Hay tres tipos de datos sin un modulo que los acompañe:
* Bitstrings - Una secuencia de bits, creado con `Kernel.SpecialForms<<>>/1`. Cuando el numero de bits es divisible por 8, son llamados binarios y pueden ser usados por el modulo de Earlang `:binary.
* Function - Una referencia a un fragmento de codigo, creado con la forma especial `Kernel.SpecialForms.fn/2`.
* Reference - Un unico valor en el tiempo de ejecucion del sistema, creado con `make_ref/0`.
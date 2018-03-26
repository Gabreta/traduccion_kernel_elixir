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
* Bitstrings - Una secuencia de bits, creado con `Kernel.SpecialForms<<>>/1`. Cuando el numero de bits es divisible por 8, son llamados binarios y pueden ser usados por el modulo de Earlang `:binary`.
* Function - Una referencia a un fragmento de codigo, creado con la forma especial `Kernel.SpecialForms.fn/2`.
* Reference - Un unico valor en el tiempo de ejecucion del sistema, creado con `make_ref/0`.

## Tipo de Datos
Elixir tambien proveen otro tipo de datos que estan construidos con los tipos mencionados anteriormente, Algunos de ellos pueden ser:
* `Date` - Estructura dada en un calendario `Año-Mes-Dia`.
* `DateTime` - Hora y fecha con zona horaria dada en un calendario.
* `Exception` - Datos generados por errores y escenarios inesperados.
* `MapSet` - Colecciones desordenadas de elementos unicos.
* `NaiveDateTime` - Hora y fecha sin zona horaria dada en un calendario.
* `Keyword` - Lista de dos tuplas de elementos, a menudo representando valores opcionales.
* `Range` - Inclusion de rango entre dos enteros.
* `Regex` - Expresiones Regulares.
* `String` - Representacion de caracteres binarios codificados en UTF-8.
* `Time` - Estructura obtenida por el calendario enfocado en `hora:minuto:segundo`.
* `URI` -  Representacion recursos que identifican URI.
* `Version` - Representacion de versiones y requerimietos.

## Modulos del sistema
Los modulos que interactuan con dicho sistema, son:
* `IO` - Manejo de entradas y salidas.
* `File` - Interactua con el sistema de archivos subyacente.
* `Path` - Manipula las rutas del sistema de archivos.
* `System` - Lee y escribe informacion del sistema.

## Protocolos
Los protocolos agregan un envio poliformico a Elixir. Estos son contratos inplementables por los tipos de datos. Ver `defprotocol/2` para mas informacion en protocolos. Elixir provee los siguientes protocolos en su libreria estandar:
* `Collectable` - Reune datos en un tipo de datos
* `Enumerable` - Manipula las colecciones en Elixir. El modulo `Enum` provee funciones vehementemente para trabajar con colecciones, el modulo `Stream` provee de funciones vagas.
* `Inspect` - Convierte el tipo de datos en su representacion de lenguaje de programacion.
* `List.Chars` - Convierte el tipo de datos en la representacion que hay en el mundo exterior como lista de caracteres (No basados en programacion).
* `String.Chars` - Convierte el tipo de datos en la representacion que hay en el mundo exterior como strings (no basado en la programacion).

## Funcionalidades basadas en el proceso y centrado de la aplicacion
Los siguientes modulos se basan en los procesos para presentar concurrencia, tolerancia a fallos, y mas...
* `Agent` - Un modulo que encapsula el estado mutable.
* `Application` - Funciones para iniciar, detener y configurar aplicaciones.
* `GenServer` - Una API generica cliente-servidor.
* `Registry`- Un proceso llave-valor basada en almacenamiento.
* `Supervisor` - Un proceso que es responsable de iniciar, supervisar y apagar otros procesos.
* `Task` - Un proceso que realice calculos
* `Task.Supervisor` - Un supervisor para la gestion exclusiva de tareas.

## Documentos de Soporte
La documentacion de Elixir tambien incluye documentacion de soporte en la seccion de "paginas"- Estas son:
* [Desuso u obsolencia](https://hexdocs.pm/elixir/deprecations.html) - Lista de todas las funciones em desuso, cuando las hay y sus respectivas alternativas.
* [Guardas](https://hexdocs.pm/elixir/guards.html) - Lista de todos los guardas y extensiones disponibles.
* [Convenciones de Nombres](https://hexdocs.pm/elixir/naming-conventions.html) - Nombrado por convencion para el lenguaje Elixir.
* [Operadores](https://hexdocs.pm/elixir/operators.html) - Lista de todos los operadores y su respectiva prioridad.
* [Referencia de Sintaxis](https://hexdocs.pm/elixir/syntax-reference.html) - Referido a la sintaxis del lenguaje.
* [Syntaxis Unicode](https://hexdocs.pm/elixir/unicode-syntax.html) - Nocion general del soporte de Elixir para Unicode.
* [Escritura de Documentacion](https://hexdocs.pm/elixir/writing-documentation.html) - Pautas para escribir documentacion en Elixir.
# Taller-Videodebate: escritura colectiva y colaborativa ctrl+c ctrl+v usando git

> ¡Para activistas, periodistas y comunicadores sociales!

**Requisitos:**

-   Cuenta en [GitHub](https://github.com/).
-   [git](https://git-scm.com/downloads), obviamente.
-   [Atom](https://github.com/atom/atom/releases/latest) u otro `$EDITOR`.
   Por defecto, Atom enviará datos de uso "anónimos" (sistema operativo,
   version de la aplicación, resolucion de pantalla, etc) a través de Google
   Analytics. Recomendamos desactivar el paquete "Metrics" en su configuración.

_Recomendaciones:_

-   Sistema operativo GNU+Linux [libre](https://www.gnu.org/philosophy/open-source-misses-the-point.html)
-   ¡[conectar Atom con GitHub](https://github.atom.io/login)!
-   Elegir una [interfaz gráfica](https://git-scm.com/downloads/guis),
    [GitKraken](https://www.gitkraken.com/) está buena pero no es libre :/

## Tabla de Contenidos

<!-- toc orderedList:0 depthFrom:1 depthTo:6 -->

* [Taller-Videodebate: escritura colectiva y colaborativa ctrl+c ctrl+v usando git](#taller-videodebate-escritura-colectiva-y-colaborativa-ctrlc-ctrlv-usando-git)
    * [Tabla de Contenidos](#tabla-de-contenidos)
    * [Git](#git)
    * [Interfaz de línea de comandos](#interfaz-de-línea-de-comandos)
    * ["Workflow" básico](#workflow-básico)
    * ["Tire" y "Empuje" abren muchas puertas](#tire-y-empuje-abren-muchas-puertas)
    * [Colgado de una rama](#colgado-de-una-rama)
    * [GitHub.com :octocat:](#githubcom-octocat)
    * [Concluyendo](#concluyendo)
            * [Discusiones de experimentos](#discusiones-de-experimentos)
    * [Markdown](#markdown)
    * [Misc.](#misc)

<!-- tocstop -->

> Todo esto, lo veremos el primer día.

- - -

## Git

Es un `sistema de control de versiones` distribuído y libre, fué
desarrollado por **programadoras del kernel Linux** en 2005 (tras
[una disputa](https://www.linux.com/news/bitkeeper-and-linux-end-road)
entre _hackers_ y derechos de propiedad intelectual). Es una herramienta pensada
para satisfacer las necesidades del trabajo colaborativo con código fuente.
Al menos, les resulta de utilidad para las **13,600** programadoras
que han contribuído las **22,000,000** líneas de código fuente que posee el
kernel de Linux
([citando datos del 2016](https://www.linux.com/infographic/25-years-linux-kernel-development)).

Ahora bien, ¿Cuán distinto es el código fuente de una aplicación informática
respecto a un cuento, o una poesía? ...a los fines prácticos de git:
¡no hay diferencias! salvo quizás porque en la prosa de un cuento esperaríamos
tener una mayor cantidad de palabras por renglón (línea).

> \- _Whaaat?!_
>
> \- sí, pozta :hankey:

## Interfaz de línea de comandos

Lamentablemente, lo desconocido es temido. Para muchas, la sóla idea de
escribir comandos en una terminal es... cosa de ~~mandinga~~ hackers.
Tengamos presente que escribir comandos en una terminal, una vez que se entiende
la lógica subyacente, no es otra cosa más que _**decirle**_ a la máquina lo que
deseamos que haga.

## "Workflow" básico

Si con la terminal vamos a una carpeta dada y ejecutamos `git init`, el comando
va a "iniciar" al sistema de control de versiones en dicha carpeta. Si luego
creáramos un archivo, necesitamos ponerlo en el área de "ensayo" (**staging**).
Para eso ejecutaremos `git add nombreDelArchivo`. A partir de entonces forma
parte de nuestra área de ensayo. Sin embargo, todavía no está en el historial.

"Normalmente" el primer archivo que debiéramos agregar, es `LICENSE` y supone
una de las decisiones mas importante para cualquier proyecto. En nuestro caso,
vamos a trabajar con la [Licencia de Producción de Pares](https://endefensadelsl.org/ppl_deed_es.html).

Si en este momento le preguntáramos a git por el "estado" del control de
versiones en dicha carpeta, pondríamos `git status`. Él nos diría que tenemos
un archivo en el área de ensayo "sin comprometer" (**commit**) al historial que
git guarda para nosotras. ¿Cómo lo comprometemos?...

**IMPORTANTE** cada `commit` _debe_ tener un comentario breve y además _permite_
incluir una descripción acerca de qué cambios son los que se introducen.

Una vez que nuestra carpeta de trabajo haya avanzado lo suficiente, puede ser
que tenga una gran cantidad de archivos. Su historial de cambios será una lista
de los sucesivos commits y puede verse con tan sólo pedir el "registro"
`git log`.

![Merge branch 'asdfasjkfdlas/alkdjf' into sdkjfls-final](https://imgs.xkcd.com/comics/git_commit.png)

## "Tire" y "Empuje" abren muchas puertas

El repositorio creado es "local", sin embargo el trabajo mas enriquecedor es
entre pares. Para poder compartir debemos agregar un repositorio "remoto".
Para esto se utiliza el comando `git remote add unNombreElegido direccionDelRepositorio.git`.
Luego, si pidiéramos el estado (`git status`) veríamos que estamos adelantados
en algunos "compromisos"/_commits_ que falta "empujar" (**push**) hacia el _repo_
remoto. Para ello es que nos valemos de `git push`.

A partir de entonces el flujo de trabajo es lineal: add, commit, push. Pero
claro que hay mucho más, veamos...

Cuando usamos _GitHub_ como repositorio remoto, siempre será público (salvo que
gatillemo\$). Por lo tanto, cualquiera puede encontrar nuestro trabajo y
copiarlo (respetando nuestra licencia). Para ello se hará una copia local
del repositorio usando `git clone direccionDelRepositorio.git`. Si además esta
persona resultara ser de nuestra confianza, podemos agregarla como
colaboradora. Entonces ella podría hacer cambios directamente y luego
_pushearlos_. Es decir, también puede aplicar un flujo de trabajo lineal:
add, commit, push. ¿Pero que pasa si yo hice un _commit_ antes y el repo
remoto está "adelantado"?... Si una "empujó" cambios antes, la otra tendrá que
"tirar" de ellos desde el repo remoto hacia el suyo local con `git pull`.

Cuando una persona cualquiera (sin ser colaboradora) realica modificaciones en
su copia local puede realizar una "propuesta de tiraje" (**pull request**) para
que el dueño del repositorio (remoto) lo acepte e incorpore.

## Colgado de una rama

Git implementa las "ramas" (**branches**) para aislar variaciones de **contexto**. Se
pueden crear con `git branch elNombreDeUnaRamaNueva`. Hasta aquí hemos venido
viendo los flujos de trabajo lineales (add, commit, push y/o pull). Estos
comandos por defecto han sido trabajando siempre en nuestra rama maestra
(**master**). Pero podríamos tener tantas ramas como nos fueran necesarias,
para ensayar distintas alternativas. Al pasar de una rama a otra con
`git checkout elNombreDeUnaRamaExistente`, los archivos del repositorio serán
los que correspondan con los cambios que deban ser. Es decir, los _commit_ son
independientes en cada rama.

<!--
Mostrar `git log --graph --decorate --oneline` .
Mostrar links de commits, q es un hash, y los diff en github...
-->

_NOTA:_ atajo para cambiar a una rama nueva:
`git checkout -b elNombreDeUnaRamaNueva`.
(El `-b` le dice a checkout que cree la rama).

## GitHub.com :octocat:

<!--
1. Gh es un frente, aclararlo pa explicitar q hay un detras. Averiguar si ese detras es gpl o no. Y gitlab q licencia tiene?
-->

Pequeña disquisición pertinente, _GitHub_ es un sitio web que permite a sus
usuarias compartir (gratuita y públicamente) sus **repositorios** de trabajo.
Sin embargo, **git** es una aplicación independiente a éste o cualquier otro
sitio web (servidor). **Git** permite guardar versiones y trabajar en
ramas locales llamadas _branches_ (bifurcaciones de la línea de producción que
posibilitan, por ejemplo, ensayar finales alternativos). Por su parte,
**GitHub** permite a las usuarias de su plataforma ramificar los repositorios
públicos de terceros. Dicha acción se llama _fork_, y copia todo el repositorio
incluídas sus _branches_. Ya lo veremos en práctica para que quede claro...

![If that doesn't fix it, git.txt contains the phone number of a friend of mine who understands git. Just wait through a few minutes of 'It's really pretty simple, just think of branches as...' and eventually you'll learn the commands that will fix everything.](https://imgs.xkcd.com/comics/git.png)

## Concluyendo

Todo lo visto hasta aquí puede parecer complicado la primera vez, pero funciona
de modo bastante directo _...peeero_ es así hasta que no. Si dos personas
modifican a la vez una misma línea git no tiene forma de saber qué cambios
son los correctos. Es entonces cuando tenemos un "conflicto de unión"
(**merge conflict**, aparece así en el git status). Se resuelve eligiendo
manualmente qué "cachos" (**hunks**) deben conservarse. En el caso mas simple,
tendríamos la línea en cuestión repetida y delimitada por `<<<<<<<` ...ya lo
verán, xq pasa! tranca 120.

![Shit happens](https://i.giphy.com/media/cFkiFMDg3iFoI/giphy-downsized.gif)

#### Discusiones de experimentos

Cuando todas tienen permiso de push (son colaboradoras) vamos a tener un modelo
de trabajo en el repositorio, tal que las ramas definen tópicos e ideas. Es
decir, cuando una diga "ah, voy a agregar/modificar/eliminar esto por cierto
motivo dado", genera la rama con los cambios y luego hace el pull request
([mostrar](https://github.com/infopublica/git-md/compare)) para que todas
discutan y alcancen consenso sobre esos cambios y ese motivo. Si se decide
proceder a unir/mergear los cambios, listo. Si no, queda el historial de la
discusión ;)

<!--
Al mergear se puede hacer un rebase o squash para elegir como se modifica
el historial de git. Esto es avanzado, lo dejo aquí picando...
https://help.github.com/articles/merging-a-pull-request/

(por cierto, vean q hay comentarios entre líneas).

Opcionalmente, se puede eliminar la rama dps de mergear.
-->

## Markdown

Para detectar las diferencias entre una version y otra, git hace comparación
de línea-a-línea. Por esto será importante que nuestros archivos tengan
líneas con un largo máximo estándar de `80` caracteres. Además, no vamos a estar
metiendo documentos de microsoft word! si no que trabajaremos con texto plano y
descubriremos que [_menos es más_](https://en.wikipedia.org/wiki/Unix_philosophy).
¿Pero cómo podremos poner los títulos,
subtítulos, copetes, negritas, cursivas, etcétera?

<!-- Comentar sobre el largo de caracteres que luego a la hora de hacer
cambios es preferible que nos queden lineas mas cortas o mas largas antes
que tener que modificar todo un párrafo por haber sacado dos palabras locas. -->

La [sintáxis "markdown"](https://daringfireball.net/projects/markdown/syntax) es
una forma sencilla de escribir texto plano con algunos elementos básicos de
formato. Por ejemplo, podemos poner texto en **negrita** rodeando la(s)
palabra(s) con dos asteriscos ó guiones bajos y en _cursiva_ rodeando con un único `*` ó
`_`. Por ejemplo: se puede escribir \*\*así\*\* y \_asá\_ para tener negrita y
cursiva, respectivamente. A lo largo de este taller adoptaremos
una convención y usaremos los asteriscos para la negrita y los guiones bajos
para la cursiva. Por contraejemplo, \_\_no así\_\_ ni \*asá\* (para tener
negrita y cursiva, respectivamente).

Existen "flavors" (sabores) de markdown que proveen algunos elementos extras.
uno de los más conocidos es el que usa GitHub en su sitio web. En
[este machete](https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf)
van a encontrar los principales elementos que vamos a estar usando. Ante cualquier duda, será de utilidad la
[guía completa al markdown de github](https://guides.github.com/features/mastering-markdown/).

- - -

## Misc.

*   Plugins de atom que pueden ser de interés para `$ apm install`:
    *   organized
    *   atom-focus-mode
    *   markdown-preview-enhanced
    *   markdown-folder
    *   linter-markdown
    *   language-markdown
    *   zotero-citations
    *   zotero-picker
    *   git-history
    *   git-time-machine
    *   split-diff
    *   latex-completions

*   Tras
    [configurar git por primera vez](https://git-scm.com/book/es/v1/Empezando-Configurando-Git-por-primera-vez#Tu-identidad)
    le hemos dicho nuestro nombre de usuario y correo electrónico. Estos datos
    se usan para asignar la autoría cada vez que guardamos cambios en un
    _commit_, si uno quisiera resguardar su dirección de correo puede poner
    `USERNAME@users.noreply.github.com`.


*   Para evitar escribir la clave de GitHub en cada push es recomendable
    utilizar el acceso [con llave criptográfica SSH](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/).


*   Algunos otros recursos de aprendizaje:
    *   [Paso a paso en GitHub](https://guides.github.com/activities/hello-world/)
    *   [Git en 15 minutos de consola](https://try.github.io/levels/1/challenges/1)
    *   [Videos introductorios](https://git-scm.com/videos)
    *   Libro de Git
        *   [v1 en español](https://git-scm.com/book/es/v1)
        *   [v2 en inglés](https://git-scm.com/book/en/v2)


        <!--
        1. poner intro marketplace de triggers y hooks
        2. Ver en atom github lista plugins comunitarios. Probarlos, comentarlos y agregarlos en recursos
        -->


*   Para tener a mano siempre:
    *   [Guías básicas y avanzadas](https://www.atlassian.com/git)
    *   [Diagrama de flujo para resolver problemas](http://justinhileman.info/article/git-pretty/git-pretty.png)
    *   [Machete interactivo y profundo](http://ndpsoftware.com/git-cheatsheet.html)


*   Alternativas a GitHub
    *   [BitBucket](https://bitbucket.org/)
    *   [GitLab](https://about.gitlab.com/)
        *   [Instancia de RiseUp](https://0xacab.org/)
    *   [ScuttleBot](http://evbogue.com/distributedgit/)


*   Lista de [listados de cosas copadas :eyeglasses:](https://github.com/sindresorhus/awesome)

<!-- Futuros encuentros: GitHub Pages? Jekyll? -->

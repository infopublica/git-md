# Git

Git es un "sistema de control de versiones" descentralizado y
[libre](https://www.gnu.org/philosophy/open-source-misses-the-point.html)
desarrollado por **programadoras del kernel Linux** en 2005 (tras
[una disputa](https://www.linux.com/news/bitkeeper-and-linux-end-road)
entre _hackers_ y derechos de propiedad intelectual). Es una herramienta pensada
para satisfacer las necesidades del trabajo colaborativo con código fuente.
Así, al menos resulta de utilidad para las **13,600** programadoras
que han contribuído las **22,000,000** líneas de código fuente que posee el
kernel de Linux
([citando datos del 2016](https://www.linux.com/infographic/25-years-linux-kernel-development)).

Ahora bien, ¿Cuán distinto es el código fuente de una aplicación informática
respecto a un cuento o una poesía?... a los fines prácticos de git, ¡no hay diferencias! salvo quizás con la prosa, porque cada renglón (línea) tiende a
tener una mayor cantidad de palabras respecto al código fuente.

_Whaaat?!_ sí, posta. Aprovechándo esto es que vamos a utilizar la potencialidad
más fundamental de git en este taller de escritura colectiva y colaborativa.
 :hankey: ...vamos a armar un repositorio! (carpeta bajo control de git) donde
 trabajaremos textos.

# GitHub.com

Pequeña disquisición pertinente, _GitHub_ es un sitio web que permite a sus
usuarias compartir (gratuita y públicamente) sus **repositorios** de trabajo.
Sin embargo, **git** es una aplicación independiente a éste o cualquier otro
sitio web (servidor). **Git** permite guardar versiones y trabajar en
ramas locales llamadas _branches_ (bifurcaciones de la línea de producción que
posibilitan, por ejemplo, ensayar finales alternativos). Por su parte,
**GitHub** permite a las usuarias de su plataforma ramificar los repositorios
públicos de terceros. Dicha acción se llama _fork_, y copia todo el repositorio
incluídas sus _branches_. Ya lo veremos en práctica para que quede claro...

# Markdown

Para detectar las diferencias entre una version y otra, git hace comparación
de línea-a-línea. Por esto será importante que nuestros archivos tengan
líneas con un largo máximo estándar de `80` caracteres. Además, no vamos a estar
metiendo documentos de microsoft word! si no que trabajaremos con texto plano y
descubriremos que _menos es más_. ¿Pero cómo podremos poner los títulos,
subtítulos, copetes, negritas, cursivas, etcétera?

La [sintáxis "markdown"](https://daringfireball.net/projects/markdown/syntax) es
una forma sencilla de escribir texto plano con algunos elementos básicos de
formato. Por ejemplo, podemos poner texto en **negrita** rodeando la(s)
palabra(s) con dos "\*" ó "\_" y en _cursiva_ rodeando con un único "\*" ó
"\_". Por ejemplo: se puede escribir \*\*así\*\* y \_asá\_ para tener negrita y
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

# Notas varias

*   Tras
    [configurar git por primera vez](https://git-scm.com/book/es/v1/Empezando-Configurando-Git-por-primera-vez#Tu-identidad)
    le hemos dicho nuestro nombre de usuario y correo electrónico. Estos datos
    se usan para asignar la autoría cada vez que guardamos cambios en un
    _commit_, si uno quisiera resguardar su dirección de correo puede poner
    `USERNAME@users.noreply.github.com`.

*   Algunos recursos de utilidad:
    *   [Paso a paso en GitHub](https://guides.github.com/activities/hello-world/)
    *   [Git en 15 minutos de consola](https://try.github.io/levels/1/challenges/1)
    *   [Guías básicas y avanzadas](https://www.atlassian.com/git)
    *   Libro de Git
        *   [v1 en español](https://git-scm.com/book/es/v1)
        *   [v2 en inglés](https://git-scm.com/book/en/v2)
    *   Otras nubes alternativas a GitHub que además podemos servirnos
        *   [BitBucket](https://bitbucket.org/)
        *   [GitLab](https://about.gitlab.com/)
            *   [Instancia de RiseUp](https://0xacab.org/)
        *   [ScuttleBot](http://evbogue.com/distributedgit/)
    *   [Lista de 'listas de cosas copadas'](https://github.com/sindresorhus/awesome)

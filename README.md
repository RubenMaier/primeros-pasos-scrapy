# CURSO DE SCRAPINGHUB 🚀
##### 📦 Actualizado al:  22/09/2020

## 1 Conocimiento general 📋
Scrapy está escrito en Python puro, por lo tanto, depnde de algunos paquetes claves de Python. Detallarémos alguno de los mas relevantes:

- [Ixml](https://lxml.de/index.html), es un analizador de XML y HTML eficiente.
- [parsel](https://pypi.org/project/parsel/), es una librería de extracción de datos HTML/XML escrita sobre Ixml.
- [w3lib](https://pypi.org/project/w3lib/), es una librería multipropósito para tratar con URL y codificaciones de paginas web.
- [twisted](https://twistedmatrix.com/trac/), es un marco de trabajo en red asincrónico.
- [cryptography](https://cryptography.io/en/latest/) y [pyOpenSSL](https://pypi.org/project/pyOpenSSL/), para afrontar diversas necesidades a nivel de seguridad de red.

Se recomienda tener actualizado estos paquetes. Debe saber que algunos de estos paquetes, dependen a su vez de paquetes que no son de Python, y que pueden requerir pasos de instalación adicionales dependiendo de su plataforma.

#### 1.1 Versiones de Python compatibles
Scrapy necesita Python 3.5.2+, ya sea para la implementación CPython (predeterminada) o para la implementación PyPy 5.9+ (Consulte [implementaciones alternativas](https://docs.python.org/3/reference/introduction.html#implementations))

## 2. Instalación de Scrapy 🔧
Si está utilizando [Anaconda](https://docs.anaconda.com/anaconda/) o [Miniconda](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html), puede instalar el paquete desde el canal [conda-forge](https://conda-forge.org/), que tiene paquetes actualizados para Linux, Windows o macOS.

Para instalar Scrapy usando *conda*, ejecute:
```
code install -c conda-forge scrapy
```

Si usted está familizariado con el instalador de paquetes de Python, puede instalar Scrapy y sus dependencias desde PyPI con:
```
pip install Scrapy
```

Debe tener en cuenta que, segun su sistema operativo, a veces puede ser necesario resolver problemas de copilación con algunas dependencias de Scrapy, así que, asegurese de consultar las [referencias de instalación específicas](#) segun su plataforma.

Se **recomienda** como buena práctica, instalar Scrapy en un [virtualenv dedicado](#), para evitar conflicos con los paquetes de su sistema.

#### 2.1. Entornos virtuales (virtualenv)
Los paquetes de Python se pueden instalar globalmente (en todo el sistema) o en el espacio del usuario. Como ya mencionamos antes, no se recomienda instalar Scrapy de manera global. En su lugar, recomendamos que instale Scrapy dentro de lo que se conoce como *entorno virtual* ([`venv`](https://docs.python.org/3/library/venv.html#module-venv)).

Los entornos virtuales nos permiten evitar confilictos con paquetes de Python ya instalados en el sistema (que podrían romper alguna de las herramientas y los scrips del propio sistema).

Si usted no sabe como crear uno, consulte la guía de [entornos y paquetes virtuales](https://docs.python.org/3/tutorial/venv.html#tut-venv).

Con un entorno virtual ya creado, puede ahora instalar Scrapy con *pip*, como cualquier otro paquete. Puede que instalar Scrapy implique previamente instalar otras librerías que tienen dependencia indirecta, por lo cual le recomendamos que lea las [referencias de instalación específicas](#) segun su plataforma para estar seguro.

## 3 Referencias de instalación específicas ⚙️

#### 3.1 Windows
Se puede instalar Scrapy por *pip*, pero recomendamos que lo instale [Anaconda]() o en su defecto [Minianaconda]() y utilice el paquete del canal [conda-forge](), lo que evitará la mayoría de los problemas de instalación. Una vez instalado alguno, ejecute:
```
conda install -c conda-forge scrapy
```
Si desea un tutorial de instalación mas interactivo para Windows, puede ver un video de [youtube en ingles](https://www.youtube.com/watch?v=7PRy5LnTLaQ) que lo explica.

#### 3.2 Ubuntu 14.04 o superior
Por temas de compatibilidad, recomendamos que tenga alguna versión actual de Ubuntu, puesto que puede llegar a existir problemas con las conexiones TLS. **NO** utilice el paquete `python-scrapy` provisto por Ubuntu (Es viejo y lento).

Para instalar Scrapy en sistemas Ubuntu (o similares), necesita varias dependencias que serán instaladas con el siguiente comando:
```
sudo apt-get install python3 python3-dev python3-pip libxml2-dev libxslt1-dev zlib1g-dev libffi-dev libssl-dev
```

Las liberías `python3-dev` `python3-pip`, `zlib1g-dev`, `libxml2-dev` y `libxslt1-dev` son necesarias para `lxml`. Mientras que `libffi-dev` y `libssl-dev` son necesarias para `cryptography`.

Si usted tiene instalado un *virtualenv* puede instalar Scrapy con *pip* ejecutando:
```
pip install scrapy
```

#### 3.2 macOS
Para utilizar Scrapy necesitará tener un compliador de C y encabezados de desarrollo. En macOS, esto suele ser proporcionado por las herramientas que provee el entorno de desarrollo integrado de Apple conocido como *Xcode*. Para instalarlo, debe ejecutar:
```
xcode-select --install
```

En esté punto suelen ocurrir problemas a la hora de instalar Scrapy con *pip*, por lo tanto, existen dos formas de resolverlo:

1) Debe instalar el administrador de paquetes [Homebrew](https://brew.sh/) siguiendo las instrucciones en su web oficial. 
- Ahora debe actualizar la variable *PATH* del sistema para indicar que los paquets de homebrew deben usarse antes que los paquetes del sistema (debe cambiarse *.bashrc* a *.zshrc* segun corresponda).
```
echo "export PATH=/usr/local/bin:/usr/local/sbin:$PATH" >> ~/.bashrc
```
- Vuelva a cargar *.bashrc* para asegurar los cambios:
```
source ~/.bashrc
```
- Instalar Python:
```
brew install python; brew update; brew upgrade python
```
2) Instalar Scrapy dentro de un entorno virtual de Python.

Finalmente, puede instalar Scrapy a traves de:
```
pip install scrapy
```

---

<p align="center">
  <b>Continuar aprendiendo...</b>
  <br>
  ⬅ Anterior 🔥
  <a href="./capitulo1/README.md">Siguiente ➡</a>
</p>

---

📌 Está misma información, o incluso más actualizada, la puede encontrar en su [fuente oficial](https://doc.scrapy.org/en/latest/intro/install.html#intro-install-platform-notes) y original en ingles.
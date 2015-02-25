Proyecto de documentacion para NetBSD alternativo creado con sphinx

Este repositorio alberga los fuentes de la documentacion para el proyecto
NetBSD.MX usando sphinx-doc, un proyecto escrito en Python para su documentacion.

Para publicar la documentacion necesitas lo siguiente:

1. Python
2. pip (python package manager ) Si tienes Python 2.7.9 en adelante, seguro ya esta instalado.
3. sphinx *http://www.sphinx-doc.org* (Software escrito en python para proyectos de documentacion.
4. Instalar el tema sphinx_bootstrap_theme.

::

  $ sudo pip install sphinx_bootstrap_theme

5. Clonar la documentacion de los depositos de Github. 

El archivo conf.py localizado en el subdiretorio source/ ya contiene la configuracion correcta
para usar el tema y ha sido personalizado para usar un poco los colores que el proyecto NetBSD
usa.

6.- Para construir la documentacion necesitas gmake (GNU make), NetBSD usa make (BSD make o nbmake) 
la documentacion incluye un Makefile para automatizar el proceso.





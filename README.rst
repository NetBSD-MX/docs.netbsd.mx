Proyecto de documentacion para NetBSD alternativo creado con sphinx

Este repositorio alberga los fuentes de la documentacion para el proyecto
NetBSD.MX usando sphinx-doc, un proyecto escrito en Python para su documentacion.

Para publicar la documentacion necesitas lo siguiente:

1.- Instalar el tema sphinx_bootstrap_theme, si tienes Python instalado seguramente
tendras pip (python install program).
::

	$ sudo pip install sphinx_bootstrap_theme

El archivo conf.py localizado en el subdiretorio source/ ya contiene la configuracion correcta
para usar el tema y ha sido personalizado para usar un poco los colores que el proyecto NetBSD
usa.

2.- Para construir la documentacion necesitas gmake (GNU make), NetBSD usa make (BSD make o nbmake) 
la documentacion incluye un Makefile para automatizar el proceso.





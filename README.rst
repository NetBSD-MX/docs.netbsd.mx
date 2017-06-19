Documentacion en español sobre el Sistema Operativo NetBSD.
==========================================================

El siguiente proyecto fue motivado por amigos aficionados y usuarios del
sistema Operativo NetBSD.

La documentacion esta escrita en formato .rst (Restructured Text Format) y generada
con Sphynx, si deseas colaborar, ten en cuenta lo siguiente:

1. Python 2.7+ o 3.x debe trabajar. 
2. pip (python package manager ) Si tienes Python 2.7.9 en adelante, seguro ya esta instalado.
3. sphinx *http://www.sphinx-doc.org* (Software escrito en python para proyectos de documentacion.
4. Instalar el tema sphinx_bootstrap_theme.

::

  $ sudo pip install sphinx_bootstrap_theme

5.- clonar los fuentes de la documentacion ubicados en Github

::
  $ git clone https://github.com/NetBSD.MX/docs.netbsd.mx.git


El archivo conf.py localizado en el subdiretorio source/ ya contiene la configuracion correcta
para usar el tema y ha sido personalizado para usar un poco los colores que el proyecto NetBSD
usa.

Sphynx usa Gmake para generar el sitio, si usas NetBSD tendras que instalarlo por separado, NetBSD usa make y bmake.

Asegurate de comentar los cambios para conocer los aportes.

Aqui hay una guía sobre la estructura del archivo .RsT *http://docutils.sourceforge.net/rst.html*

Gracias.






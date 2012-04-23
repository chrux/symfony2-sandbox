symfony2-sandbox
================

Plantilla para proyectos con PHP (v.5.3.8+) + Symfony2 (Standard Edition sin vendors v.2.0.12)

Para una explicación más detallada de Symfony2 ver:
[Libro de Symfony](http://symfony.com/doc/current/book/index.html)

1) Bundles
----------

Este paquete viene pre-configurado con los siguientes bundles:

*Symfony Standard Edition*

``FrameworkBundle``  
``SensioFrameworkExtraBundle``  
``DoctrineBundle``  
``TwigBundle``  
``SwiftmailerBundle``  
``MonologBundle``  
``AsseticBundle``  
``JMSSecurityExtraBundle``  
``WebProfilerBundle (en dev/test env)``  
``SensioDistributionBundle (en dev/test env)``  
``SensioGeneratorBundle (en dev/test env)``  
``AcmeDemoBundle (en dev/test env)``  

*Extras*

``DoctrineFixturesBundle (en dev/test env)``  
``DoctrineMigrationsBundle (en dev/test env)``
``SonataAdminBundle``
``SonataDoctrineORMAdminBundle``
``SonataBlockBundle``
``SonataCacheBundle``
``SonatajQueryBundle``
``KnpMenuBundle``
``FOSUserBundle``
``SonataUserBundle``
``SonataEasyExtendsBundle (end dev/test env)``
``LiipImagineBundle``

2) Instalación
--------------

Una vez que hallas bajado el repo, la instalación es fácil y básicamente involucra
la verificar si tu sistema esta listo para Symfony2.

### a) Chequear la configuración del Sistema

Antes de comenzar, asegurate de tener tu sistema configurado a como es debido
para Symfony2. Para hacer esto, ejecuta el siguiente comando:

    php app/check.php

Si obtienes algún advertencia o recomendación, corrigela primero antes de proseguir.

### b) Instala las librerias Vendor

Para ello ejecuta el siguiente comando:

    php bin/vendors install

Nota que tu *debes* tener git instalado y ser capaz de ejecutar el comando git
para poder ejecutar este script, de lo contrario no podras instalarlo ni bajar
las librerias

### c) Establece los permisos

1. Utilizando ACL en sistemas que soportan chmod +a

    rm -rf app/cache/* app/logs/*
    sudo chmod +a "www-data allow delete,write,append,file_inherit,directory_inherit" app/cache app/logs web/media/cache
    sudo chmod +a "`whoami` allow delete,write,append,file_inherit,directory_inherit" app/cache app/logs web/media/cache

2. Utilizando ACL en sistemas que no soportan chmod +a

    sudo setfacl -R -m u:www-data:rwx -m u:`whoami`:rwx app/cache app/logs web/media/cache
    sudo setfacl -dR -m u:www-data:rwx -m u:`whoami`:rwx app/cache app/logs web/media/cache

``Nota: www-data es el usuario que utiliza apache. Para saber más busca la guía de [instalación](http://symfony.com/doc/current/book/installation.html) en sitio web de Symfony``

### d) Aceso a la aplicación ai través del Navegador Web

Debes colocar la instalación en una carpeta accesible por el servidor web,
es decir colocarla dentro de la raíz del directorio web, luego de esto tu debes
ser capaz de acceder a la versión web de los requerimientos mediante el chequeo
de la siguiente dirección web:

    http://localhost/Symfony/web/config.php

Aquí tu puedes usar el configurador web al hacer click en el enlace de 
"Configure your Symfony Application online" que nos enviara a la página
``config.php``.

Disfrutalo! :D

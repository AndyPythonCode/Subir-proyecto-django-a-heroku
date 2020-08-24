# Subir-proyecto-django-a-heroku
## Despliegue en heroku:

### Se necesita:

1. __git__ 
    * administrador de versiones.
    
2. __heroku cli__
    * hacer cambios a heroku.
    
3. __gunicorn__ 
    * servidor en el que va a correr.
    
4. __whitenoise__
    * ir a buscar los archivos estaticos.
    
5. __django-heroku__
    * configura automáticamente.


### Configuraciones en django.seeting:
- __import django_heroku__
   * El paquete django-heroku configura automáticamente su aplicación Django para que funcione en Heroku.
- __STATIC_ROOT = Path.joinpath(BASE_DIR, 'staticfiles')__
   * La carpeta que iran todos los archivos estaticos.
- __STATICFILES_DIRS = (Path.joinpath(BASE_DIR, 'static'),)__
   * Archivos estaticos adicionales.

### Activate Django-Heroku.
- __django_heroku.settings(locals())__
   * configuraciones que pide heroku

### Archivos estaticos(Opcional).
Django no admite el servicio de archivos estáticos en producción. Sin embargo, el fantástico proyecto WhiteNoise puede integrarse en su aplicación Django y fue diseñado exactamente con este propósito en mente. A continuación, instale WhiteNoise en su aplicación Django. Esto se hace en settings.pyla sección de middleware (en la parte superior):
* settings.py
    * 'whitenoise.middleware.WhiteNoiseMiddleware',

### Ve a tu proyecto
1. __Web: gunicorn myapp.wsgi__
    * Crea un archivo con ese nombre Procfile.
2. __pip freeze >requirements.txt__
    * Guarda todos los paquetes instalados en un txt.
3. __git init__
    * Crear un repositorio.
4. __git add__
    * guardar los cambios.
5. __git commit m- "Mensaje que deseas"__
    * Salvar el proyecto.

### Subir proyecto a heroku
#### Usare visual studio code:
1. __Crear una cuenta en heroku__
    * Poder utilizar el servicio en la nube.
2. __heroku login__
    * sincronizar tu cuenta con tu git.
3. __heroku create app_name__
    * Dominio.
4. __git push heroku master__ 
    * subir git a heroku.
5. __heroku run python manage.py migrate__
    * hacer migracion de tu base de datos en heroku.
6. __heroku open__
    * ver pagina.

### Comandos adicionales(Opcional)
- __heroku run python manage.py createsuperuser__
   * Crear un usuario para la base de datos con todos los privilegios.

> Andy Juan Arciniega.

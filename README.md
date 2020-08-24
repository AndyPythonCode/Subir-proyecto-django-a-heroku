# Subir-proyecto-django-a-heroku
****Despliegue en heroku:****

***Se necesita:
-git 
    ---------> administrador de versiones
-heroku cli 
    ---------> hacer cambios a heroku
-gunicorn 
    ---------> servidor en el que va a correr
-whitenoise 
    ---------> ir a buscar los archivos estaticos
-django-heroku 
    ---------> configura automáticamente

**Configuraciones en django.seeting**
import django_heroku ----> El paquete django-heroku configura automáticamente su aplicación Django para que funcione en Heroku
#STATIC_ROOT = Path.joinpath(BASE_DIR, 'staticfiles') ----> la carpeta que iran todos los archivos estaticos
#STATICFILES_DIRS = (Path.joinpath(BASE_DIR, 'static'),) ----> archivos estaticos adicionales
# Activate Django-Heroku.
django_heroku.settings(locals()) ----> configuraciones que pide heroku

**Archivos estaticos(Opcional)**
Django no admite el servicio de archivos estáticos en producción. Sin embargo, el fantástico proyecto WhiteNoise puede integrarse en su aplicación Django y fue diseñado exactamente con este propósito en mente. A continuación, instale WhiteNoise en su aplicación Django. Esto se hace en settings.pyla sección de middleware (en la parte superior):
settings.py
      -----> 'whitenoise.middleware.WhiteNoiseMiddleware',

**Ve a tu proyecto**
1-Crea un archivo con ese nombre Procfile --> Web: gunicorn myapp.wsgi
2-Guarda todos los paquetes instalados en un txt --> pip freeze >requirements.txt
3-Crear un repositorio: git init
4-guardar los cambios: git add .
5-Salvar el proyecto: git commit m- "Mensaje que deseas"

**Subir proyecto a heroku**
1-Crear una cuenta en heroku
-Usare visual studio code:
2-heroku login ---> sincronizar tu cuenta con tu git
3-heroku create app_name --->Dominio
4-git push heroku master ----> subir git a heroku
5-heroku run python manage.py migrate ---> hacer migracion de tu base de datos en heroku 
6- heroku open ---->ver pagina

**Comandos adicionales(Opcional)**
-heroku run python manage.py createsuperuser

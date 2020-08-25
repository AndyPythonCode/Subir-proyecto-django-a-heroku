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
- __ALLOWED_HOSTS = ['URL','LOCALHOST']__
   * Decirle a django cuales host estan permitidos, el url lo veremos mas abajo... tambien puedes escribir '*' para decirle que todos.
   
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

### Usar PostgreSql
- __Ojo__: Heroku Postgres es un servicio de base de datos SQL administrado proporcionado directamente por Heroku. Puede acceder a una base de datos de Heroku Postgres desde cualquier idioma con un controlador PostgreSQL, incluidos todos los idiomas admitidos oficialmente por Heroku.

- Ir a tu app en heroku, luego ir a setting y presionar 'reveal config vars' y copiar DATABASE_URL ya que es por defecto de heroku.

</br>

DATABASES = {

</br>

     'default': {
        - 'ENGINE': 'django.db.backends.postgresql',
        - 'NAME': 'd79emu3263ip2s',
        - 'HOST': 'ec2-54-234-28-165.compute-1.amazonaws.com',
        - 'PORT': '5432',
        - 'USER': 'esizurvhlzmibt',
        - 'PASSWORD': 'b4707d197279836d97a1f9d0c2f5d5fd778185080535a80995655f189c460b53',
     }

</br>

 }
 
- __PostgresSQL__ ://__USER__(esizurvhlzmibt):__PASSWORD__(b4707d197279836d97a1f9d0c2f5d5fd778185080535a80995655f189c460b53)
@__HOST__(ec2-54-234-28-165.compute1.amazonaws.com):__PORT__(5432)/__NAME__:( d79emu3263ip2s)


### Comandos adicionales(Opcional)
- __heroku run python manage.py createsuperuser__
   * Crear un usuario para la base de datos con todos los privilegios.
- __heroku ps__
   * Lista de dynos para una app.
- __heroku ps:stop run.4859__
   * Detener dynos corriendo.

> Andy Juan Arciniega.

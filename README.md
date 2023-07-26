# Tumblr_Scrapper
Script de web scrapping que usa Scrapy y Selenium para obtener nombres de usuarios texto de los post principales y su correspondiente url de un blog de tumblr.

#################################################
#------------------INSTALACION------------------#
#################################################

1) Descargar (clonar) el archivo del repositorio de github
2) Crea un entorno virtual y activalo
3) Ahora instala los paquetes del archivo requirements.txt con el comando:

	pip install -r requirements.txt

4) Ahora desplazate hacia la carpeta tumblr_scrapper que contiene el spider de scrapy

	cd \tumblr_scrapper\tumblr_scrapper

5) Para ejecutar el script, necesitas introducir un comando en la terminal del siguiente modo:

	scrapy crawl tumblr -a email="email" -a password= -a url='url' -a iterations=n -o output_name.jsonl
	donde:
        # email: Es el correo electronico asociado a nuestra cuenta de tumblr
        # password: Es la contraseña asociada al correo de nuestra cuenta de tumblr
        # url: Es la url del blog de tumblr que se desea scrapear
        # iterations: Es la cantidad de contenido que cargara por cada scroll down para Scrapear (Tumblr carga contenido de forma dinamica, 	  para ello hay que hacer scroll down a atraves del blog)
	# output_name: Nombre del archivo jsonl o csv 


#################################################
#----------------CONSIDERACIONES----------------#
#################################################

1) La velocidad de este web_scrapping dependera de cuantas iteraciones se use, por lo general 30 iteraciones tardaran 20 minutos.
   Esto se debe al uso de selenium por la naturaleza dinamica de la pagina, la cual solo carga los links de las publicaciones cuando
   interactuas con los botones.

2) No es posible scrapear todo tipo de blog de tumblr, solo funciona con blogs de estilo estandar. Una buena forma de diferenciarlo es en
   base al url como s emuestra a continuacion:

   https://www.tumblr.com/hearttattack (Pagina estandar - SI se puede Scrapear)

   https://sleep-sounds-nice-rn.tumblr.com (Pagina personalizada - NO se puede Scrapear)


<h1 align="center"> Proyecto DNS en máquina virtual linux </h1>

## Antes de empezar
Lo primero es ir a git y crear un nuevo repositorio. Después de esto, creamos nuestro nuevo proyecto en el Code. Una vez listo esto, creamos también un nuevo proyecto en Git y lo asociamos al repositorio creado anteriormente. 

## Bind9
Entonces instalamos bind9 en nuestra máquina virtual con lo siguiente:

```
$ sudo apt install bind9
```

## Configuración nades.conf.local
Lo que haremos en este apartado es configurar poniendo esto:
```
`zone "asircastelao.int" { type master; file "/var/lib/bind/db.asircastelao.int"; allow-query { any; }; };``
```
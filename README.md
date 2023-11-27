
<h1 align="center"> Proyecto DNS en máquina virtual linux </h1>

## Antes de empezar
Lo primero es ir a git y crear un nuevo repositorio. Después de esto, creamos nuestro nuevo proyecto en el Code. Una vez listo esto, creamos también un nuevo proyecto en Git y lo asociamos al repositorio creado anteriormente. 

## Bind9
Entonces instalamos bind9 en nuestra máquina virtual con lo siguiente:

```
$ sudo apt install bind9
```

## Configuración named.conf.local
Lo que haremos en este apartado es entrar en:

```
$ sudo nano /etc/named.conf,local
```

para configurar poniendo esto:
```
`zone "asircastelao.int" { type master; file "/var/lib/bind/db.asircastelao.int"; allow-query { any; }; };``
```

## Configuración named.conf.options
Lo mismo:

```
$ sudo nano /etc/named.conf,local
```

para configurar poniendo esto:

```


`options { directory "/var/cache/bind";

forwarders {
 	8.8.8.8;
	1.1.1.1;
 };
 forward only;

listen-on { any; };
listen-on-v6 { any; };

allow-query {
	any;
};

};`
```


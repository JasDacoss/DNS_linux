
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

## db.asircastelao.int
Lo que haremos en este apartado es crear una zona con este nombre y añadir lo siguiente:

```

    @		IN SOA	ns.asircastelao.int. some.email.address. ( - 17161016   ; serial - 10800      ; refresh (3 hours) - 3600       ; retry (1 hour) - 604800     ; expire (1 week) - 38400      ; minimum (10 hours 40 minutes) ) @		IN NS	ns.asircastelao.int. ns		IN A 	172.28.5.1 test	IN A	172.28.5.4 wwww    IN A    172.28.5.7 alias	IN CNAME  test texto   IN TXT 	mensaje

```

# Comercio

Esta página proveerá una muy rápida introducción de cómo interpretar los términos usandos por el DEX y como los pares del comercio son presentados.

## Pares

En BitShares, casi cualquier activo puede ser intercambiado con todos los demás activos. Una vez que hayamos escogido dos activos, usualmente preferimos usar el término *emparejamiento de mercado*. Por ejemplo, podemos intercambiar USD con EUR en un emparejamiento USD:EUR.

Buscando consistencia, utilizaremos los términos generalizados *base* y *cotización* para que los pares sean representados de la forma

    *cotización* : *base*
    

y por ejemplo con la *base* siendo USD y la *cotización* EUR se denota el emparejamiento EUR:USD.

## Libros de Órdenes

El libro de orden consiste en un lado de *demanda* y un lado de *oferta*. Ya que los emparejamientos de comercio no tienen una orientación preferida, la siguiente tabla demuestra una visión de la oferta/demanda y las correspondientes operaciones de compra/venta para cada lado:

| Lado          | Venta        | Compra       |
| ------------- | ------------ | ------------ |
| Demanda       | *cotización* | *base*       |
| Oferta        | *base*       | *cotización* |
| \---\---\---- | \---\----    | \---\----    |

Obviamente, lo que esté en lado de ofertas en emparejamientos USD:EUR estará en el lado de demandas en el emparejamiento EUR:USD. Desde luego los precios son representados internamente como fracciones, por lo tanto ambos pares resultan idénticos.

## Comercio

Para publicar una orden de comercio, se requiere llenar un formulario en cualquiera de los dos lados de *demanda* u *oferta* (respectivamente, el lado *compra* o *venta*). Usted debe definir un *precio* y una *cantidad* para comprar/vender. El costo de esta orden será calculado automáticamente. Nótese que habrá una cuota adicional requerida para realmente publicar la orden.

Once the order is filled (i.e. someone sold/bought your offer), your account will be credited by the corresponding asset.

Unfilled orders can be canceled at any time.
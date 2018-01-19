# Comercio

Esta página proveerá una muy rápida introducción de cómo interpretar los términos usandos por el DEX y como los pares del comercio son presentados.

## Pares

En BitShares, casi cualquier activo puede ser intercambiado con todos los demás activos. Una vez que hayamos escogido dos activos, usualmente preferimos usar el término *emparejamiento de mercado*. Por ejemplo, podemos intercambiar USD con EUR en un emparejamiento USD:EUR.

Buscando consistencia, utilizaremos los términos generalizados *base* y *cita* para que los pares sean representados de la forma

    *cita* : *base*
    

and for instance with *base* being USD and *quote* being EUR, denote the EUR:USD pair.

## Order Books

The order book consists of an *ask* and a *bid* side. Since trading pairs do not have a preferred orientation, and can be flipped, the following table shall give an overview of ask/bid and the corresponding buy/sell operations for each side:

| Side          | Sell      | Buy       |
| ------------- | --------- | --------- |
| Ask           | *quote*   | *base*    |
| Bid           | *base*    | *quote*   |
| \---\---\---- | \---\---- | \---\---- |

Obviously, what is on the bid side of the USD:EUR pair will be on the ask side on the EUR:USD pair. Of course prices are internally represented as fractions, and thus results in both pairs being identical.

## Trading

To place a trading order, it is required to fill the form on either the *ask* or the *bid* side (respectively, *buy* or *sell* side). You will need to define a *price* and an *amount* to sell/buy. The cost for this order will be calculated automatically. Note that there will be an additional fee required to actually place the order.

Once the order is filled (i.e. someone sold/bought your offer), your account will be credited by the corresponding asset.

Unfilled orders can be canceled at any time.
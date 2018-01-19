# Venta Corta de BitActivos

Para incrementar su exposición a BTS y ofrecer liquidez a los BitActivos, tal como USD, EUR, GOLD, etc. usted puede *pedir prestado* este bitActivo de la red y *vender acciones por adquirir*. Aquí describiremos brevemente el procedimiento.

## Pedir Prestado

La red BitShares es capás de emitir cualquier cantidad de BitActivo y prestarla a participantes dado que haya suficiente colateral.

- *precio de liquidación*: El precio de 1 BTS tal como es negociado en mercados de intercambio externos.
- *relación colateral de mantenimiento* (MCR - maintenance collateral ratio): Una relación definida por los testigos que describe el mínimo requerido de proporción con colaterales
- *máxima relación de contracción alcista* (MSQR - maximum short squeeze ratio): Una relación definida por los testigos que define que tanto se protegen los cortos ante contracciones altistas
- *protección a contracción altista* (SQP - short squeeze protection): Define lo máximo que se obligará a una posición de margen a pagar para cubrir 
- *call price* (CP): The price at which short/borrow positions are margin called

### Margin Call

The BitShares network is capable of margin calling those positions that do not have enough collateral to back their borrowed bitAssets. A margin call will occur any time the highest bid is less than the *call price* and greater than *SQP*. The margin position will be forced to sell its collateral anytime the highest offer to buy the collateral is less than the call price (x/BTS).

    SQP = settlement price / MSQR
    call price = DEBT / COLLATERAL * MCR
    

The margin call will take the collateral, buy shares of borrowed bitAsset at market rates up to the SQP and close the position. The remaining BTS of the collateral are returned to the customer.

### Precio de Liquidación

Los poseedores de cualquier bitActivo pueden solicitar una liquidación a un *precio justo* en cualquier momento. La liquidación cierra las posiciones de prestamo/corto con la menor relación de colateral y vende el colateral para la liquidación.

## Vender

Después de pedir prestado bitActivos, estos pueden ser vendidos sin costo en cualquiera de los mercados correspondientes a cualquier precio que un comprador esté dispuesto a pagar. With this step, the short-selling is now complete and you are short that particular bitAsset.

## Updating Collateral Ratio

At any time, the holder of a borrow/short position can modify the collateral ratio in order to flexibly adjust to market behavior. If the collateral ratio is increase, an additional amount of BTS is locked as collateral, while reducing the collateral ratio will require an amount of the corresponding BitAsset to be payed back to the network.

## Covering

To close a borrow/short position, one must hold the borrowed amount of that particular bitAsset to hand it over to the BitShares network. After that, the BitAssets are reduced from the corresponding supply and the collateral is released and given back to its owner.
## Servicios de gateway y de puente

Ambos, los puentes y los gateways, le permiten depositar y retirar monedas, pero hay una diferencia entre la cantidad de confianza que debe colocar en los proveedores de servicio.

### Puentes: modelo libre de confianza

Un servicio de puente provee una ruta para depositar una cantidad de una criptomoneda diferente a BitShares, y en su lugar recibir su equivalente en SmartCoin. Las SmartCoins no poseen riesgo por contraparte, por lo que el único riesgo que usted puede experimentar al usar un puente es durante el pequeño tiempo que tarda en completarse la transferencia. Esto resulta mejor que un mercado de intercambios tal como Poloniex, donde usted siempre afronta el riesgo de que el mercado de intercambios centralizado sea "hackeado" o caiga en quiebra, entre otros problemas que puede experimentar.

### Gateways: modelo basado en confianza

Gateways are basically equivalent to the standard exchange model where you depend on the solvency of the exchange to be able to redeem your coins. Generally gateways issue assets prefixed with their symbol, like OPEN, TRADE, or META. These assets are backed 100% by the real BTC or ETH or any other coin that people deposit with the gateways.

An OPEN.BTC is thus in theory equivalent to the BTC you get on Poloniex, which could be prefixed POLO.BTC. In both cases you rely on the service provider, CCEDK for OPEN. assets and Poloniex for POLO. assets, to remain solvent in order to back the value of the assets they've issued. Because gateways only provide this one service which is normally only one part of running an exchange, one might even argue that they have an easier job of securing their holdings.
# Permisos

En BitShares, cada cuenta está separada en

* **Permiso Activo**: control sobre sus fondos y
* **Permiso de Propietario**: control sobre la cuenta.

Ambos pueden ser definidos en la pestaña `Permisos` de su cuenta usando la llamada *autoridades* (ver abajo) en conjunto al llamado *umbral* que debe ser excedido para que una transacción sea válida.

## Autoridades

En BitShares una *autoridad* consiste en una de muchas entidades que autorizan una acción, así como transferencias o intercambios.

Una autoridad consiste en uno de varios pares de un nombre de cuenta con una *relevancia*.

Para obtener una transacción válida, la suma de las relevancias de las partes firmantes debe exceder el umbral como se ha definido en los permisos.

# Ejemplos

Discutams algunos ejemplos para aclarar en la terminología utilizad y los casos de uso. Asumimos que una nueva cuenta es creada con sus permisos activos ajustados de la forma descrita a continuación. ¡Note que el mismo esquema también funciona para los permisos de propietario!

## Firma Múltiple (Simple)

Un esquema de firma múltiple simple está compuesto por `M` entidades de las cuales `N` deben firmar para que la transacción sea válida. Ahora, en BitShares, tenemos *relevancias* y un *umbral* en lugar de `M` y `N`. Aun así podemos alcanzar el mismo fin con incluso más flexibilidad como ahora veremos.

Asumamos, Alicia, Roberto, Carlos y Daniel tienen fondos comunes. Queremos ser capaces de construir una transacción válida si solo dos de ellos están de acuerdo. Entonces un esquema **2-de-4** (N-de-M) se puede ver de la forma:

| Cuenta        | Relevancia |
| ------------- | ---------- |
| Alice         | 33%        |
| Bob           | 33%        |
| Charlie       | 33%        |
| Dennis        | 33%        |
| \---\---\---- | \---\---   |
| Umbral:       | 51%        |

Los cuatro participantes tienen una relevancia del 33% pero el umbral está establecido en 51%. Entonces solo dos de los cuatro deben estar de acuerdo para validar la transacción.

Alternativamente, para construir un esquema 3-de-4, podemos o disminuir las relevancias a 17 o incrementar el umbral a 99%.

## Firma Múltiple Flexible (Simple)

Con los umbrales y relevancias, podemos ahora tener más flexibilidad sobre nuestros fondos, o más precisamente, tenemos más *control*. Por ejemplo, podemos tener relevancias separadas para diferentes personas. Asumamos que Alice desea asegurar aquí fondos en contra de robos a través de un esquema de firma múltiple pero ella no desea ceder demasiado control a sus amigos. Por lo tanto, creamos una autoridad similar a:

| Cuenta        | Relevancia |
| ------------- | ---------- |
| Alice         | 49%        |
| Bob           | 25%        |
| Charlie       | 25%        |
| Dennis        | 10%        |
| \---\---\---- | \---\---   |
| Umbral:       | 51%        |

Ahora los fondos pueden ser accedidos por Alice y tan solo un amigo o por los tres amigos en conjunto.

## Firma Múltiple Flexible de Jerarquía Múltiple

Echemos un vistazo a un ajuste de cuenta corporativo de jerarquía múltiple simple. Estamos observando a una compañía que tiene un Director de Finanzas (CFO) y a algunos departamentos trabajando para él, así como el Tesorero, el Controlador, el gerente de impuestos, el contador, etc. La compañía tambien tiene un CEO que desea tener privilegios para gastos. Por lo tanto construimos una autoridad para los fondos de acuerdo a:

| Cuenta        | Relevancia |
| ------------- | ---------- |
| CEO.COMPAÑÍA  | 51%        |
| CFO.COMPAÑÍA  | 51%        |
| \---\---\---- | \---\---   |
| Umbral:       | 51%        |

whereas CEO.COMPANY and CFO.COMPANY have their own authorities. For instance, the CFO.COMPANY account could look like:

| CFO.COMPANY               | Weight   |
| ------------------------- | -------- |
| Chief.COMPANY             | 51%      |
| Treasurer.COMPANY         | 33%      |
| Controller.COMPANY        | 33%      |
| Tax Manager.COMPANY       | 10%      |
| Accounting.COMPANY        | 10%      |
| \---\---\---\---\---\---- | \---\--- |
| Threshold:                | 51%      |

This scheme allows:

* the CEO to spend funds
* the Chief of Finance Officer to spend funds
* Treasurer together with Controller to spend funds
* Controller or Treasurer together with the Tax Manager and Accounting to spend funds.

Hence, a try of arbitrary depth can be spanned in order to construct a flexible authority to reflect mostly any business use-case.
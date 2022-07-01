---
title: Introducción
description: Introducción a cfdi API
layout: ../../layouts/MainLayout.astro
---
**¡Bienvenido a cfdi API!**

Nuestra api te permite conocer el estatus de las facturas emitidas por el SAT MX haciendo una consulta a nuestro servicio con la siguiente información:

- ✅ **RFC del emisor**
- ✅ **RFC del receptor**
- ✅ **Monto total**
- ✅ **Folio fiscal**

Nosotros nos encargamos de la conexión con el webservice y te regresamos una respuesta en un JSON
## Comencemos

Simplificamos todo y con una petición `GET` puedes obtener es status de tus facturas.

✍️ Ejemplo:

`https://www.cfdiapi.com/api/estatus/RTU111018SV3/OEE0508161P7/34800.00/49E87987-F780-42B2-AA23-4385D7CA1D75`

✔️ Valores:

- https://www.cfdiapi.com/api/estatus/ ⬅️ **URL base**
- RTU111018SV3 ⬅️ **RFC del emisor**
- OEE0508161P7 ⬅️ **RFC del receptor**
- 34800.00 ⬅️ **Total con centavos**
- 49E87987-F780-42B2-AA23-4385D7CA1D75 Folio fiscal ⬅️ **Folio fiscal**

‼️ Importante

Los datos se deben enviar en el orden descrito separados por `/` de lo contrario recibirás un mensaje de error.

👌 Respuesta satisfactoria:

  ```json
{
    "s:Envelope": {
        "_attributes": {
            "xmlns:s": "http://schemas.xmlsoap.org/soap/envelope/"
        },
        "s:Body": {
            "ConsultaResponse": {
                "_attributes": {
                    "xmlns": "http://tempuri.org/"
                },
                "ConsultaResult": {
                    "_attributes": {
                        "xmlns:a": "http://schemas.datacontract.org/2004/07/Sat.Cfdi.Negocio.ConsultaCfdi.Servicio",
                        "xmlns:i": "http://www.w3.org/2001/XMLSchema-instance"
                    },
                    "a:CodigoEstatus": {
                        "_text": "S - Comprobante obtenido satisfactoriamente."
                    },
                    "a:EsCancelable": {
                        "_text": "Cancelable con aceptaciÃ³n"
                    },
                    "a:Estado": {
                        "_text": "Vigente"
                    },
                    "a:EstatusCancelacion": {

                    },
                    "a:ValidacionEFOS": {
                        "_text": "200"
                    }
                }
            }
        }
    }
}
```

Happy hacking. 🧑‍🚀

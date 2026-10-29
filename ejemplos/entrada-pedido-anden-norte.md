# Caso AN-031 — entrada ficticia y revisión parcial

**Todos los nombres, folios, mercancías y valores son FICTICIOS de Andén Norte.** No es un CFDI válido, no se envía al SAT ni sirve para circular. Fecha simulada de viaje: 2026-10-30. Fecha de revisión: 2026-10-29.

Solicitud: «Revisa esta proyección del borrador antes de timbrar, crúzala con pedido y empaque y prepara el mensaje al transportista. No cambies el archivo».

Contexto declarado por el cliente: autotransporte federal nacional remunerado, tipo `I` propuesto por el emisor; dos entregas. No se solicita decidir obligación/exención. No se aportan catálogos ni esquema. No se ha confirmado la vigencia normativa a la fecha del viaje.

Los tres documentos tienen versión 1. El empaque muestra **peso total de cada renglón**, no peso unitario. Una caja pesa 10 kg en este caso ficticio. El emisor confirma que A y B se mapearán a exactamente **dos** nodos Mercancia, sin subdivisión.

## Documento P: pedido AN-031-v1, responsable cliente

| Fila | Producto | Cantidad solicitada | Unidad |
|---|---|---:|---|
| P1 | A, piezas de cartón de demostración | 10 | caja |
| P2 | B, separadores de demostración | 5 | caja |

## Documento E: lista de empaque AN-031-v1, responsable cliente

| Fila | Producto | Cantidad preparada | Unidad | Peso total del renglón (kg) | Nodo propuesto |
|---|---|---:|---|---:|---|
| E1 | A | 10 | caja | 100.00 | Mercancia[1] |
| E2 | B | 4 | caja | 40.00 | Mercancia[2] |

## Documento B: proyección del borrador AN-031-v1, responsable emisor/transportista

Son **campos seleccionados**, no el XML completo. La lista de ubicaciones y mercancías sí es completa para las sumas indicadas. `NumLicencia` está **confirmado ausente** en la figura 01; el resto de campos no mostrados se considera **no aportado**, nunca ausente por omisión en esta muestra.

| Localizador B | Campo | Valor |
|---|---|---|
| B1 | Comprobante/Version | 4.0 |
| B2 | Comprobante/TipoDeComprobante | I |
| B3 | CartaPorte/Version | 3.0 |
| B4 | CartaPorte/TranspInternac | No |
| B5 | CartaPorte/Mercancias: modo registrado | Autotransporte, único modo |
| B6 | CartaPorte/TotalDistRec | 160.00 km |
| B7 | Ubicacion[1]/TipoUbicacion; IDUbicacion | Origen; OR000001 |
| B8 | Ubicacion[2]/TipoUbicacion; IDUbicacion; DistanciaRecorrida | Destino; DE000001; 100.00 km |
| B9 | Ubicacion[3]/TipoUbicacion; IDUbicacion; DistanciaRecorrida | Destino; DE000002; 50.00 km |
| B10 | Mercancias/PesoBrutoTotal | 150.00 kg |
| B11 | Mercancias/NumTotalMercancias | 3 |
| B12 | Mercancia[1]: producto; Cantidad; PesoEnKg | A; 10 cajas; 100.00 kg |
| B13 | Mercancia[2]: producto; Cantidad; PesoEnKg | B; 4 cajas; 40.00 kg |
| B14 | FiguraTransporte/TiposFigura[1]/TipoFigura | 01 |
| B15 | FiguraTransporte/TiposFigura[1]/NumLicencia | atributo ausente, confirmado por emisor |

No se aportan RFC, domicilios, fechas/horas del borrador, conceptos/importes/moneda, peligrosidad/claves sanitarias, configuración, seguros, placas, permisos ni validación externa. Que no aparezcan aquí **no demuestra** que falten en el XML. Pedirlos agrupados como insumos pendientes; no generar un rechazo fiscal por cada campo omitido en la proyección.

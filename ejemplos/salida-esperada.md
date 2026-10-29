# Caso AN-031 — resultado esperado y comprobación manual

**Datos FICTICIOS de Andén Norte.** Revisión 2026-10-29 de documentos P/E/B v1, viaje simulado 2026-10-30. Modo: borrador parcial, autotransporte nacional remunerado, tipo I propuesto. **CON HALLAZGOS e INCOMPLETO**: no hay dictamen de obligación ni validación integral de CFDI/XML. Fuentes: matriz SAT y FAQ consultadas el 2026-10-29; la FAQ cita fundamentos de 2024.

## Hallazgos

Prioridad interna de H1–H5: corregir antes de enviar al certificador. H6: confirmar cantidad con cliente antes de modificar documentos. No es una clasificación de gravedad del SAT.

| ID | Estado | Campo y evidencia recibida | Esperado o cuenta | Regla SAT y fuente/fecha | Acción | Responsable propuesto |
|---|---|---|---|---|---|---|
| H1 | INCUMPLIMIENTO OBSERVADO | B3, CartaPorte/Version = 3.0 | 3.1 | CP115, matriz SAT, fila NUM 15; consulta 2026-10-29 | Pedir nueva versión del borrador conforme a CCP 3.1; revisar sus dependencias, no solo cambiar una etiqueta | Emisor/transportista |
| H2 | INCUMPLIMIENTO OBSERVADO | B6 = 160 km; B8/B9, destinos = 100 y 50 km | 100 + 50 = 150 km; diferencia declarada menos suma = +10 km | CP126, matriz SAT, NUM 26; consulta 2026-10-29 | Confirmar distancias de los tramos y conciliar total; no imponer 150 km como ruta real sin confirmación | Emisor/transportista |
| H3 | INCUMPLIMIENTO OBSERVADO | B10 = 150 kg; B12/B13 = 100 y 40 kg | 100 + 40 = 140 kg; diferencia = +10 kg | CP149, matriz SAT, NUM 49; consulta 2026-10-29 | Confirmar pesos y cantidad de B; conciliar total contra los nodos definitivos | Cliente confirma carga; emisor corrige |
| H4 | INCUMPLIMIENTO OBSERVADO | B11 = 3; lista completa B12/B13 tiene dos nodos | Conteo = 2, no 3 | CP154, matriz SAT, NUM 54; consulta 2026-10-29 | Confirmar agregación final y corregir conteo | Emisor/transportista |
| H5 | INCUMPLIMIENTO OBSERVADO | B14 = 01; B15 confirmado ausente | Debe existir NumLicencia para operador 01 | CP196, matriz SAT, NUM 96; consulta 2026-10-29 | Aportar número de licencia del operador al emisor; después verificar patrón y evidencia aplicable, sin afirmar vigencia por presencia | Transportista |
| H6, OP-01 | INCONSISTENCIA OPERATIVA | P2 solicita 5 cajas B; E2 y B13 indican 4 | Diferencia preparado menos pedido = -1 caja; confirmar carga efectiva | Regla SAT: no determinada; cruce P2/E2/B13, sin código CP | Confirmar entrega parcial o corregir empaque/borrador con evidencia. No cambiar 4 a 5 automáticamente | Cliente; transportista confirma lo cargado |

[Texto íntegro de reglas](../references/matriz-errores-ccp-31.md). No se atribuye H6 a CP154: contar nodos no es contar cajas. La lista de empaque y los nodos coinciden en 140 kg, pero el total declarado del borrador no coincide con sus propios nodos: eso sí permite H3.

## Cobertura sin hallazgo y pendientes

| Códigos | Resultado | Evidencia o dependencia |
|---|---|---|
| CP101 | Revisada sin hallazgo | B1, CFDI 4.0 |
| CP102, CP103, CP105, CP107, CP111 | No aplicables a las condiciones T de estas filas | B2 es I; no se afirma que todo el CFDI cumpla |
| CP114 | Revisada sin hallazgo para el tipo permitido | B2 = I |
| CP125 | Revisada sin hallazgo de existencia | B5 autotransporte, B6 tiene TotalDistRec; su suma falla en H2 |
| CP128, CP129 | No aplicables | B5 declara modo único autotransporte, sin ferroviario |
| CP130 | Revisada sin hallazgo | B7–B9: un origen y dos destinos |
| CP150, CP151, CP152 | No aplicables | B5 sin marítimo ni ferroviario |
| CP181 | NO VERIFICABLE | Sin marítimo debería omitirse DetalleMercancia; la proyección no acredita su ausencia |
| CP115, CP126, CP149, CP154, CP196 | Incumplimiento observado | H1–H5 |
| CP104, CP106, CP108–CP110, CP112–CP113 | NO VERIFICABLE | Moneda, conceptos/impuestos, RFC, complementos completos y listas no aportados |
| CP116–CP124, CP127 | NO VERIFICABLE | B4 nacional determina parte de las condiciones; no se aportó presencia/ausencia de los otros atributos/nodos ni condición de polos |
| CP131–CP148 | NO VERIFICABLE | Faltan ubicaciones completas, atributos condicionales, domicilios, catálogos, identificación fiscal, complementación de nodos; IDs presentes no prueban condición de CantidadTransporta |
| CP153, CP155–CP180 | NO VERIFICABLE | Faltan mercancías completas, peligrosidad, catálogos, valores/moneda, referencias de cantidades y presencia/ausencia de atributos aduanales/sanitarios |
| CP182–CP184 | NO VERIFICABLE | Peligrosidad, seguros y configuración/catálogo/remolques no aportados |
| CP185–CP192 | No aplicables | Reglas de modos marítimo/aéreo/ferroviario; B5 declara solo autotransporte |
| CP193, CP194 | Revisadas sin hallazgo de existencia | B14: existe figura y tipo 01; no acredita los demás datos |
| CP195, CP197–CP204 | NO VERIFICABLE | Identificación fiscal, residencia, domicilio y demás figuras no aportados |
| CP999 | Residual, no evaluable como prueba | No se usa para clasificar los faltantes de este caso |

Pendiente DOC-01: pedir borrador completo y sus documentos soporte, catálogos/esquemas oficiales aplicables y confirmación del emisor sobre obligación y vigencia normativa para el viaje. Las placas, póliza de responsabilidad civil y demás datos del vehículo no fueron compartidos: no se concluye que estén ausentes (FAQ Autotransporte 2–3, p. 28, fundamento de 2024, consultada 2026-10-29). Tampoco se comprobaron autenticidad de documentos, lista de RFC, requisitos generales CFDI 4.0, esquema XSD ni aceptación del certificador.

## Mensaje propuesto; no enviado

> Asunto: AN-031 — datos y borrador por conciliar antes de enviar al certificador
>
> Transportista Andén Norte: revisamos la proyección v1. Favor de devolver una nueva versión que atienda H1 (CCP 3.1, CP115), H2 (total 160 km frente a destinos que suman 150 km, CP126), H3 (total 150 kg frente a nodos que suman 140 kg, CP149), H4 (3 declaradas frente a 2 nodos, CP154) y H5 (falta confirmada del número de licencia del operador 01, CP196).
>
> Para H6 necesitamos que el cliente confirme si B saldrá con 4 o 5 cajas y ustedes confirmen lo cargado. No cambien cantidades ni pesos hasta conciliar esa evidencia. Si cambian, recalculen pesos y conteos. Envíen al emisor los datos del operador por el canal acordado, sin credenciales privadas.
>
> Para completar DOC-01, compartan el borrador completo y soporte de ruta, vehículo/remolques, permisos, seguros y figuras; el cliente debe completar mercancías y ubicaciones. El emisor debe confirmar las fuentes vigentes aplicables al viaje. Indiquen responsable y versión de cada corrección. Esta revisión es parcial y no constituye certificación ni autorización para circular.

## Cómo comprobarlo y cerrarlo a mano

1. Localizar CP115/126/149/154/196 en el Excel o Markdown y comprobar la condición y el atributo, antes de mirar el mensaje de error.
2. Sumar solo destinos: 100 + 50 = 150 km. El origen no añade distancia.
3. Sumar pesos de nodos: 100 + 40 = 140 kg. Son totales por renglón: no multiplicar de nuevo por 10 y 4 cajas.
4. Contar los dos nodos B12 y B13. Comparar 4 cajas preparadas con 5 pedidas por separado.
5. Confirmar B14=01 y ausencia explícita de B15. No confundir ausencia confirmada con los demás campos no aportados.
6. Si el cliente confirma entrega parcial de cuatro cajas B y transportista confirma distancias/pesos, una corrección candidata es Version=3.1, TotalDistRec=150, PesoBrutoTotal=140, NumTotalMercancias=2 y licencia documentada. Es una **candidata condicionada**, no un archivo listo para timbrar. Si confirma cinco cajas, rehacer cantidades/pesos con nueva evidencia: no usar esta candidata.
7. Guardar versión v2, fecha y responsable de cada confirmación. Repetir H1–H5 y cruces dependientes de H6, completar DOC-01 y mantener NO VERIFICABLE lo que siga sin evidencia. La presencia de licencia no cierra patrón/vigencia.

Pre-revisa, cruza y arma evidencia; no sustituye al contador, al agente aduanal ni al SAT, y no certifica ni timbra.

Basado en una skill de Heroldo Escobedo — heroldo.org

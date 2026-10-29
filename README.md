# Pre-revisor de Carta Porte 3.1

Convierte pedido, lista de empaque y borrador de CFDI 4.0 con Complemento Carta Porte en una tabla de correcciones con evidencia y regla SAT, más un mensaje que puedes copiar al transportista. Precio previsto del paquete empresarial: **USD 20**. Es un paquete de instrucciones para un asistente de IA; no incluye software de timbrado ni acceso al SAT.

Su valor está en cruzar documentos: separar un total mal sumado de una entrega parcial sin confirmar, pedir el dato al responsable correcto y dejar evidencia de qué se revisó. No promete aceptación del comprobante, ahorro medido ni eliminación de sanciones.

## Cómo usarlo

1. Sube `pre-revisor-carta-porte.zip` a tu asistente como skill (en claude.ai: Configuración → Capacidades → Skills → Subir) o conéctala desde Agensi. El ZIP ya trae la matriz y la FAQ del SAT, el ejemplo y la licencia; no hay que instalar, configurar ni mover nada.
2. Adjunta fecha del viaje, papel de las partes, modo/ruta, pedido, lista de empaque y datos de transporte/operador; si tienes borrador XML (o una parte), súmalo e indica su versión y qué no compartiste. No compartas llaves, contraseñas ni e.firma.
3. Pide la tabla, las cuentas, la cobertura de reglas y el mensaje al transportista; revísalo antes de enviarlo. El paquete no manda mensajes, no cambia documentos ni timbra.

El asistente debe poder leer Markdown o PDF; consultar fuentes nuevas requiere internet.

Solicitud sugerida:

> Usa pre-revisor-carta-porte para revisar este embarque antes de enviarlo al certificador. Cruza pedido, empaque y borrador; distingue faltantes documentales de incumplimientos observados, cita cada regla SAT con fuente y fecha, muestra cálculos y pendientes y prepara el mensaje al transportista. No inventes datos ni corrijas automáticamente el archivo.

## Qué recibes

- Tabla de faltantes e inconsistencias con localizador, evidencia, regla, acción y responsable propuesto.
- Cálculos de pesos, distancias y conteo de nodos con bases explícitas; registro de discrepancias operativas sin código fiscal inventado.
- Cobertura de reglas: revisadas, no aplicables y no verificables con su dependencia.
- Petición al transportista y evidencia necesaria para cerrar cada hallazgo.

El [ejemplo AN-031](ejemplos/entrada-pedido-anden-norte.md) usa solo datos **FICTICIOS de Andén Norte**. Su [salida esperada](ejemplos/salida-esperada.md) tiene cinco incumplimientos demostrados contra la matriz, una discrepancia operativa y pendientes explícitos. Puede seguirse a mano, sin ejecutar programas ni contratar un servicio.

## Fuentes y límites

Incluye [las 105 filas de la matriz](references/matriz-errores-ccp-31.md), el Excel original, la FAQ original y una [guía por pregunta/página](references/faq-carta-porte-31.md). Las URL oficiales, fecha de consulta **2026-10-29**, huellas y método están en [fuentes.md](references/fuentes.md). Los documentos oficiales se atribuyen al SAT; no se presentan como obra propia de Heroldo.

La FAQ descargada fundamenta respuestas en normas de **2024**. La skill exige comprobar la norma aplicable al viaje antes de concluir obligación o exención y marca la vigencia no comprobada. No decide excepciones por ruta local, importes de multas ni tratamientos aduanales a partir de esa edición antigua.

No incluye catálogos vigentes, esquema XML, listas de RFC, certificación ni validación completa del CFDI. Si faltan, devuelve NO VERIFICABLE; no los da por aprobados. Admite modos distintos de autotransporte usando la condición exacta de cada fila, pero el caso de práctica es de autotransporte nacional. No sustituye al contador, al agente aduanal ni al SAT: **pre-revisa, cruza y arma evidencia**. La revisión final y el timbrado corresponden al emisor y al certificador.

## Licencia

**Propiedad intelectual de Heroldo Escobedo**, con el código a la vista ([Licencia de uso de Heroldo 1.0](LICENSE)):

- **Uso personal: gratis.** Léelo, pruébalo y adáptalo para aprender o en tus propios datos.
- **Uso en una empresa o con fines de lucro: solo con compra.** Cómpralo en [Agensi](https://agensi.io/skills/pre-revisor-carta-porte)
  o escribe a heroldo@lolo-enterprises.com. La compra cubre a tu empresa.
- **Siempre se cita la fuente:** «Basado en una skill de Heroldo Escobedo — heroldo.org».
- No se revende ni se vuelve a publicar.

> **In English:** Source-available, not open source. Free for personal use. Business use requires purchase on
> [Agensi](https://agensi.io/skills/pre-revisor-carta-porte). Attribution to Heroldo Escobedo — heroldo.org is always required.

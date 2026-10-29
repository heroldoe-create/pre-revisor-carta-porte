# Fuentes, procedencia y actualización

Consulta: **2026-10-29 (UTC)**. El contenido de SAT se identifica como fuente de autoridad, no como autoría de Heroldo. La licencia del paquete cubre las instrucciones y materiales propios; no se atribuye propiedad sobre documentos oficiales de terceros.

| Fuente | URL oficial consultada | Resultado medido |
|---|---|---|
| Matriz de errores CCP 3.1 | http://omawww.sat.gob.mx/tramitesyservicios/Paginas/documentos/Matriz_Errores_CCP_V31.xls | HTTP 200; 342528 bytes; hoja `Validaciones Carta Porte 3.1`; 105 filas con código; publicada por el SAT el 2024-06-17 (encabezado Last-Modified) |
| FAQ Carta Porte 3.1 | http://omawww.sat.gob.mx/tramitesyservicios/Paginas/documentos/Preguntas_frecuentes_CartaPorte_31.pdf | HTTP 200; 724059 bytes; 55 páginas; fundamentos de 2024; publicada por el SAT el 2024-08-07 (encabezado Last-Modified) |
| Portal SAT, contexto de versiones | https://wwwmat.sat.gob.mx/consultas/68823/complemento-carta-porte- | Consultado por navegador el 2026-10-29; indica CFDI 4.0 + CCP 3.1 desde 17-jul-2024. No se usa para ampliar reglas de la matriz ni decidir exenciones |

## Integridad de las copias incluidas

SHA-256 (huella del contenido):

```text
5435ed272510461ff24f22ab675a7dd86013894fdb9cb98e4ae0655b6246c5c3  Matriz_Errores_CCP_V31.xls
1c276876ed3806f9da264a26aaaf214f907142d995f2eb8a9a83dc17fe2fd73e  Preguntas_frecuentes_CartaPorte_31.pdf
```

Se descargaron con `curl -L --max-time 30 -sS -o <destino> -w '%{http_code} %{size_download}\n' <URL>`.
La fecha de publicación se leyó con `curl -sI <URL>` (encabezado `Last-Modified`) el 2026-10-29.
Se midieron tamaño y SHA-256 con `pathlib.Path.read_bytes()` y `hashlib.sha256()`.
El intento HTTPS del mismo host no respondió oportunamente; se usaron las URL HTTP del SAT. Una huella comprueba igualdad de copias, no autenticidad criptográfica del servidor. Para uso real, volver a obtener y contrastar contra la publicación oficial disponible; si no es posible, declarar la vigencia no comprobada.

La transcripción Markdown se generó desde el Excel con SheetJS `xlsx` leyendo filas cuyo código coincide con `CP` seguido de dígitos: se conservaron las siete columnas originales, se escaparon barras verticales y se reemplazaron saltos de línea de celda por `<br>`. No se corrigieron aparentes erratas del SAT. En particular, CP129 dice cinco destinos ferroviarios y CP204 contiene referencias a ubicaciones dentro de una regla de figuras: no reinterpretar silenciosamente; consultar original y escalar cualquier duda de aplicación.

La guía FAQ se contrastó con `pdftotext -layout <original.pdf> <texto.txt>` y localizadores de página del PDF, contando portada como 1. Es una selección explicada; el PDF completo sigue disponible para los otros casos. No se reproducen las multas de la edición antigua en las instrucciones.

## Antes de aplicar a un viaje nuevo

1. Registrar fecha del viaje y fecha de consulta; obtener fuentes del portal SAT, verificar versión y condición aplicable.
2. Si cambia el archivo, conservar la instantánea anterior en el historial, registrar nueva URL/fecha/huella y comparar reglas. Repetir el ejemplo y revisar los hallazgos afectados antes de ofrecer conclusiones con la nueva versión.
3. Obtener de fuente oficial los catálogos, esquema y normativa que el caso necesite. Registrar archivo/edición y fila de catálogo utilizada. Este paquete no los incluye ni afirma haberlos validado.
4. Cuando no pueda verificarse la vigencia, trabajar con la instantánea declarada y marcar la limitación en el informe; nunca presentar la fecha de consulta como fecha de entrada en vigor.

No se usan reglas internas de empresas, fuentes comerciales ni memoria del modelo para fundamentar una regla fiscal o aduanal.

## Fuente de la ley citada en la licencia

La sección 6 de LICENSE menciona la Ley Federal del Derecho de Autor. Fuente oficial: Cámara de Diputados, https://www.diputados.gob.mx/LeyesBiblio/pdf/LFDA.pdf ; texto vigente, última reforma DOF 14-05-2026; consulta 2026-10-29. Esta referencia identifica la ley citada; no constituye un dictamen sobre la validez de las cláusulas de la licencia.

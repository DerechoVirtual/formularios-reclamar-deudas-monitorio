---
name: oposicion-monitorio-falta-legitimacion-pasiva-deuda-civ-1166
description: "Oposición al monitorio por falta de legitimación pasiva en una deuda de suministro eléctrico. Lo redacta con los datos del caso y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Oposición al monitorio por falta de legitimación pasiva en una deuda de suministro eléctrico

> Formulario **CIV-1166** del plugin **Cobrar deudas: monitorio y cambiario** (`formularios-reclamar-deudas-monitorio`) · Civil › Monitorio y cambiario · normativa revisada el 25-11-2026.

## Qué es

Escrito de oposición a proceso monitorio en reclamación de cantidad por consumos derivados de contrato de suministro eléctrico alegando falta de legitimación pasiva por novación consentida con comunicación de traspaso o subrogación de contrato a nuevo usuario

Es un modelo de tipo **contestaciones, oposiciones y alegaciones**, en su versión revisada y actualizada a la normativa vigente.

## Para qué sirve

Para obtener, en pocos minutos, un borrador completo de «Oposición al monitorio por falta de legitimación pasiva en una deuda de suministro eléctrico» adaptado a tu caso y a la normativa vigente, en Word y listo para revisar. Claude no se limita a copiar el modelo: te pide los datos, decide contigo las opciones, redacta las partes que dependen de los hechos y comprueba en el BOE cada norma que cita.

## Cómo se usa

1. **Pídelo con tus palabras**, por ejemplo: «Prepárame el documento “Oposición al monitorio por falta de legitimación pasiva en una deuda de suministro eléctrico” para mi caso». También puedes invocarla directamente con `/formularios-reclamar-deudas-monitorio:oposicion-monitorio-falta-legitimacion-pasiva-deuda-civ-1166`.
2. **Dale los datos del caso** cuando te los pida (abajo tienes la lista para tenerlos a mano). Lo que no sepas queda como hueco visible.
3. **Resuelve las opciones** que te plantee (las marcadas [ELEGIR] y [OPCIONAL] en el modelo).
4. **Recibe el documento en Word, tal cual es el formulario**: empieza por su primera línea (por ejemplo «En [LOCALIDAD], a [FECHA]» o «A LA SECCIÓN…»), sin títulos ni notas añadidas, en Times New Roman 11, interlineado 1,15 y texto justificado. Lo pendiente, las normas comprobadas y el plazo te los dice en el chat.

Si no estás seguro de que este sea el formulario que necesitas, usa el índice del plugin: `/formularios-reclamar-deudas-monitorio:indice`.

## Qué contiene esta skill

- `SKILL.md` (este fichero): qué es el formulario, para qué sirve, cómo se usa, los datos que pide, las normas que cita, los avisos de actualización y las instrucciones para Claude.
- `assets/formulario.md`: el formulario seco, tal cual, desde su primera línea hasta la firma, con sus campos [EN MAYÚSCULAS] y sus opciones [ELEGIR…] / [OPCIONAL…]. Es el texto que se rellena; no lleva explicaciones.
- `../indice/marco.md` (en la skill `indice` del plugin): la guía del tema (Cobrar deudas: monitorio y cambiario) con las normas, órganos y plazos vigentes que Claude lee antes de redactar.

## Datos que conviene tener a mano

- [ ] DENOMINACIÓN SOCIAL (2 veces)
- [ ] FECHA (2 veces)
- [ ] NOMBRE DE LA PARTE (2 veces)
- [ ] NOMBRE DEL REPRESENTADO/A (2 veces)
- [ ] Nº DE DOCUMENTO (2 veces)
- [ ] LOCALIDAD
- [ ] LUGAR
- [ ] NOMBRE Y APELLIDOS
- [ ] NÚMERO

## Normas que cita el formulario

- art. 815 LEC
- art. 813 LEC
- art. 85.1 LOPJ
- art. 818.1 LEC
- art. 31 LEC

## Instrucciones para Claude

### Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

### Avisos de actualización (0) — se aplican en el texto, nunca se copian en el documento

- Ninguno.

### Notas de uso del formulario — orientan la redacción, nunca se copian en el documento

Notas al pie del formulario original:
(1) Según la ley en el escrito de oposición no hay limitación en cuanto a motivos de oposición, que podrán ser procesales o de fondo. En el escrito que se ha configurado se invoca falta de legitimación pasiva que, de hecho, viene indisolublemente unida a la cuestión de fondo, en cuanto sólo cabrá afirmar definitivamente que el demandado estaba pasivamente legitimado en el proceso si, finalmente, se llega a la conclusión de que es deudor frente al demandante de las cantidades reclamadas, y cuyo desarrollo es propio del declarativo posterior que tenga lugar, en su caso.

(2) Para la comprensión del ejemplo que contempla el escrito, debe recordarse que el Real Decreto 88/2026, de 11 de febrero, por el que se aprueba el Reglamento general de suministro, comercialización y agregación de energía eléctrica, impone al consumidor que pretende darse de baja del servicio (art. 40.1) o tramitar el traspaso y subrogación del contrato de suministro (art. 31.1), comunicarlo de manera fehaciente a la entidad eléctrica, y en aquellos supuestos en los que no existe subrogación de un tercero consentida por la compañía suministradora —ni de forma expresa, ni tácita—, considera obligado al pago del servicio al titular del contrato; y esto con independencia de que sea otro el usuario o beneficiario del suministro, contra el que el titular del contrato podría deducir las acciones de repetición o regreso que pudieran asistirle (SSAP Barcelona 31/2012 de 2 Feb. 2012, Rec. 277/2011, 387/2011 de 18 Jul. 2011, Rec. 843/2010 y 163/2011 de 1 Abr. 2011, Rec. 284/2010; Cáceres 441/2010 de 10 Nov. 2010, Rec. 604/2010; Jaén 38/2012 de 14 Feb. 2012, Rec. 3/2012; Baleares de 15 Mar. 2012, Rec. 381/2011 y 22 Mar. 2012, Rec. 542/2011; Málaga de 20 Abr. 2006, Rec. 117/2006; Valencia de 14 Jun. 2006 y 6 Abr. 2006; o Coruña de 1 Jul. 2010, Rec. 322/2010).

(3) Téngase en cuenta que cuando la cuantía de la pretensión reconduce al juicio verbal (inferior a 15.000 euros), como es el caso, en el escrito de oposición podrá solicitarse la celebración de vista si se considera necesaria.

========================================================================


### Flujo

1. **Paso 0**: comprueba Jurisprudenciator (arriba).
2. Lee entero `assets/formulario.md` (el formulario que vas a rellenar, en la carpeta de esta skill) y la parte de `../indice/marco.md` que afecte al caso. Limítate a la materia de este formulario: no añadas contenido ajeno a él.
3. Pide los datos de la lista en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez. Lo que el usuario no sepa se queda como hueco visible con su etiqueta (p. ej. [FECHA]).
4. Resuelve cada [ELEGIR …] y cada [OPCIONAL …] según los hechos, y sustituye cualquier indicación entre paréntesis del formulario («(se describirá…)», «(indicar…)») por el contenido que corresponda. Redacta las partes que dependen del caso (hechos, motivos, descripción de bienes).
5. Aplica los avisos de actualización en el lugar que indican. Comprueba con `buscar_articulo` cada norma citada; si alguna ha cambiado, usa la redacción vigente. Si citas jurisprudencia, localízala con `buscar_sentencias` o `buscar_por_cita` y léela con `leer_sentencias`.
6. Antes de entregarlo, pasa `verificar_escrito` con las frases que citan normas o sentencias y corrige lo que señale.
7. **Documento final = el formulario tal cual, rellenado y limpio.**
   - Empieza exactamente por la primera línea de `assets/formulario.md` y sigue su estructura y su orden hasta la firma.
   - No pongas en el documento título, nombre del formulario o de la skill, código, encabezados, «Para qué sirve», leyendas, avisos, notas de uso, comentarios ni explicaciones. Tampoco marcas [ELEGIR…] u [OPCIONAL…]: ya están resueltas.
   - Formato Word (.docx, con la skill de Word disponible): **Times New Roman 11 pt** en todo el documento, **interlineado 1,15**, **texto justificado**, márgenes de 2,5 cm. Los rótulos del formulario (REUNIDOS, CLÁUSULAS, HECHOS, SUPLICO…) en su propia línea y en negrita, sin cambiar su texto.
8. En el chat (nunca dentro del documento): datos pendientes, partes redactadas por ti, normas y sentencias comprobadas con Jurisprudenciator (y, si algún dato sale de internet, cuál y su enlace) y, si es un escrito judicial o administrativo, el plazo y el órgano ante el que se presenta.

El resultado es un borrador para que lo revise un profesional antes de usarlo.

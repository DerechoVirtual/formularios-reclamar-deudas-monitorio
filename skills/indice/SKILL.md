---
name: indice
description: "Índice de los 64 formularios de Cobrar deudas: monitorio y cambiario. Úsala cuando el usuario pida un documento de esta materia y no esté claro qué formulario usar: propone el adecuado y lo abre. Requiere Jurisprudenciator."
---

# Cobrar deudas: monitorio y cambiario: índice de formularios

> Plugin `formularios-reclamar-deudas-monitorio` · 64 formularios · normativa revisada el 25-11-2026.

## Qué es

Para reclamar deudas: petición inicial de monitorio (también de comunidad de propietarios), oposición del deudor, impugnación de la oposición, paso al declarativo y juicio cambiario con letras, pagarés y cheques.

## Cómo se usa

Cuéntale a Claude qué documento necesitas y para qué caso. Esta skill busca en la lista de abajo el formulario que mejor encaja (por tipo de documento y por su nombre) y lo abre. Si hay dos o tres que encajan, te los propone para que elijas.

Ejemplos de petición:

- «Petición inicial de monitorio por facturas impagadas»
- «Oposición a un monitorio por prescripción»
- «Demanda de juicio cambiario por un pagaré impagado»

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

### Cómo elegir

Busca por tipo de documento y por nombre. Cada formulario es una skill de este plugin (`/formularios-reclamar-deudas-monitorio:<skill>`). Si dudas entre dos, elige el que mejor encaje con los hechos y dilo; si la petición es ambigua, propón al usuario los dos o tres formularios que mejor encajan y pregúntale cuál quiere. Las reglas del tema están en `marco.md`.

### Cómo usar el formulario elegido

Invoca su skill. Si esa skill no aparece en tu lista de skills disponibles (puede pasar cuando hay muchas skills instaladas), lee directamente su fichero `SKILL.md`: está en la carpeta hermana de esta (`../<skill>/SKILL.md`). Síguelo igual que si la hubieras invocado: el formulario que se rellena está en `../<skill>/assets/formulario.md` y la guía del tema es el `marco.md` de esta carpeta.

### Demandas, peticiones y solicitudes iniciales (17)

| Código | Formulario | Skill |
|---|---|---|
| CIV-1145 | Escrito inicial de jurisdicción voluntaria por robo o extravío de cheque bancario | `escrito-inicial-jurisdiccion-voluntaria-robo-extravio-civ-1145` |
| CIV-1149 | Demanda de oposición en juicio cambiario por novación extintiva e incumplimiento del contrato | `demanda-oposicion-juicio-cambiario-novacion-extintiva-civ-1149` |
| CIV-1151 | Demanda de juicio cambiario por acción directa contra la sociedad aceptante y sus avalistas | `demanda-juicio-cambiario-accion-directa-contra-civ-1151` |
| CIV-1152 | Demanda de juicio cambiario por acción de regreso contra el librador de un cheque impagado | `demanda-juicio-cambiario-accion-regreso-contra-civ-1152` |
| CIV-1153 | Demanda de juicio cambiario por acción directa contra el único aceptante de una letra a plazo | `demanda-juicio-cambiario-accion-directa-contra-unico-civ-1153` |
| CIV-1154 | Demanda de juicio cambiario contra el aceptante de una letra que firmó además un pagaré impagado | `demanda-juicio-cambiario-contra-aceptante-letra-firmo-civ-1154` |
| CIV-1155 | Demanda de juicio cambiario por regreso contra el librador y directa contra el aceptante solidario | `demanda-juicio-cambiario-regreso-contra-librador-civ-1155` |
| CIV-1161 | Petición inicial de proceso monitorio para reclamar honorarios de abogado | `peticion-inicial-proceso-monitorio-reclamar-honorarios-civ-1161` |
| CIV-1172 | Solicitud de ejecución tras el decreto que termina el monitorio por incomparecencia del deudor | `solicitud-ejecucion-tras-decreto-termina-monitorio-civ-1172` |
| CIV-1175 | Demanda de juicio cambiario por cheque con declaración sustitutiva de protesto de la cámara | `demanda-juicio-cambiario-cheque-declaracion-civ-1175` |
| CIV-1177 | Solicitud de ejecución provisional de la sentencia de un juicio cambiario | `solicitud-ejecucion-provisional-sentencia-juicio-civ-1177` |
| CIV-1180 | Demanda de juicio cambiario por pagaré con declaración sustitutiva de protesto y embargo preventivo | `demanda-juicio-cambiario-pagare-declaracion-civ-1180` |
| CIV-1182 | Demanda de juicio ordinario posterior a la oposición en monitorio por precio de suministro | `demanda-juicio-ordinario-posterior-oposicion-monitorio-civ-1182` |
| CIV-1183 | Solicitud de ejecución cambiaria por falta de oposición del deudor, con embargo de bien ganancial | `solicitud-ejecucion-cambiaria-falta-oposicion-deudor-civ-1183` |
| CIV-2778 | Demanda de juicio cambiario por pagaré impagado con acción directa contra el firmante | `demanda-juicio-cambiario-pagare-impagado-accion-civ-2778` |
| CIV-2780 | Demanda ordinaria tras la oposición al monitorio ante el mismo tribunal por competencia funcional | `demanda-ordinaria-tras-oposicion-monitorio-ante-mismo-civ-2780` |
| CIV-2781 | Demanda ordinaria tras la oposición al monitorio con la misma pretensión de la petición inicial | `demanda-ordinaria-tras-oposicion-monitorio-misma-civ-2781` |

### Contestaciones, oposiciones y alegaciones (12)

| Código | Formulario | Skill |
|---|---|---|
| CIV-1162 | Oposición al monitorio por nulidad del título debida a cláusulas abusivas | `oposicion-monitorio-nulidad-titulo-debida-clausulas-civ-1162` |
| CIV-1164 | Alegaciones del demandante sobre competencia objetiva en un monitorio por transporte de mercancías | `alegaciones-demandante-sobre-competencia-objetiva-civ-1164` |
| CIV-1166 | Oposición al monitorio por falta de legitimación pasiva en una deuda de suministro eléctrico | `oposicion-monitorio-falta-legitimacion-pasiva-deuda-civ-1166` |
| CIV-1168 | Escrito de oposición del deudor en el procedimiento monitorio | `escrito-oposicion-deudor-procedimiento-monitorio-civ-1168` |
| CIV-1169 | Escrito de oposición del requerido en el monitorio de desahucio | `escrito-oposicion-requerido-monitorio-desahucio-civ-1169` |
| CIV-1174 | Oposición del deudor a la ejecución despachada en un monitorio por rentas de alquiler | `oposicion-deudor-ejecucion-despachada-monitorio-rentas-civ-1174` |
| CIV-1176 | Oposición al requerimiento de pago en un monitorio de cuantía propia del juicio verbal | `oposicion-requerimiento-pago-monitorio-cuantia-propia-civ-1176` |
| CIV-1179 | Oposición del deudor a la ejecución despachada en un proceso monitorio | `oposicion-deudor-ejecucion-despachada-proceso-monitorio-civ-1179` |
| CIV-1184 | Oposición en juicio cambiario por indebida acumulación de la acción cambiaria y la del contrato caus | `oposicion-juicio-cambiario-indebida-acumulacion-accion-civ-1184` |
| CIV-1193 | Escrito de oposición del deudor en monitorio de más de 15.000 euros | `escrito-oposicion-deudor-monitorio-mas-15-000-euros-civ-1193` |
| CIV-1195 | Oposición del deudor por pluspetición en monitorio de más de 2.000 euros | `oposicion-deudor-pluspeticion-monitorio-mas-2-000-euros-civ-1195` |
| CIV-2779 | Oposición del deudor al monitorio alegando que el procedimiento no es el adecuado | `oposicion-deudor-monitorio-alegando-procedimiento-no-civ-2779` |

### Recursos (3)

| Código | Formulario | Skill |
|---|---|---|
| CIV-1148 | Recurso de apelación contra el auto que inadmite la petición inicial de proceso monitorio | `recurso-apelacion-contra-auto-inadmite-peticion-civ-1148` |
| CIV-1173 | Recurso directo de revisión contra el decreto que da por terminado el proceso monitorio | `recurso-directo-revision-contra-decreto-da-terminado-civ-1173` |
| CIV-1178 | Recurso de reposición potestativo contra la inadmisión en el juicio cambiario | `recurso-reposicion-potestativo-contra-inadmision-civ-1178` |

### Comunicaciones, requerimientos y cartas (1)

| Código | Formulario | Skill |
|---|---|---|
| CIV-1163 | Denuncia judicial por extravío de un pagaré | `denuncia-judicial-extravio-pagare-civ-1163` |

### Escritos de trámite y otros (31)

| Código | Formulario | Skill |
|---|---|---|
| CIV-1146 | Escrito de inicio del expediente de jurisdicción voluntaria sobre letra de cambio sustraída | `escrito-inicio-expediente-jurisdiccion-voluntaria-civ-1146` |
| CIV-1147 | Escrito comunicando al Tribunal el cambio de domicilio de la empresa demandada en el monitorio | `escrito-comunicando-tribunal-cambio-domicilio-empresa-civ-1147` |
| CIV-1150 | Escrito del deudor requerido en juicio cambiario para alzar el embargo por falta de representación | `escrito-deudor-requerido-juicio-cambiario-alzar-civ-1150` |
| CIV-1156 | Petición de proceso monitorio de la comunidad de propietarios por gastos comunes impagados | `peticion-proceso-monitorio-comunidad-propietarios-civ-1156` |
| CIV-1157 | Petición de monitorio por gastos comunes impagados de una comunidad, con abogado y procurador | `peticion-monitorio-gastos-comunes-impagados-comunidad-civ-1157` |
| CIV-1158 | Petición de proceso monitorio por suministro impagado de productos de carnicería y embutidos | `peticion-proceso-monitorio-suministro-impagado-civ-1158` |
| CIV-1159 | Petición de proceso monitorio de un abogado contra su cliente por honorarios impagados | `peticion-proceso-monitorio-abogado-contra-cliente-civ-1159` |
| CIV-1160 | Petición de proceso monitorio por suministro impagado de productos agrícolas | `peticion-proceso-monitorio-suministro-impagado-civ-1160` |
| CIV-1165 | Escrito del actor que acepta la propuesta de requerir de pago por una cantidad menor en el monitorio | `escrito-actor-acepta-propuesta-requerir-pago-cantidad-civ-1165` |
| CIV-1167 | Escrito del actor que rechaza la propuesta de requerimiento por menor cantidad en el monitorio | `escrito-actor-rechaza-propuesta-requerimiento-menor-civ-1167` |
| CIV-1170 | Escrito de allanamiento del deudor en el procedimiento monitorio | `escrito-allanamiento-deudor-procedimiento-monitorio-civ-1170` |
| CIV-1171 | Declinatoria de jurisdicción en un monitorio por sometimiento a arbitraje | `declinatoria-jurisdiccion-monitorio-sometimiento-civ-1171` |
| CIV-1181 | Escrito del demandado que niega la firma del aceptante de la letra y pide alzar el embargo | `escrito-demandado-niega-firma-aceptante-letra-pide-civ-1181` |
| CIV-1185 | Escrito iniciando proceso monitorio para reclamar el precio de la reparación de un automóvil | `escrito-iniciando-proceso-monitorio-reclamar-precio-civ-1185` |
| CIV-1186 | Escrito del deudor que acredita el pago en el monitorio ingresando en la cuenta de consignaciones | `escrito-deudor-acredita-pago-monitorio-ingresando-civ-1186` |
| CIV-1187 | Escrito iniciando monitorio por gastos comunes impagados de la comunidad, con embargo preventivo | `escrito-iniciando-monitorio-gastos-comunes-impagados-civ-1187` |
| CIV-1188 | Escrito pidiendo costas y multa por mala fe procesal al demandante que desiste en el monitorio | `escrito-pidiendo-costas-multa-mala-fe-procesal-civ-1188` |
| CIV-1189 | Escrito iniciando monitorio para reclamar el precio de obras de albañilería | `escrito-iniciando-monitorio-reclamar-precio-obras-civ-1189` |
| CIV-1190 | Escrito iniciando monitorio por compras reiteradas con reconocimiento de deuda | `escrito-iniciando-monitorio-compras-reiteradas-civ-1190` |
| CIV-1191 | Escrito iniciando monitorio por una venta efectuada por fax | `escrito-iniciando-monitorio-venta-efectuada-fax-civ-1191` |
| CIV-1192 | Escrito iniciando monitorio para reclamar el impago de hospedaje | `escrito-iniciando-monitorio-reclamar-impago-hospedaje-civ-1192` |
| CIV-1194 | Escrito iniciando monitorio por impago de facturas de una compraventa de muebles | `escrito-iniciando-monitorio-impago-facturas-civ-1194` |
| CIV-1196 | Escrito del actor pidiendo auto que admita el allanamiento parcial del deudor en el monitorio | `escrito-actor-pidiendo-auto-admita-allanamiento-civ-1196` |
| CIV-1197 | Escrito de desistimiento del monitorio antes del requerimiento de pago | `escrito-desistimiento-monitorio-antes-requerimiento-civ-1197` |
| CIV-1198 | Escrito de desistimiento del monitorio después del requerimiento de pago | `escrito-desistimiento-monitorio-despues-requerimiento-civ-1198` |
| CIV-2772 | Escrito que pide suspender el juicio cambiario por prejudicialidad penal hasta sentencia firme | `escrito-pide-suspender-juicio-cambiario-civ-2772` |
| CIV-2773 | Petición de embargo de elementos comunes por destino de la comunidad ejecutada en juicio cambiario | `peticion-embargo-elementos-comunes-destino-comunidad-civ-2773` |
| CIV-2774 | Petición de embargo de cuotas futuras de la comunidad de propietarios ejecutada tras un monitorio | `peticion-embargo-cuotas-futuras-comunidad-propietarios-civ-2774` |
| CIV-2775 | Declinatoria por falta de competencia territorial en el juicio cambiario | `declinatoria-falta-competencia-territorial-juicio-civ-2775` |
| CIV-2776 | Escrito del deudor cambiario que pide alzar el embargo negando la autenticidad de su firma | `escrito-deudor-cambiario-pide-alzar-embargo-negando-civ-2776` |
| CIV-2777 | Escrito del deudor cambiario que acredita haber pagado lo reclamado | `escrito-deudor-cambiario-acredita-haber-pagado-lo-civ-2777` |

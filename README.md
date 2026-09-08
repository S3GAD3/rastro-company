# RASTRO · COMPANY

Herramienta web de apoyo a la investigación OSINT de empresas, personas jurídicas e infraestructura digital corporativa.

**Versión actual:** 1.7  
**Herramienta publicada:** [https://s3gad3.github.io/rastro-company/](https://s3gad3.github.io/rastro-company/)

RASTRO · COMPANY permite organizar en un único entorno la identificación de una empresa, validar datos básicos, preparar consultas en fuentes públicas, documentar relaciones y generar un resumen exportable de la investigación.

> RASTRO · COMPANY no es una fuente oficial ni sustituye a los registros públicos. Los resultados deben ser contrastados por el investigador antes de incorporarlos a un informe o actuación.

## Características principales

- Validación local del NIF/CIF de personas jurídicas españolas.
- Interpretación orientativa de la provincia y la forma jurídica derivadas del CIF.
- Normalización de denominaciones sociales.
- Eliminación automática de formas jurídicas como `S.L.`, `S.A.`, `S.L.U.`, `S.A.U.` y sus denominaciones completas para mejorar las búsquedas.
- Validación sintáctica de dominios y direcciones IPv4.
- Consulta voluntaria de registros DNS mediante DNS-over-HTTPS.
- Consulta RDAP con acceso alternativo a servicios WHOIS.
- Acceso ordenado a fuentes mercantiles, fiscales, societarias, comerciales y de propiedad industrial.
- Generación automática de consultas OSINT mediante Google y Bing.
- Investigación de infraestructura digital, certificados TLS e histórico web.
- Consulta de contratación pública, procedimientos concursales, sanciones e identificadores LEI.
- Grafo interactivo de empresas, personas, marcas, dominios, IP y domicilios.
- Registro de fuentes, fechas y evidencias asociadas a cada relación.
- Importación y exportación de relaciones en CSV y JSON.
- Generación de informes en HTML, CSV y JSON.
- Diseño adaptable a ordenadores, tabletas y teléfonos móviles.
- Funcionamiento principal en el navegador, sin instalación ni servidor propio.

## Flujo de investigación

La interfaz se divide en siete apartados:

1. **00 · Información:** finalidad, tratamiento de datos y limitaciones.
2. **01 · Consulta:** introducción de la empresa investigada.
3. **02 · Análisis:** validación y normalización local de los datos.
4. **03 · Fuentes:** acceso organizado a buscadores y consultas externas.
5. **04 · Relaciones:** construcción manual del grafo de entidades vinculadas.
6. **05 · Informe:** resumen, observaciones y exportación de resultados.
7. **06 · Ayuda:** instrucciones de utilización.

Dentro de **03 · Fuentes**, las consultas siguen una ruta operativa:

1. Identidad mercantil y publicidad oficial.
2. Estructura, cargos y datos comerciales.
3. Riesgo, solvencia y contratación pública.
4. Presencia pública, documentos e infraestructura digital.
5. Marcas, nombres comerciales y localización.

## Datos de entrada

La herramienta admite uno o varios de los siguientes datos:

- denominación social o nombre comercial;
- NIF/CIF;
- dominio corporativo;
- domicilio social;
- referencia de la investigación;
- hipótesis o notas iniciales.

No es necesario completar todos los campos. La calidad y amplitud de las consultas dependerán de los datos disponibles.

## Consultas OSINT preparadas

RASTRO · COMPANY depura la denominación social antes de construir las búsquedas. Por ejemplo:

```text
VERITAS & HÁBITAT, S.L. → VERITAS & HÁBITAT
```

Cuando existe denominación y CIF, los combina mediante `OR`:

```text
("VERITAS & HÁBITAT" OR "B21771712")
```

Esto permite recuperar páginas que contengan cualquiera de los dos identificadores.

### Ejemplos de dorks generados

Presencia en LinkedIn, sin restringir la ruta interna de la página:

```text
site:linkedin.com ("VERITAS & HÁBITAT" OR "B21771712")
```

Personas vinculadas y cargos societarios:

```text
site:linkedin.com ("VERITAS & HÁBITAT" OR "B21771712")
(administrador OR apoderado OR CEO OR "consejero delegado")
```

Documentos públicos:

```text
("VERITAS & HÁBITAT" OR "B21771712")
filetype:pdf (memoria OR "cuentas anuales" OR contrato OR informe)
```

Señales de riesgo:

```text
("VERITAS & HÁBITAT" OR "B21771712")
(fraude OR estafa OR sanción OR investigada OR concurso OR insolvencia OR sentencia)
```

Los resultados de estas búsquedas son indicios para orientar la investigación. La aparición de una empresa en un resultado no demuestra por sí sola ningún hecho.

## Fuentes y líneas de investigación

### Identidad mercantil y publicidad oficial

- BOE y buscador de anuncios del BORME.
- Registro Mercantil Central.
- Buscador mercantil de Registradores de España.
- Datos abiertos de Registradores.
- Registro Público Concursal.
- European e-Justice.

### Estructura, cargos y datos comerciales

- DatosCif.
- LibreBOR.
- InfoNIF.
- OpenCorporates.
- GLEIF.

Los resultados de fuentes comerciales o agregadores deben contrastarse con registros y documentos oficiales.

### Contratación, solvencia y cumplimiento

- VIES de la Comisión Europea.
- Plataforma de Contratación del Sector Público.
- TED, contratación pública europea.
- EU Sanctions Map.
- OFAC Sanctions List Search.

### Marcas y propiedad industrial

- OEPM — Localizador de Marcas y Nombres Comerciales.
- TMview.
- BOPI.

### Infraestructura digital y presencia pública

- Google y Bing.
- LinkedIn mediante búsquedas dirigidas desde Google.
- Certificate Transparency mediante crt.sh.
- Wayback Machine.
- RDAP.
- WHOIS.
- ICANN Lookup.
- Google Maps y OpenStreetMap.

## Consultas precargadas y portales manuales

RASTRO diferencia entre:

- **PRECARGADA:** el enlace incorpora automáticamente la denominación, el CIF, el dominio o la dirección.
- **BUSCADOR OFICIAL:** conduce al formulario correcto, pero el dato debe introducirse manualmente.
- **PORTAL:** acceso general a un servicio que no ofrece una URL pública estable para precargar la búsqueda.
- **PAGO o PRÉMIUM:** el servicio puede exigir registro, identificación o pago.

Algunos organismos utilizan formularios de sesión, peticiones `POST`, CAPTCHA o controles internos que impiden precargar una consulta de forma fiable desde una herramienta HTML externa. En esos casos, RASTRO abre el buscador correcto y ofrece, cuando resulta útil, una consulta alternativa mediante Google.

## Utilización

### Uso en línea

Abre:

[https://s3gad3.github.io/rastro-company/](https://s3gad3.github.io/rastro-company/)

### Uso local

1. Descarga `index.html`.
2. Abre el archivo con un navegador actualizado.
3. Accede a **01 · Consulta**.
4. Introduce los datos disponibles de la empresa.
5. Pulsa **Iniciar análisis**.
6. Revisa la validación local en **02 · Análisis**.
7. Sigue la ruta de investigación de **03 · Fuentes**.
8. Registra únicamente los vínculos contrastados en **04 · Relaciones**.
9. Revisa y exporta el resultado desde **05 · Informe**.

## Grafo de relaciones

El grafo permite representar vínculos entre:

- empresa investigada;
- administradores y apoderados;
- socios o accionistas;
- otras sociedades;
- marcas y nombres comerciales;
- dominios e IP;
- domicilios compartidos;
- otras entidades de interés.

Cada relación puede incluir su fuente y fecha. Las relaciones son introducidas por el investigador y no están verificadas automáticamente por la herramienta.

## Importación de relaciones

Se admiten archivos JSON y CSV con la siguiente estructura:

```csv
origen,tipo,destino,fuente,fecha
Empresa Ejemplo SL,administrador,Persona Ejemplo,BORME 123/2026,2026-06-15
Empresa Ejemplo SL,dominio,ejemplo.es,Sitio corporativo,2026-06-15
```

Tipos reconocidos:

- `administrador`
- `socio`
- `empresa`
- `marca`
- `dominio`
- `ip`
- `direccion`
- `otro`

## Exportación

La herramienta permite exportar:

- resumen de la investigación en HTML;
- datos principales en CSV;
- informe estructurado en JSON;
- relaciones del grafo en CSV;
- relaciones del grafo en JSON.

Las exportaciones se generan localmente en el navegador.

## Privacidad y tratamiento de datos

El análisis principal se ejecuta localmente. La herramienta:

- no requiere registro;
- no utiliza cuentas de usuario;
- no incorpora telemetría propia;
- no almacena investigaciones en un servidor propio;
- no envía automáticamente los datos introducidos;
- conserva el estado únicamente en memoria mientras la pestaña permanece abierta.

Solo existe comunicación con terceros cuando el investigador ejecuta expresamente una consulta DNS/RDAP o abre un enlace externo. Al abrir una búsqueda preparada, los términos incluidos en la URL se transmiten al servicio de destino.

Antes de emplear la herramienta con información sensible debe valorarse el entorno operativo y la política de seguridad aplicable.

## Limitaciones

- No accede automáticamente al Registro Mercantil, la OEPM ni otros servicios que carecen de una API pública adecuada.
- No extrae ni almacena el contenido de DatosCif, LibreBOR, InfoNIF u otros portales externos.
- Un NIF/CIF matemáticamente válido no acredita que la entidad exista o continúe activa.
- La provincia y la forma jurídica derivadas del CIF son orientativas.
- La validación sintáctica de un dominio no acredita su existencia, titularidad o actividad.
- DNS y RDAP dependen de servicios externos y pueden fallar por disponibilidad o restricciones CORS.
- Algunos portales pueden modificar sus URL, exigir cookies, registro, pago o comprobaciones adicionales.
- La indexación de Google, Bing y otros buscadores puede ser incompleta o estar desactualizada.
- Las relaciones del grafo son aportadas manualmente y deben documentarse mediante fuentes verificables.

## Estructura del repositorio

```text
rastro-company/
├── index.html
├── README.md
└── LICENSE
```

La aplicación se distribuye como un único archivo HTML autocontenido para facilitar su revisión, publicación y uso local.

## Contribuciones y forks

Se permiten forks, adaptaciones y mejoras de la herramienta.

Las contribuciones pueden proponerse mediante *issues* o *pull requests*. Al redistribuir una versión modificada debe mantenerse la atribución al autor original y diferenciar claramente los cambios realizados por terceros.

## Uso responsable

RASTRO · COMPANY está orientada a investigación OSINT, ciberinteligencia, análisis corporativo, formación y apoyo a investigaciones legítimas.

Cada usuario es responsable de:

- utilizar fuentes y datos conforme a la legislación aplicable;
- respetar las condiciones de uso de los servicios externos;
- aplicar los principios de necesidad, proporcionalidad y minimización;
- verificar los hallazgos antes de atribuir hechos o relaciones;
- conservar adecuadamente las evidencias y su trazabilidad.

La herramienta no determina culpabilidad, titularidad real, vinculación societaria ni responsabilidad jurídica.

## Autor

**S3GAD3**  
Autor original de RASTRO · COMPANY y del proyecto RASTRO — Kit de investigación de fuentes abiertas.

## Licencia

Este proyecto se distribuye bajo la **Licencia MIT**.

Se permite usar, copiar, modificar, fusionar, publicar, distribuir, sublicenciar y vender copias del software, siempre que se conserve el aviso de copyright y el texto completo de la licencia.

Los forks y versiones derivadas deben mantener la atribución al autor original:

```text
Copyright (c) 2026 S3GAD3
```

Consulta el archivo [`LICENSE`](LICENSE) para ver el texto completo de la licencia MIT.

---

**RASTRO · COMPANY v1.7 — Creado por S3GAD3**

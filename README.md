# RASTRO · COMPANY

Herramienta web de apoyo a la investigación OSINT de empresas, personas jurídicas e infraestructura digital corporativa.

**RASTRO · COMPANY** permite organizar en un único entorno la identificación de una empresa, validar datos básicos, preparar consultas en fuentes públicas, documentar relaciones y generar un resumen exportable de la investigación.

Enlace a la herramienta: 
https://s3gad3.github.io/rastro-company/

> La herramienta no sustituye a los registros oficiales ni verifica automáticamente la veracidad de los datos encontrados. Los resultados deben ser contrastados por el investigador.

## Características principales

- Validación local del NIF/CIF de personas jurídicas españolas.
- Normalización de denominaciones y formas societarias.
- Validación sintáctica de dominios y direcciones IPv4.
- Consulta voluntaria de registros DNS mediante DNS-over-HTTPS.
- Consulta RDAP con acceso alternativo a servicios WHOIS.
- Acceso ordenado a fuentes mercantiles, fiscales, societarias y de propiedad industrial.
- Búsquedas dirigidas mediante consultas OSINT preparadas automáticamente.
- Investigación de infraestructura digital, certificados TLS e histórico web.
- Consulta de contratación pública, sanciones e identificadores LEI.
- Grafo interactivo de empresas, personas, marcas, dominios, IP y domicilios.
- Registro de fuentes, fechas y evidencias asociadas a cada relación.
- Importación y exportación de relaciones en CSV y JSON.
- Generación de informes en HTML, CSV y JSON.
- Diseño responsive para ordenadores, tabletas y teléfonos móviles.
- Funcionamiento principal en el navegador, sin instalación ni servidor propio.

## Fuentes y líneas de investigación

La herramienta facilita el acceso a fuentes como:

- BOE y BORME.
- Registro Mercantil Central y Registradores.org.
- Registro Público Concursal.
- OEPM, BOPI y TMview.
- VIES de la Comisión Europea.
- European e-Justice.
- Plataforma de Contratación del Sector Público y TED.
- GLEIF y OpenCorporates.
- EU Sanctions Map y OFAC.
- Certificate Transparency mediante crt.sh.
- Wayback Machine, RDAP y WHOIS.
- LinkedIn, Google y Bing mediante búsquedas dirigidas.

Los servicios externos conservan sus propias condiciones de uso, políticas de privacidad y limitaciones técnicas.

## Utilización

1. Descarga el archivo `index-rastro-company.html`.
2. Ábrelo con un navegador actualizado.
3. Accede a **01 · Consulta**.
4. Introduce uno o varios datos del objetivo:
   - denominación social o nombre comercial;
   - NIF/CIF;
   - dominio corporativo;
   - domicilio social;
   - referencia de la investigación y notas iniciales.
5. Pulsa **Iniciar análisis**.
6. Revisa la validación local en **02 · Análisis**.
7. Abre las fuentes necesarias desde **03 · Resultados**.
8. Registra únicamente los vínculos contrastados en **04 · Relaciones**.
9. Revisa y exporta el resultado desde **05 · Informe**.

## Grafo de relaciones

El grafo ayuda a representar vínculos entre:

- empresa investigada;
- administradores y apoderados;
- socios o accionistas;
- otras sociedades;
- marcas y nombres comerciales;
- dominios e IP;
- domicilios compartidos;
- otras entidades de interés.

Cada relación puede incluir su fuente y fecha. Estos datos son introducidos por el investigador y no deben interpretarse como relaciones verificadas automáticamente por la herramienta.

### Importación de relaciones

Se admiten archivos JSON y CSV con esta estructura:

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

## Privacidad y tratamiento de datos

El análisis principal se ejecuta localmente en el navegador. La herramienta:

- no requiere registro;
- no utiliza cuentas de usuario;
- no incorpora telemetría propia;
- no almacena investigaciones en un servidor propio;
- no envía automáticamente los datos introducidos.

Solo existe comunicación con terceros cuando el investigador ejecuta expresamente una consulta DNS/RDAP o abre un enlace externo. Antes de emplearla con información sensible, debe valorarse el entorno operativo y la política de seguridad aplicable.

## Limitaciones

- No accede automáticamente al Registro Mercantil, la OEPM ni otras fuentes que carecen de una API pública adecuada.
- Un NIF/CIF con control correcto no acredita que la entidad exista o permanezca activa.
- El prefijo territorial histórico de un CIF no acredita el domicilio actual.
- La validez sintáctica de un dominio no implica que esté registrado, activo o controlado por la empresa.
- Las relaciones del grafo proceden de la información aportada por el investigador.
- Los resultados de servicios externos pueden cambiar, requerir autenticación o dejar de estar disponibles.
- Las coincidencias de nombres, domicilios o infraestructuras son indicios que requieren contraste adicional.

## Contribuciones y forks

Se permiten contribuciones, modificaciones, mejoras y forks de este proyecto conforme a la licencia MIT.

Al reutilizar o redistribuir el código debe conservarse el aviso de copyright y la licencia, identificando a **S3GAD3 como autor original de RASTRO · COMPANY**. Las modificaciones de terceros deben presentarse de forma que no se atribuyan al autor original cambios que no haya realizado.

Las propuestas de mejora pueden enviarse mediante *issues* o *pull requests*.

## Uso responsable

RASTRO · COMPANY está destinada a investigación legítima, formación, análisis OSINT y apoyo profesional. Quien la utilice es responsable de respetar la legislación aplicable, los derechos fundamentales, la normativa de protección de datos y las condiciones de uso de cada fuente consultada.

La herramienta no formula acusaciones, no determina responsabilidades y no convierte una coincidencia en un hecho probado.

## Autor

**S3GAD3**  
Autor original y responsable del proyecto RASTRO · COMPANY.

## Licencia

Este proyecto se distribuye bajo la [licencia MIT](LICENSE).

Copyright © 2026 S3GAD3.

La licencia permite usar, copiar, modificar, publicar, distribuir y crear forks, siempre que se conserve el aviso de copyright y el texto de la licencia, manteniendo así la referencia al autor original.


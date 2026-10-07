# Ruta de Madurez · Universidad Colegio Mayor de Cundinamarca

Página de diagnóstico de madurez de resultados de investigación. Los investigadores diligencian su ficha, responden preguntas de Sí o No (con ejemplos de su disciplina), adjuntan evidencia y obtienen un informe en PDF con su telaraña de madurez.

## Cómo funciona (y por qué no depende de nadie)

- Es **un solo archivo** (`index.html`) más la carpeta `img/`. No necesita servidor, base de datos ni cuentas.
- Todo lo que el investigador escribe queda en **su propio navegador**. Para entregar, descarga dos archivos (informe PDF y «Guardar mi avance») y los sube al formulario de entrega.
- Funciona abriendo `index.html` con doble clic, o publicado en cualquier sitio web.

## Si quien lo administra se va: lista de continuidad

1. **Alojamiento.** Copiar `index.html` y `img/` a cualquier servidor web (el de la universidad, GitHub Pages, Netlify, Vercel…). No hay nada más que instalar.
2. **Cuentas.** Conviene que el repositorio y el alojamiento estén en una cuenta **institucional**, no personal. Transferir el repositorio a una organización de GitHub de la universidad y volver a conectar el alojamiento.
3. **Formulario de entrega.** Crearlo en la plataforma institucional (Google Forms o Microsoft Forms, con carga de archivos) y poner su dirección en `CONFIG.formularioUrl`.
4. **Revisión (ATRI).** El Área de Transferencia de Resultados de Investigación (ATRI) usa un archivo **privado** de revisión (carpeta `ATRI_revision`), que **no se publica** en este sitio. Se comparte solo con el equipo (por ejemplo, en una carpeta de Drive restringida). Importa los archivos recibidos, revisa la evidencia y marca «Verificado». No requiere servidor.

## Qué se edita y dónde (todo dentro de `index.html`)

| Qué | Dónde |
|---|---|
| Dirección del formulario de entrega, nombre del área (ATRI), textos de contacto | Bloque `CONFIG`, al inicio del script |
| Grupos de investigación y líneas | Constantes `GRUPOS` y `LINEAS` (fuente: sitio oficial de la universidad; revisar contra la actualización vigente) |
| Opciones de vinculación, ODS, mecanismos de PI | Constante `OPT` y listas cercanas |
| Preguntas, niveles y ejemplos por disciplina | Constante `BANK` (JSON) |
| Colores | Variables CSS al inicio del archivo (`:root`) |

## Opcional: envío automático con n8n

El botón «Enviar a ATRI» solo aparece si `CONFIG.webhookUrl` tiene una dirección. **Sin ella, la página funciona completa.** El flujo de n8n (recepción en Google Drive) es una comodidad, no un requisito.

## Ruta de transferencia

La pestaña «Ruta de transferencia» presenta las cinco etapas del Modelo de Transferencia de Conocimiento e Innovación (Acuerdo 041 de 2026 del Consejo Académico, art. 7) y ofrece el Acuerdo para descargar en `docs/`. Esta herramienta corresponde a la etapa 2 (diagnóstico de madurez). Las etapas están en la constante `ETAPAS`.

## Atribución del modelo

Basado en el **KTH Innovation Readiness Level™**, desarrollado por KTH Innovation (KTH Royal Institute of Technology). Sitio oficial: https://kthinnovationreadinesslevel.com. Según el sitio del modelo, está bajo licencia Creative Commons **BY-NC-SA 4.0** (atribución, uso no comercial, compartir igual).

Esta versión fue adaptada: se unen cliente y negocio en una dimensión de mercado, se añade la madurez social, los criterios se redactan como preguntas con ejemplos por disciplina y se pide evidencia. Los niveles de TRL se describen con definiciones de MINCIENCIAS (2019) y de la ESA.

> Nota: la licencia BY-NC-SA exige indicar los cambios y compartir las obras derivadas bajo la misma licencia. Conviene que la oficina jurídica confirme cómo aplica a esta adaptación antes de difundirla fuera de la universidad.


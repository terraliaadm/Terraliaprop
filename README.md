# Portafolio Inmobiliario · ABM Holdings

Aplicación web de administración patrimonial para la cartera de inmuebles del grupo **ABM Holdings** (División Inmobiliaria). Es un archivo HTML único, sin servidor, con estética de inmobiliaria internacional. Este repositorio también almacena las **imágenes de las propiedades** y los **respaldos** generados por la app.

---

## Contenido del repositorio

| Ruta | Descripción |
|------|-------------|
| `Portafolio_Inmobiliario_App.html` | La aplicación completa (un solo archivo). |
| `propiedades/` | Imágenes de las propiedades subidas desde la app. |
| `backups/portafolio.json` | Respaldo automático del estado (propiedades, gastos, parámetros). |

---

## La aplicación

Cartera de **21 inmuebles** en México y España, distribuidos en seis empresas (TERRALIA, MASLOW, SOCIOS, FORTIA, FERTI FORTE, GRATIL) y consolidados en pesos con tipos de cambio editables (MXN · EUR · USD).

### Funciones principales

- **Catálogo de propiedades** con filtros por tipo y por empresa, agrupables, e imagen de portada por inmueble.
- **Ficha de propiedad** con valuación, rendimiento, integración en pesos (para euros y dólares) y calendario de pagos.
- **Administración**: alta, edición y eliminación de propiedades, con cálculo automático de plusvalía, plusvalía %, patrimonio, yield y LTV.
- **Análisis** con tres rankings: mayor plusvalía, mejor yield y mayor apalancamiento (LTV).
- **Adeudos y flujo**: captura del adeudo de compra y su calendario de pagos, con proyección del flujo de egresos mes a mes.
- **Gastos** por propiedad (Predial, Mantenimiento, Reparaciones, Interiorismo) con alta de gastos y filtros por propiedad y por fecha.
- **Parámetros**: tipos de cambio editables, reporte a Excel, plantilla de importación, respaldo en JSON y configuración de la nube.

---

## Cómo usar

1. Abre `Portafolio_Inmobiliario_App.html` en un navegador (o publícalo en tu hosting).
2. Los datos se guardan en el navegador (localStorage). Usa **Parámetros** para respaldar o exportar.

---

## Almacenamiento en la nube (GitHub)

La app sube imágenes y respaldos a este repositorio mediante la API de GitHub. Configuración en **Parámetros → Almacenamiento de imágenes en la nube**:

| Campo | Valor |
|-------|-------|
| Usuario / organización | `terraliaadm` |
| Repositorio | `Terraliaprop` |
| Rama | `main` |
| Carpeta | `propiedades` |
| Token | *(tu token fine-grained)* |

### Generar el token

1. GitHub → **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
2. **Repository access:** *Only select repositories* → `Terraliaprop`.
3. **Permissions → Repository → Contents:** *Read and write* (único permiso necesario).
4. Copia el token (`github_pat_…`) y pégalo en la app.

El respaldo automático se dispara al guardar cambios (con un retardo breve) y escribe en `backups/portafolio.json`.

---

## Datos: exportar e importar

- **Reporte Excel**: descarga un `.xlsx` con hojas de Propiedades, Gastos, Adeudos, Flujo de pagos y Parámetros.
- **Plantilla**: `.xlsx` con las columnas esperadas para capturar en Excel.
- **Importar desde Excel**: carga una plantilla llena, con opción de **fusionar** (actualiza por ID y agrega) o **reemplazar todo**.
- **Respaldo JSON**: descarga o sube a GitHub el estado completo.

---

## Seguridad

- El **token** se guarda únicamente en el navegador; no se incluye en los respaldos ni en el archivo HTML.
- Usa un token de alcance mínimo (un repositorio, permiso Contents) y con vigencia; renuévalo al vencer.
- No compartas el token en correos ni mensajes.

---

## Notas

- Los porcentajes (plusvalía %, yield, LTV) son invariantes al tipo de cambio; solo los montos absolutos de los activos en euros/dólares se ajustan al TC del día.
- La exportación a Excel y la subida de imágenes requieren conexión a internet.

---

*Uso interno · ABM Holdings — División Inmobiliaria. Base de datos: agosto 2026.*

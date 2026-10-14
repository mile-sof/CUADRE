# Cuadre · cuadra tus costos, cuida tu utilidad

**Cuadre** (de *cuadrar*) es un programa de costos estándar para tu negocio. Sirve para saber **cuánto debería costar** cada producto o platillo y **cuánto te está costando de verdad**: materia prima, mano de obra y costos indirectos (CIF), con variaciones, utilidad, impuesto al consumo y reportes en Excel y PDF.

- Funciona **en tu computador, sin internet** y tus datos **no salen de tu equipo**.
- No hay que instalar librerías: solo necesitas **Python** (se instala una vez).
- Puedes cargar tu libro de Excel (formato **Libro Cuadre**) y el programa arma las hojas de costo por ti.

---

## Contenido

1. [Qué necesitas](#1-qué-necesitas)
2. [Instalar Python](#2-instalar-python-una-sola-vez)
3. [Descargar desde GitHub](#3-descargar-desde-github)
4. [Abrir el programa](#4-abrir-el-programa)
5. [Primer ingreso](#5-primer-ingreso)
6. [Crear tu empresa y tu periodo](#6-crear-tu-empresa-y-tu-periodo)
7. [Cargar tus datos](#7-cargar-tus-datos)
8. [Ver tus costos y tu utilidad](#8-ver-tus-costos-y-tu-utilidad)
9. [Registrar la producción real y ver variaciones](#9-registrar-la-producción-real-y-ver-variaciones)
10. [Reportes](#10-reportes-excel-pdf-e-imprimir)
11. [Cada día: abrir y cerrar](#11-cada-día-abrir-y-cerrar)
12. [Respaldo y actualización](#12-respaldo-y-actualización)
13. [Problemas frecuentes](#13-problemas-frecuentes)
14. [Cómo se llama cada cosa](#14-cómo-se-llama-cada-cosa)
15. [Para quien quiera saber más](#15-para-quien-quiera-saber-más)

---

## 1. Qué necesitas

| | |
|---|---|
| **Un computador** | Windows, Mac o Linux. **No funciona en celular ni en tablet.** |
| **Python 3.10 o superior** | Gratis. Se instala una sola vez (paso 2). |
| **Un navegador** | Chrome, Edge o Firefox. |
| **Internet** | Solo para descargar el programa y Python. **Después no hace falta.** |

---

## 2. Instalar Python (una sola vez)

Primero revisa si ya lo tienes. Abre una terminal (en Windows: tecla Windows, escribe `cmd` y Enter) y escribe:

```
python --version
```

(en Mac y Linux: `python3 --version`). Si muestra **3.10 o un número mayor** (por ejemplo `Python 3.12.4`), pasa al paso 3.

Si no lo tienes o es más viejo:

**Windows**
1. Entra a <https://www.python.org/downloads/> y pulsa **Download Python**.
2. Abre el instalador. **Marca la casilla «Add python.exe to PATH»** (abajo, antes de continuar). Es lo más importante.
3. Pulsa **Install Now** y espera a que termine.
4. Cierra y vuelve a abrir la terminal, y repite `python --version` para comprobar.

**Mac:** descarga el instalador desde <https://www.python.org/downloads/> y ábrelo. Luego comprueba con `python3 --version`.

**Linux:** casi todas las distribuciones lo traen. Si no, instálalo con tu gestor de paquetes (por ejemplo `sudo apt install python3`).

---

## 3. Descargar desde GitHub

Hay dos formas. La **A** es la más fácil y no necesita saber nada de GitHub.

### Opción A · Descargar el ZIP (recomendada)

1. Entra a **<https://github.com/mile-sof/CUADRE>**.
2. Pulsa el botón verde **`<> Code`** (arriba a la derecha de la lista de archivos).
3. En el menú que se abre, elige **`Download ZIP`**. Se descarga un archivo llamado `CUADRE-main.zip`.
4. Ve a tu carpeta **Descargas**, haz **clic derecho** sobre `CUADRE-main.zip` y elige **Extraer todo…** (en Mac: doble clic).
5. Se crea la carpeta **`CUADRE-main`**. Muévela a un lugar fácil, por ejemplo **Documentos** o el **Escritorio**.

> ⚠️ **No abras el programa desde dentro del ZIP.** Siempre extrae primero. Es el error más común.

### Opción B · Con Git (para quien ya lo usa)

```
git clone https://github.com/mile-sof/CUADRE.git
cd CUADRE
```

---

## 4. Abrir el programa

**Windows:** entra a la carpeta y haz **doble clic en `iniciar.bat`**.

> Si Windows muestra «Windows protegió tu PC»: pulsa **Más información** y luego **Ejecutar de todas formas**. Aparece porque el archivo viene de internet; el programa no instala nada ni se conecta a internet.

**Mac y Linux:** abre una terminal dentro de la carpeta y escribe:

```
python3 app.py
```

(o `bash iniciar.sh`).

Se abre una **ventana negra** con un texto como este:

```
================================================
 Cuadre - cuadra tus costos, cuida tu utilidad
================================================
 Abre en tu navegador:  http://127.0.0.1:5000
 Usuario: admin   Contrasena: admin123   (cambiala al entrar)
 Para cerrar el sistema, cierra esta ventana.
================================================
```

- **Déjala abierta**: es el programa funcionando. Si la cierras, el programa se detiene.
- El navegador se abre solo. Si no, escribe en tu navegador la dirección que aparece en la ventana (normalmente **http://127.0.0.1:5000**).
- Si el puerto 5000 estaba ocupado, el programa usa otro y te lo indica en esa misma ventana.

---

## 5. Primer ingreso

Entra con:

| Usuario | Contraseña | Para qué sirve |
|---|---|---|
| `admin` | `admin123` | **Administrador**: puede hacer todo |
| `estudiante` | `estudiante123` | Solo registra producción y costos; no borra ni cambia catálogos |

**Cambia la contraseña ahora:** botón **Contraseña** (arriba a la derecha).

Al entrar por primera vez el programa está **vacío**:

---

## 6. Crear tu empresa y tu periodo

**Empresa** (menú *Empresas* → *Nueva empresa*). Escribe el nombre y el NIT.

- **Impuesto al consumo:** viene en **8 %**, que es el de restaurantes y bares. Los precios de venta que escribas son los del público (con el impuesto incluido); el programa lo descuenta para calcular ingresos y margen. Si tu negocio no lo cobra, desmarca la casilla.
- **Utilidad deseada:** con ella el programa te sugiere el precio de venta de cada producto.
- **Costo logístico:** el aumento del costo de lo que no recibes en la sucursal (por ejemplo, lo que llega del CEDIS o de un almacén).

**Periodo** (menú *Periodos* → *Nuevo periodo*): por ejemplo *Octubre 2026*, del 1 al 31. Arriba verás la empresa y el periodo activos; todo lo que hagas queda en ese periodo.

---

## 7. Cargar tus datos

### Opción A · Importar tu libro de Excel (la más rápida)

El programa lee un libro de Excel con **dos hojas**: **Insumos** (lo que compras) y **Platillos** (tus productos con su receta, los gastos del mes y las unidades que vendes).

1. Menú **Importar de Excel**.
2. Pulsa **Elegir libro de Excel** y selecciona tu archivo. **No necesitas ninguna plantilla si ya tienes tu libro.**
3. El programa lo **revisa antes de guardar** y te muestra qué va a crear o actualizar, y los supuestos que tomó:

4. Si todo está bien, pulsa **Importar a …**. Si hay errores, te dice la hoja, la fila y qué corregir, y **no se guarda nada** hasta que esté bien.

**¿Quieres probar primero?** Usa el libro de ejemplo `ejemplos/libro-cuadre-ejemplo.xlsx` (datos inventados de un restaurante llamado «Cocina La Ceiba»).

**¿Quieres empezar de cero?** Usa la plantilla `plantillas/libro-cuadre-plantilla.xlsx` (o descárgala desde el mismo programa: botón *Descargar plantilla vacía*). Sigue las instrucciones de su primera hoja. Importar el mismo libro otra vez **actualiza** lo que ya existe, no lo duplica.

### Opción B · Escribir los datos en el programa

Menús **Materias primas**, **Mano de obra**, **CIF**, **Productos** y **Hoja estándar**. Cada pantalla tiene también los botones **Exportar** e **Importar** (Excel; las plantillas se llaman `cuadre-plantilla-<módulo>.xlsx` y están en la carpeta `plantillas`).

En **Materias primas** basta con el costo de compra, la cantidad, la merma y dónde lo recibes: el costo por unidad se calcula solo.

---

## 8. Ver tus costos y tu utilidad

Menú **Hoja estándar**: cuánto debería costar una unidad de cada producto, con el resumen del mes según las unidades que vendes.

Pulsa un producto para ver el detalle: materia prima, mano de obra, CIF, margen y el **precio sugerido** para tu utilidad deseada.

---

## 9. Registrar la producción real y ver variaciones

El costo **estándar** es lo que *debería* costar. Para compararlo con lo que **realmente** costó:

1. Menú **Órdenes de producción** → **Nueva orden** (producto, cantidad planificada, fechas).
2. Dentro de la orden, pestaña **Producción**: unidades terminadas y en proceso.
3. Pestaña **Costos reales**: lo que realmente se consumió (materia prima) y las horas trabajadas.
4. Pestaña **Hoja de costos**: estándar frente a real, línea por línea, con producto terminado y en proceso.

Menú **Variaciones**: por qué el costo real se aleja del estándar (precio y cantidad de materia prima, tarifa y eficiencia de mano de obra, presupuesto y volumen del CIF). Positivo es **desfavorable** (costó más); negativo es **favorable**.

---

## 10. Reportes: Excel, PDF e imprimir

Menú **Reportes**: hoja de costos de una orden, resumen por producto, variaciones, CIF y producción. Cada uno se ve en pantalla y se **exporta a Excel o PDF** o se **imprime**.

---

## 11. Cada día: abrir y cerrar

- **Abrir:** doble clic en `iniciar.bat` (Windows) o `python3 app.py` (Mac/Linux). Espera a que se abra el navegador.
- **Cerrar:** pulsa **Salir** en el programa y luego **cierra la ventana negra**.

---

## 12. Respaldo y actualización

Todo lo que escribes vive en un solo archivo: **`data/cuadre.db`**.

- **Respaldo:** con el programa cerrado, copia `data/cuadre.db` (y `config.json`) a una USB o a tu nube. Para restaurar, vuelve a ponerlos en esa carpeta.
- **Actualizar a una versión nueva:** descarga el ZIP nuevo, extráelo, y **copia a la carpeta nueva** tu `data/cuadre.db` y tu `config.json`. El programa actualiza solo la base de datos al abrirla.
- **Empezar con datos de demostración:** en `config.json` pon `"datos_demo": true` y borra `data/cuadre.db` antes de abrir.

---

## 13. Problemas frecuentes

| Qué pasa | Qué hacer |
|---|---|
| «No se encontró Python» | Instala Python (paso 2) y marca **Add python.exe to PATH**. |
| «Falta app.py» o «Falta la carpeta libs» | Abriste el programa desde dentro del ZIP. Extrae **todo** primero (paso 3). |
| La ventana negra se cierra sola | Abre `iniciar.bat` otra vez y fíjate en el mensaje, o escribe `python app.py` en una terminal dentro de la carpeta para verlo. |
| «Windows protegió tu PC» | Más información → Ejecutar de todas formas (paso 4). |
| El navegador no abre la página | Usa la dirección exacta que muestra la ventana negra. Debe seguir abierta. |
| «Usuario o contraseña incorrectos» | Usa `admin` / `admin123`. Tras 5 intentos fallidos se bloquea 5 minutos. |
| Olvidé mi contraseña de administrador | Mira «Recuperar contraseña» en [`docs/MANUAL_TECNICO.md`](docs/MANUAL_TECNICO.md). |
| No puedo descargar la plantilla | Está en la carpeta `plantillas`. O pega en el navegador `http://127.0.0.1:5000/plantillas/libro-cuadre-plantilla.xlsx`. |
| Un periodo no me deja cambiar datos | Está **cerrado**. Un administrador puede reabrirlo en *Periodos*. |

---

## 14. Cómo se llama cada cosa

| Qué | Nombre |
|---|---|
| El programa | **Cuadre** (de *cuadrar*) |
| El formato de libro de Excel que importa | **Libro Cuadre** (`libro-cuadre-plantilla.xlsx`, ejemplo en `ejemplos/libro-cuadre-ejemplo.xlsx`) |
| Plantillas por módulo | `cuadre-plantilla-<módulo>.xlsx` |
| Archivos que exporta | `cuadre-<lo-que-sea>-<fecha>.xlsx` o `.pdf` |
| Tus datos | `data/cuadre.db` |
| Ejecutable (si lo generas) | `Cuadre.exe` |
| Empresa de demostración | «Fogón del Sinú» |
| Restaurante del libro de ejemplo | «Cocina La Ceiba» |

Si venías de una versión anterior (cuando el programa se llamaba *Costeo*), no pierdes nada: al abrirlo, Cuadre pasa tu archivo `data/costos.db` a `data/cuadre.db` automáticamente.

---

## 15. Para quien quiera saber más

- **Manual técnico** (arquitectura, fórmulas, API, seguridad, respaldo): [`docs/MANUAL_TECNICO.md`](docs/MANUAL_TECNICO.md)
- **Generar un `.exe`** para usarlo sin instalar Python: `build_exe.bat` (en un equipo Windows con Python e internet; el resultado queda en `dist\Cuadre`).
- Hecho con Python, Flask y SQLite; la interfaz es HTML, CSS y JavaScript sin librerías externas.



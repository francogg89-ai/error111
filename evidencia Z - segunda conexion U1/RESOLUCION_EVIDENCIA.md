# Resolución descriptiva — segunda conexión real U1

## Identidad y alcance

- Trabajo: `ideas-audiencia-ia`, carril Z, unidad 1.
- Contratos congelados: `C-U1-2A` y `C-U1-2B`.
- Auditoría de congelamiento: `audit-chatgpt-z @ 7e07a0100295758cd169d410cdfbee3d18123acb`.
- Candidato ejecutado: `work-claude-z @ cb023ed6c53dd63470da9463a6ea1697294f1055`.
- Checkpoint ejecutado: `unidad-1-viabilidad-ia-contratada/CHECKPOINT_HUMANO.md`.
- Fecha de ejecución: 2026-09-12.
- Cuenta declarada: ChatGPT Plus personal.
- Administrador necesario: no.
- Exposición aceptada: Quick Tunnel aleatorio de Cloudflare, únicamente durante la prueba.
- Límite de ChatGPT observado: ninguno; el ejecutor declaró estar lejos del límite.

Este documento transcribe y organiza la evidencia observada. No emite un veredicto sobre los contratos ni decide el cierre de U1; esas decisiones corresponden al auditor y al humano.

## Puertas previas

### G-1 — candidato exacto

```text
git diff --quiet cb023ed6c53dd63470da9463a6ea1697294f1055 -- .
$LASTEXITCODE
0
git status --porcelain -- .
[sin salida]
```

### G0 — entorno

```text
Python 3.12.4
............................................................ [100%]
60 passed in 18.03s
```

### G1 — sonda

El ejecutor informó que `probe.launch --fresh` inició la sonda en `127.0.0.1:8000` en modo público y dejó la ventana activa durante la prueba.

### Quick Tunnel

```text
cloudflared version 2026.9.1 (built 2026-09-10T13:52 UTC)
Registered tunnel connection
location=gru07
protocol=quic
```

La URL base pública se utilizó para G2. La URL portadora y el token no se incluyen en este paquete.

### G2 — exposición certificada

```json
{
  "ok": true,
  "tools": [
    "get_evaluations",
    "get_proposal",
    "list_proposals",
    "save_evaluation",
    "show_proposal"
  ],
  "without_token": 404,
  "invalid_token": 404,
  "error": ""
}
```

```text
EXPOSICION LISTA
$LASTEXITCODE = 0
```

## Preparación en ChatGPT

- Marcador `inicio-chatgpt` registrado a `2026-09-12T13:01:58.279867+00:00`.
- Developer mode confirmado como activo.
- App de la corrida anterior eliminada.
- App creada: `Sonda propuestas U1 v2`.
- Conexión elegida: URL pública, no Tunnel.
- Autenticación: No Authentication.
- La URL portadora pasó del disco al portapapeles mediante `probe.url copiar`, se pegó únicamente en el campo URL y el portapapeles se limpió enseguida mediante `probe.url limpiar`.
- El escaneo encontró las cinco herramientas enumeradas en G2.
- ChatGPT no pidió confirmación al crear o conectar la app.
- La captura `01-app-conectada.png` documenta la conexión y parte del listado de acciones sin mostrar el secreto.

## Primera conversación

Las cinco peticiones se enviaron en el orden y con el texto fijados por el checkpoint.

### Petición 1

```text
Usá la app de propuestas para listar todas las propuestas de la convocatoria y decime cuántas hay y el identificador de la primera y de la última.
```

Respuesta informada:

```text
Hay 100 propuestas en total.
- Primera: P-001
- Última: P-100
```

No hubo confirmación. Inicialmente el ejecutor informó que no veía una llamada; después advirtió que `Sonda propuestas U1 v2` figuraba en el panel `Sources`, como también en las demás respuestas.

### Petición 2

```text
Traé el texto original completo de la propuesta P-042 y decime si incluye algún dato de contacto.
```

La vista de la app mostró:

```text
Id: P-042
Propuesta: [SINTETICO] Propongo un especial sobre música independiente.
Por qué aporta: Aporta porque permite participación en directo.
Ejemplo:
Huella de lo mostrado: bac7f90c
Huella del servidor: bac7f90c
Coinciden: SI
```

El texto redactado por ChatGPT debajo de la vista utilizó `[SINTÉTICO]` y afirmó que no había datos de contacto. No hubo confirmación. La captura `02-peticion-2-vista-y-texto.png` distingue la vista de la redacción del modelo.

### Petición 3

```text
Mostrá la propuesta P-042 en la vista de la app, tal como se recibió.
```

La vista renderizada mostró literalmente:

```text
Huella de lo mostrado: bac7f90c
Huella del servidor: bac7f90c
Coinciden: SI
```

La vista y la respuesta del modelo se distinguen en `03-peticion-3-vista.png`. No hubo confirmación.

### Petición 4

```text
Guardá para P-042 una evaluación con resultado duda, razones "prueba real C1.3" y dudas "ninguna". Después leé las evaluaciones guardadas de P-042 y mostrámelas.
```

Respuesta informada:

```text
Evaluación guardada correctamente para P-042.
Resultado: duda
Razones: prueba real C1.3
Dudas: ninguna
ID de evaluación: 1
Guardada: 2026-09-12 13:14:57 UTC
Actualmente, esa es la única evaluación guardada para P-042.
```

No hubo confirmación. Inicialmente el ejecutor no identificó un bloque de llamada en línea; posteriormente aclaró que la app figuró en `Sources` durante todas las respuestas.

### Petición 5

```text
Traé la propuesta X-001.
```

Respuesta:

```text
La propuesta X-001 no está disponible en esta convocatoria.
```

No hubo confirmación. La captura `04-peticion-5-X001.png` muestra la app y la respuesta.

## Única repetición admitida

Debido a la interpretación inicial de que las peticiones 1 y 4 no habían mostrado llamadas, se realizó una única repetición completa en una conversación nueva, antes del marcador de capacidad inválida. Durante esa repetición el ejecutor comprobó que la app aparecía en `Sources`. No hubo confirmaciones, errores ni restricciones.

Resultados observados:

1. ChatGPT volvió a informar 100 propuestas, primera `P-001` y última `P-100`. `05-sources-repeticion.png` muestra la app en `Sources`.
2. ChatGPT recuperó `P-042`, redactó `[SINTÉTICO]` y afirmó que no contenía datos de contacto.
3. La vista volvió a mostrar `bac7f90c`, `bac7f90c` y `SI`; se documenta en `06-peticion-3-repeticion.png`.
4. Se guardó la evaluación ID `2` y se recuperaron las dos evaluaciones idénticas; se documenta en `07-evaluaciones-repeticion.png`.
5. ChatGPT volvió a informar que `X-001` no estaba disponible.

## Control de capacidad inválida

- Marcador `inicio-intento-capacidad-invalida`: `2026-09-12T13:31:59.296787+00:00`.
- Se preparó una segunda app por URL pública y sin autenticación.
- `probe.url copiar-invalida` cargó la URL inválida en el portapapeles; se pegó únicamente en el campo URL y `probe.url limpiar` limpió el portapapeles inmediatamente.
- Se intentó crear la app una sola vez.
- La app no se creó y no se descubrió ninguna herramienta; por ello no existió una app inválida utilizable.
- Mensaje literal de ChatGPT:

```text
Error creating connector
Something went wrong. If this issue persists please contact us through our help center at help.openai.com.
```

- `08-error-capacidad-invalida.png` documenta el rechazo. El campo URL solo muestra visualmente el comienzo truncado de la URL base pública; no muestra el token ni la ruta portadora.

La exportación registra entre `inicio-intento-capacidad-invalida` y `fin` dos solicitudes `POST` y una solicitud `GET`, todas con `path_ok=false`, respuesta `404` y `User-Agent: openai-mcp/1.0.0`. No registra llamadas a herramientas en ese intervalo.

## Cierre y exportación

- Marcador `fin`: `2026-09-12T13:34:35.628959+00:00`.
- Duración entre `inicio-chatgpt` y `fin`: 32 minutos y 37 segundos.
- El túnel se cerró primero con `Ctrl+C` y volvió a PowerShell.
- La sonda se cerró después con `Ctrl+C` y volvió a PowerShell.
- Exportación ejecutada:

```text
.\.venv\Scripts\python.exe -m probe.export .data\evidencia-servidor.json
Evidencia escrita en .data\evidencia-servidor.json
```

## Resumen factual de la exportación

- Solicitudes: 28.
- Llamadas a herramientas: 12.
- Evaluaciones almacenadas: 2.
- Primera conversación: seis llamadas a herramientas.
- Repetición: seis llamadas a herramientas.
- `P-042`: llamadas correctas mediante `show_proposal` o `get_proposal`, todas con `original_fp=bac7f90c`.
- `show_proposal` se invocó correctamente en ambas conversaciones.
- La plantilla de la vista fue solicitada mediante `resources/read` con `User-Agent: openai-mcp/1.0.0`.
- Se registraron dos pares correctos `save_evaluation` → `get_evaluations`.
- `X-001` produjo una llamada fallida en cada conversación y no se devolvió contenido de propuesta.
- Todas las solicitudes con ruta correcta y respuesta `2xx` entre `inicio-chatgpt` e `inicio-intento-capacidad-invalida` tienen un `User-Agent` que comienza con `openai-mcp/`.
- El intervalo de capacidad inválida contiene tres respuestas `404`, ninguna solicitud aceptada y ninguna llamada a herramientas.

## Confirmaciones, acciones humanas e incidencias

- Confirmaciones solicitadas por ChatGPT durante creación, conexión, lectura, vista, escritura y control inválido: ninguna.
- Acciones humanas: activar/verificar Developer mode; eliminar la app anterior; crear y seleccionar la app válida; enviar cada petición; observar `Sources`; capturar las vistas; copiar y limpiar ambas URLs mediante los comandos establecidos; intentar una vez la creación inválida; cerrar túnel y sonda; exportar la evidencia.
- No hizo falta un administrador.
- No apareció ningún límite de uso de ChatGPT.
- No se informó que el token o la URL portadora se hubieran mostrado o pegado fuera del campo de ChatGPT.
- La única ambigüedad de interfaz informada fue que la atribución a la app aparecía en el panel `Sources`, aunque no siempre había un bloque de llamada en línea.
- Único error de producto observado: el mensaje literal del control de capacidad inválida transcrito arriba.

## Archivos

- `evidencia-servidor.json`: exportación original de la sonda.
- `01-app-conectada.png`: app válida conectada y acciones visibles.
- `02-peticion-2-vista-y-texto.png`: vista fiel junto al texto regenerado por ChatGPT.
- `03-peticion-3-vista.png`: evidencia principal de la vista de la primera conversación.
- `04-peticion-5-X001.png`: rechazo de identificador fuera de alcance.
- `05-sources-repeticion.png`: atribución de la app en `Sources` durante la repetición.
- `06-peticion-3-repeticion.png`: vista de la repetición.
- `07-evaluaciones-repeticion.png`: dos evaluaciones recuperadas.
- `08-error-capacidad-invalida.png`: mensaje exacto del intento inválido.

SHA-256 de `evidencia-servidor.json`:

```text
a346857235534d044e4121b179b197df4bd71c32fde12b1e21512de0051bf2b6
```

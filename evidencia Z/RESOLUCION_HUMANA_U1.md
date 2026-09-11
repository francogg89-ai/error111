# Resolución humana U1 — conexión real de la sonda con ChatGPT

```text
WORK_ID=ideas-audiencia-ia
CARRIL=Z
UNIDAD=unidad-1-viabilidad-ia-contratada
AUDIT_SHA=e246b058de80ca83d3a4d2db189124a2fce62c5e
WORK_SHA_CONGELADO=f181d3728b7e8fa09045a1f0ac6acd11f9e407e5
PLAN_CUENTA=ChatGPT Plus personal
ADMINISTRADOR_REQUERIDO=NO
QUICK_TUNNEL_ACEPTADO=SI
CONEXION_REAL_EJECUTADA=SI
```

## Puertas previas

### G-1 — aprobada

- `git diff --quiet f181d3728b7e8fa09045a1f0ac6acd11f9e407e5 -- .` devolvió `0`.
- `git status --porcelain -- .` no imprimió ninguna línea.

### G0 — aprobada

- Python `3.12.4`.
- `pytest`: `43 passed in 16.11s`.
- No hubo `failed` ni `error`.

### G1 — aprobada

- La sonda informó: `Sonda escuchando en http://127.0.0.1:8000 (modo publico)`.

### Túnel

- `cloudflared version 2026.9.0`.
- Quick Tunnel creado y conexión registrada mediante QUIC.
- Los precontroles de DNS, UDP, TCP y Cloudflare API informaron `PASS`.

### G2 — aprobada

```text
ok=true
tools=get_evaluations,get_proposal,list_proposals,save_evaluation
without_token=404
invalid_token=404
error=
EXPOSICION LISTA
LASTEXITCODE=0
```

## Configuración de ChatGPT

- La opción `Developer mode` existía en la cuenta y pudo activarse.
- No pidió confirmación al activarla.
- Primera app creada con nombre `Sonda propuestas U1`, conexión por URL pública y `No Authentication`.
- El escaneo encontró `get_evaluations`, `get_proposal`, `list_proposals` y `save_evaluation`.
- ChatGPT mostró una confirmación con el botón `Connect` para conectar la primera app; fue aceptada.
- Se abrió una conversación nueva con la app seleccionada.

## Transcripción de la conversación de prueba

### Petición 1

**Humano:**

> Usá la app de propuestas para listar todas las propuestas de la convocatoria y decime cuántas hay y el identificador de la primera y de la última.

**ChatGPT:**

> La convocatoria contiene **100 propuestas**.
>
> - Primera: `P-001`
> - Última: `P-100`
>
> El listado está completo: la app no devolvió una página siguiente.

Confirmación antes de usar la herramienta: **no**.

### Petición 2

**Humano:**

> Traé el texto original completo de la propuesta P-042 y decime si incluye algún dato de contacto.

**ChatGPT:**

> Texto original completo de `P-042`:
>
> **Propuesta:** “[SINTÉTICO] Propongo un especial sobre música independiente.”
>
> **Motivo:** “Aporta porque permite participación en directo.”
>
> **Ejemplo:** vacío.
>
> No incluye ningún dato de contacto. La app tampoco devuelve campos de contacto.

Confirmación antes de usar la herramienta: **no**.

### Petición 3

**Humano:**

> Guardá para P-042 una evaluación con resultado duda, razones "prueba real C1.3" y dudas "ninguna". Después leé las evaluaciones guardadas de P-042 y mostrámelas.

**ChatGPT:**

> Evaluación guardada y verificada para `P-042`:
>
> - ID: `1`
> - Resultado: `duda`
> - Razones: `prueba real C1.3`
> - Dudas: `ninguna`
> - Guardada: `2026-09-11 01:25:28 UTC`
>
> Actualmente es la única evaluación registrada para esa propuesta.

Confirmación antes de la escritura: **no**.

### Petición 4

**Humano:**

> Traé la propuesta X-001.

**ChatGPT:**

> La propuesta `X-001` no está disponible en esta convocatoria. La app rechazó el identificador como inválido.

Confirmación antes de usar la herramienta: **no**.

## Control de capacidad inválida

Después del marcador `inicio-intento-capacidad-invalida` se intentó crear una segunda app, una sola vez, con la URL inválida producida por G2, conexión por URL pública y `No Authentication`.

La app no pudo crearse. Mensaje literal:

> **Error creating connector**
>
> Something went wrong. If this issue persists please contact us through our help center at help.openai.com.

Momento exacto: al crear/conectar la segunda app después de pegar la URL con capacidad inválida.

No se reintentó ni se modificó la URL. No fue posible usar la segunda app en una conversación porque no llegó a crearse. La captura del mensaje se conserva junto con esta resolución.

## Cierre y evidencia servidor

- Se registró el marcador `fin`.
- Se cerraron `cloudflared` y la sonda con `Ctrl+C`; ambas ventanas volvieron a PowerShell.
- Se exportó `evidencia-servidor.json`.
- Duración entre `inicio-chatgpt` y `fin`: **18 minutos 50,638 segundos**.
- No se observaron límites de uso.

Validación del archivo adjunto:

```text
ARCHIVO=evidencia-servidor.json
BYTES=8813
SHA256=e0097aa99d79c0bc9d18c9dd29119c0c404da6430b19c16b5f08360703c13502
REQUESTS=22
CALLS=5
EVALUATIONS=1
```

La exportación registra:

- `list_proposals` con `limit=100`, correcto;
- `get_proposal` de `P-042`, correcto;
- `save_evaluation` de `P-042`, correcto;
- `get_evaluations` posterior, correcto;
- `get_proposal` de `X-001`, con error;
- en el intervalo inválido, 6 solicitudes HTTP, 4 respuestas `404`, 0 rutas aceptadas y 0 llamadas a herramientas;
- una evaluación almacenada con los valores solicitados.

El JSON contiene el hostname público necesario para la trazabilidad HTTP, pero no contiene el token, ninguna ruta `/mcp/` ni los archivos locales que contenían las URLs.

## Incidencia durante la asistencia

Durante la asistencia humana se copió accidentalmente la URL completa de la primera app en la conversación del agente externo, exponiendo allí el token portador. El valor no se reproduce en esta resolución ni en ningún archivo del commit.

No se reinició ni se repitió la prueba. El túnel y la sonda fueron cerrados al finalizar. La incidencia se entrega para que el AUDITOR determine su efecto conforme al contrato congelado.

## Interpretación reservada

Esta pieza registra la ejecución y la evidencia reportada. No decide el veredicto, la atribución causal, el cierre de U1 ni cambios de plan, mecanismo, manifiesto o alcance. Corresponde al AUDITOR interpretar el resultado contra el contrato congelado.

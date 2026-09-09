# CONSTITUCION INICIAL — PUENTE G

WORK_ID=reconstruccion-dev-vita-delta
CARRIL=G
UNIDAD=U06_N8N_DEV

## Autoridades

METODO_TECNICO_REF=b9ff578224b5705ba1ed2716865c374b86d72b87

RULES_REPO=francogg89-ai/rules-orchestrator-ai
RULES_PATH=REGLAS-ORQUESTADOR.md
RULES_SHA=e04e653fe6b9d3f394c18dee18274090ddb79ff9

TRANSPORT_REPO=francogg89-ai/orchestra-revolutions-ai
TRANSPORT_PATH=metodo/REVOLUTIONS.md
TRANSPORT_SHA=4d88fce3ed3c87bd231c45ec60dcb713538b2514

El método técnico viejo fijado por METODO_TECNICO_REF conserva toda autoridad sobre materia, eventos, auditorías, unidades, relevos y necesidades humanas del carril G. De TRANSPORT_SHA se adopta exclusivamente revolutions-hop/v1 y su turn_id. No se migra el carril al método técnico nuevo.

## Repositorios y runtimes

WORK_REPO=francogg89-ai/work-claude-g
AUDIT_REPO=francogg89-ai/audit-chatgpt-g
RAMA=main
AUDITOR_RUNTIME=ChatGPT web
CONSTRUCTOR_RUNTIME=Claude Code local
CONSTRUCTOR_LOCAL_PATH=C:/Franco_VitaDelta/work-claude-g
AUDITOR_LOCAL_PATH=C:/Franco_VitaDelta/audit-chatgpt-g

## Arranque

El AUDITOR inicial lee esta constitución en el SHA indicado por auditor-init/v1 y luego lee, en ese mismo SHA:

G/PROMPT_AUDITOR_FRESCO.md
G/PROMPT_CONSTRUCTOR_FRESCO.md

Ejecuta PROMPT_AUDITOR_FRESCO.md. La auditoría de handoff ya fue publicada en audit-chatgpt-g @ b020b604dc0bdb9ac4bc40e4c974712b7aaa62e0. La rederiva y verifica sin publicar otra auditoría. Si queda conforme, emite el primer sobre con turn_id=1 hacia CONSTRUCTOR fresh y materializa PROMPT_CONSTRUCTOR_FRESCO.md sustituyendo <INCOMING_TURN_ID> por 1, <AUDIT_SHA_POST_HANDOFF> por b020b604dc0bdb9ac4bc40e4c974712b7aaa62e0 y <BRIDGE_SHA_DEL_LOCATOR> por el CONSTITUTION_SHA recibido literalmente en auditor-init/v1.

## Contrato permanente de salida mínima

Cada intervención responde exclusivamente con un único bloque cercado etiquetado json y nada antes ni después. Dentro del bloque existe un único objeto JSON válido con exactamente los campos de revolutions-hop/v1. Las llaves sin bloque cercado no cumplen la forma de transporte.

Cuando continúa el loop, next_prompt contiene sólo cabecera mínima, cortes Git exactos, SHA/path relevante, próxima acción irreducible, comprobaciones, prohibiciones y condición de terminación. No incluye saludo, narrativa, resultados ya preservados ni conclusiones rederivables desde Git.

INCOMING_TURN_ID dentro de next_prompt es exactamente el turn_id del sobre que lo transporta. El receptor emite turn_id=INCOMING_TURN_ID+1.

El AUDITOR inicial toma CONSTITUTION_SHA_RECIBIDO literalmente del locator auditor-init/v1. Al materializar el primer prompt del CONSTRUCTOR sustituye <BRIDGE_SHA_DEL_LOCATOR> por CONSTITUTION_SHA_RECIBIDO. El placeholder nunca llega al receptor.

Desde ese primer salto, todo next_prompt conserva BRIDGE_REPO, BRIDGE_PATH y el BRIDGE_SHA concreto recibido. Un actor fresh debe leerlos antes de actuar; un actor current puede revalidarlos. Estas coordenadas no sustituyen WORK_SHA ni AUDIT_SHA.

El CONSTRUCTOR siempre vuelve al AUDITOR. Sólo el AUDITOR decide veredictos, continuidad, finalización, relevo y necesidad humana. next_instance es current salvo relevo decidido durablemente conforme al método técnico viejo.

## Necesidad humana

Para detener el transporte, únicamente el AUDITOR emite human_need distinto de null y deja next_actor, next_instance y next_prompt en null.

El request empieza con "NECESIDAD DEL HUMANO" y dice únicamente qué necesita Franco y que debe entregar work-claude-g y audit-chatgpt-g a un agente externo fresco para que rederive desde Git y lo guíe. No se exige checkpoint, guide_prompt ni trabajo administrativo adicional para esta notificación; checkpoint=null y guide_prompt=null. expected_evidence indica qué resolución debe volver si se pretende reanudar.

El ORQUESTADOR se detiene y muestra la necesidad. No abre al agente externo, no modifica repositorios y no inventa la resolución.
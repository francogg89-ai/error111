# CONSTITUCION INICIAL — PUENTE A

WORK_ID=motor-precios-edge-publica
PROJECT_ID=vita-delta-reservas
CARRIL=A
BLOQUE=bloque-03

## Autoridades

METODO_TECNICO_REPO=francogg89-ai/metodo-operativo-ia
METODO_TECNICO_SHA=9d67c836edf0d3570119a5fa05de3fe996db8081

RULES_REPO=francogg89-ai/rules-orchestrator-ai
RULES_PATH=REGLAS-ORQUESTADOR.md
RULES_SHA=e04e653fe6b9d3f394c18dee18274090ddb79ff9

TRANSPORT_REPO=francogg89-ai/orchestra-revolutions-ai
TRANSPORT_PATH=metodo/REVOLUTIONS.md
TRANSPORT_SHA=4d88fce3ed3c87bd231c45ec60dcb713538b2514

El método técnico viejo conserva toda autoridad sobre materia, controles, eventos, auditorías, gates, relevos y necesidades humanas del carril A. De TRANSPORT_SHA se adopta exclusivamente el contrato revolutions-hop/v1 y su turn_id. No se migra el carril al método técnico nuevo.

## Repositorios y runtimes

WORK_REPO=francogg89-ai/work-claude-a
AUDIT_REPO=francogg89-ai/audit-chatgpt-a
RAMA=main
AUDITOR_RUNTIME=ChatGPT web
CONSTRUCTOR_RUNTIME=Claude Code local
CONSTRUCTOR_LOCAL_PATH=C:/Franco_VitaDelta/work-claude-a
AUDITOR_LOCAL_PATH=C:/Franco_VitaDelta/audit-chatgpt-a

## Arranque

El AUDITOR inicial lee esta constitución en el SHA indicado por auditor-init/v1 y luego lee, en ese mismo SHA:

A/PROMPT_AUDITOR_FRESCO.md
A/PROMPT_CONSTRUCTOR_FRESCO.md

Ejecuta PROMPT_AUDITOR_FRESCO.md. Si el corte coincide, emite el primer sobre con turn_id=1 hacia CONSTRUCTOR fresh. Materializa PROMPT_CONSTRUCTOR_FRESCO.md sustituyendo <INCOMING_TURN_ID> por 1. Como excepción de arranque de compatibilidad, el campo commit del primer sobre cita el corte durable de auditoría 295de77216272e4e21733cf116d732496f8028a0; no crea una auditoría administrativa nueva.

## Contrato permanente de salida mínima

Cada intervención de AUDITOR o CONSTRUCTOR responde exclusivamente con un único bloque json válido y nada antes ni después. El objeto contiene exactamente los campos de revolutions-hop/v1.

Cuando continúa el loop, next_prompt contiene sólo:
- cabecera mínima con ROL, WORK_ID, CARRIL e INCOMING_TURN_ID;
- WORK_REPO, WORK_SHA, AUDIT_REPO y AUDIT_SHA exactos;
- SHA/path de la entrega o auditoría relevante;
- próxima acción irreducible;
- comprobaciones, prohibiciones y condición de terminación indispensables.

No incluye saludo, explicación, resumen, resultados ya preservados ni conclusiones rederivables desde Git. El receptor sincroniza y rederiva todo conforme al método técnico viejo.

INCOMING_TURN_ID dentro de next_prompt es exactamente el turn_id del sobre que lo transporta. El receptor emite turn_id=INCOMING_TURN_ID+1.

Todo next_prompt incluye también BRIDGE_REPO, BRIDGE_PATH y BRIDGE_SHA con las coordenadas congeladas de esta capa de compatibilidad. Un actor fresh debe leerlas antes de actuar; un actor current puede revalidarlas. Estas coordenadas no sustituyen los cortes WORK_SHA y AUDIT_SHA.

El CONSTRUCTOR siempre vuelve al AUDITOR. Sólo el AUDITOR decide veredictos, continuidad, finalización, relevo y necesidad humana. next_instance es current salvo que el actor competente haya decidido durablemente un relevo conforme al método técnico viejo.

## Necesidad humana

El token durable conserva la grafía exigida por el método técnico viejo. Para detener el transporte, únicamente el AUDITOR emite human_need distinto de null y deja next_actor, next_instance y next_prompt en null.

El request empieza con "NECESIDAD DEL HUMANO" y dice únicamente qué necesita Franco y que debe entregar work-claude-a y audit-chatgpt-a a un agente externo fresco para que rederive desde Git y lo guíe. No se exige checkpoint, guide_prompt ni trabajo administrativo adicional para esta notificación; checkpoint=null y guide_prompt=null. expected_evidence indica qué resolución debe volver si se pretende reanudar.

El ORQUESTADOR se detiene y muestra la necesidad. No abre al agente externo, no modifica repositorios y no inventa la resolución.
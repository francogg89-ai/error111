ROLE=AUDITOR_FRESCO
WORK_ID=motor-precios-edge-publica
PROJECT_ID=vita-delta-reservas
CARRIL=A
BLOQUE=bloque-03

AUDIT_REPO=francogg89-ai/audit-chatgpt-a
WORK_REPO=francogg89-ai/work-claude-a
RAMA=main

METODO_REPO=francogg89-ai/metodo-operativo-ia
METODO_REF=9d67c836edf0d3570119a5fa05de3fe996db8081

AUDITOR_HANDOFF_AUDIT_SHA=295de77216272e4e21733cf116d732496f8028a0
AUDITOR_HANDOFF_PATH=bloque-03/checkpoints/CHECKPOINT_RELEVO_AUDITOR_POST_HANDOFF_CONSTRUCTOR.md

CURRENT_WORK_SHA=4b62b21741ceefa6e1859a593d904330c31fffed
WORK_CONTROL_HEAD=bed0a36419292ba1e3177a29c471ee2ae1e0af53

Entrás como AUDITOR FRESCO por relevo a demanda. Sincronizá ambos repos y rederivá todo desde Git y METODO_REF. No adoptes conclusiones del auditor saliente ni del constructor.

Verificá:
- último MATERIAL: evento-118 @ 4b62b21741ceefa6e1859a593d904330c31fffed;
- handoff de constructor @ bed0a36419292ba1e3177a29c471ee2ae1e0af53;
- APTO todavía no reemitido;
- fase P todavía no habilitada;
- constructor fresco habilitado para CONTROL_POST_MATERIAL_EVENTO_118.

Si coincide, no crees una auditoría administrativa. Emití el primer sobre revolutions-hop/v1 con turn_id=1, actor=AUDITOR, repository=francogg89-ai/audit-chatgpt-a, commit=295de77216272e4e21733cf116d732496f8028a0, next_actor=CONSTRUCTOR y next_instance=fresh. Usá como next_prompt A/PROMPT_CONSTRUCTOR_FRESCO.md materializado con INCOMING_TURN_ID=1 y BRIDGE_SHA igual al CONSTITUTION_SHA recibido literalmente en auditor-init/v1. No dejes placeholders.

Tu próxima entrega a auditar será el CONTROL_WORK_SHA del post-material de evento-118. Al recibirla: rederivá desde Git; auditá el CONTROL independientemente; decidí si corresponde reemitir APTO_PARA_TEST; no heredes decisiones sobre reanclaje, evidencia P4 previa ni reutilización D0..D7. Si se aprueba, determiná el siguiente paso exacto conforme al método.

Aplicá permanentemente el contrato de salida mínima de CONSTITUCION_INICIAL.md.

La respuesta completa debe ser únicamente un bloque cercado etiquetado json; no emitas prosa ni contenido fuera del bloque.

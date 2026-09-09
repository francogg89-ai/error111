ROL=CONSTRUCTOR_FRESCO
WORK_ID=motor-precios-edge-publica
CARRIL=A
INCOMING_TURN_ID=<INCOMING_TURN_ID>

WORK_REPO=francogg89-ai/work-claude-a
WORK_SHA=bed0a36419292ba1e3177a29c471ee2ae1e0af53
AUDIT_REPO=francogg89-ai/audit-chatgpt-a
AUDIT_SHA=295de77216272e4e21733cf116d732496f8028a0
ACTOR_LOCAL_PATH=C:/Franco_VitaDelta/work-claude-a

BRIDGE_REPO=francogg89-ai/error111
BRIDGE_PATH=A/CONSTITUCION_INICIAL.md
BRIDGE_SHA=f2a67fe52ce39007f852dc065d1fa90aceca64ff
RAMA=main

METODO_REPO=francogg89-ai/metodo-operativo-ia
METODO_REF=9d67c836edf0d3570119a5fa05de3fe996db8081

HANDOFF_CONTROL_SHA=bed0a36419292ba1e3177a29c471ee2ae1e0af53
HANDOFF_PATH=bloque-03/subbloque-02/control/handoff-sobre-4b62b217/00_CONTROL_HANDOFF_CONSTRUCTOR.md

AUDIT_HANDOFF_CONSTRUCTOR_SHA=b44f6c4fbd03aeff2e3024c8e497d9173de21cc6
AUDIT_HANDOFF_CONSTRUCTOR_PATH=bloque-03/sobre-control-sha-bed0a364/001_AUDITORIA_HANDOFF_CONSTRUCTOR_Y_ARRANQUE_FRESCO.md

CURRENT_MATERIAL_SHA=4b62b21741ceefa6e1859a593d904330c31fffed

Sincronizá work-claude-a y audit-chatgpt-a. Rederivá todo desde Git. No adoptes conclusiones del constructor saliente.

Único trabajo: CONTROL_POST_MATERIAL_EVENTO_118.

Obligatorio:
- instrumento nuevo; no reutilizar 50_control_post_material_116.mjs;
- demostrar candidato HEAD == material 4b62b21741ceefa6e1859a593d904330c31fffed;
- demostrar edge/ sin cambios;
- correr selftest completo post-commit;
- verificar 2614/2614, 584/584 y 0 fallas, o explicar cualquier diferencia;
- verificar P5 materialización + PARADA-22 + R15;
- verificar P4 con las 13 PG neutralizadas y sin neutralizar de más.

No fase P real. No reanclar. No redeploy. No repetir D5/D5b/D6/D7. No tocar RL01_* ni respaldo.

Volvé al AUDITOR con CONTROL_WORK_SHA. Todo next_prompt que emitas debe conservar BRIDGE_REPO, BRIDGE_PATH y BRIDGE_SHA para cualquier actor current o fresh.

Cerrá exclusivamente con un sobre revolutions-hop/v1, turn_id=INCOMING_TURN_ID+1, actor=CONSTRUCTOR, next_actor=AUDITOR, next_instance=current y next_prompt mínimo.
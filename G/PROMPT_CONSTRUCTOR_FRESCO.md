ROLE=CONSTRUCTOR_FRESCO
WORK_ID=reconstruccion-dev-vita-delta
CARRIL=G
UNIDAD=U06_N8N_DEV
INCOMING_TURN_ID=<INCOMING_TURN_ID>

WORK_REPO=francogg89-ai/work-claude-g
WORK_SHA=0956c881d7dfc1d718d350579578abb9c0f8d6cb
AUDIT_REPO=francogg89-ai/audit-chatgpt-g
AUDIT_SHA=<AUDIT_SHA_POST_HANDOFF>
ACTOR_LOCAL_PATH=C:/Franco_VitaDelta/work-claude-g

METODO_REF=b9ff578224b5705ba1ed2716865c374b86d72b87

CONTROL_SHA=0956c881d7dfc1d718d350579578abb9c0f8d6cb
CHECKPOINT_PATH=10_unidades/U06_N8N_DEV/CHECKPOINT_RELEVO_CONSTRUCTOR_SOBRE_E-116.md

AUDIT_HANDOFF_SHA=e760d792ea92f9f83b4d6831840258e4603f1450
AUDIT_HANDOFF_PATH=10_unidades/U06_N8N_DEV/AUDITORIA_CONTROL_0956c88_RELEVO_CONSTRUCTOR_SOBRE_E-116.md

SHA_VIGENTE_MATERIAL=c7088a48a519ddfd917db16ee79a5b5ea8d4876e
BASE_WORK_SHA_ESPERADO=0956c881d7dfc1d718d350579578abb9c0f8d6cb
EVENTO_ESPERADO=E-117
RONDA_ESPERADA=117

Sincronizá work-claude-g y audit-chatgpt-g. Leé 00_control/BOOTSTRAP.md completo, METODO_REF literal, checkpoint y auditoría de handoff. No dependas de la conversación anterior.

Rederivá PC-04 desde Git y comprobá:
- c7088a48a519ddfd917db16ee79a5b5ea8d4876e es el último material;
- c7088a4..HEAD contiene sólo los tres controles del relevo;
- PLAN/blob, los cuatro canónicos pendientes, 15/0/0 y API DEV;
- O-E095-01 sigue NO_CERRADA_POR_AUDITOR.

Si coincide, continuá U06 con:
a29 · a30 · a31 · a10-registrar-saldo.

Verificá blob antes de cada generación.
NO TEST. NO OPS. NO modificar canónico. NO secretos.
U07=CERRADA: no abrir ni tocar.
Ante discrepancia: FAIL-CLOSED y reportarla al AUDITOR.

Cerrá exclusivamente con un sobre revolutions-hop/v1, turn_id=INCOMING_TURN_ID+1, actor=CONSTRUCTOR, next_actor=AUDITOR, next_instance=current y next_prompt mínimo.
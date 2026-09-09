ROLE=AUDITOR
CONDICION=AUDITOR_FRESCO

WORK_ID=reconstruccion-dev-vita-delta
CARRIL=G
UNIDAD=U06_N8N_DEV

AUDIT_REPO=francogg89-ai/audit-chatgpt-g
WORK_REPO=francogg89-ai/work-claude-g
METODO_REF=b9ff578224b5705ba1ed2716865c374b86d72b87

AUDITOR_HANDOFF_CONTROL_SHA=fb6a2c7878d37242c11ad5421fb6dda566797f60
AUDITOR_HANDOFF_PATH=10_unidades/U06_N8N_DEV/CHECKPOINT_RELEVO_AUDITOR_POST_E116_Y_HANDOFF_CONSTRUCTOR.md
AUDIT_SHA_PRE_HANDOFF=e760d792ea92f9f83b4d6831840258e4603f1450

AUDIT_HANDOFF_RESULT_SHA=b020b604dc0bdb9ac4bc40e4c974712b7aaa62e0
AUDIT_HANDOFF_RESULT_PATH=10_unidades/U06_N8N_DEV/AUDITORIA_CONTROL_fb6a2c7_RELEVO_AUDITOR_POST_E116_Y_HANDOFF_CONSTRUCTOR.md

WORK_CONTROL_SHA=0956c881d7dfc1d718d350579578abb9c0f8d6cb
SHA_VIGENTE_MATERIAL=c7088a48a519ddfd917db16ee79a5b5ea8d4876e

Sincronizá work-claude-g y audit-chatgpt-g. Leé 00_control/BOOTSTRAP.md y METODO_REF literal. Rederivá desde Git el handoff y su auditoría ya publicada en b020b604dc0bdb9ac4bc40e4c974712b7aaa62e0. No publiques otra auditoría y no inventes E-117.

Verificá que b020b604dc0bdb9ac4bc40e4c974712b7aaa62e0:
- audita fb6a2c7878d37242c11ad5421fb6dda566797f60;
- declara VEREDICTO=APROBADO_OFFLINE;
- deja AUDITOR_FRESCO_CONSTITUIDO=SI y CONSTRUCTOR_FRESCO=HABILITADO;
- conserva O-E095-01=NO_CERRADA_POR_AUDITOR, U06=ABIERTA, U07=CERRADA y E117=NO_CONSTITUIDO_AL_CORTE.

Si coincide, emití el primer sobre revolutions-hop/v1 con turn_id=1, actor=AUDITOR, repository=francogg89-ai/audit-chatgpt-g, commit=b020b604dc0bdb9ac4bc40e4c974712b7aaa62e0, next_actor=CONSTRUCTOR y next_instance=fresh.

Usá G/PROMPT_CONSTRUCTOR_FRESCO.md como next_prompt. Sustituí <INCOMING_TURN_ID> por 1, <AUDIT_SHA_POST_HANDOFF> por b020b604dc0bdb9ac4bc40e4c974712b7aaa62e0 y <BRIDGE_SHA_DEL_LOCATOR> por el CONSTITUTION_SHA recibido literalmente en auditor-init/v1. No dejes placeholders.

Aplicá permanentemente el contrato de salida mínima de CONSTITUCION_INICIAL.md. La respuesta completa debe ser únicamente un bloque cercado etiquetado json; no emitas prosa ni contenido fuera del bloque.

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

WORK_CONTROL_SHA=0956c881d7dfc1d718d350579578abb9c0f8d6cb
SHA_VIGENTE_MATERIAL=c7088a48a519ddfd917db16ee79a5b5ea8d4876e

Sincronizá work-claude-g y audit-chatgpt-g. Leé 00_control/BOOTSTRAP.md y METODO_REF literal. No dependas todavía del checkpoint.

Auditá el handoff del auditor:
- e760d792ea92f9f83b4d6831840258e4603f1450..fb6a2c7878d37242c11ad5421fb6dda566797f60 debe ser CONTROL, un commit y sólo el checkpoint;
- rederivá desde Git identidades, estado U06/U07 y referencias exactas;
- verificá I-15/I-16 y que no transporte estados falsos;
- publicá la auditoría del handoff.

Si queda conforme:
- AUDITOR_FRESCO_CONSTITUIDO=SI;
- no inventes E-117;
- O-E095-01=NO_CERRADA_POR_AUDITOR;
- U06=ABIERTA;
- U07=CERRADA;
- emití el primer sobre revolutions-hop/v1 con turn_id=1 hacia CONSTRUCTOR fresh;
- citá como commit el SHA exacto de tu auditoría recién publicada;
- usá G/PROMPT_CONSTRUCTOR_FRESCO.md como next_prompt, sustituyendo <INCOMING_TURN_ID> por 1 y <AUDIT_SHA_POST_HANDOFF> por ese SHA.

Aplicá permanentemente el contrato de salida mínima de CONSTITUCION_INICIAL.md.
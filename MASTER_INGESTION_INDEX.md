# StrideLab Engine 1.5 — Master Consolidated Ingestion Index

- **Immutable Research Snapshot:** `28878a67fe577427a936734b981892fef03164f9`
- **Split Manifest Commit:** `f461bb3c6d32aa7cb8ca70148e879cc26ff21d15`
- **Development Source Commit:** `11a59b329341135039a30d24df0d55c8f085cc5d`
- **Already Ingested (Excluded):** `AI-Studio-Prompts/Batch_001.txt`–`Batch_003.txt` (`42` URLs)
- **Consolidated Remaining URLs:** `464` (`458` remaining chunks + `6` `< 18 KB` `SOURCE_MANIFEST_part001..006.txt` parts) across `8` batches (`56–70` URLs each, zero split multi-part files).
- **Fallback Workflow:** Original 36 granular batches remain preserved unchanged under `AI-Studio-Prompts/`.

## Consolidated Batches

| Batch File | URLs | Files | Research Objective & Dependency Scope |
| :--- | ---: | ---: | :--- |
| `AI-Studio-Prompts-Large/Batch_Large_001.txt` | 59 | 34 | Split Manifest + Activity/HR/Evidence + Plan/Persistence/Callers + Engine 1.5 Core |
| `AI-Studio-Prompts-Large/Batch_Large_002.txt` | 57 | 39 | Activity/HR/Evidence + Plan/Persistence/Callers + Research & Policy Docs + Engine 1.5 Core |
| `AI-Studio-Prompts-Large/Batch_Large_003.txt` | 57 | 56 | Research & Policy Docs |
| `AI-Studio-Prompts-Large/Batch_Large_004.txt` | 57 | 52 | Activity/HR/Evidence + Research & Policy Docs + Unit & Regression Tests + Engine 1.5 Core |
| `AI-Studio-Prompts-Large/Batch_Large_005.txt` | 57 | 45 | Activity/HR/Evidence + Unit & Regression Tests + Engine 1.5 Core |
| `AI-Studio-Prompts-Large/Batch_Large_006.txt` | 57 | 55 | Activity/HR/Evidence + Unit & Regression Tests + Engine 1.5 Core |
| `AI-Studio-Prompts-Large/Batch_Large_007.txt` | 57 | 45 | Activity/HR/Evidence + Plan/Persistence/Callers + Unit & Regression Tests + Engine 1.5 Core |
| `AI-Studio-Prompts-Large/Batch_Large_008.txt` | 63 | 48 | Plan/Persistence/Callers + Engine 1.5 Core |

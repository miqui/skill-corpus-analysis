# Skill Corpus Token Consumption Review

Generated: 2026-06-28 12:20:30 EDT

## Executive Summary

- Corpus scanned: `/Users/miqui/.hermes/skills`
- Skills found: **204**
- Text files scanned: **1,024**; non-text/binary files noted: **89**
- Estimated total text tokens across all scanned files: **2,588,468**
- Estimated `SKILL.md` tokens: **525,096**
- Estimated linked support-file tokens (`references/`, `templates/`, `scripts/`, `assets/`): **1,889,133**
- Estimated other text-file tokens: **174,239**
- Median `SKILL.md` size: **2,232 tokens**
- Mean `SKILL.md` size: **2,574 tokens**
- Oversized main skills ≥ 5,000 estimated tokens: **11**
- Very large main skills ≥ 10,000 estimated tokens: **1**

Token estimates use `ceil(characters / 4)`. They are directional sizing estimates, not exact model-tokenizer counts.

## Top Findings

1. **The largest optimization target is broad `SKILL.md` content, not small metadata.** A minority of large main skill files dominate frequently loaded context risk.
2. **The IaC/AWS skill cluster is the largest category by volume.** This is expected after importing many AWS operational skills, but it should be the first area for token-aware consolidation and support-file splitting.
3. **Support files are a major latent token store.** They are optional at runtime if not loaded, which is good; however, very large support files should still be summarized/split for targeted retrieval.
4. **High-trigger broad skills deserve stricter size budgets.** Skills such as API, backend, GitHub, cloud, and local workflow skills are likely to be loaded often; they should be concise routers with deep detail in references.
5. **Related-skill fanout is present in several skills.** It is cheaper than body text, but excessive fanout can cause unnecessary multi-skill loading and routing ambiguity.
6. **The newly added `event-driven-api-design` skill is useful but above the preferred 8–15k character peer target.** It is still within hard limits, but a future pass should split AsyncAPI/CloudEvents details into references if it becomes frequently loaded.

## Corpus Inventory

| Metric | Count / Estimate |
| --- | --- |
| Skills (`SKILL.md`) | 204 |
| All text files scanned | 1,024 |
| Support text files | 697 |
| Other text files | 123 |
| Non-text/binary files | 89 |
| Total estimated text tokens | 2,588,468 |
| Estimated `SKILL.md` tokens | 525,096 |
| Estimated support-file tokens | 1,889,133 |
| Estimated other text-file tokens | 174,239 |

## Category-Level Footprint

| Category | Skills | Skill tokens | Support files | Support tokens | Combined tokens |
| --- | --- | --- | --- | --- | --- |
| creative | 20 | 66,276 | 254 | 548,285 | 614,561 |
| mlops/training | 3 | 4,780 | 14 | 559,851 | 564,631 |
| iac | 51 | 102,250 | 194 | 393,015 | 495,265 |
| research | 6 | 35,402 | 57 | 329,995 | 365,397 |
| productivity | 10 | 21,722 | 56 | 287,688 | 309,410 |
| software-development | 47 | 123,671 | 109 | 131,424 | 255,095 |
| autonomous-ai-agents | 9 | 38,000 | 16 | 15,326 | 53,326 |
| mlops/inference | 4 | 12,259 | 18 | 32,327 | 44,586 |
| devops | 11 | 29,141 | 3 | 2,388 | 31,529 |
| mlops/evaluation | 2 | 6,103 | 7 | 23,404 | 29,507 |
| red-teaming | 1 | 4,974 | 8 | 23,420 | 28,394 |
| mlops/models | 2 | 7,120 | 4 | 14,011 | 21,131 |
| github | 6 | 13,557 | 9 | 5,110 | 18,667 |
| local-utils | 1 | 8,461 | 3 | 7,849 | 16,310 |
| mlops/research | 1 | 3,803 | 3 | 11,566 | 15,369 |
| software-development/python-dev | 3 | 8,589 | 0 | 0 | 8,589 |
| mlops | 3 | 6,032 | 2 | 1,259 | 7,291 |
| media | 5 | 5,276 | 2 | 1,327 | 6,603 |
| apple | 5 | 4,789 | 0 | 0 | 4,789 |
| social-media | 2 | 4,777 | 0 | 0 | 4,777 |
| email | 1 | 1,814 | 2 | 2,424 | 4,238 |
| mcp | 2 | 3,894 | 1 | 304 | 4,198 |
| gaming | 2 | 3,787 | 0 | 0 | 3,787 |
| (root) | 1 | 2,778 | 0 | 0 | 2,778 |
| software-development/node-backend | 1 | 1,676 | 0 | 0 | 1,676 |
| devops/argocd-advanced/References | 2 | 1,434 | 0 | 0 | 1,434 |
| data-science | 1 | 1,319 | 0 | 0 | 1,319 |
| note-taking | 1 | 734 | 0 | 0 | 734 |
| smart-home | 1 | 678 | 0 | 0 | 678 |

## Top 20 Largest Main Skill Files

| Skill | Category | Est. tokens | Chars | Lines | Path |
| --- | --- | --- | --- | --- | --- |
| research-paper-writing | research | 25,605 | 102,417 | 2,378 | research/research-paper-writing/SKILL.md |
| hermes-agent | autonomous-ai-agents | 9,751 | 39,001 | 929 | autonomous-ai-agents/hermes-agent/SKILL.md |
| aws-transform | iac | 9,471 | 37,884 | 855 | iac/aws-transform/SKILL.md |
| claude-code | autonomous-ai-agents | 9,064 | 36,254 | 768 | autonomous-ai-agents/claude-code/SKILL.md |
| macos-cleaner | local-utils | 8,461 | 33,843 | 1,093 | local-utils/macos-cleaner/SKILL.md |
| amazon-bedrock | iac | 7,723 | 30,891 | 393 | iac/amazon-bedrock/SKILL.md |
| humanizer | creative | 7,488 | 29,949 | 579 | creative/humanizer/SKILL.md |
| p5js | creative | 6,833 | 27,329 | 557 | creative/p5js/SKILL.md |
| comfyui | creative | 5,924 | 23,693 | 613 | creative/comfyui/SKILL.md |
| aws-containers | iac | 5,571 | 22,284 | 259 | iac/aws-containers/SKILL.md |
| event-driven-api-design | software-development | 5,311 | 21,244 | 387 | software-development/event-driven-api-design/SKILL.md |
| llm-wiki | research | 4,976 | 19,903 | 508 | research/llm-wiki/SKILL.md |
| godmode | red-teaming | 4,974 | 19,893 | 405 | red-teaming/godmode/SKILL.md |
| claude-design | creative | 4,953 | 19,809 | 592 | creative/claude-design/SKILL.md |
| code-performance-engineering | software-development | 4,721 | 18,882 | 353 | software-development/code-performance-engineering/SKILL.md |
| graphql-api | software-development | 4,467 | 17,866 | 414 | software-development/graphql-api/SKILL.md |
| python-cli-patterns | software-development | 4,460 | 17,839 | 541 | software-development/python-cli-patterns/SKILL.md |
| secure-agent-skills | autonomous-ai-agents | 4,368 | 17,472 | 328 | autonomous-ai-agents/secure-agent-skills/SKILL.md |
| hermes-agent-skill-authoring | software-development | 4,197 | 16,788 | 189 | software-development/hermes-agent-skill-authoring/SKILL.md |
| api-governance | software-development | 4,180 | 16,717 | 392 | software-development/api-governance/SKILL.md |

## Top 20 Largest Support Files

| Kind | Est. tokens | Chars | Lines | Path |
| --- | --- | --- | --- | --- |
| references | 268,685 | 1,074,740 | 16,800 | mlops/training/unsloth/references/llms-full.md |
| references | 202,713 | 810,852 | 12,045 | mlops/training/unsloth/references/llms-txt.md |
| references | 35,055 | 140,218 | 3,564 | mlops/training/axolotl/references/other.md |
| references | 30,216 | 120,861 | 5,549 | mlops/training/axolotl/references/api.md |
| references | 18,206 | 72,821 | 1,866 | creative/ascii-video/references/effects.md |
| references | 15,944 | 63,774 | 1,698 | iac/aws-launching-ec2-instance-with-best-practices/references/launch-ec2-instance-with-best-practices.md |
| references | 14,732 | 58,927 | 1,603 | iac/aws-exporting-rds-to-s3/references/export-rds-to-s3.md |
| templates | 13,174 | 52,695 | 1,469 | creative/pretext/templates/donut-orbit.html |
| references | 12,591 | 50,364 | 1,386 | creative/ascii-video/references/shaders.md |
| scripts | 11,668 | 46,669 | 1,298 | productivity/maps/scripts/maps_client.py |
| references | 11,480 | 45,917 | 1,030 | mlops/training/axolotl/references/dataset-formats.md |
| scripts | 10,871 | 43,483 | 1,226 | productivity/google-workspace/scripts/google_api.py |
| references | 9,341 | 37,362 | 1,012 | creative/ascii-video/references/scenes.md |
| references | 8,720 | 34,877 | 893 | creative/ascii-video/references/composition.md |
| references | 8,442 | 33,767 | 836 | iac/aws-setting-up-ec2-instance-profiles/references/ec2-instance-profile-setup.md |
| scripts | 8,428 | 33,710 | 836 | creative/comfyui/scripts/_common.py |
| references | 8,382 | 33,525 | 967 | creative/touchdesigner-mcp/references/network-patterns.md |
| references | 8,211 | 32,841 | 803 | creative/ascii-video/references/architecture.md |
| scripts | 7,892 | 31,565 | 797 | creative/comfyui/scripts/run_workflow.py |
| scripts | 7,888 | 31,551 | 770 | red-teaming/godmode/scripts/auto_jailbreak.py |

## Main Skill Size Distribution

| Estimated token bucket | Skill count |
| --- | --- |
| 0–999 | 45 |
| 1,000–2,499 | 72 |
| 2,500–4,999 | 76 |
| 5,000–9,999 | 10 |
| 10,000–19,999 | 0 |
| 20,000+ | 1 |

## Metadata and Routing Cost Review

- Skills with descriptions over 500 chars: **6**
- Skills with `related_skills` fanout ≥ 8: **2**
- Best-effort broken `related_skills` references: **10**

### Long Description Candidates

| Skill | Description chars | Path |
| --- | --- | --- |
| aws-observability | 930 | iac/aws-observability/SKILL.md |
| aws-serverless | 893 | iac/aws-serverless/SKILL.md |
| amazon-bedrock | 822 | iac/amazon-bedrock/SKILL.md |
| aws-containers | 671 | iac/aws-containers/SKILL.md |
| fastify-oauth | 530 | software-development/node-backend/fastify-oauth/SKILL.md |
| aws-transform | 527 | iac/aws-transform/SKILL.md |

### High Related-Skill Fanout

| Skill | Related count | Related skills sample | Path |
| --- | --- | --- | --- |
| event-driven-api-design | 11 | api-governance, openapi-api-designer, openapi-specification, graphql-api, grpc-api, aws-serverless, aws-messaging-and-streaming, node-backend, spring-boot-engineer, writing-plans, test-driven-development | software-development/event-driven-api-design/SKILL.md |
| code-performance-engineering | 9 | systematic-debugging, test-driven-development, requesting-code-review, python-performance-optimization, golang-troubleshooting, node-backend, spring-boot-engineer, grpc-api, graphql-api | software-development/code-performance-engineering/SKILL.md |

### Possible Broken Related-Skill References

| Source skill | Unresolved related skill |
| --- | --- |
| apple/macos-computer-use/SKILL.md | browser |
| computer-use/SKILL.md | browser |
| creative/architecture-diagram/SKILL.md | concept-diagrams |
| creative/comfyui/SKILL.md | stable-diffusion-image-generation |
| creative/comfyui/SKILL.md | image_gen |
| creative/touchdesigner-mcp/SKILL.md | hermes-video |
| mcp/native-mcp/SKILL.md | mcporter |
| mlops/inference/obliteratus/SKILL.md | gguf |
| mlops/inference/obliteratus/SKILL.md | huggingface-tokenizers |
| software-development/hermes-s6-container-supervision/SKILL.md | hermes-agent-dev |

## Duplication and Residue Signals

- Exact duplicate text-file groups >200 chars: **1**
- Near-duplicate skill candidates by word-set Jaccard ≥ 0.55: **4**
- Pattern `foreign_tool_mentions` matched files: **57**
- Pattern `curl_pipe_shell` matched files: **13**
- Pattern `global_install` matched files: **43**
- Pattern `long_description_candidates` matched files: **6**

### Exact Duplicate File Groups

#### Duplicate group 1
- `domain/DESCRIPTION.md` (283 est. tokens)
- `research/domain-intel/SKILL.md` (283 est. tokens)

### Near-Duplicate Skill Candidates

| Jaccard | Skill A | Skill B |
| --- | --- | --- |
| 0.73 | software-development/plan/SKILL.md | software-development/writing-plans/SKILL.md |
| 0.63 | apple/macos-computer-use/SKILL.md | computer-use/SKILL.md |
| 0.59 | iac/aws-debugging-lambda-timeouts/SKILL.md | iac/aws-troubleshooting-application-failures/SKILL.md |
| 0.59 | iac/aws-configuring-vpc-endpoints-for-private-aws-service-access/SKILL.md | iac/aws-enabling-lambda-vpc-internet-access/SKILL.md |

### Residue / Risk Pattern Matches

#### foreign_tool_mentions
- `apple/macos-computer-use/SKILL.md`
- `autonomous-ai-agents/building-agents-with-sdks/references/claude-sdk.md`
- `autonomous-ai-agents/claude-code/SKILL.md`
- `autonomous-ai-agents/claude-code/references/hermes-controller-repair-loop.md`
- `autonomous-ai-agents/claude-code/references/node-typescript-cli-integration.md`
- `autonomous-ai-agents/hermes-agent/SKILL.md`
- `autonomous-ai-agents/hermes-multi-model-routing/SKILL.md`
- `autonomous-ai-agents/hermes-multi-model-routing/references/split-gpt54-parent-sonnet46-child.md`
- `autonomous-ai-agents/secure-agent-skills/SKILL.md`
- `computer-use/SKILL.md`
- `creative/ascii-video/references/inputs.md`
- `creative/ascii-video/references/shaders.md`
- `creative/baoyu-article-illustrator/PORT_NOTES.md`
- `creative/baoyu-comic/PORT_NOTES.md`
- `creative/baoyu-infographic/PORT_NOTES.md`
- `creative/p5js/references/interaction.md`
- `creative/p5js/references/typography.md`
- `creative/p5js/templates/viewer.html`
- `creative/popular-web-designs/SKILL.md`
- `creative/popular-web-designs/templates/cursor.md`
- `creative/popular-web-designs/templates/ollama.md`
- `creative/popular-web-designs/templates/vercel.md`
- `creative/pretext/SKILL.md`
- `creative/pretext/references/patterns.md`
- `creative/pretext/templates/donut-orbit.html`
- `creative/pretext/templates/hello-orb-flow.html`
- `creative/touchdesigner-mcp/references/mcp-tools.md`
- `creative/touchdesigner-mcp/references/projection-mapping.md`
- `devops/argocd-advanced/References/image-updater.md`
- `gaming/pokemon-player/SKILL.md`
- `iac/aws-transform/SKILL.md`
- `iac/aws-transform/references/multi-transformation.md`
- `iac/aws-transform/references/single-transformation.md`
- `local-utils/macos-cleaner/SKILL.md`
- `mlops/ai-engineering-toolkit/SKILL.md`
- `productivity/linear/SKILL.md`
- `research/polymarket/references/api-endpoints.md`
- `research/research-paper-writing/templates/README.md`
- `research/research-paper-writing/templates/aaai2026/README.md`
- `social-media/xurl/SKILL.md`
- ...and 17 more

#### curl_pipe_shell
- `apple/macos-computer-use/SKILL.md`
- `autonomous-ai-agents/hermes-agent/SKILL.md`
- `autonomous-ai-agents/secure-agent-skills/SKILL.md`
- `computer-use/SKILL.md`
- `iac/aws-transform/SKILL.md`
- `iac/aws-transform/references/remote-execution.md`
- `mlops/huggingface-hub/SKILL.md`
- `mlops/training/axolotl/references/other.md`
- `mlops/training/unsloth/references/llms-full.md`
- `mlops/training/unsloth/references/llms-txt.md`
- `productivity/notion/SKILL.md`
- `social-media/xurl/SKILL.md`
- `software-development/bun-backend/SKILL.md`

#### global_install
- `apple/macos-computer-use/SKILL.md`
- `autonomous-ai-agents/claude-code/SKILL.md`
- `autonomous-ai-agents/codex/SKILL.md`
- `autonomous-ai-agents/hermes-agent/SKILL.md`
- `computer-use/SKILL.md`
- `creative/ascii-art/SKILL.md`
- `creative/manim-video/scripts/setup.sh`
- `creative/touchdesigner-mcp/references/external-data.md`
- `devops/shellcheck-configuration/SKILL.md`
- `gaming/minecraft-modpack-server/SKILL.md`
- `github/github-auth/SKILL.md`
- `iac/ansible/SKILL.md`
- `iac/ansible/references/inventory.md`
- `iac/ansible/references/modules.md`
- `iac/ansible/references/nopasswd-sudo.md`
- `iac/ansible/references/troubleshooting.md`
- `iac/aws-amplify/references/scaffolding.md`
- `iac/aws-launching-ec2-instance-with-best-practices/references/launch-ec2-instance-with-best-practices.md`
- `iac/aws-serverless/references/troubleshooting.md`
- `iac/aws-transform/SKILL.md`
- `iac/aws-transform/references/multi-transformation.md`
- `iac/aws-transform/references/single-transformation.md`
- `iac/aws-troubleshooting-efs/SKILL.md`
- `iac/aws-troubleshooting-s3-files/SKILL.md`
- `iac/cicd-automation-workflow-automate/resources/implementation-playbook.md`
- `local-utils/macos-cleaner/SKILL.md`
- `local-utils/macos-cleaner/references/cleanup_targets.md`
- `local-utils/macos-cleaner/references/safety_rules.md`
- `mlops/inference/llama-cpp/references/troubleshooting.md`
- `mlops/inference/vllm/references/quantization.md`
- `mlops/inference/vllm/references/troubleshooting.md`
- `mlops/models/audiocraft/references/troubleshooting.md`
- `mlops/training/unsloth/references/llms-full.md`
- `mlops/training/unsloth/references/llms-txt.md`
- `productivity/notion/SKILL.md`
- `productivity/powerpoint/SKILL.md`
- `productivity/powerpoint/pptxgenjs.md`
- `research/llm-wiki/SKILL.md`
- `research/research-paper-writing/SKILL.md`
- `research/research-paper-writing/templates/README.md`
- ...and 3 more

#### long_description_candidates
- `iac/amazon-bedrock/SKILL.md`
- `iac/aws-containers/SKILL.md`
- `iac/aws-observability/SKILL.md`
- `iac/aws-serverless/SKILL.md`
- `iac/aws-transform/SKILL.md`
- `software-development/node-backend/fastify-oauth/SKILL.md`

## Prioritized Optimization Recommendations

### Priority 1 — Slim high-trigger, oversized main skills

Turn broad, frequently loaded skills into concise routers and move deep operational detail into `references/`. Target 8–15k chars for broad skills, and only exceed that when the extra detail is truly needed on every load.

| Candidate | Est. tokens | Category | Path |
| --- | --- | --- | --- |
| research-paper-writing | 25,605 | research | research/research-paper-writing/SKILL.md |
| hermes-agent | 9,751 | autonomous-ai-agents | autonomous-ai-agents/hermes-agent/SKILL.md |
| aws-transform | 9,471 | iac | iac/aws-transform/SKILL.md |
| claude-code | 9,064 | autonomous-ai-agents | autonomous-ai-agents/claude-code/SKILL.md |
| macos-cleaner | 8,461 | local-utils | local-utils/macos-cleaner/SKILL.md |
| amazon-bedrock | 7,723 | iac | iac/amazon-bedrock/SKILL.md |
| humanizer | 7,488 | creative | creative/humanizer/SKILL.md |
| p5js | 6,833 | creative | creative/p5js/SKILL.md |
| comfyui | 5,924 | creative | creative/comfyui/SKILL.md |
| aws-containers | 5,571 | iac | iac/aws-containers/SKILL.md |
| event-driven-api-design | 5,311 | software-development | software-development/event-driven-api-design/SKILL.md |

### Priority 2 — Rationalize the AWS/IaC cluster

The imported AWS/IaC skills are useful but collectively large. Prefer a cleanup/consolidation pass that keeps narrow service skills but reduces repeated boilerplate and pushes long examples into targeted references. This aligns with the existing note that the AWS IaC skill imports need a later consolidation pass.

### Priority 3 — Split very large support files for targeted retrieval

| Est. tokens | Kind | Path |
| --- | --- | --- |
| 268,685 | references | mlops/training/unsloth/references/llms-full.md |
| 202,713 | references | mlops/training/unsloth/references/llms-txt.md |
| 35,055 | references | mlops/training/axolotl/references/other.md |
| 30,216 | references | mlops/training/axolotl/references/api.md |
| 18,206 | references | creative/ascii-video/references/effects.md |
| 15,944 | references | iac/aws-launching-ec2-instance-with-best-practices/references/launch-ec2-instance-with-best-practices.md |
| 14,732 | references | iac/aws-exporting-rds-to-s3/references/export-rds-to-s3.md |
| 13,174 | templates | creative/pretext/templates/donut-orbit.html |
| 12,591 | references | creative/ascii-video/references/shaders.md |
| 11,668 | scripts | productivity/maps/scripts/maps_client.py |
| 11,480 | references | mlops/training/axolotl/references/dataset-formats.md |
| 10,871 | scripts | productivity/google-workspace/scripts/google_api.py |
| 9,341 | references | creative/ascii-video/references/scenes.md |
| 8,720 | references | creative/ascii-video/references/composition.md |
| 8,442 | references | iac/aws-setting-up-ec2-instance-profiles/references/ec2-instance-profile-setup.md |

### Priority 4 — Reduce routing ambiguity

Review high `related_skills` fanout and possible broken references. Keep relationships that guide real skill pairing, but remove generic or aspirational links that encourage unnecessary loading.

### Priority 5 — Establish token budgets

- Broad/high-trigger skill: target **2k–4k estimated tokens** in `SKILL.md`.
- Narrow operational skill: target **3k–6k estimated tokens** if detail is needed.
- Deep references: no hard cap, but split files above **5k estimated tokens** by task/section.
- Description: target **120–300 chars** unless routing truly requires more.
- Related skills: target **3–7 high-confidence links** for most skills.

## Estimated Cleanup Savings

| Potential est. token reduction | Action |
| --- | --- |
| 11,523 | Refactor oversized main SKILL.md `research/research-paper-writing/SKILL.md` into concise router + optional references |
| 5,462 | Summarize/split large support file `creative/ascii-video/references/effects.md` |
| 3,778 | Summarize/split large support file `creative/ascii-video/references/shaders.md` |
| 2,803 | Summarize/split large support file `creative/ascii-video/references/scenes.md` |
| 2,616 | Summarize/split large support file `creative/ascii-video/references/composition.md` |
| 2,529 | Summarize/split large support file `creative/comfyui/scripts/_common.py` |
| 2,464 | Summarize/split large support file `creative/ascii-video/references/architecture.md` |
| 2,368 | Summarize/split large support file `creative/comfyui/scripts/run_workflow.py` |
| 1,842 | Summarize/split large support file `creative/ascii-video/references/inputs.md` |
| 1,818 | Summarize/split large support file `creative/ascii-video/references/optimization.md` |
| 1,757 | Summarize/split large support file `creative/p5js/references/visual-effects.md` |
| 283 | Remove exact duplicate text files or replace duplicates with references |

## Notes on the New Event-Driven API Skill

- `event-driven-api-design` currently weighs in at **5,311 estimated tokens** / **21,244 chars**.
- It is within hard validation limits and covers a real corpus gap.
- Because it is likely to be a high-trigger API design skill, consider a future split into:
  - concise `SKILL.md` router
  - `references/asyncapi-authoring.md`
  - `references/cloudevents-envelope.md`
  - `references/event-contract-testing.md`

## Methodology

- Read-only scan of `~/.hermes/skills`.
- Text files included common source/document formats and all `SKILL.md` files.
- Token estimates use `ceil(characters / 4)`. This favors stable corpus comparisons over tokenizer-specific exactness.
- Category is inferred from the path segments before the skill directory.
- Support files are files under `references/`, `templates/`, `scripts/`, and `assets/` inside each skill directory.
- Duplicate detection includes exact SHA-256 matches and a lightweight word-set Jaccard check for near-duplicate `SKILL.md` files.
- Broken related-skill detection is best-effort against discovered frontmatter names and directory names.

## Recommended Next Pass

Run a focused cleanup in this order:

1. Fix broken `related_skills` references.
2. Trim or split the top 10 largest high-trigger `SKILL.md` files.
3. Consolidate repeated AWS/IaC boilerplate while preserving narrow service guidance.
4. Split support files above 5k estimated tokens into task-specific references.
5. Re-run this report and compare category totals and top-20 lists.


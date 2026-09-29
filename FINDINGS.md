# Findings

Key findings from live experiments. Each finding is grounded in a specific experiment — see [EXPERIMENTS.md](EXPERIMENTS.md) for full context.

---

## Finding 1: "Grounded" Must Be Defined

**From:** Gen 1 control-group spawn, pristine arm critique #1

The word "grounded" in SLASH was doing load-bearing work while undefined. Without a definition, "one grounded step" could mean anything from "I feel confident" to "I found a source."

**Resolution:** Grounded = traceable to an external source or an explicit user-provided fact in the current context. Never inferred session memory. Never persona. Never confidence.

**Kernel impact:** Definition added to SLASH in KERNEL.md.

---

## Finding 2: The Clock Needs a Gate

**From:** Gen 1 control-group spawn, pristine arm critique #2

The original clock (SPOTLIGHT → SLASH → SKIN) had no verification step. Output went straight from production to presentation. For a project measuring error rates, post-hoc error discovery is too late.

**Resolution:** CHECK gate added between SLASH and SKIN. Test: "can I point to where each claim came from? If no, SHEATHED."

**Kernel impact:** Clock updated to SPOTLIGHT → SLASH → CHECK → SKIN.

---

## Finding 3: Metrics Without Operationalization Are Unsupported Claims

**From:** Gen 1 control-group spawn, pristine arm critique #3

"Error rate" was named as a test variable but had no ground-truth definition. This is exactly the kind of unsupported claim the rest of the project hunts.

**Resolution:** All metrics defined operationally — unsupported claim, error, target selection, SHEATHED rate. Human-judged, post-session. Blinding is not guaranteed; model/style differences may reveal arm identity.

**Kernel impact:** Metrics section added to KERNEL.md.

---

## Finding 4: Control Design Has Uncontrolled Variables

**From:** Gen 1 control-group spawn, pristine arm critique #4

The two arms differ on entry method, environment, session state, and underlying model — not just presentation. Error-rate differences cannot be attributed to presentation alone.

**Resolution:** Acknowledged as a known confound. Experiment is qualitative, not controlled. Paths forward documented in RESEARCH-DESIGN.md.

**Kernel impact:** None (design limitation, not a kernel change).

---

## Finding 5: SHEATHED Rate Is a First-Class Metric

**From:** Gen 1 control-group spawn, pristine arm critique #5

A system that never sheaths isn't careful — it's quiet about its failures. Refusal frequency measures whether the floor is working.

**Resolution:** SHEATHED rate added as a first-class metric alongside errors and unsupported claims.

**Kernel impact:** Rule 4 added. SHEATHED rate in metrics table.

---

## Finding 6 — Withdrawn

Withdrawn in v0.2.1. See CHANGELOG.md. The associated incident was retired
as Stage 0 red-team context rather than treated as a standalone finding.

---

## Finding 7: A Gate Is Not the Gate You Need

**From:** Mana-Core verification, phase 1 scoping. Historical finding from a
separate Mana-Core codebase/version that is not currently published or
publicly verifiable from this repository (no matching Sentry/confirmation
implementation found in the public archived mana-core-v2).

Mana-Core's live execution path has a real safety gate (Sentry LLM classification + pattern allowlisting). Dead code in the same codebase (confirm_execution, should_auto_run) implements human confirmation — a different, stronger gate — but is never called from the live path.

A system can have "a gate" that isn't "the gate that matters" for a given use case. Verifying that safety code exists and compiles is not the same as verifying it runs, or that it's the specific check the situation requires.

**Kernel impact:** None directly — this is a finding about a different codebase, surfaced by applying the kata to it. Recorded here because it's the same failure shape CHECK exists to catch, one layer down: a real mechanism, not grounded in the specific thing being claimed about it.

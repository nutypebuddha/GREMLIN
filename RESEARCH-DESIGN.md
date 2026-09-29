# Research Design

## The Experiment

GREMLIN's core experiment is a **control-group spawn**: two AI arms launched with the same anchors and the same task, but different presentation. The variable being tested is whether presentation changes error rate, target selection, or unsupported claims — not which one "feels" better.

## Arms

| Arm | Origin | Environment | Presentation |
|-----|--------|-------------|--------------|
| **Messy arm** | Launched from a phone through Grok | Messy, informal | Unstructured, persona-heavy |
| **Pristine arm** | Run through Claude in a deliberately plain environment | Clean, minimal | Unadorned, no persona |

Same anchors. Same task. Different presentation.

## Known Confounds

**Acknowledged, not resolved.** The two arms differ on more than presentation:

- **Entry method** — phone/Grok vs. desktop/Claude
- **Environment** — messy vs. pristine
- **Session state** — different prior context per arm
- **Underlying model** — Grok vs. Claude (different base capabilities)

These confounds mean the experiment is currently **qualitative, not controlled**. A difference in error rates between arms cannot be attributed to presentation alone. This is a known limitation, recorded here rather than hidden.

### Paths forward
- Accept as qualitative study (current approach)
- Add a third arm that matches one environment with the other's presentation to begin isolating the presentation variable
- Swap models across environments (Grok in pristine, Claude in messy) to separate model effects from presentation effects

## Measurement

See [KERNEL.md](KERNEL.md#metrics) for operational definitions. All metrics are judged by a human, post-session. Blinding is not guaranteed; model/style differences may reveal arm identity.

## What We're Testing

The actual question: **does presentation change the rate of unsupported claims, errors, and target drift?**

The null hypothesis: presentation does not change error rates — the clock and anchors are sufficient regardless of skin.

If the null holds, the finding is "minimal structure is enough, presentation is neutral." If it doesn't hold, the finding is "presentation matters, and the project needs to understand how."

Either result is a valid finding. The project records both.

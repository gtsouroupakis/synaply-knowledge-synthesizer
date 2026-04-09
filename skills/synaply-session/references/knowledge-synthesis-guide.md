# Knowledge Synthesis Guide

Apply this methodology during Step 5 (Synthesize Knowledge) of the Synaply session workflow. This is the cross-source synthesis layer that transforms raw signals into structured insight candidates.

## The Goal

Transform this:
```
Email result: "George mentioned the client pushed back on the Q2 timeline in a thread with the CSM team"
Slack result (DM): "honestly the real issue is their board hasn't approved the budget yet — I found this out from a sidebar with their CTO"
Calendar result: "Client QBR — George attended, 60 min, notes attached"
AI conversation: "George asked for help drafting a revised proposal with a Q3 option"
```

Into this:
```
The client's Q2 timeline is at risk — their board has not yet approved the budget, which the user
learned directly from a sidebar with the CTO. The user has already begun drafting a revised proposal
with a Q3 option. The official stance in the QBR was timeline concerns, but the real blocker is
internal budget approval.

Sources: DM (Slack, Jan 14), Email thread with CSM team (Jan 12), AI conversation (Jan 15)
```

## Deduplication

### Cross-Source Deduplication

The same information often appears in multiple places. Identify and merge duplicates before drafting.

Signals that results are about the same thing:
- Same or very similar text content
- Same author/sender
- Timestamps within a short window (same day or adjacent days)
- References to the same entity (project name, client, decision)
- One source references another ("as I mentioned in the email", "per our Slack thread")

How to merge:
- Combine into a single narrative item
- Cite all sources where it appeared
- Use the most complete version as the primary text
- Add unique details from each source

### Deduplication Priority

When the same information exists in multiple sources, prefer:
1. The most complete version (fullest context)
2. The most authoritative source (formal doc > email > chat > DM)
3. The most recent version (latest update wins for evolving info)

### What NOT to Deduplicate

Keep as separate insight candidates when:
- The same topic is discussed but with different conclusions
- The information evolved meaningfully between sources (initial assumption vs. confirmed fact)
- Different time periods are represented
- The user's reaction or decision in one source is substantively different from another

## Confidence Scoring

### Freshness

| Recency | Confidence |
|---------|------------|
| Today / yesterday | High |
| This week | Good |
| This month | Moderate — flag if status-sensitive |
| Older than a month | Lower — flag as potentially outdated |

### Authority

| Source type | Authority |
|-------------|-----------|
| Formal documents (final versions) | Highest |
| Email announcements / confirmations | High |
| Meeting notes | Moderate-high |
| Slack/Teams threads (conclusions) | Moderate |
| DMs and informal chat | Lower authority, but highest signal value for unfiltered thinking |
| AI conversation history | High — reflects user's actual reasoning and decisions |

### Conflicting Information

When sources disagree, surface the conflict — do not silently pick one version:
```
I found conflicting signals about the client's budget status:
- The formal QBR notes (Jan 12) indicate budget is approved pending board sign-off
- The user's DM with the CTO (Jan 14) suggests board approval has not happened yet

The DM is more recent and direct — the insight draft reflects the DM, but flags the discrepancy.
```

## Synthesis Workflow

```
[Raw signals from all sources within resolved timeframe]
          ↓
[1. Scope — confirm every signal directly involves the user]
          ↓
[2. Deduplicate — merge same info from different sources]
          ↓
[3. Cluster — group related signals by theme/topic]
          ↓
[4. Rank — order clusters by relevance to available Insight Types]
          ↓
[5. Assess confidence — freshness × authority × agreement]
          ↓
[6. Produce shortlist of raw insight candidates with source attribution]
          ↓
[Hand off to Step 6: Sanitize]
```

## Summarization by Result Volume

### Small result set (1–5 signals)
Present each signal with full context. No compression needed.

### Medium result set (5–15 signals)
Group by theme. Summarize each group. Cite top 3–5 sources.

### Large result set (15+ signals)
High-level synthesis with offer to drill down. Prioritize most recent material first per the workflow instructions (signal density check).

## Anti-Patterns

Do not:
- List results source by source ("From Slack: ... From email: ...")
- Include signals that do not directly involve the user
- Bury the insight under methodology explanation
- Present conflicting info without flagging the conflict
- Omit source attribution
- Compress multiple distinct situations into one insight candidate — keep them separate

Do:
- Lead with the signal, not the source
- Group by topic, not by tool
- Flag confidence when sources are old or informal
- Surface conflicts explicitly
- Attribute all candidates to their sources
- Preserve the specificity that makes insights valuable — "the client pushed back on the 90-day timeline because their board set a Q2 go-live date" beats "the client had timeline concerns"

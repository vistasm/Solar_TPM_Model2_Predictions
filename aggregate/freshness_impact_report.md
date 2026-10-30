# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-10-30 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (80.0%) is 5.0% HIGHER than DEGRADED (75.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (6.2%) is 2.6× the overall rate (2.3%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.1%) is 2.4× the overall rate (4.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 18.5% | 0.501 | 0.3 |       81 | 80.0% |  33.3% | 1.8× | 6.7% |   0.4444 |
|       OK |   42 |   37.0 | 7.1% | 0.419 | 0.1 |       42 | 33.3% |  20.0% | 2.8× | 5.4% |   0.1190 |
| DEGRADED |   92 |  122.7 | 4.3% | 0.381 | 0.0 |       92 | 75.0% |  15.0% | 3.5× | 1.4% |   0.2174 |
|      ALL |  215 |   64.6 | 10.2% | 0.433 | 0.1 |      215 | 72.7% |  26.2% | 2.6× | 3.9% |   0.2837 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 6.2% | 0.487 | 0.1 |       81 | 60.0% |  23.1% | 3.7× | 2.9% |   0.1605 |
|       OK |   42 |   37.0 | 0.0% | 0.358 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   92 |  122.7 | 0.0% | 0.324 | 0.0 |       92 |    - |   0.0% |    - | 0.0% |   0.0543 |
|      ALL |  215 |   64.6 | 2.3% | 0.392 | 0.0 |      215 | 60.0% |  16.7% | 7.2× | 1.0% |   0.0837 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 11.1% | 0.597 | 0.1 |       81 | 11.1% |  20.0% | 1.8× | 10.5% |   0.0617 |
|       OK |   42 |   37.0 | 2.4% | 0.535 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   92 |  122.7 | 0.0% | 0.507 | 0.0 |       92 |    - |   0.0% |    - | 0.0% |   0.0109 |
|      ALL |  215 |   64.6 | 4.7% | 0.547 | 0.1 |      215 | 10.0% |  16.7% | 3.6× | 4.3% |   0.0279 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   11 |  110.5 | 27.3% | 0.467 | 0.3 |       11 | 100.0% |  60.0% | 2.2× | 0.0% |   0.4545 |
|      ALL |   11 |  110.5 | 27.3% | 0.467 | 0.3 |       11 | 100.0% |  60.0% | 2.2× | 0.0% |   0.4545 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   11 |  110.5 | 0.0% | 0.418 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|      ALL |   11 |  110.5 | 0.0% | 0.418 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   11 |  110.5 | 0.0% | 0.553 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   11 |  110.5 | 0.0% | 0.553 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available
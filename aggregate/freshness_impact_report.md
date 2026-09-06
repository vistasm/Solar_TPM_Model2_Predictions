# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-06 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (78.6%) is 78.6% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (6.5%) is 2.4× the overall rate (2.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.7%) is 2.1× the overall rate (5.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.7 | 19.5% | 0.517 | 0.3 |       73 | 78.6% |  32.4% | 1.7× | 7.7% |   0.4658 |
|       OK |   39 |   36.7 | 7.7% | 0.424 | 0.1 |       39 | 33.3% |  20.0% | 2.6× | 5.9% |   0.1282 |
| DEGRADED |   65 |  118.5 | 1.5% | 0.393 | 0.0 |       65 | 0.0% |   0.0% |    - | 2.0% |   0.2308 |
|      ALL |  181 |   55.9 | 10.5% | 0.453 | 0.1 |      177 | 66.7% |  22.2% | 2.2× | 4.9% |   0.3051 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.7 | 6.5% | 0.505 | 0.1 |       73 | 60.0% |  23.1% | 3.4× | 3.3% |   0.1781 |
|       OK |   39 |   36.7 | 0.0% | 0.365 | 0.0 |       39 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   65 |  118.5 | 0.0% | 0.338 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0462 |
|      ALL |  181 |   55.9 | 2.8% | 0.415 | 0.0 |      177 | 60.0% |  18.8% | 6.6× | 1.2% |   0.0904 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.7 | 11.7% | 0.601 | 0.1 |       73 | 11.1% |  20.0% | 1.6× | 11.8% |   0.0685 |
|       OK |   39 |   36.7 | 2.6% | 0.536 | 0.0 |       39 | 0.0% |      - |    - | 2.6% |   0.0000 |
| DEGRADED |   65 |  118.5 | 0.0% | 0.498 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0154 |
|      ALL |  181 |   55.9 | 5.5% | 0.550 | 0.1 |      177 | 10.0% |  16.7% | 3.0× | 5.3% |   0.0339 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.1 | 20.0% | 0.569 | 0.3 |       11 | 50.0% |  20.0% | 1.1× | 16.7% |   0.4545 |
|       OK |    7 |   36.3 | 14.3% | 0.554 | 0.1 |        7 | 0.0% |   0.0% |    - | 16.7% |   0.1429 |
| DEGRADED |    9 |  135.9 | 0.0% | 0.345 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|      ALL |   31 |   54.0 | 12.9% | 0.500 | 0.2 |       27 | 33.3% |  14.3% | 1.3× | 10.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.1 | 0.0% | 0.530 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |    7 |   36.3 | 0.0% | 0.528 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |  135.9 | 0.0% | 0.277 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   54.0 | 0.0% | 0.456 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.1 | 0.0% | 0.572 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   36.3 | 0.0% | 0.574 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |  135.9 | 0.0% | 0.528 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   54.0 | 0.0% | 0.560 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available
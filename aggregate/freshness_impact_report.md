# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-19 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (10.3%) is 2.1× the overall rate (4.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.3 | 10.3% | 0.436 | 0.1 |       39 | 100.0% |  23.5% | 2.3× | 0.0% |   0.4359 |
|       OK |   24 |   37.5 | 4.2% | 0.375 | 0.0 |       24 | 100.0% |  33.3% | 8.0× | 0.0% |   0.1250 |
| DEGRADED |   39 |  120.7 | 0.0% | 0.365 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.2571 |
|      ALL |  102 |   60.0 | 4.9% | 0.394 | 0.1 |       98 | 100.0% |  17.2% | 3.4× | 0.0% |   0.2959 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.3 | 0.0% | 0.438 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.1282 |
|       OK |   24 |   37.5 | 0.0% | 0.321 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   39 |  120.7 | 0.0% | 0.317 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0857 |
|      ALL |  102 |   60.0 | 0.0% | 0.364 | 0.0 |       98 |    - |   0.0% |    - | 0.0% |   0.0816 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.3 | 7.7% | 0.596 | 0.1 |       39 | 0.0% |   0.0% |    - | 8.3% |   0.0769 |
|       OK |   24 |   37.5 | 4.2% | 0.536 | 0.0 |       24 | 0.0% |      - |    - | 4.2% |   0.0000 |
| DEGRADED |   39 |  120.7 | 0.0% | 0.473 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0286 |
|      ALL |  102 |   60.0 | 3.9% | 0.535 | 0.0 |       98 | 0.0% |   0.0% |    - | 4.3% |   0.0408 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   15.2 | 0.0% | 0.379 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |    7 |   42.9 | 0.0% | 0.349 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   98.0 | 0.0% | 0.392 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.4444 |
|      ALL |   31 |   56.2 | 0.0% | 0.378 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   15.2 | 0.0% | 0.401 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    7 |   42.9 | 0.0% | 0.285 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   98.0 | 0.0% | 0.340 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|      ALL |   31 |   56.2 | 0.0% | 0.349 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   15.2 | 9.1% | 0.596 | 0.1 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    7 |   42.9 | 0.0% | 0.556 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   98.0 | 0.0% | 0.507 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   56.2 | 3.2% | 0.549 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available
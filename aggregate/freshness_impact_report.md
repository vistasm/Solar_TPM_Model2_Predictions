# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-02 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (12.9%) is 2.2× the overall rate (5.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   13.3 | 12.9% | 0.436 | 0.2 |       30 | 100.0% |  26.7% | 2.0× | 0.0% |   0.5000 |
|       OK |   20 |   36.6 | 5.0% | 0.394 | 0.1 |       19 | 100.0% |  33.3% | 6.3× | 0.0% |   0.1579 |
| DEGRADED |   34 |  124.7 | 0.0% | 0.368 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.2188 |
|      ALL |   85 |   63.4 | 5.9% | 0.399 | 0.1 |       81 | 100.0% |  20.0% | 3.2× | 0.0% |   0.3086 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   13.3 | 0.0% | 0.424 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |   20 |   36.6 | 0.0% | 0.332 | 0.0 |       19 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   34 |  124.7 | 0.0% | 0.311 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   85 |   63.4 | 0.0% | 0.357 | 0.0 |       81 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   13.3 | 6.5% | 0.590 | 0.1 |       30 | 0.0% |   0.0% |    - | 7.1% |   0.0667 |
|       OK |   20 |   36.6 | 5.0% | 0.532 | 0.1 |       19 | 0.0% |      - |    - | 5.3% |   0.0000 |
| DEGRADED |   34 |  124.7 | 0.0% | 0.485 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0312 |
|      ALL |   85 |   63.4 | 3.5% | 0.534 | 0.0 |       81 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.0 | 0.0% | 0.361 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    8 |   37.4 | 0.0% | 0.365 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   85.8 | 0.0% | 0.391 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.3333 |
|      ALL |   31 |   52.5 | 0.0% | 0.376 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.0 | 0.0% | 0.281 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.4 | 0.0% | 0.255 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   85.8 | 0.0% | 0.298 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   31 |   52.5 | 0.0% | 0.282 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.0 | 0.0% | 0.543 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.4 | 0.0% | 0.546 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   85.8 | 0.0% | 0.565 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   52.5 | 0.0% | 0.554 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available
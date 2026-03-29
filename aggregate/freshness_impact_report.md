# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-03-29 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

✅ No anomalies detected. Insufficient data or metrics within normal range.

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   16.5 | 0.0% | 0.332 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.4286 |
|       OK |    7 |   37.3 | 0.0% | 0.320 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.2000 |
| DEGRADED |    4 |   86.1 | 0.0% | 0.323 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   20 |   37.7 | 0.0% | 0.326 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.3125 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   16.5 | 0.0% | 0.401 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.3 | 0.0% | 0.381 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   86.1 | 0.0% | 0.338 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   20 |   37.7 | 0.0% | 0.381 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   16.5 | 0.0% | 0.493 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.3 | 0.0% | 0.499 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   86.1 | 0.0% | 0.457 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   20 |   37.7 | 0.0% | 0.488 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   16.5 | 0.0% | 0.332 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.4286 |
|       OK |    7 |   37.3 | 0.0% | 0.320 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.2000 |
| DEGRADED |    4 |   86.1 | 0.0% | 0.323 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   20 |   37.7 | 0.0% | 0.326 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.3125 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   16.5 | 0.0% | 0.401 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.3 | 0.0% | 0.381 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   86.1 | 0.0% | 0.338 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   20 |   37.7 | 0.0% | 0.381 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   16.5 | 0.0% | 0.493 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.3 | 0.0% | 0.499 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   86.1 | 0.0% | 0.457 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   20 |   37.7 | 0.0% | 0.488 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available
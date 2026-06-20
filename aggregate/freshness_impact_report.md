# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-20 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (10.0%) is 2.1× the overall rate (4.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   40 |   13.0 | 10.0% | 0.429 | 0.1 |       39 | 100.0% |  23.5% | 2.3× | 0.0% |   0.4359 |
|       OK |   24 |   37.5 | 4.2% | 0.375 | 0.0 |       24 | 100.0% |  33.3% | 8.0× | 0.0% |   0.1250 |
| DEGRADED |   39 |  120.7 | 0.0% | 0.365 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |  103 |   59.5 | 4.9% | 0.392 | 0.1 |       99 | 100.0% |  17.2% | 3.4× | 0.0% |   0.2929 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   40 |   13.0 | 0.0% | 0.431 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.1282 |
|       OK |   24 |   37.5 | 0.0% | 0.321 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   39 |  120.7 | 0.0% | 0.317 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |  103 |   59.5 | 0.0% | 0.362 | 0.0 |       99 |    - |   0.0% |    - | 0.0% |   0.0808 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   40 |   13.0 | 7.5% | 0.593 | 0.1 |       39 | 0.0% |   0.0% |    - | 8.3% |   0.0769 |
|       OK |   24 |   37.5 | 4.2% | 0.536 | 0.0 |       24 | 0.0% |      - |    - | 4.2% |   0.0000 |
| DEGRADED |   39 |  120.7 | 0.0% | 0.473 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.0278 |
|      ALL |  103 |   59.5 | 3.9% | 0.534 | 0.0 |       99 | 0.0% |   0.0% |    - | 4.2% |   0.0404 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.8 | 0.0% | 0.380 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |    7 |   42.9 | 0.0% | 0.349 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   98.0 | 0.0% | 0.392 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   55.7 | 0.0% | 0.378 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.8 | 0.0% | 0.407 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    7 |   42.9 | 0.0% | 0.285 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   98.0 | 0.0% | 0.340 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   31 |   55.7 | 0.0% | 0.351 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.8 | 9.1% | 0.593 | 0.1 |       10 | 0.0% |   0.0% |    - | 11.1% |   0.1000 |
|       OK |    7 |   42.9 | 0.0% | 0.556 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   98.0 | 0.0% | 0.507 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   55.7 | 3.2% | 0.548 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available
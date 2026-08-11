# DTDC Shipment Operations Dashboard (Mock Data)

An Excel-based operations dashboard simulating shipment, revenue, and delivery-performance data for a logistics/courier network modeled on DTDC. Built for practicing dashboarding, pivot analysis, and KPI reporting in Excel.

## 📂 File

| File | Description | Link |
|---|---|---|
| `DTDC.Dataset.working.file.2.xlsx` | Full workbook — raw data, calculation sheets, and dashboards | [📥 Download](https://github.com/Hareshwaran55/DTDC-Analysis-Dashboard/releases/download/dashboard-v1/DTDC.Dataset.working.file.2.xlsx) |

## 📊 Workbook Structure

The workbook has three sheets:

| Sheet | Purpose |
|---|---|
| **Dashboard** | High-level KPI scorecard and charts |
| **Data** | Raw, row-level shipment records (180 rows) |
| **Summary** | Pivot-style breakdowns feeding the dashboard visuals |

### Data sheet columns
Origin, Destination, Sender State, Receiver State, Booking Date, Month, Mode (Surface / Express / Air Cargo), Nature of Consignment (Dox / Non-Dox), Value Added Service (COD / Insurance / Express / None), Mode of Payment (Cash / Card / Wallet), Actual/Volumetric/Chargeable Weight, Total Amount, Expiry Date, Receive Date, Transit Time (days), Buffer Days, SLA Status, Paperwork Complete, Sender Signature.

### Summary sheet breakdowns
Monthly trend, service-mode split, payment-mode split, Dox vs Non-Dox split, value-added-service split, SLA delivery status, top 10 routes by shipment count, and an origin-state × destination-state shipment matrix.

## 🔑 Headline KPIs

| Metric | Value |
|---|---|
| Total Shipments | 180 |
| Total Revenue | ₹59,762.50 |
| Average Transit Time | 3.71 days |
| On-Time Delivery Rate | 87.8% |

## 📈 Key Insights

- **Monthly trend:** June recorded 91 shipments (₹26,041.05) and July recorded 89 shipments (₹33,721.45) — July generated ~30% more revenue on slightly fewer shipments, pointing to a higher average order value. August has no bookings yet in this dataset.
- **Service mode:** Surface is the most-used mode (79 shipments) but generates the least revenue (₹15,592.80). Express (66 shipments, ₹26,750.90) is the top revenue contributor, and Air Cargo, despite the fewest shipments (35), earns a disproportionately high ₹17,418.80 — consistent with higher per-shipment freight charges for air mode.
- **Payment mix:** Card is the leading payment method by both count (80) and revenue (₹27,013.65), narrowly ahead of Cash (77 shipments, ₹25,959.00). Wallet trails well behind (23 shipments, ₹6,789.85).
- **Consignment type:** Non-Dox shipments (128) far outnumber Dox/document shipments (52) and carry a much higher average weight (9.13 kg vs 1.66 kg), as expected for parcels versus paperwork.
- **Value-added services:** 75 shipments used no add-on service, while COD was the most popular add-on (62 shipments), followed by Express (23) and Insurance (20).
- **SLA performance:** 158 of 180 shipments (87.8%) were delivered on time, with 22 (12.2%) delivered late — matching the dashboard's on-time KPI.
- **Route concentration:** No single route dominates — the busiest corridors (e.g., Jamshedpur–Agra, Ranchi–Srinagar, Amritsar–Bangalore) each account for only 2–3 shipments, indicating a highly fragmented, pan-India route network rather than a few high-volume lanes.
- **State-to-state flow:** The Uttar Pradesh → Punjab corridor is the single busiest state pair (6 shipments), and Maharashtra and Uttar Pradesh appear as the most frequent receiver states across multiple origins, suggesting these are key demand hubs in the network.

### Top 5 States (by combined sender + receiver activity)

| Rank | State | Total Shipments (sent + received) | Total Revenue (Rs) |
|---|---|---|---|
| 1 | Maharashtra | 48 | ₹17,997.15 |
| 2 | Uttar Pradesh | 46 | ₹15,530.05 |
| 3 | Jharkhand | 36 | ₹10,561.80 |
| 4 | Punjab | 32 | ₹9,873.10 |
| 5 | Andhra Pradesh | 28 | ₹8,793.05 |

Maharashtra and Uttar Pradesh are the clear demand hubs, together accounting for over a quarter of all shipment activity (94 of 360 sender+receiver instances) and nearly 56% of the combined top-5 revenue. Both states also lead individually as top **sender** states (Uttar Pradesh and Maharashtra tied at 24 shipments each) and top **receiver** states (Maharashtra 24, Uttar Pradesh 22) — indicating strong two-way traffic rather than a one-directional hub.

### Top 5 Cities (by combined origin + destination activity)

| Rank | City | Total Shipments (origin + destination) | Total Revenue (Rs)* |
|---|---|---|---|
| 1 | Ranchi | 18 | — |
| 1 | Jamshedpur | 18 | ₹5,906.35 |
| 3 | Bhubaneswar | 17 | ₹5,653.10 |
| 4 | Ludhiana | 16 | ₹5,489.90 |
| 4 | Coimbatore | 16 | — |

*Revenue is attributed to a city whenever it appears as either origin or destination on a shipment.*

Ranchi and Jamshedpur (both in Jharkhand) top the city-level activity list, reinforcing Jharkhand's position as the #3 state overall. By revenue specifically, **Bangalore** is the single highest-earning city (₹7,496.75) despite lower shipment volume — consistent with the earlier finding that revenue doesn't track volume 1:1, likely driven by heavier/higher-value Non-Dox and Air Cargo shipments through that city.

**Top origin cities (outbound volume):** Vizag (11), Jamshedpur (10), Bangalore (10), Amritsar (9), Ranchi (8)
**Top destination cities (inbound volume):** Ludhiana (10), Ranchi (10), Coimbatore (9), Chandigarh (9), Bhubaneswar (9)

### Dashboards
<img width="878" height="656" alt="Screenshot 2026-08-11 090033" src="https://github.com/user-attachments/assets/f8b7aaad-127c-4c04-a7e0-fbe8bce71e60" />


## ✅ Conclusion

This mock dataset illustrates a mid-sized courier network with balanced volume across service modes but a clear split between low-value, high-frequency Surface shipments and higher-value, lower-frequency Air Cargo shipments. Revenue is not simply proportional to shipment count — Air Cargo's outsized revenue share highlights the importance of tracking revenue-per-shipment alongside raw volume. On-time delivery at ~88% is solid but leaves room for improvement, particularly worth investigating against Surface-mode routes and longer-distance state pairs, which are the more likely sources of the 22 late deliveries. The lack of route concentration suggests operational complexity (many low-volume lanes) rather than a few lanes driving most of the load, which has implications for hub/routing optimization.



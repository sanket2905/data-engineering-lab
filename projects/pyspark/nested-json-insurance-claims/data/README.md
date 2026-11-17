# Input data

`insurance_claim.json` contains **100 synthetic claim records** in JSON Lines (NDJSON) format: one complete JSON object per line. Spark's `spark.read.json("data/insurance_claim.json")` reads this format directly.

Each claim includes:
- A unique `claim_id`
- Nested customer and hospital details
- A `treatments` array containing nested arrays of treatment records
- Treatment details including `treatment_id`, `treatment_name`, `cost`, `units`, and a `medicines` array
- Medicine details including `medicine_name`, `price`, and `quantity`
- A `deductions` array with `deduction_type` and `amount`

All names, hospitals, and amounts in this dataset are fictional and generated for practice. They do not represent real customers, patients, hospitals, or claims.

To read the data in PySpark:

```python
df = spark.read.json("data/insurance_claim.json")
```

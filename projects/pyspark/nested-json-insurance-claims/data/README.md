# Input data

Add the source JSON file here with the exact filename `insurance_claim.json`. The notebook reads it from this folder.

The input is expected to contain a claim-level identifier (`claim_id`), a nested `treatments` array (nested one level, with treatment records), a `medicines` array within each treatment, and a `deductions` array. Each treatment record is expected to include `treatment_id`, `treatment_name`, `cost`, `units`, and `medicines`. Each medicine is expected to include `medicine_name`, `price`, and `quantity`. Each deduction is expected to include `deduction_type` and `amount`.

No source data is committed yet. Add only data you are permitted to publish; remove or anonymize personal, medical, and other sensitive information before making a repository public.

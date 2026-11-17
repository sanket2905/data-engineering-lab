# PySpark: Nested JSON Insurance Claims

## Objective

Process nested insurance claim JSON and calculate a final amount for each claim using:

**Final claim amount = Treatment cost + Medicine cost - Total deductions**

## Concepts demonstrated

- Reading multiline JSON with PySpark
- Understanding nested `StructType` and `ArrayType` fields
- Using `flatten()` and `explode()` on nested arrays
- Calculating treatment-level and medicine-level costs
- Aggregating deductions at claim level
- Managing DataFrame grain to avoid double counting
- Joining independently aggregated results

## Project files

- `insurance_claims_analysis.ipynb` — end-to-end notebook
- `data/` — location for the source JSON file

## Input data

Place the input file at `data/insurance_claim.json`. The expected schema and setup notes are in [data/README.md](data/README.md).

The source data file has not been included in this repository yet.

## Run locally

1. Install Python and Java (required by Apache Spark).
2. Install dependencies: `pip install -r requirements.txt` (from the repository root).
3. Place `insurance_claim.json` inside this project's `data/` directory.
4. Open the notebook and run the cells from top to bottom, with this project directory as the working directory.

## Important implementation note

The notebook explodes the medicines array, which repeats treatment columns across medicine rows. It therefore selects distinct treatment-level records before aggregating treatment costs. In production, validate the business key and duplicate-handling rules against the source system.

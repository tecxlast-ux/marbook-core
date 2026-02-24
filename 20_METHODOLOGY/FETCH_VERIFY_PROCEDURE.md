# FETCH & VERIFY CURRENT STATE PROCEDURE

Objective:
Ensure any AI model starts from the actual current GitHub state before doing work.

Repository:
https://github.com/tecxlast-ux/marbook-core
Branch: main

Step 1 — Fetch
Model must open the repository main branch.

Step 2 — Return Proof
Model must respond with exactly:

CURRENT_SHA: <40-character commit SHA of main HEAD>
PROOF_FILE: <full relative path of one file opened>
PROOF_LINE: <first heading or first line from that file>

Step 3 — Verification
Human checks:
- SHA matches GitHub main HEAD
- PROOF_FILE exists
- PROOF_LINE exists in that file

If any item fails:
- Model is considered NOT current
- Work must not proceed

Rule:
GitHub main HEAD is the only source of truth.
Model internal memory is not authoritative.
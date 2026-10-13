# Analysis data

Each study has its own folder under `main/` or `supplementary/`. Main Study 3a and 3b are grouped under `main/study3/a` and `b`.

The public files retain study responses, derived scores used for checks, numeric demographics and inclusion flags. Original participant IDs are replaced with `P0001`, `P0002`, and so on within each study; the same anonymous ID links a supplementary response export to its supplied working file. Row order is preserved for the participant bootstrap analyses. These IDs do not link participants across studies.

Platform account IDs, response identifiers, IP addresses, locations, timestamps, timing metadata and open-text responses are omitted. The response values used by `paper.Rmd` are unchanged. The public inputs reproduce the working analysis results at tolerance 1e-7.

## Files and coding

- Main `study*.csv` files are supplied working data, with `Condition` coded 1 = agency and 2 = compliance. Analyses retain `Exclusion == 0`; Study 1 also checks `Finished == 1`. Study 1’s behavioral items are 0/1 checkboxes; the notebook treats unchecked boxes as zero only for included completed surveys. Other main behavioral ratings range from 1 to 5; mediator ratings range from 1 to 7.
- Supplementary `raw.csv` files are column-restricted response exports. Their first two rows retain the Qualtrics question labels and import identifiers. `supplied_cleaned.csv` files retain one response-code row. The notebook removes these rows and verifies included participants’ mapped item values and vignette scores against the supplied working files.
- Supplementary condition codes also use 1 = agency and 2 = compliance. The notebook reports exclusion criteria, sample checks and the retained inclusion flags. The files include available excluded and incomplete records; they are not restricted to the final samples.

## Scoring and analysis decisions

Main behavioral scores average answered items within each vignette and then weight the three vignettes equally. Study 1 instead counts selected sabotage actions per vignette. Main Study 3b’s retained mediation uses all answered behavioral items; three single-item omissions create a small difference from its equally weighted vignette score. Both scoring rules remain explicit in the notebook.

Supplementary Study 1 has one missing de-escalation item; its vignette score uses the answered items and the overall score weights vignettes equally. In Supplementary Studies 1 and 2, agency participants received an incorrect compliance reminder after vignette 2. The behavioral analyses retain all three vignettes. Supplementary Study 2's retained exploratory mediation uses vignettes 1 and 3 and is labeled separately from the registered behavioral analyses. Supplementary Study 2 retains the supplied 259-person primary sample and separately reports the 232-person sample obtained by applying the registered second attention-check exclusion rule. Supplementary Study 4’s two unemployment exclusions are an additional eligibility decision.

The original main platform exports, independent coder/adjudication records, 40 excluded Main Study 3a records and Supplementary Study 1 thematic coding were not available. These gaps do not prevent reproducing the analyses of the supplied samples. Retention of the 259-person Supplementary Study 2 primary sample remains an author decision.

# South Florida Condominium Register and Florida condo age by county

7,940 condominiums with 20 or more units in Miami-Dade, Broward and Palm Beach counties, compiled by Miami Condo HQ from Florida DBPR condominium public records: association legal name, DBPR managing-entity and project numbers, unit count, declaration recorded date and address on file. This repository also holds the county table of Miami Condo HQ's Florida condo age report 2026: for each of 54 counties, the registered condominiums of 20 or more units, their units, and how many were recorded with the state before 1996.

Miami Condo HQ is published by Eltherion, LLC. It is an independent research website, not a condo association or management company.

## Canonical pages

| What | Page |
| --- | --- |
| The register, with the CSV download and how to cite it | https://miamicondohq.com/condo-associations |
| Florida condo age report 2026 (every county) | https://miamicondohq.com/research/florida-condo-age-report |
| South Florida condo age report 2026 (Miami-Dade, Broward and Palm Beach) | https://miamicondohq.com/research/south-florida-condo-age-report |
| Data sources and methodology | https://miamicondohq.com/methodology |
| Archived snapshot of the register CSV (Zenodo) | https://doi.org/10.5281/zenodo.23924754 |

## Files

All files were downloaded on 2026-11-13 and are kept exactly as published. The file names are the download names the site sends. SHA-256 checksums are in `CHECKSUMS.txt`.

| File | Published at | Data rows | Columns |
| --- | --- | --- | --- |
| `data/south-florida-condominium-register.csv` | https://miamicondohq.com/condo-associations/data.csv | 7,940 | 12 |
| `data/florida-condo-age-by-county.csv` | https://miamicondohq.com/research/florida-condo-age-report/counties.csv | 54 | 7 |
| `data/south-florida-condominium-register-sample.csv` | Not on the site. The header and the first 100 data rows of the register file, added here because the full file (about 2.2 MB) is large to browse on GitHub. | 100 | 12 |

Format notes, from the files themselves:

- The register file has one header line and uses CRLF line endings.
- The county file starts with one comment line that begins with `#`, then the header line. Skip the first line when loading it (for example `pandas.read_csv(path, skiprows=1)`). The comment line reads: `# Florida condo age report: Florida DBPR condominium public records, checked 2026-11-07. Source: Miami Condo HQ (Eltherion, LLC).`
- The South Florida condo age report has no file of its own. Its page says the South Florida register behind its figures is the register CSV above.

## Source of the underlying records

The records are the Florida Department of Business and Professional Regulation's (DBPR) condominium public-records extracts, published on the [DBPR public records page](https://www2.myfloridalicense.com/condos-timeshares-mobile-homes/public-records/).

The register (Miami-Dade, Broward and Palm Beach), as its page lists the sources:

| Source | Checked |
| --- | --- |
| Florida DBPR condominium public records, Dade and Monroe Counties (Condo_MD.csv) | 2026-09-27 |
| Florida DBPR condominium public records, Broward and Palm Beach Counties (condo_PB.csv) | 2026-10-26 |

The county table, as the Florida condo age report lists the sources:

| Source | Checked |
| --- | --- |
| Florida DBPR condominium public records, Dade and Monroe Counties (Condo_MD.csv) | 2026-09-27 |
| Florida DBPR condominium public records, Broward and Palm Beach Counties (condo_PB.csv) | 2026-10-26 |
| Florida DBPR condominium public records, Dade and Monroe Counties (Condo_MD.csv), Monroe County rows | 2026-11-07 |
| Florida DBPR condominium public records, Central Florida West (Condo_CW.csv) | 2026-11-07 |
| Florida DBPR condominium public records, Central Florida East (condo_CE.csv) | 2026-11-07 |
| Florida DBPR condominium public records, North Florida (Condo_NF.csv) | 2026-11-07 |

## Columns

### south-florida-condominium-register.csv

The register page says the file holds only the public fields shown on each condominium's page.

| Column | Meaning | First row | Blank cells |
| --- | --- | --- | --- |
| `condominium_dbpr_name` | Condominium name as it is on file with DBPR | `1 OCEAN BOULEVARD CONDO` | 0 |
| `condominium` | Condominium name as Miami Condo HQ shows it | `1 Ocean Boulevard Condo` | 0 |
| `association_legal_name` | Association legal name on the DBPR record | `1 OCEAN BOULEVARD CONDO ASSN, INC` | 5 |
| `dbpr_managing_entity_no` | DBPR managing-entity number | `MA63871` | 5 |
| `dbpr_project_no` | DBPR project number of the condominium | `PR68924` | 0 |
| `units` | Unit count on the DBPR record | `81` | 0 |
| `declaration_recorded` | Date the condominium declaration was recorded, as YYYY-MM-DD | `2005-02-23` | 0 |
| `address_on_file` | Address on file with DBPR | `49 & 149 SE 20TH AVE, DEERFIELD BEACH, FL 33441` | 0 |
| `city` | City. The report pages say cities follow the mailing city on the state record. | `Deerfield Beach` | 0 |
| `county` | County: `Broward County`, `Miami-Dade County` or `Palm Beach County` | `Broward County` | 0 |
| `zip` | ZIP code | `33441` | 4 |
| `page_url` | The condominium's page on miamicondohq.com | `https://miamicondohq.com/condo-associations/1-ocean-boulevard-condo-pr68924` | 0 |

### florida-condo-age-by-county.csv

| Column | Meaning | First row |
| --- | --- | --- |
| `county` | County. The report says counties are the county on the state record. | `Broward County` |
| `dbpr_region` | One of `South Florida`, `Florida Keys`, `Central Florida West`, `Central Florida East`, `North Florida` | `South Florida` |
| `condominiums_20_plus_units` | Registered condominiums with 20 or more units | `2962` |
| `units` | Units in those condominiums | `242972` |
| `condominiums_recorded_before_1996` | Condominiums recorded with the state before 1996 | `2513` |
| `units_recorded_before_1996` | Units in the condominiums recorded before 1996 | `185206` |
| `share_of_units` | `units_recorded_before_1996` as a share of `units`, written as a decimal (`0.7623`; the report page shows Broward County as 76%) | `0.7623` |

## Method

From the Florida condo age report:

> Counts cover every condominium with 20 or more units in our register, built from the Florida Department of Business and Professional Regulation's condominium public-records extracts for every region of the state, grouped by the declaration's recorded date. Older means recorded before 1996. Counties are the county on the state record; cities follow the mailing city on that record, which can cross a county line.

From the South Florida condo age report:

> Counts cover every condominium with 20 or more units in Miami-Dade, Broward and Palm Beach in our register, built from the Florida Department of Business and Professional Regulation's condominium public-records extracts, grouped by the declaration's recorded date. Older means recorded before 1996. Cities follow the mailing city on the state record.

## Caveats stated on the live pages

- A recorded date is not a construction date. "A recorded date is when the condominium was registered with the state; a building converted to condominium later can be older than its record."
- The figures are not a count of inspections due. "The files do not record building height, so these figures are an upper bound on buildings covered by milestone inspections, not a count of inspections due."
- "Some large older condominiums are campground or resort condominiums, which the state registers the same way."
- "A recorded date and a unit count say nothing about a building's condition, height, inspection results, reserves or charges."
- "A record identifies the association registered for a condominium, not its finances, rules or current management."
- The methodology page says a record "says nothing about finances, rules, inspections or current management."
- Coverage of the CSV: "The CSV and its DOI snapshot (archived November 3, 2026) cover Miami-Dade, Broward and Palm Beach only." Condominiums in the other counties are on their own pages on the site, not in this file.

## Updates

The Miami Condo HQ methodology page says the condominium register is "updated when we re-run or review them, with the check date shown beside the information." The register page says: "Cite the DOI for a fixed version, or the page for the latest data." The files in this repository are the copies downloaded on 2026-11-13; the pages above have the latest data.

## How to cite

The register, as its page gives it:

> Miami Condo HQ (Eltherion, LLC). South Florida Condominium Register (Miami-Dade, Broward and Palm Beach), compiled from Florida DBPR condominium public records (Condo_MD.csv and condo_PB.csv), checked October 26, 2026. https://miamicondohq.com/condo-associations. Archived snapshot: https://doi.org/10.5281/zenodo.23924754

The register page adds: "A dated snapshot of this file is archived on Zenodo with a permanent DOI: 10.5281/zenodo.23924754 (deposited 2026-11-03)."

The county table, as the Florida condo age report gives it:

> Miami Condo HQ (Eltherion, LLC), Florida condo age report 2026, from Florida DBPR condominium records checked 2026-11-07.

The South Florida report, as its page gives it:

> Miami Condo HQ (Eltherion, LLC), South Florida condo age report 2026, from Florida DBPR condominium records checked 2026-10-26.

A machine-readable citation is in `CITATION.cff`.

## License

The Florida condo age report says: "County figures are free to reuse with that credit." This compilation is released under the Creative Commons Attribution 4.0 International license (CC BY 4.0); see `LICENSE`. Credit Miami Condo HQ (Eltherion, LLC) as shown above. The underlying records are public records from the Florida Department of Business and Professional Regulation.

## Corrections

From the methodology page: "If something here is wrong, email hello@miamicondohq.com with the page address, the statement in question and a supporting public source."

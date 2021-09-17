# NCQA - Template Repo Breakdown

- [Original Github Repo](https://github.com/nistar/ncqa), P4PVB certification
- Notes
    - this seems to have been attempted by a java developer (from doing a little background search on the autor)
        - so the setup seems to be somewhat less pythonic than a standard repo, but also rather formal and advanced stylistically relative to most other 3rd party libraries of solo developers that aren't under active develment

## Breakdown

Due to the complexity and sophistication, we are taking this repository as a self-guided textbook, and will be breaking down each module, via the mkdocs documentation, parallel with the established project hierarchy

###  Root `/
    
- analyze
    - analyzer.py
- db
    - mongo
        - connector.py
- fda
    - ndc_loader.py
- input
    - code_to_desc.py
    - member-en.py
    - member-gm.py
    - mmdf.py
    - pharm.py
    - provider.py
    - visit.py
- load
    - populate-db`
        - bulk insert handler for mongo interactions
    - populate-sample-results
- measures
    - bcs.py - example measure logic
- merge
    - create_member.py
- model
    - code.py
    - context.py
    - enrollment.py
    - member.py
    - mmdf.py
    - optional_exclusions.py
    - overlapping_enrollments.py
    - pharm.py
    - valueset.py
    - visit.py
- natusfilter
    - exclude_members.py
- util
    - natus_config.py
    - natus_logging.py
    - natus_util.py
- valueset
    - uses config variable, which contains the ncqa excel VSD file refs, and which is set in `util` module under `natus_config`
    - `measures_to_valuesets`
        - reads in stock ncqa data, measures x value sets 
        - here, reads from mongoDB
    - `vs_to_codes`
        - reads in value set, codes from mongoDB
    - `load_oid_to_codes`
        -  read Value Set OID -> Codes data, incl code system marker

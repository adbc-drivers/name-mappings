# Canonical Name Mappings for ADBC Drivers

This repository provides authoritative mappings between identifiers used in the [ADBC](https://arrow.apache.org/adbc/) ecosystem. All identifiers use lowercase slug format. These mappings are intended for use in ADBC client libraries, connection string parsers, driver managers, and related tools.

This repository currently contains two mapping files:

| File | Description |
|------|-------------|
| `system-to-driver.yaml` | Maps data system names to compatible driver names |
| `alias-to-driver.yaml` | Maps driver aliases to canonical driver names |

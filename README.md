<!--
  Copyright (c) 2026 ADBC Drivers Contributors

  Licensed under the Apache License, Version 2.0 (the "License");
  you may not use this file except in compliance with the License.
  You may obtain a copy of the License at

          http://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License.
-->

# Canonical Name Mappings for ADBC Drivers

This repository provides authoritative mappings between identifiers used in the [ADBC](https://arrow.apache.org/adbc/) ecosystem. All identifiers use lowercase slug format. Canonical driver names correspond to the driver names used to install drivers with [dbc](https://docs.columnar.tech/dbc/). These mappings are intended for use in ADBC client libraries, connection string parsers, driver managers, and related tools.

This repository currently contains two mapping files:

| File | Description |
|------|-------------|
| [`alias-to-driver.yaml`](./alias-to-driver.yaml) | Maps driver aliases to canonical driver names |
| [`system-to-driver.yaml`](./system-to-driver.yaml) | Maps data system names to compatible/preferred driver names |

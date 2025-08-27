## Overview
Use REST APIs to create, list, modify, and delete resources in facileManager modules from within programs and scripts.

Current modules that support API actions:

* fmDNS

You can automate some tasks that are usually performed manually using the UI.

The REST APIs can be accessed via applications or scripts that support the following request methods:

| Method | Description |
|--------|-------------|
| `GET`  | Get resource information |
| `POST` | Create new resources |
| `PATCH` | Update existing resources |
| `DELETE` | Delete existing resources |

In addition, [`client.php`](./client.php.md) can be used to access the API. This client can often be easier to setup and provides the common functions a user requires.

### Setup
REST APIs are part of the facileManager installation and can be used once enabled in **_Settings → General_**.

![Enable API](../images/api/EnableAPI.png)

Once the API is enabled, [create the key pairs](./auth.md).

### Usage
If you don't want to use the [client.php](client.php.md), you can use this information to form your REST requests.

#### Required Headers
Pass the [required headers for authentication](./auth.md#other-client).

#### URIs
Below are the available URIs to use with your REST client of choice.

##### fmDNS
| URI | Method | Description |
|-----|--------|-------------|
| /api/fmDNS/views/ | `GET` | Retrieves the list of views |
| /api/fmDNS/views/`id`/ | `GET` | Retrieves information for view `id` |
| /api/fmDNS/views/`id`/zones/ | `GET` | Retrieves the list of zones associated with view `id` |
| /api/fmDNS/zones/ | `GET` | Retrieves the list of zones |
| /api/fmDNS/zones/`id`/ | `GET` | Retrieves information for zone `id` |
| /api/fmDNS/zones/`id`/ | `PATCH` | Increments the zone serial number for zone `id` |
| /api/fmDNS/zones/`id`/ | `PATCH` | Sets the zone reload flag for zone `id` |
| /api/fmDNS/zones/`id`/records/ | `GET` | Retrieves the records for zone `id` |
| /api/fmDNS/zones/`id`/records/ | `POST` | Adds a new record for zone `id` |
| /api/fmDNS/zones/`id`/records/`RR`/ | `GET` | Retrieves the `RR` type records for zone `id` |
| /api/fmDNS/zones/`id`/records/`id`/ | `GET` | Retrieves the information for record `id` for zone `id` |
| /api/fmDNS/zones/`id`/records/`id`/ | `PATCH` | Updates record `id` for zone `id` |
| /api/fmDNS/zones/`id`/records/`id`/ | `DELETE` | Deletes record `id` for zone `id` |
| /api/fmDNS/zones/`id`/records/`id`/ | `PATCH`/`POST` | Sets the automatically linked PTR for record `id` for zone `id` |

#### Body Keys
Below are the available keys to use in the body of your REST request for `POST` and `PATCH` methods.

##### fmDNS
| Key | Description |
|-----|-------------|
| record_name | The record name |
| record_ttl | The record TTL |
| record_type | The record type (`A`, `CNAME`, etc.) |
| record_value | The record value |
| record_comment | The record comment |
| setPTR | Whether to set the automatic PTR (`yes` or `no`) |
| reload | Whether to reload the zone (`yes` or `no`) |
| soa-only | Whether to update the SOA serial number only (`yes` or `no`) |

--8<--
footer.md
--8<--

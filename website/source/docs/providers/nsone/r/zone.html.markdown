---
layout: "nsone"
page_title: "NSOne: nsone_zone"
sidebar_current: "docs-nsone-resource-zone"
description: |-
  Creates and manages zones.
---

# nsone\_zone

The ``nsone_zone`` resource creates and manages zones on an NSOne account.

## Example Usage

```
# Create a new zone
resource "nsone_zone" "example" {
  zone = "mycompany.com"
  ttl = 60
}
```

## Argument Reference

The following arguments are supported:

* `zone` - (Required) The name of the zone to define
* `link` - (Optional) The name of another zone to link this zone to (so that they serve the same DNS records)
* `ttl` - (Optional) The TTL for the SOA record for this zone
* `nx_ttl` - (Optional) The TTL for NXDOMAIN answers in this zone
* `refresh` - (Optional) Frequency for slaves to try to refresh this zone
* `retry` - (Optional) Time between slave retries if "refresh" has expired
* `expiry` - (Optional) Time after an expired "refresh" to keep "retrying" before giving up
* `primary` - (Optional) The master nameserver hostname to AXFR this zone from, creates a secondary zone

## Attributes Reference

The following attributes are exported:

* `id` - The internal ID for the zone in the NSONE API
* `hostmaster` - The hostmaster for the zone

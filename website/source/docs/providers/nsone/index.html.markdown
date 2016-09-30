---
layout: "nsone"
page_title: "Provider: NSOne"
sidebar_current: "docs-nsone-index"
description: |-
  A provider for the NSOne DNS and Traffic management service.
---

# NSOne Provider

[NSOne](https://ns1.com) is a DNS and Traffic management service. The NSOne
provider exposes resources used to manage the configuration of your NSOne account.

Use the navigation to the left to read about the available resources.

To provide the API key you can also set the NSONE_APIKEY environment variable.

## Example Usage

The following is a minimal example:

```
# Configure the NSOne provider
provider "nsone" {
  api_key = "xxxxxxx" # Or set NSONE_APIKEY environment variable
}

# Create a zone
resource "nsone_zone" "example" {
  zone = "mycompany.com"
  ttl = 60
}
```

## Argument Reference

The following arguments are supported:

* `api_key` - (Optional) API Key for a given NSOne account

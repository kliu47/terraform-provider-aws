---
subcategory: "SSM"
layout: "aws"
page_title: "AWS: aws_ssm_maintenance_windows"
description: |-
  Get information on SSM maintenance windows.
---

# Data Source: ssm_maintenance_windows

Use this data source to get the window IDs of SSM maintenance windows.

## Example Usage

```terraform
data "aws_ssm_maintenance_windows" "example" {
  filter {
    name   = "Enabled"
    values = ["true"]
  }
}
```

## Argument Reference

* `filter` - (Optional) Configuration block(s) for filtering. Detailed below.

### filter Configuration Block

The following arguments are supported by the `filter` configuration block:

* `name` - (Required) The name of the filter field. Valid values can be found in the [SSM DescribeMaintenanceWindows API Reference](https://docs.aws.amazon.com/systems-manager/latest/APIReference/API_DescribeMaintenanceWindows.html#API_DescribeMaintenanceWindows_RequestSyntax).
* `values` - (Required) Set of values that are accepted for the given filter field. Results will be selected if any given value matches.

## Attributes Reference

* `ids` - List of window IDs of the matched SSM maintenance windows.

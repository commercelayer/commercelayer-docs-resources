---
description: >-
  The import object and the allowed CRUD operations on the related resource
  endpoint
---

# Imports

Imports are very handy resources that let you asynchronously import SKUs, prices, stock items, and many other resources into your organization's environment.

After creating an import, you can poll the resource until the import is complete to get its reports. Import errors and warnings (if any) are reported through the `errors_count`, `errors_log`, `warnings_count`, and `warnings_log` attributes.

When you import a list of resources, you can choose to delete any record that is not included in the list, by setting the `cleanup_records` variable to `true`. In that case, after the import is complete, you also get the number of destroyed records through the `destroyed_count` attribute.

For the complete list of importable resources and any further information about the import process (e.g. import limits, unique key, examples) please check the [related guide](https://docs.commercelayer.io/developers/importing-resources).

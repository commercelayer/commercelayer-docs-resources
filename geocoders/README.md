---
description: The geocoder object and the allowed CRUD operations on the geocoders endpoint
---

# Geocoders

A geocoder allows a user to convert an address in text form into geographic coordinates (like latitude and longitude). A geocoder can be optionally associated with a market. By connecting a geocoder to a market, all the shipping and billing addresses belonging to that market orders will be geocoded. The geocoded coordinates can serve many purposes: placing markers or positions on the map, validating the accuracy and reliability of an address, performing target marketing, location-based promotions, and other ecommerce operations.

Commerce Layer currently supports [Google](../google\_geocoders/) and [Bing](../bing\_geocoders/) geocoder integration.

<details>

<summary>Data model</summary>

Check the related [ER diagram](https://commercelayer.io/docs/data-model/geocoders) and explore the flowchart that illustrates how the geocoder resource relates with the other API entities.

</details>

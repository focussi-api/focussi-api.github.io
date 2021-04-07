---
title: Driver Only Fleet
has_children: true
nav_order: 2
---

# Driver Only Fleet

For a driver only fleet, you can add driver with [Add Driver](/driver_only_fleet/add_driver) API, and simultaneously add a coverage optionally. It's OK to just add the driver without coverage while later insure the driver using the API [Add Coverage for Driver](/driver_only_fleet/add_coverage_for_driver). To close coverage for a given driver is also possible with [Close Coverage for Driver](/driver_only_fleet/close_coverage_for_driver). You can close a driver directly with [Close Driver](/driver_only_fleet/close_driver), this would close any active coverage underneath the coverage automatically. [Search Driver](/driver_only_fleet/search_driver) will list all drivers with coverages underneath that meet the criteria.
# WMI Filters

| WMI Filter | What it does |
|-----|-----|
| select * from Win32_OperatingSystem where ProductType="1" | Only applies to workstations and not servers (Domain controllers and standalone servers) |
| Select DayOfWeek from Win32_LocalTime where DayOfWeek = 1 | Run on a Specific day (1 = Monday, 2 = Tuesday, etc.) |

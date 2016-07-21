## Passenger Paths
Filename: `passenger_paths.csv`

 *  Filename MAY be named `passenger_paths.csv`
 *  File MUST contain a record for each passenger-trip-< link/path segment >
 *  File MUST be a valid CSV file.
 *  The first line of each file MUST contain case-sensitive field names.
 *  Field names MUST NOT contain tabs, carriage returns or new lines.
 
File MUST contain the following attributes:

Required Attributes	| Description										
----------			| -------------		
`person_id`			| Corresponds to `person_id` field in `dyno-demand`-formated demand
`trip_list_id_num`	| Corresponds to line number field in `dyno-demand`-formatted [`trip_list.txt`](https://github.com/osplanning-data-standards/dyno-demand/blob/master/files/trip_list.md) where 1 is the first trip.
`linknum`			| The integer link/path segment number representing the order that this link takes place in the entire path
`A_id_num`			| Internal to fast-trips. (Numeric version of `A_id`, which could be a `stop_id` and `taz`.)
`B_id_num`			| Internal to fast-trips. (Numeric version of `B_id`, which could be a `stop_id` or `taz`.)
`A_id`				| Starting node for link / path segment.  Can be a `stop_id` corresponding to [`stops.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/stops.md) or a `taz` corresponding to an access link such as [`walk_access_ft.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/walk_access_ft.md)
`B_id`				|  Ending node for link / path segment. Can be a `stop_id` corresponding to [`stops.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/stops.md) or a `taz` corresponding to an access link such as [`walk_access_ft.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/walk_access_ft.md)
`mode_num`			| Internal to fast-trips. (Numeric version of `mode`.)
`mode`       | Supply mode for the link, corresponds to `mode` in `GTFS-PLUS`-formatted [`routes_ft.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/routes_ft.md) or an access or egress mode.
`linkmode`			| One of 
-					|    access
-					|    egress
-					|    transfer
-					|    transit
`dist`				| Drive distance in miles between TAZ and lot.
`cost`				| Float cost in the unit specified by `currency_type` variable in [`fare_attributes_ft.txt`](/files/fare_attributes_ft.md)
`travel_time`		| Float driving time in minutes between TAZ and lot.
`start_time`		| HH:MM:SS from midnight.  If blank, it is assumed that this is the base condition and other time of days will override it.
`end_time`			| HH:MM:SS from midnight.  If blank, it is assumed that this is the base condition and other time of days will override it.

File MAY contain the following attributes:

Optional Attributes	| Description										
----------			| -------------		
`pf_iteration`		| ???
`path_num`			| ???
`trip_id_num`		| ???
`trip_id`			| ??? Duplicate?
`route_id`			| Transit route short name corresponding to `route_id` variables in GTFS-PLUS-formatted [`route_ft.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/routes_ft.md)
`A_seq` 			| ???
`B_seq` 			| ???
`pf_A_time` 		| ???	
`pf_B_time` 		| ???	
`pf_linktime min`	| ???
`pf_waittime min`	| ???


bump_iter	bumpstop_boarded	alight_delay_min	new_A_time	new_B_time	new_linktime min	new_waittime min	missed_xfer	sim_cost	chosen	board_time	overcap	overcap_frac	alight_time	iteration

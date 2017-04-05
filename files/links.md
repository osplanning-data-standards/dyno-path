## Passenger Links
Filename: `chosen_links.csv` or `pathset_links.csv`

 *  Filename MAY be named `chosen_links.csv` or `pathset_links.csv`
 *  File MUST contain a record for each passenger-trip-< link/path segment >
 *  File MUST be a valid CSV file.
 *  The first line of each file MUST contain case-sensitive field names.
 *  Field names MUST NOT contain tabs, carriage returns or new lines.

File MUST contain the following attributes:

Required Attributes	| Description										
----------			| -------------		
`person_id`			| Corresponds to `person_id` field in `dyno-demand`-formatted demand
`p-trip_id`			| Corresponds to `p-trip_id` in `dyno-demand`-formatted [`trip_list.txt`](https://github.com/osplanning-data-standards/dyno-demand/blob/master/files/trip_list.md).  Unique within the household/person. 
`link_num`			| The integer link/path segment number representing the order that this link takes place in the entire path
`A_id`				| Starting node for link / path segment.  Can be a `stop_id` corresponding to [`stops.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/stops.md) or a `taz` corresponding to an access link such as [`walk_access_ft.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/walk_access_ft.md)
`B_id`				| Ending node for link / path segment. Can be a `stop_id` corresponding to [`stops.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/stops.md) or a `taz` corresponding to an access link such as [`walk_access_ft.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/walk_access_ft.md)
`mode`          	| Supply mode for the link, corresponds to `mode` in `GTFS-PLUS`-formatted [`routes_ft.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/routes_ft.md) or an access or egress mode.
`link_mode`			| One of:  [ access \| egress \| transfer \| transit ] |
`trip_id` | Transit trip ID for the trip, corresponding to `trip_id` in `GTFS-PLUS`-formatted [`trips.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/trips.md)
`route_id` | Transit route short name corresponding to `route_id` variables in GTFS-PLUS-formatted [`route_ft.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/routes_ft.md)

File MAY contain the following attributes:

Optional Attributes	| Description										
----------			| -------------		
`pathnum`			| ID within a pathset.
`A_time` 			| Time at start node accounting for dwell delays. In fast-trips, it is based on `pf_A_time` but adjusted due to dwell delays.
`B_time` 			| Time at end node accounting for dwell delays.  In fast-trips, it is based on `pf_B_time` but adjusted due to dwell delays.
`wait_time` 		| Wait time in minutes accounting for dwell time.  In fast-trips, it is based on `pf_wait_time` at the start node and adjusted based on difference between `A_time` and `pf_A_time`.
`board_time` 		| Time passenger boards a transit vehicle (as opposed to arriving at the start node) accounting for dwell time.
`alight_time`		| Time passenger alights from the transit vehicle accounting for dwell time.
`link_time` 		| Link time in minutes accounting for dwell times.  In fast-trips,it is based on `pf_link_time` but adjusted for dwell times.
`A_seq` 			| Stop sequence for the starting node of the link, corresponding to `stop_sequence` in `GTFS-PLUS`-formatted [`stop_times.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/stop_times.md)
`B_seq` 			| Stop sequence for the ending node of the link, corresponding to `stop_sequence` in `GTFS-PLUS`-formatted [`stop_times.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/stop_times.md)
`sim_cost` 			| Generalized cost calculated in the assignment/simulation.
`missed_xfer` 		| 1 if the transfer is missed. (This happens if `new_waittime` is negative.)
`chosen` 			| Chosen status for path. <br>-1 if not chosen by passenger<br>-2 if chosen but passenger rejected because of capacity or timing issues<br>otherwise: <iteration>+<simulation>\_<iteration>/100.
`overcap`			| Number of passengers overcap for the transit vehicle for this link.
`overcap_frac` 		| Fraction of attempted boards that are overcapacity at this stop.
`iteration` 		| Iteration corresponding to this pathset.
`A_id_num`			| Internal to fast-trips. (Numeric version of `A_id`, which could be a `stop_id` and `taz`.)
`B_id_num`			| Internal to fast-trips. (Numeric version of `B_id`, which could be a `stop_id` or `taz`.)
`mode_num`			| Internal to fast-trips. (Numeric version of `mode`.)
`trip_id_num`		| Internal to fast-trips. (Numeric version of `trip_id`.)
`pf_iteration`		| Debug. Path-finding iteration.
`pf_A_time` 		| Debug. The time at the start node when used by the path-finding algorithm.
`pf_B_time` 		| Debug. The time at the end node when used by the path-finding algorithm.
`pf_link_time`		| Debug. The link time in minutes when used by the path-finding algorithm.
`pf_wait_time`		| Debug. The wait time in minutes at the start node when used by the path-finding algorithm.
`bump_iter`       	| Debug. Iteration a passenger was bumped.
`bump_stop-boarded` | Debug. 1 means this passenger boarded, 0 means got bumped.
`alight_delay_min`  | Debug. Delay in alight time from the input path-finding understanding of alight time due to changes in dwell time.


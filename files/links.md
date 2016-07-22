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
`trip_list_id_num`	| Corresponds to line number field in `dyno-demand`-formatted [`trip_list.txt`](https://github.com/osplanning-data-standards/dyno-demand/blob/master/files/trip_list.md) where 1 is the first trip.  To be replaced when [dyno-demand issue#2](https://github.com/osplanning-data-standards/dyno-demand/issues/2) is resolved.
`linknum`			  | The integer link/path segment number representing the order that this link takes place in the entire path
`A_id_num`			| Internal to fast-trips. (Numeric version of `A_id`, which could be a `stop_id` and `taz`.)
`B_id_num`			| Internal to fast-trips. (Numeric version of `B_id`, which could be a `stop_id` or `taz`.)
`A_id`				  | Starting node for link / path segment.  Can be a `stop_id` corresponding to [`stops.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/stops.md) or a `taz` corresponding to an access link such as [`walk_access_ft.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/walk_access_ft.md)
`B_id`				  |  Ending node for link / path segment. Can be a `stop_id` corresponding to [`stops.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/stops.md) or a `taz` corresponding to an access link such as [`walk_access_ft.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/walk_access_ft.md)
`mode_num`			| Internal to fast-trips. (Numeric version of `mode`.)
`mode`          | Supply mode for the link, corresponds to `mode` in `GTFS-PLUS`-formatted [`routes_ft.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/routes_ft.md) or an access or egress mode.
`linkmode`			| One of 
-					|    access
-					|    egress
-					|    transfer
-					|    transit
`trip_id`			  | Transit trip ID for the trip, corresponding to `trip_id` in `GTFS-PLUS`-formatted [`trips.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/trips.md)
`route_id`			| Transit route short name corresponding to `route_id` variables in GTFS-PLUS-formatted [`route_ft.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/routes_ft.md)
`A_seq` 			| Stop sequence for the starting node of the link, corresponding to `stop_sequence` in `GTFS-PLUS`-formatted [`stop_times.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/stop_times.md)
`B_seq` 			| Stop sequence for the ending node of the link, corresponding to `stop_sequence` in `GTFS-PLUS`-formatted [`stop_times.txt`](https://github.com/osplanning-data-standards/GTFS-PLUS/blob/master/files/stop_times.md)
`new_A_time` | Time at start node, adjusted due to dwell delays.
`new_B_time` | Time at end node, adjusted due to dwell delays.
`board_time` | Time passenger boards a transit vehicle (as opposed to arriving at the start node).
`alight_time`	| Time passenger alights from the transit vehicle.
`new_linktime min` | Link time in minutes, adjusted due to dwell delays.
`new_waittime min` | Wait time in minutes at the start node, given the `new_A_time`
`sim_cost` | Generalized cost calculated in the assignment/simulation.

File MAY contain the following attributes:

Optional Attributes	| Description										
----------			| -------------		
`pf_iteration`	| Debug. Path-finding iteration.
`pathnum`			| ID within a pathset.
`trip_id_num`		| Debug. (Numeric version of `trip_id`.)
`pf_A_time` 		| Debug. The time at the start node when used by the path-finding algorithm.
`pf_B_time` 		| Debug. The time at the end node when used by the path-finding algorithm.
`pf_linktime min`	| Debug. The link time when used by the path-finding algorithm.
`pf_waittime min`	| Debug. The wait time at the start node when used by the path-finding algorithm.
`bump_iter`       | Debug. Iteration a passenger was bumped.
`bumpstop_boarded` | Debug. 1 means this passenger boarded, 0 means got bumped.
`alight_delay_min`  | Debug. Delay in alight time from the original path-finding understanding of alight time.
`missed_xfer` | 1 if the transfer is missed. (This happens in `new_waittime` is negative.)
`chosen` | Chosen status for path. -1 if not chosen, -2 if chosen but rejected, otherwise iteration+simulation_iteration/100.
`overcap`	| Number of passengers overcap for the transit vehicle for this link.
`overcap_frac` | Fraction of attempted boards that are overcapacity at this stop.
`iteration` | Iteration corresponding to this pathset.

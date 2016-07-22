## Passenger Paths
Filename: `chosen_paths.csv` or `pathset_paths.csv`

 *  Filename MAY be named `chosen_paths.csv` or `pathset_paths.csv`
 *  File MUST contain a record for each passenger-trip (chosen or in the pathset, respectively)
 *  File MUST be a valid CSV file.
 *  The first line of each file MUST contain case-sensitive field names.
 *  Field names MUST NOT contain tabs, carriage returns or new lines.

File MUST contain the following attributes:

Required Attributes	| Description										
----------			| -------------		
`person_id`			| Corresponds to `person_id` field in `dyno-demand`-formatted demand
`trip_list_id_num`  | Corresponds to line number field in `dyno-demand`-formatted [`trip_list.txt`](https://github.com/osplanning-data-standards/dyno-demand/blob/master/files/trip_list.md) where 1 is the first trip.  To be replaced when [dyno-demand issue#2](https://github.com/osplanning-data-standards/dyno-demand/issues/2) is resolved.
`pathdir` | Direction. 1 for outbound, 2 for inbound.
`pathmode`  | Demand mode.  Corresponds to `mode` field in `dyno-demand`-formatted [`trip_list.txt`](https://github.com/osplanning-data-standards/dyno-demand/blob/master/files/trip_list.md).

Debug Attributes | Description
-----------------|------------
`pf_iteration`  | Path-finding iteration.
`pathnum` | ID within a pathset.
`pf_cost` | Debug. The generalized cost as calculated by the path finder.
`pf_probability`  | Debug. The probability of the path as calculated by the path finder.
`description` | Text description of the path, including all nodes and links.
`chosen`  | Chosen status for path. -1 if not chosen, -2 if chosen but rejected, otherwise iteration+simulation_iteration/100.
`missed_xfer` | 1 if the path has a missed transfer.
`sim_cost` | Generalized cost calculated in the assignment/simulation.
`logsum_component` | Debug. Portion of the total logsum from this path.
`logsum`  | Debug. Total logsum for the pathset.
`probability` | Debug. Probability of this path as calculated by the route choice model.
`iteration` | Iteration in which this path was found.

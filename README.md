# dyno-path
Path data standards.  Suitable for assignment output including vehicle and passgenger paths.

**version**: 0.1.X
**updated**: 26 July 2016
**created**: 20 July 2016  
**authors**:  

 * Lisa Zorn (LMZ LLC)  
 * Elizabeth Sall (UrbanLabs LLC)  
 * Brice Nichols (Puget Sound Regional Council)
 * Andisheh Ranjbari (Puget Sound Regional Council)
 * Drew Cooper (San Francisco County Transportation Authority)  
 
[issues]: https://github.com/osplanning-data-standards/dyno-path/issues
[repo]: https://github.com/osplanning-data-standards/dyno-path
[GTFS-PLUS]: github.com/osplanning-data-standards/GTFS-PLUS
[dyno-demand]: github.com/osplanning-data-standards/dyno-demand


NOTE: This is a draft specification and still under development. If you have comments
or suggestions please file them in the [issue tracker][issues]. If you have
explicit changes please fork the [git repo][repo] and submit a pull request.

### Changelog

-  To come - still in too much flux

# Specification

dyno-path assignment files consist of required and optional data files that together 
describe the movement of people or vehicles through a transportation system.  

A dyno-path assignment MUST include the following files:

Filename 			| Description										
----------			| -------------										
[`chosen_paths.csv`](/files/paths.md)		| passenger paths that were chosen
[`chosen_links.csv`](/files/links.md)		| links for chosen paths

A dyno-path assignment MAY include the following files:

Filename 					| Description										
----------					| -------------		
[`pathset_paths.csv`](/files/paths.md)		| path-based information for pathsets
[`pathset_links.csv`](/files/links.md)		| link-based information for pathsets











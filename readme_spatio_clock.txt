Autonomous overtaking requirements
We model autonomous driving maneuvers as a parallel timed automata composition. The network of timed
automata in model checker UPPAAL is the traffic scenario depicted. There are three lanes 0 to 2 and six cars
A to F contained in the spatio-clock synchronous constraint safety-critical scope. Every vehicle automaton describes the sensor
 models with incoming perceptions and actions execution. It communicates with other automata about negotiations and
actions through five broadcast channels Claiming_req, Change_claim_agr, Turn_left, Potentialcol, and Reserving. Models also 
contain four pairs of binary channels No_change_claim_agr, Set_spacing_c, Lane_change_suc, and No_turn_left for 
maneuver commands and responses. Firstly, in order to model spatial behaviors, we define discrete lane identification 
LaneID, direction range RangeID, and continuous vehicles’ positions along the road. We also
give relevant spatial functions to model the spatial assessments using claim, reserve, withdraw claim, and withdraw reserve
actions. Secondly, in order to model clock behaviors, we define discrete logical clocks and continuous time interval waiting
for response and overtaking to do time model assessments. We use SCSL to model logical clocks in globally asynchronous
and locally synchronous distribute and autonomous systems, because they have independent and multiple clock rates. We can
model interactive events in state-based SCSL models, e.g., communication events, and temporal trigger events. Thirdly, to model
spatio-clock behavior for autonomous overtaking, we define spatio-clock synchronous constraint safety-critical scope to describe
spatial position at any instant. Spatio-clock synchronous actions and their occurring relationships are also presented for safety
and liveness properties. Spatio-clock collision check must occur at the clock of receiving lane changing agreement and in the
same reserved lane segments according to autonomous driving safety guards. It must take precedence over the
occurrence of claiming overlap check, which occurs at the clock of receiving lane change agreement and no spatial overlap after
collision check. It checks potential position overlap not only with surrounding vehicles’ reserved lane segments, but also with
claiming lane segments.

UPPAAL model
We give the autonomous driving systems model including the following templates, Ego, EgoFront, EgoBehind, ClaimFront, 
ClaimBehind, and Adjacent. when we do the experiments. we perform an evaluation of the properties described in the 
previous section, using different set-ups of parameters. The experiments are performed on a machine with a processor Intel(R) 
Core(TM) i5-10210U CPU at 1.60GHz, 2.11Ghz, 2 cores, and 4 logical processors with 16GB of RAM, running 64bit Windows 10. 
We use academic version of UPPAAL 4.1.24 (rev. 29A3ECA4E5FB0808), from November 2019. Firstly, we give the template 
instantiations; then we list one or more processes to be composed into a system.
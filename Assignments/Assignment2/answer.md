##Week 2 Quiz: Answers

#Here we will explore an event dataset with both Disco and ProM tools.
#ProMbook_Ch1_running-example.fbt using Disco

#P1: How many events does Case ‘1’ have?
5. As shown on P1.png image.

#P2: How often is the activity ‘check ticket’ executed?
9. As shown on P2.png image.

#P3: Filter dataset by activity 'reject request'. 
#When you inspect the new process map, how many times is the 'reinitiate request' activity executed for rejected cases?
2. As shown in P3.png image.

#P4: For how many cases is the activity ‘check ticket’ executed?
6. As shown on P2.png image.

#P5:  Between which activities is the longest mean time delay?
Between 'decide' and 'pay compensation' activities. As shown in P5.png image.

#P6: What is the timespan of the events that are replayed by the animation?
From 29 Dec '10 to 28 Jan '11. Aprox 1 month. As shown in P6.png image.

#P7: What is the mean case duration?
11.2 days. As shown in P7.png image.

#P8: What percentage of events the four most frequent activities accumulate.
71.43%. As shown in P8.png image.

#P9: Which resource performed most of the activities?
Sara. As shown in P9.png image.

#P10: How much time is spent between activities 'examine casually' and 'decide' in case 2?
5 days 21 hours. As shown in 10.png image.

#Export the event log to a XES file and load it into ProM. 
#ProMbook_Ch1_running-example.fbt using ProM

#P11: How many events are in the event log?
48. As shown in P11.png image.

#P12: Which resource most frequently performs the start activity of a case?
Pete. As shown in P12.png image.

#P13: For which case is the latest event recorded?
5. As shown in P13.png image.

#P14: For the cases with the activity 'reinitiate request', how often is the activity 'check ticket' executed?
5. As shown in P14.png image.

#P15: In the discovered Petri net (alpha algorithm), in this process model the ‘check ticket’ activity is?
Executed in parallel to the activities ‘examine thoroughly’ and ‘examine casually’. As shown in P15.png image.

#P16: Using the 'Convert Petri net to BPMN diagram' plugin, how many operator nodes (or gateways) do you see?
4 (3 times a choice (X) and 1 times a parallel (+) operator). As shown in P16.png image.

#P17: Using the 'Show PomPom View' plug-in, slide the significance cutoff to 100. What Petri Net do you see?
A single place. As shown in image P17.png.

#P18: Using the 'Handover of work' plug-in on the event log, after which users does user 'Sue' perform work?
Pete and Sara. As shown in image P18.png.

#P19: Using the 'Mine for a Heuristics Net using Heuristics Miner' plug-in on the event log, with the
#'Visualize HeuristicsNet with Annotations' visualization, What possible combinations of activities can 
#follow from the 'register request' activity?
One of 'Check ticket', 'examine thoroughly', 'examine casually' or both 'examine thoroughly' and 'examine casually' 
activities. As shown in image P19.png.

#P20: using the 'Replay a Log on Petri Net for Performance/Conformance Analysis' plug-in on the Petri Net model 
#discovered and the event log, and the 'Project Manifest to Model for Conformance' visualizer, use the Inspector panel to
#determine how often is this activity executed correctly, and how often in the model only?
9 times correctly, 0 in model only. As shown in image P20.png.
##Week 4 Project: Answers

#Here we will explore an event dataset with both Disco and ProM tools.
#('Receipt phase of an environmental permit application process (_WABO_) CoSeLoG project.fbt' using Disco

###

#P1.1: How many events are there on average per case?
#P1.2: Can you indicate whether each case seems to be unique or whether many cases follow the same activity sequence?
#P1.3: What is the main observation that can be made from the 'Events over time' graph?

#S1.1:
*Approach I used:* In the 'Statistics' tab we go to 'Events per case' section. This shows both a graph and statistics of the
number of events per case. This is shown in image1.png.

*What I saw:* There are two sections with information. A bar graph showing the number of cases that have N events (N from 1 to 25)
and a section on the right with statistics about the cases. This section, in particular, has information about the total number of 
cases and events.

*My analysis:* From the graph we can see that most of the cases consist on 6 events since this is the largest bar. From the statistics 
section on the right section we see that there are 8577 events and 1434 cases, thus 8577/1434 = 5.98 events per case on average. 
This figure is consistent with what we observed on the graph.

#S1.2: 
*Approach I used:* In the 'Statistics' tab we go to 'Case variants' section. This shows a graph with the different case variants
present in the log. This is shown in image2.png.

*What I saw:* Each bar in the chart represents a case variant and the larger it is, the more cases correspond to it. Those are ordered
decreasingly and are accompanied by a line that represents the accumulative percentage of cases as we add more variants.
The chart shows that about half the cases (713) correspond to the same variant (variant 1). There are 116 different variants
although only 13 of them have 10 or more cases in them. Most have 1-2 cases only.

*My analysis:* From the graph we can see that most of the cases correspond to variant 1 (about 50%). This means that about half the cases
in the log follow the same activity sequence. We can also see that there are some activity sequences that are unique to a few (1-2) cases too.

#S1.3*
*Approach I used:* In the 'Statistics' tab we go to 'Events over time' section. This shows a graph with the number of activities done in time
for the time interval of the log. This is shown in image3.png.

*What I saw:* The chart shows that the time interval of the log goes from Oct 2, 2010 to Jan 20, 2012. It represents how many activities were 
performed each day where higher peaks indicate more activity and lower peaks indicate fewer activity.

*My analysis:* The graph has a landscape with several spikes indicating that the number of activities performed was not close to constant in time, 
but that there are days with several activites interleaved with days with few activities along the time interval of study. 

###

#P2.1: Discuss this process map, what is the main process? 
#P2.2: Which activities and paths between activities are frequent? 

#S2.1:
*Approach I used:* In the 'Map' tab have set both the activities and paths sliders to 0 to view only the most common activities and paths.
This allows us to visualize the main process only. This is shown in image4.png.

*What I saw:* The process map has 6 activities and 8 arcs connecting them. THe most frequent activities are darker blue and the most frequent 
paths are thicker.

*My analysis:* The main process is a sequential process consisting of 6 activities in the following order: 'Confirmation of receipt-complete',
'T02- Check confirmation of receipt-complete', 'T04- Determine confirmation of receipt-complete', 'T05- Print and send confirmation of receipt-complete',
'T06- Determine necessity of stop advice-complete', 'T10- Determine necessity to stop indication-complete'. 

#S2.2:
*Approach I used:* Same as S2.1.

*What I saw:* Same as S2.2.

*My analysis:* All the activities displayed are frequent, since we have used the settings that only show the most frequent activities. 
As for the paths we see that those connecting the main activities along the sequential process are more frequent while there is a loop backwards from
activity T10 to activity T02 that only 155 cases followed and is thus less frequent. 

###

#P3: Discuss where the process takes most time, e.g. where there are possibilities for improvement.

#S3: 
*Approach I used:* In the 'Map' tab we switch to the performance projection and use 'Mean duration' as metric. This is shown in image5.png.

*What I saw:* We see that the arcs in the model now are coloured red and its thickness is related to the metric chosen ('Mean duration').
In particular activities that take most time are connected with thicker arcs.

*My analysis:* The arcs connecting activities 'T05- Print and send confirmation of receipt-complete' and 'T06- Determine necessity of stop advice-complete'
and the arc conecting activity 'T10- Determine necessity to stop indication-complete' back to 'T02- Check confirmation of receipt-complete' are those
that take on average more time (3.1 days) compared to the rest of arcs that take less than 1 day. This indicates that there is room for improvement in these
sections of the process.

###

#('Receipt phase of an environmental permit application process (_WABO_) CoSeLoG project.xes.gz' using ProM.

#P4.1: Is the arrival rate of new cases constant? If not, when are there fluctuations? If yes, how can we see this from the Dotted Chart?
#P4.2: Can you observe a change in the global process? 

#S4.1:
*Approach I used:* First I loaded the file into ProM and then I have selected the 'Dotted Chart' visualization from the dropdown menu 
('Select visualization:') after clicking on the 'Eye' button. We have sorted on 'time:timestamp of first event' using the dropdown menu on the left.
This is shown in image6.png.

*What I saw:* We see a Dotted Chart where rows are cases and the horizontal axis is time. 

*My analysis:* The arrival rate is fairly constant as showed by the constant slope of the graph with some minor bumps.

#S4.2:
Approach I used:* Same as S4.1.

*What I saw:* Same as S4.1.

*My analysis:* Cases seem to be resolved faster the latest on the log we look at, with some exceptions that take several months to complete. 
Graphically, the 'thickness' of the main group of points tends to decrease in time.

###

#P5: Discover a Petri net on the event log.

#S5:
*Approach I used:* First I have run the 'Filter log using simple heuristics' plug-in on the event log with the following settings:
- Log filter: complete (keep)
- Start events: Confirmation of receipt+complete
- End events: T10- Determine necessity to stop indication+complete'
- Event filter: 'Confirmation of receipt-complete', 'T02- Check confirmation of receipt-complete', 'T04- Determine confirmation of receipt-complete', 
'T05- Print and send confirmation of receipt-complete', 'T06- Determine necessity of stop advice-complete', 'T10- Determine necessity to stop indication-complete'

The choosing of this settings came motivated by the study of the log using Disco in previous questions. We have set the initial and end events observed there
and only kept those events that appeared on the graph.

Then we used this filtered log as input of the plug-in 'Mine a Petri Net using an Inductive Miner' to generate a Petri Net. The choice of algorithm came
motivated by the results obtained. Other algorithms like Alpha Miner produced disconnected Petri Nets with activities not connected between them while ILP
prodced an overly complex Petri Net. The output of this plug-in is similar to what we observed using Disco in questions before and shows a clear picture 
of the process. We can see it in image7.png.

*What I saw:* We can see in the Petri Net that there are 6 activites (the ones we filtered) and that the process is fairly linear with activity T06 concurrent
to activities T02, T04 and T05. 

*My analysis:* The main process is 'Confirmation of receipt' then activities T02, T04 and T06 in sequential order that are concurrent with T06 and finally T10.

#P6.0: Apply conformance checking on this process model, and on the full unfiltered original event log.
#P6.1: What is the replay fitness (the 'trace fitness' statistic) of the event log on the normative process model?
#P6.2: Select the transition 'T06 Determine necessity of stop advice+complete' (on the top left of the model) and discuss its element statistics: how many times 
#is the transition executed correctly and how many times incorrectly?
#P6.3: Using the element statistics of transition 'T06 Determine necessity of stop advice+complete', what can you say about the (in)correct execution of this activity?

#S6.0:
*Approach I used:* I used the approach described in the instructions.

*What I saw:* The normative model is showed with the conformance information projected on it. We have zoomed in the sections with most of the deviations occur.
DDeviations are showed in activities in the activity boxes. They include the 'moves' between log and model needed to align both in the coloured bars below.
It is shown on image8.png.

*My analysis:* The activities where most of the deviations occur are T04, T05, T06 and T10.

#S6.1:
*Approach I used:* I looked at the 'Global Statistics' tab in the 'Inspector'.

*What I saw:* The information about 'Trace fitness' (among others).

*My analysis:* The replay fitness is 0.84 (84%) as indicated in the 'Trace fitness' section.

#S6.2: 
*Approach I used:* Selecting transition 'T06 Determine necessity of stop advice+complete', I looked at the 'Element Statistics' tab in the 'Inspector'.

*What I saw:* The information about correctly and incorrectly aligned traces for this activity.

*My analysis:* The transition was correctly executed 1327 times (in 1309 traces) and incorrectly in 125 times (125 traces).

#S6.3:
*Approach I used:* Same as S6.2.

*What I saw:* Same as S6.2.

*My analysis:* The transition was executed more than once per trace since there are more correct executions than traces with correct execution, but it
only was executed wrong at most once per trace (since both values are the same).

###

#P7.1: Use the plug-in 'Mine for a Subcontracting Social Network'. Can two or more groups of users be distinguished?
#P7.2: Again use one of the two Dotted Chart plug-ins. For the XDottedChart change the component type to 'org:resource'. 
#Are all users executing activities from the start of the event log, or are some users joining later?
#Are users mainly executing particular activities or are most users executing most of the activities?

#S7.1: 
*Approach I used:* Used the plug-in 'Mine for a Subcontracting Social Network' on the event log with default settings. See image9.png.

*What I saw:* A graph where each node represents a resource and each arrow represents that resource i subcontracts resource j. That is resoruce j frequently 
realises an activity between two activities realised by resource i.

*My analysis:* We can observe one large group that is highly connected, i.e. they subcontract each other frequently, with some of the resources being central
in the graph (admin1 and Resource 10). Then there is another group of resources that are not connected with the rest. This could indicate that the first group
usually work in the same parts of the process, doing several interleaved activities on it.

#S7.2:
*Approach I used:* Used the Dotted Chart visualization with 'C: Resource Classifier' as Y-axis and 'C: Activity Classifier' as Colour attribute. See image10.png.

*What I saw:* The dotted chart now represents each resource in a row and time in x-axis. We can see the activities each resource did in time coloured by activity.

*My analysis:* We can see that only a few users have activities from the very start of the log, while a lot more joined from mid Oct 2010. Others only do
activities very sparingly along time (from Resource 28 to 43). We can also see that although some users perform mainly one activity (mainly the user that almost 
exclusively do 'yellow' activities at the bottom of the chart) and some of those that execute activities very sparingly, most resoruces execute several activities
along time. This can be shown because for most rows, there are activities in different colours in time. 

#Observations:
1) There are 2 bottlenecks that decrease overall performance of the process, further investigation should be made to discover the causes and try to find improvements.
2) There are several non-conformities to the Normative model, further investigation should be made to discover the causes and try to prevent them.
3) Some resources seem to be underused (have few tasks assigned), they could be allocated to more problematic tasks to either increase performance or conformity.
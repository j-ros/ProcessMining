##Week 1 Quiz: Answers


#P1 (Purchasing Process dataset): How many cases had to settle a dispute with the purchasing agent?

Importing the dataset we can see on the Map tab the process model generated. Using the Case Frequency View we can see that
24 cases had to settle a dispute with the purchasing agent. (image q1.pdf)

#P2 (Purchasing Process dataset): Is there a difference in overall case duration for the cases that had to settle a dispute 
#with the purchasing agent, compared to the ones that did not? Make sure you only compare cases that actually reach the endpoint
#'Pay invoice'. 

First we filter the dataset by those cases that contain the endpoint 'Pay Invoice' by using the 'Filter this activity' button
on the 'Pay Invoice' activity in the process map. Then we can filter the resulting dataset on the 'settle a dispute with the 
purchasing agent' activity from the 'Filter' menu. On image q2_1.png we have the Statistics tab for the cases without
the 'settle a dispute with the purchasing agent' activity while on the q2_2.png image we have those with that activity present.
We see that there is a 1-day difference between both.

#P3 (Refund Process dataset): The trigger for the analysis is the feeling of the process manager that the process had several 
#problems. Customer complaints and the inspection of individual cases indicated that there were inefficiencies and too long 
#throughput times in the process. Assume that only cases that have reached the 'Order completed' step are finished. Apply a 
#filter to only keep the completed cases. You will see that only about 24% of the cases are left. Would it be a problem if you 
#would take the average throughput time of all cases to estimate the typical case duration for this process, including the ones 
#that have not finished yet?

Yes, since cases without the 'Order completed' activity have not finished we would be considering a shorter time than real
by considering unfinished activities in the average throughput computations. Unifinshed activities will have a longer
timeframe than described by the dataset alone.

#P4 (Refund Process dataset): The 'Channel' data attribute indicates through which channel the refund process was started. 
#The process for each channel is different. Based on the full data set (not just for the complete cases), which channels have 
#the biggest problems with missing documents that need to be requested from the customer?

By filtering by the 3 activities using the Filter menu we can check how many problemes with missing documents there were
with respect to the total cases in each channel. Images q4_1.pdf, q4_2.pdf and q4_3.pdf depict the Map for the dataset
filtered by Callcenter, Dealer and Internet respectively. We can see that both Internet and Dealer have a high proportion
of problems with missing documents ('Missing documents requested' activity), while Callcenter does not.

#P5 (Refund Process dataset): How many customers have received a refund (activities 'Refund issued' or 'Special Refund 
#issued') without the product being received by the electronics manufacturing company (activity 'Product received')?

We can filter the dataset by the activity 'Product received' keeping records that do not have this activity (image p5.pdf).
There we see 3 'Special refund issued' and 1 'Refund issued' activities that should not be there. Compliance issue.

#P6 (Refund Process dataset): Has a customer received double payment? To check this compliance rule, find out if any of the 
#activities 'Payment issued', 'Refund issued', or 'Special Refund issued', which all indicate a payment to the customer, was 
#ever followed by any of these three activities later in the process. Count the number of cases.

By filtering the dataset using a 'Follower Filter' keeping cases where any of those 3 activities is eventually followed by 
another activity of the same group (image p6.pdf) we see that there is one such case. Compliance issue.
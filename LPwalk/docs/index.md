Linear periodic estimation of responses in perturbed treadmill walking
================

### F. Ehtemam, H. Wang, T. van den Bogert & T. Kiemel

------------------------------------------------------------------------

Meeting of 2017-06-09
---------------------

Using designed perturbation as input: ![](irf_dPert.png) Using measured perturbation as input: ![](irf_mPert.png) Slices of IRFs for designed perturbation as input: ![](emg_dPert.png) Slices of IRFs for measured perturbation as input: ![](emg_mPert.png) Impulse response (designed to measured) for both higher and lower accelerations: ![](Impulse_response.png) Step response (designed to measured) for both higher and lower accelerations: ![](Step_response.png)

Meeting of 2017-06-23
---------------------

The effect of input frequency bandwidth on impulse response function of the treadmill:
From top to bottom the bandwidth is changing from 5 Hz to 20 Hz (intervals of 5 Hz). Higher frequencies create less ringing. (more on ringing here: [Ringing artifacts](https://en.wikipedia.org/wiki/Ringing_artifacts)) ![](Impulse_response_5_10_15_20.png) The effect of input frequency bandwidth on step response function of the treadmill: ![](Step_response_5_10_15_20.png) The effect of input frequency bandwidth on IRF estimation for EMG (e.g. TA) : ![](TA_5to8.png) IRFs for thigh muscles: ![](upper1.png) IRFs for hip extensors: ![](upper2.png)

Meeting of 2017-07-07
---------------------

Slices of IRFs (at phases of gait cycle for which the largest changes in the activity are observed) for TA and plantarflexors. IRFs were calculated using input bandwidths of 5, 8 and 10 Hz to see the effect of ringing artifacts on the responses.

![](slices_5Hz.png)

![](slices_8Hz.png)

![](slices_10Hz.png)

Meeting of 2017-07-28
---------------------

![](emgs_Nz.png) ![](emgs_P1z.png) ![](emgs_P2z.png)

Meeting of 2017-08-11
---------------------

![](contourLowLegH.png) ![](contourUpLegH.png) ![](contourLowLegL.png) ![](contourUpLegL.png)

Slices at the phase where the high and low perturbations each show maximum changes: ![](slicesLowLeg_both.png) Slices at the phase where the high perturbation shows maximum changes: ![](slicesLowLeg_H.png) Slices at the phase where the low perturbation shows maximum changes: ![](slicesLowLeg_L.png)

Meeting of 2017-08-25
---------------------

### Averaged EMG profiles

I subtracted the mean from each EMG signal before rectifying them. No filtering is done on the data. The data is averaged over all cycles, all trials and all subjects (15 subjects). Each cycle has 100 nodes in them. The heel-strike was identified using vertical coordinate of the heel marker. There were a few bad cycles (less than 5) for each trial that have been excluded. I will focus on EMG of RF here for two reasons: RF is a large muscle and identifying it is rather easy so with a little practice anyone should be able to place the sensor on the right spot to capture high quality signals which means that if signals are off for RF either sensors were not placed correctly for any of the muscles (which is unlikely) or something else is going on that has affected quality of all signals. The second reason is that RF was one of the muscles with a baseline that appeared to be high from the results I previously sent. Below is the RF plot. **The baseline is close to 0.005 and the peak is around 0.011.** The left shows the data without any normalization while the right shows the data that is normalized for each subject to RMS of their average (over trials) before data is averaged over all subjects. The top rows show the data for the high perturbation and the bottom shows the low perturbation data. The confidence intervals for the mean are shown for the non-normalized data (I skipped it for the normalized). ![](RF.png) Now comparing this with what Dana had from two subjects:

She had different perturbation conditions (left belt vs. right belt vs. both belts) and she presented the data for both perturbed and unperturbed legs. Over all conditions for RF **the baseline changes between about 0.0025 to 0.005** (I don’t have the data so this is from visual inspection) and **the peak changes between about 0.007 and 0.018.** Comparing this to the numbers we have from the data Huawei and I collected I don’t think our data is bad. I think it is actually pretty good. I have looked at the data for individual subjects and I haven’t seen any subject showing any weird pattern. The confidence intervals also show that individual subjects don’t depart from the average by much. However, the story is different for normalized data. Normalizing using the aforementioned method results the baseline to go up. So to conclude this topic I think we need to answer these questions:
1. Do we think the data (as presented) is of acceptable quality meaning that there are no major artifacts or issues in the raw data? My answer to this question is yes but we can all discuss it to see what everyone is thinking.
2. If the answer to the first question is yes then how do we want to visualize the EMG data in a way that does not cause any distractions? Important points to think about here are these:

-   Do graphs have to start from zero? Most people think not including the origin (i.e. zero here) is misleading when presenting data (any data) so I think they should probably start from zero.
-   Do we have to have the same axis limit for all muscles? The same limits for all muscles results in some graphs to look weird since the peak to baseline ratio is different for different muscles. But the axis limits should definitely be the same for each muscle between different conditions.
-   Do we want to normalize the data before averaging between subjects or not? If the answer is yes then what method of averaging is the best and do we have to scale the axis after averaging in a way that minimizes distractions? Some people show their normalized data in a way that it always changes between zero and one. The answer here depends on which method we want to use for normalization if we want to do so.

### EMG transient responses (i.e. slices of IRFs)

I showed some graphs in the last meeting and we discussed how we would like to present the data. The conclusion was that for both low and high perturbations we want to discuss the effect of perturbations over a few important phases. After going through different phases I picked a few phases for different muscle groups. The figure below shows the lower leg muscles responses. The horizontal axis shows a full gait cycle starting from toe-off. Notice that even though the zero on the axis is the heel-strike, the axis does not start from heel-strike. The reason for starting it from toe-off is that most interesting events happen around heel-strike (i.e. mid to late swing or early to mid stance). This means that keeping the heel-strike in the middle is a better way of presenting the changes. The green arrow in each figure shows the onset of perturbation. The red is high perturbation and blue is low (i.e. temperature analogy).

![](4slice_shank.png) The plots for the lower leg show that all muscles respond to the perturbation delivered in early stance. TA shows an increase in the activity in response to the positive perturbation. As a reminder, with the current sign convention we have, positive perturbation is a step forward in the position of the belt which means that positive perturbation creates a plantarflexion. The calf muscles all show decreases in their activities in response to positive perturbation. Since the horizontal axis is one gait cycle and each cycle has 100 nodes and the data was presented with sampling rate of 100 Hz, this means that the latencies read from the graphs for the four muscles are between about 100 and 130 milliseconds. These responses are very straightforward to explain since they match our expectations from how TA and plantarflexors should respond to a perturbation applied to the foot when it is on the belt. However, we should keep in mind that TA has other responses that are not as easy as this one to explain. Looking at IRF plots below (left is for high perturbation and right is for low) we see that TA increases its activity in response to perturbation delivered at mid swing and decreases its activity in response to perturbation delivered in early swing. These responses have to be explained separately since they are unique to TA.

For upper leg muscles the late swing is suitable to explain the responses in quadriceps and hamstrings. All three quadriceps (figure below) decrease their activity in early stance in response to perturbation from late swing. This makes sense since the lower leg goes through a dorsiflexion in early stance so quadriceps from the upper leg become active to increase the knee angle and straighten the leg in preparation to raise the COM to the peak. But the positive perturbation now has introduced plantarflexion which can partly contribute to straightening of the leg so the activity of quadriceps becomes lower compared to what it should have been without this perturbation. We expect the opposite effect for hamstrings. This is clear in the activity of BF but ST doesn’t show any statistically significant change.

![](4slice_upper.png) Apart form the responses discussed for the upper leg, hamstrings show a decrease in the activity in response to perturbation from early swing (figure below). The quadriceps don’t show much of a change in their activity during the same period which means that this should be discussed separately as a response unique to hamstrings.

![](4slice_hams.png) So far I think the conclusion is that we have very clear responses in all leg muscles and the frequency domain approach we used was successful in identifying these responses. Also the latencies are reasonable even though this method cannot guarantee accurate estimation of latencies since the perturbation bandwidth is limited (i.e. there might be components of responses that we are missing because we have not perturbed the system over all frequencies it responds to) and also we do not include all harmonics involved in captured responses (i.e. in practice we assume after certain number of modes the harmonics are small enough that they could be ignored while in theory the number of harmonic modes that should be used to describe the response completely is infinite). One step that has to be followed for AP perturbations is to choose phases that best describe the responses of the hip and the trunk muscles. I have not done that yet.

Meeting of 2017-09-08
---------------------

### Statistical tests

We use bootstapping to calculate p-values defined based on the maximum value of IRFs (the entire IRF not just one slice). This determines if the IRF that is averaged across all subjects is significantly different than zero or not. If the averaged IRF for a muscle is significantly different than zero then we can look at slices of the IRFs for that muscle otherwise responses for that muscle are not significant (p&gt;0.05). The table below summarizes the results of tests for significance.

| Muscle     | Low perturbation | High perturbation |
|------------|:----------------:|:-----------------:|
| TA         |         p        |         p         |
| soleus     |         p        |         p         |
| lGastroc   |         p        |         p         |
| mGastroc   |         p        |         p         |
| lGastroc   |         p        |         p         |
| RF         |         p        |         p         |
| vas lat    |         p        |         p         |
| vas med    |         p        |         p         |
| **`BF`**   |      **`f`**     |         p         |
| **`ST`**   |      **`f`**     |         p         |
| **`TFL`**  |      **`f`**     |      **`f`**      |
| **`Gmed`** |      **`f`**     |      **`f`**      |
| **`Gmax`** |      **`f`**     |      **`f`**      |
| **`ESL`**  |      **`f`**     |         p         |
| EST        |         p        |         p         |

Meeting of 2017-09-22
---------------------

The effect of number of modes of harmonic transfer function on IRFs:

Mode zero (i.e. LTI approximation) ![](im1.png) Up to mode 3 ![](im2.png) Up to mode 6 ![](im3.png) Up to mode 9 ![](im4.png) Up to mode 12 ![](im5.png) Up to mode 15 ![](im6.png) Up to mode 18 ![](im7.png)

Meeting of 2017-10-06
---------------------

Right leg ![](emgLR.png) Left leg ![](emgLL.png) Right leg ![](emgUR.png) Left leg ![](emgUL.png) Kinematics for right leg (early stance) ![](KinL.png) Kinematics for right leg (late swing) ![](KinU.png)

Meeting of 2017-10-20
---------------------

Lower leg ipsilateral (top) and contralateral (bottom) transient responses:
![](legL_emg_ipsi.png) ![](legL_emg_cont.png) Upper leg ipsilateral (top) and contralateral (bottom) transient responses: ![](legU_emg_ipsi.png) ![](legU_emg_cont.png) IRFs for the heel and the belt: ![](Heel_belt.png)

![](Heel_belt_slice_CI.png) ![](Heel_belt_slice.png)

Meeting of 2017-11-03
---------------------

Up to mode 9 ![](IR_all_9mode.png) Up to mode 12 ![](IR_all_12mode.png) Up to mode 15 ![](IR_all_15mode.png) Averages across all perturbation phases 15% of the cycle after onset of perturbation: ![](diag_15CI.png) individual subjects across all perturbation phases 15% of the cycle after onset of perturbation: ![](diag_15all.png) ![](nov_ta1.png) ![](nov_ta2.png) ![](nov_kin.png) ![](nov_kin_slice.png)

Meeting of 2017-11-17
---------------------

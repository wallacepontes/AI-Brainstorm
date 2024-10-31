# building resilient systems

## single points of failure

This concept you’ve highlighted—eliminating single points of failure (SPOF)—is crucial, especially in systems like self-driving cars where safety is paramount. Tesla's approach, which ensures the car can still navigate and avoid accidents even without an internet connection, reinforces this principle. Internet dependency in a self-driving car for crash avoidance would indeed be a major SPOF, as internet connections can be unpredictable or unavailable in certain areas. 

Tesla mitigates this by ensuring that critical, time-sensitive decisions like obstacle avoidance and adherence to traffic laws are handled locally, on-board the car, without requiring external input. The car’s internet usage is primarily for non-critical tasks like data collection and navigation assistance. Even if the car loses its connection, it retains enough local intelligence and awareness (via sensors, cameras, and onboard processing) to continue operating safely.

This design philosophy of making internet a non-critical dependency aligns well with the idea of building resilient systems that can operate autonomously in the face of partial failures, such as a loss of internet. It's analogous to redundant systems in other industries where failures could be catastrophic, like aerospace or nuclear power plants, where systems are engineered to continue functioning even if certain components fail.

By localizing the critical functions and using the internet only for updates, improvements, and secondary features, Tesla reduces the likelihood of a catastrophic failure due to a single point of failure.

## Quora Comment

Tesla has made a particular point that the car should not have any external dependencies to avoid crashing or breaking traffic laws. This is a good rule to have and should be the rule for anyone developing a self-driving car. In engineering we call such things “single point of failure” meaning a single thing that can fail which causes the whole thing to fail. The more critical the proper functioning of the whole system is, the more important it becomes to avoid having a single point of failure. A car that could crash and kill people qualifies as the MOST critical scenario, and therefore single points of failure should be completely unacceptable.

A dependency on internet to avoid crashing into things is a big glaring single point of failure. The internet is inherently unreliable for time sensitive operations, and there isn’t a second “backup” internet that you could add in for redundancy to lower the odds of a failure. So, as a rule, internet dependency in order to avoid causing a crash is unacceptable.

Tesla Autopilot relies on internet in the car for three things:

The car saves data about driving situations and sends them to Tesla in order to improve Autopilot by having it understand more situations.
The car receives updates, which may include improvements to Autopilot. These updates may add the ability to understand and handle new situations that it couldn’t before, or may fix glitches in situations that were already working but might do the wrong thing in some cases.
The car uses Google map data for navigation.
The third one is the main point of interest here. The car does require internet to know how to get where you want to go. But if it loses that, it won’t crash, it just won’t know how to get to your destination. When it loses its navigation data, the car isn’t suddenly blind. It will continue to see what it around it, and to follow the rules and road markings And avoid other cars and pedestrians. It just won’t make any actions related to your destination, like lane changes, off ramps, or turns.

## References
1. [Tesla-car-need-an-internet-connection](https://www.quora.com/Does-the-Tesla-car-need-an-internet-connection-to-run-the-autopilot-If-so-what-is-the-minimum-internet-speed-required-for-the-auto-pilot-to-work-as-it-should)
2. 
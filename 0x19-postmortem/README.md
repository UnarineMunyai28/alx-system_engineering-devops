Postmortem: Incident Report: May 12, 2024, Service Outage
Problem Synopsis
Duration: May 12, 2024, from 8:00 UTC to 10:30 UTC on May 12, 2024
Impact: Our API's main service endpoint experienced sporadic outages, which increased error rates by 30% and hindered user access for about 15% of our user base.
Timetable
08:00 UTC: Increased error rates were detected by the monitoring system, indicating a problem.
08:05 UTC: The DevOps team started looking into possible problems with database connectivity.
08:15 UTC: A false suspicion of a possible DNS problem was made; an investigation was conducted but found to be unfounded.
08:45 UTC: Because of the extended service degradation, the incident was reported to the senior engineering team.
09:15 UTC: A misconfigured load balancer affecting API routing was found to be the root cause.
10:00 UTC: The load balancer's configuration was changed to
The issue was caused by an incorrect load balancer configuration, causing dropped requests and increased error rates. Engineers corrected the configuration, restoring API normal operation. Corrective measures include automated testing of load balancer configurations, enhancing monitoring alerts for API endpoint responsiveness and error rates. Tasks include automating load balancer configuration checks and deployment, implementing granular monitoring for API endpoints, and conducting a post-incident review with the engineering team to discuss lessons learned and document best practices.

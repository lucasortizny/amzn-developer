# Autoscaling Policies

Number of complexities that make difference to the quality and consistency
of the performance.

Four different ways:
- Manual Scaling
- Schedule Scaling
- Dynamic Scaling
- Predictive Scaling

Each of these methods have their pros and cons. 

### Manual Scaling

Why would we ever get our hands dirty on something that is supposed to be automatic? 
The perfect way is to say you're going to expect a large surge of traffic. You can use it to 
prevent a problem. Examples: running an ad during a sporting event. You would 
adjust number of instances + max and min number. 

- Get ahead of the event
- Reduce downtime for end users
- Flexibility to scale up or down manually

Cons:
- Not a scalable solution
- Not a long term solution
- Ideal for blue moon and planned events

### Dyanmic Scaling

Removes burden of having to manually launch instances yourself. Atm only two types of dynamic scaling
policies. 
1) **Step Scaling:**
A method of adding or removing instances based on a metric. Autoscaling can add more instances to get below the 
metric. Lower 60% CPU so you can fall below. You can also add triggers to lower instance counts. Cooldown policy to allow time
to spin up instances so that we do not just infinitely spin up instances and charge a bunch of money. Set Cloudwatch Alarm 
that autoscaling can listen to. One alarm to go off 60% or 70% etc. Each of these alarms can be hit in sequence, system will check
if there is an autoscaling event going on in place. It will only add the difference and will not STACK on top of previous alarms. 
- Try to scale up more aggressively to help deal with load issues. Scale back down slower. 
2) **Target Tracking:**
More simplified version of Step Scaling. It takes all the configuration by you away and will handle it in the background.
It is going to be based on simple ranges of metrics that you specify. Do not delete any of the Cloudwatch Alarms set by the policy
here. 

### Predictive Scaling

Previous section was scaling in REACTION to an existing metric. Goal of the system is to get ahead of the goal. Scale up 
before this happens. How do we determine this? We use Machine learning and will learn when traffic increases and expect it. 
This is good for cyclical traffic. Also finds a good use when you have a recurring on and off workloads. Since it uses ML, we
need to give it some time to learn. Predictive Scaling can use Cloudwatch Metrics as long as it has 24 hours of logs. Finds patterns
in the past 14 days and updated daily. 

When you use the forecase, it will start the instances at the start of every hour so it is not as much of real time
as you may think. Predictive Scaling + Dynamic Auto Scaling will be good coverage but it may cost more money.

### Scheduled Scaling

Add or remove scaling groups based on time parameters. Great way to reduce costs. Use it to turn off dev environments after 
business has concluded. Can save you quite a bit of money. Works well when using Spot Instances. 


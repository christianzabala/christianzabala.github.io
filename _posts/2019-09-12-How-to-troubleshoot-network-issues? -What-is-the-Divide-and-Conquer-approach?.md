Since my domain name is called divide-and-conquer.network so my first technical post is about troubleshooting when you are on the network field and how I used the divide and conquer approach in troubleshooting. 

**Note:** The explanation that I shared in this post does not mean that way you should troubleshoot or it is the best way to do during your troubleshooting work because we have all different ways on how to approach an issue. However the main goal on why I created this post is to help others on how they can improve their way of troubleshooting especially does who are still new on the networking field. .
{: .notice}

## Think first before you act!
Well first step when troubleshooting you must first gather all the information you can get for example asking questions to the person reported the problem or checking the alarm on your NMS(Network Management System) and the topology of your network. By gathering all the information you need, expect from it that it will speed up the time for you to identify the problem.
Typically you can guess already the problem if the issue was reported on your Monitoring tool but what if a user or customer  had reported an issue like on accessing a website/server,  or he/she has intermittent connection, or has a slow connection? And you did not ask more detailed information regarding his/her issue, then you can’t exactly guess where the issue is, so you must first ask the user questions about the issue and as much as possible gather information that is specific like:
What is the main problem? 
When did it start happening?
Where is the issue located?
How does the issue occured?
Is there a committed changes?
Is the issue constant or just happens for a specific time?
Are there any users/device has the same issue?
What are the actions that has been tried already to fix the issue? 
and other questions that can help you narrow down where the problems is.

Then after you gather information and verify that issue still exists start on making an hypothesis on your mind or by writing down the things that have not been answered, like on why that issue happened, is that a normal behaviour on your network, is there any maintenance or work being done that contributes to that issue, and perhaps you already encounter the same symptoms from your past experiences that you might already know where to look at, but don’t assume that it’s has the same fix.

## You still don’t know the answer?
Now if you still don’t know  the root cause or where to look for the issue. You can use the  [layered approach](http://www.ciscopress.com/articles/article.asp?p=2273070&seqNum=2) which is checking every layer in the OSI or TCP/IP model from top to bottom, or bottom to top of the model. But for me I usually use the **Divide and Conquer Approach** rather than doing the layered approach which may take up more time to find the things that are not working fine and the things that are working fine on all the components involved on the end to end communication. Usually I start on the network layer then decide whether to go above or below the layer so using ping, traceoptions, ping record-route, output from operational commands, and system logs are the best tools in starting on the network layer. You might also check or compare other users or devices that might have a commonality. 

**Note:** In some cases I  might start on other layer first which is based on the information that I gathered or on my gut feeling from my previous experiences.  
Ping or traceroute might not be effective in some cases because those 2 tools does not have all the same characteristics of all types of traffic, there might be a firewall rules or other security options that might affect the ping, traceroute and other types of data traffic.
{: .notice}

## We are not perfect!
So you are done on checking all the components involved on the issue and you still did not find the problem. I suggest you double check again specially the things that involved reading, like checking the log files and for configuration errors buseace arocdnicg to rsceearch, we as huamns are prone to errors.Tihs is buseace the huamn mnid deos not raed ervey lteter by istlef, but the wrod as a wlohe.

Use more detailed or extensive operational mode commands and used the pipe | commands  to identify the problem. For example: *show interfaces xe-0/0/0 extensive | match "phy|desc|err|last"*
This is an example of juniper command that will show only the things you only want to see like the physical status, description of the interface, what are the errors, and when is the last flapped happened.

Now if you already know the issue or you think that you found out what is causing the issue then think or identify the possible solutions, then implement the solutions but know when to use a [Change Control Procedure](https://en.wikipedia.org/wiki/Change_control) because not all changes needed to be done during operation hours  especially if the issues are not impacting the overall services. Make a draft [Method of Procedure(MOP)](https://www.techopedia.com/definition/31833/method-of-procedure-mop) that you can show to your senior engineers for them to double check the procedures and had it approved the changes that would be made. 
For example you move the user or device  to another port, line card, or other device. Then suddenly your CEO called to your boss and said he has an ongoing video conference to a billionaire investor and that’s the only time you realize that there are other devices that are working fine got affected. :scream:  :runner:  
So do the disruptive things that you know during the allocated maintenance window.

## Don’t make the problem much worse!
 Always remember to double check the things that you will do because regrets are felt when it's just too late. So leverage the Internet and ask your colleagues if what you are doing is appropriate. Always have a backup plan and a rollback or backup config. If your company has a lab, use it to simulate the scenario and do the troubleshooting steps that are service impacting especially if you think its a software related issues. If it is a complex issue engaged with the TAC team of the device you think has an issue especially if your company is already losing millions due to an outage.
.
 
The above discussion is somehow mainly focus only on  user or customer reported issues and did not get much into a NOC environment.

## What if the problem was seen on your monitoring tool?
The first thing you will do is to acknowledge the alarm and create a ticket for it so your colleagues will know that you are already working on it, then start troubleshooting!
Nope that's wrong, you should first check other alarms that may also connected or the result of  the alarm that you have acknowledged because not all alarms will indicate where should you look at first because that alarm might be a result of a bigger problem or  there might be other factors is contributing to the issue. Well usually if the issue has connecting issues, you will get bombarded by alarms especially if your network implements different protocols. For example: It’s weekend and you are on a night shift alone because your partner got sick and you said you will be fine since its weekend and there are no maintenance, then suddenly boom! :boom:  your monitoring tool got flooded by different kinds of alarms like BGP Neighbor State Changed, your IGP had adjacency changed, MPLS LSP down, RSVP neighbor down, LAG alarms and etc, . What should you do? Of Course stay calm, your mind won’t work properly if you are tense, next find the worst alarm that you can think of that may have triggered that alarms, well in most cases there is a device went down or link went down on your network. This is where the [bottom-up approach](http://www.ciscopress.com/articles/article.asp?p=2273070&seqNum=2) is much better to use because the protocols like BGP, MPLS, IGPs relies on the layers below it.

 
Ok so you have a glimpse on what is happening on your network the next thing to do is search for any related tickets or email like an ongoing maintenance, an open troubleshooting ticket, or any tickets or emails that can help you identify if is that a legit alarm or a normal behaviour on your network that can make your ticket be cancelled and let you continue to watch movies on netflix :joy: or let you study for the certification that you would take.

But what if you are really unlucky because it’s a legit alarm, well good luck on your weekend shift. :sob: 
If the network of the company that you are working for is not that big, you might perhaps start troubleshooting remotely.
But if your are on a large-scale network you might start calling on site technicians / Engineers, your drunk senior network engineer and your boss that is already snoring. After hearing all the angry voices(if you are really unlucky person), you now start on troubleshooting and apply the steps that I have discussed earlier and make sure you document all the things that you see and done already so that other engineers knows the background of the issue and also you can write something for your Post-Mortem. :satisfied:

**Note:** That won’t usually happen on a large-scale network, so leverage your colleagues, work as a team like 1 person calling other teams and setting up an outage group chat or video conference, 2 persons are troubleshooting and 1 person is documenting and reporting, and  If you can have a short-term fix do it  instead of sacrificing the money being lost by your company due to an outage that is taking too long to be resolved. 
{: .notice}

Ok that’s all I can think of for now which are based from my experiences and have read, I hope you have learned something on this post that can help you on your daily work. Perhaps in the future I’ll add more troubleshooting post which is targeted on a specific issues like on routing, switching, software, hardware and etc.

If you have other troubleshooting steps on your mind, previous outage experiences whether its funny or informational, comment it down bellow so that we can read it.

>If you hate troubleshooting and having stressful task, Then learn how to love it or find yourself a new job while it’s still early.

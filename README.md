# <img src='https://raw.githack.com/FortAwesome/Font-Awesome/master/svgs/solid/bus.svg' card_color='#40DBB0' width='50' height='50' style='vertical-align:bottom'/> Public transport Tracking
Announce arrivals of Public transport.

## About

Based off MBTA project hopefully make it more general so that you can add other public transports. 

Because mycroft 1 and mycroft 2 are meant to be be in one location the idea is to add a discrete list of bus stops in the confibguration page that can then be called to find out if you have to run for the bus or underground. 

The idea is that this should be shorter process than taking out your phone. 


<details><summary>View Sample situation</summary>
<dl>
Puts on coat with one hand removes toast from mouth on the other hand 

<dt>Hey Mycroft Bus</dt>
<dd>Are you going outbound toward Richmond or toward Kingston?</dd>
<dt>Kingston</dt>
<dd>The next bus to Kingston is: <dd>
<dd>Arriving in 11 minutes<dd>
<dd>Arriving in 21 minutes<dd>
<dd>Arriving in 34 minutes<dd>
</dl>
</details>



Please see orginal project: https://github.com/richhowley/mbta-bus-tracking-skill



Mycroft will announce estimated arrival times of MBTA buses at your stop so you never leave the house before you have to.  All data and arrival predictions used by this skill are provided by the MBTA.  

See below for full documentation, including how to track buses traveling toward your stop, but to get started just say "Hey Mycroft, T Bus Arrivals".  You will be prompted for the bus route, direction and stop name.  Mycroft will respond with all estimated arrival times at your stop.

<details><summary>View Sample dialog</summary>
<dl>
<dt>Hey Mycroft T Bus Arrivals</dt>
<dd>Which route are you riding?</dd>
<dt>One</dt>
<dd>Are you going outbound toward Harvard or Inbound toward Dudley?</dd>
<dt>Inbound</dt>
<dd>Which stop?</dd>
<dt>Mount Auburn Street at Putnam Ave</dt>
<dd>Route One service to Dudley arrivals for Mount Auburn Street at Putnam Avenue:<dd>
<dd>Arriving in 11 minutes<dd>
<dd>Arriving in 21 minutes<dd>
<dd>Arriving in 34 minutes<dd>
</dl>
</details>

<details><summary>View Full Documentation</summary>

#### T bus or Transit

Wherever this documentation calls for saying "T bus" to Mycroft it can be replaced with "transit", and vice versa.  If Mycroft is having difficulty understanding  one, try the other.

#### Arrival Times

To provide bus arrival times the skill requires three pieces of information:  bus route, traveling direction and bus stop.  If you do not provide all information needed the skill will prompt you for the rest.  For example, saying

> T bus arrivals route 57 going inbound stop Brighton Ave and Linden Street

will retrieve all arrival times predicted for the stop.  The arrival times could also be retrieved by any of the following:

> T bus arrivals route 57 going inbound

> T bus arrivals route 57

> T bus arrivals

Mycroft will prompt for any missing information.

#### Bus Tracking

Bus tracking is similar to Arrival Times but Mycroft will continue to track buses, periodically updating their predicted arrival times, until they have passed the stop.  By default Mycroft will track the next three buses and will announce updated arrival predictions every 30 seconds.  These values can be changed in the skill settings on Mycroft Home.  The minimum frequency of updates  is 30 seconds.

As with Arrivals, say

> T bus tracking

to begin.  Predicted arrival times of the next three tracked buses will be announced right away and updated every 30 seconds.  Be aware that there may be any number of buses heading to your stop but only the arrival predictions for the tracked buses will be announced.

When a bus passes your stop it will drop off the tracking list and there will be one fewer arrival time announced on subsequent updates.  When all buses have passed your stop Mycroft will automatically stop tracking.  If you would like tracking to end at any time say

> T bus shutdown

#### Shortcuts

If you ride the same route from the same stop often you will want to use shortcuts.  After Mycroft announces arrivals or starts tracking buses you may save the route, direction and stop combination as a shortcut using any name you wish.

Suppose you take the bus to work and went through the process of asking for arrivals, telling Mycroft the bus route, direction and stop.  Now say

> transit save shortcut

and Mycroft will prompt you for a name.  If you say

> rat race

you may get Arrivals or begin Bus Tracking using the shortcut

>T bus tracking rat race

Two additional phrases

> list T bus shortcuts

> T bus remove shortcut rat race

allow you to list and delete saved shortcuts.

#### API Key

When installed this skill does not use an API key when getting data from the MBTA servers.  Using a key allows a higher rate limit when requesting data.  It should not be necessary to use an API key but if you like you may obtain one on the [MBTA website](https://api-v3.mbta.com/register). In the skill settings on Mycroft Home check the box next to "Use my API key" and enter your key in the text field.

</details>


## Examples
* "T Bus Arrivals"
* "T Bus Tracking"
* "Save Transit Shortcut"

## Credits
Rich Howley

## Category
**Transport**

## Tags
#MBTA,#Boston

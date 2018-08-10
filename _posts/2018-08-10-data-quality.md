
---
post_author: Phelim Bradley
layout: post
title: "Bots and data-quality on crowdsourcing platforms"
description: ""
category: 
tags: [mturk, bots, data quality]
---

<div class="row">
	<div class="col-md-12">
 		<img class="img-responsive col-md-14" style="display: block;margin-left: auto;margin-right: auto;margin-top:40px;margin-bottom:15px;" src="/assets/img/programming.jpg">
	 </div>
</div>

<font size="+1">
<br>
<p>Recently, researchers using Amazon Mechanical Turk to collect data for their studies found large numbers of bot-like responses in their data from workers with very similar geoIP co-ordinates. You can read more about this <a target="_blank" href="https://www.maxhuibai.com/blog/evidence-that-responses-from-repeating-gps-are-random">here</a>, and in many other forums and mailing lists.</p>

<p><a target="_blank" href="https://twitter.com/kgweisman/status/1027567993658720257">Some have reported</a> that the "bots" may be able to pass a range of different attention checks. Our assessment of the reports coming from MTurk is that these accounts are more likely to be bot-assisted humans (or human-assisted bots?), rather than bots with sufficient AI to pass attention checks. Is also seems possible they are using VPNs to hide their true location.</p>

<p>From a data quality perspective there is little difference between malingerers providing random responses (while passing attention checks) and true bots. However, it does mean that using passwords or captchas within surveys may not improve this situation and it may be more challenging to catch and block these accounts.</p>

<p>One of the key reported signals are responses from repeated Latitude and Longitude values. The author has described these as "GPS" coordinates. However, since the author is using Qualtrics to collect data, it's likely that these are geoIP values—which are <a target="_blank" href="https://www.qualtrics.com/support/survey-platform/data-and-analysis-module/data/download-data/understanding-your-dataset/"> only accurate to the city level according to Qualtrics</a> rather than true Google-Maps-esque GPS coordinates. As such, it's possible to see repeated lat/long values in your data and for these to be respondents in the same city, rather than in an identical location. Qualtrics data is somewhat misleading in this respect as they provide lat/long values to several decimal places despite only being accurate to city level. </p>

<p>However, the particular signature of "88639831" after the latitude decimal point seems to be informative (from the data of the linked blog post above), and may be a signature of a particular VPN these bot-like accounts are using. Based on our own analysis it does seem like VPNs seem more likely to give these repeated geoIP locations, although that still doesn’t guarantee that these are bots. </p>

<h2>Data quality at Prolific</h2>

<p>In case there are concerns about this being an issue beyond Mturk: <em>We have not seen evidence of similar bot-like accounts on Prolific</em>. We have several processes in place to prevent these types of accounts. These include (but are not limited to) the following:</p>

<ol>
<li> Every account needs a unique non-<a target="_blank" href="https://en.wikipedia.org/wiki/Voice_over_IP">VOIP</a> phone number to verify.</li>
<li> We restrict signups based on IP and ISP (e.g. we allow common residential ISPs but block low-trustworthy IP/ISPS).</li>
<li> We limit to the number of accounts that can use the same IP address and the machine to prevent duplicate accounts.</li>
<li> We limit the number of unique IPs per "HIT" (study).</li>
<li> PayPal and Circle accounts for getting paid must be unique to a participant account. This means that in order to have 2 participant accounts that get paid, you would also need to have 2 PayPal accounts. PayPal and Circle also have steps to prevent duplicate accounts.</li>
<li> We take any data-quality reports very seriously and whenever researchers have suspicions about accounts they can report the relevant participant IDs to us we investigate the individual accounts as well as any shared patterns between them.</li>
<li> We analyse our internal data to monitor for unusual usage patterns, and and data reports from researchers.</li>
</ol>

<p>Unlike Mturk, Prolific is dedicated to empowering great research, so data quality is our top priority. We have extensive quality checks to make sure our participants are trustworthy, attentive, engaged, and where possible, <a target="_blank" href="https://link.springer.com/article/10.3758/s13428-013-0365-7">naïve</a>. And we are continuing to improve these features all the time.</p>

<p>There are many aspects to data quality, and not having participants who are (or are using) bots is the lowest bar. Malingerers or unengaged participants will provide similarly poor data. Also, participants who are over-exposed to your manipulation and no longer naïve, may also provide poor data (although of a slightly different nature). </p>

<p>At Prolific, we take a holistic approach to data quality and we hope to have many announcements to come in this regard as we improve internal and external tools and processes to improve the quality of data our participants provide. We'll aim to be as open and transparent about our processes as possible without providing sufficient evidence to bad actors, who may try to circumvent these checks.<p>

<p>If you want to come and help us with this challenge, <a target="_blank" href="https://prolific.breezy.hr/">we're currently hiring</a>! Or, please get in touch if you have suggestions for improvements, features, or any questions at support@prolific.ac.



After several years of development in [Java](http://java.com "Java") with the [J2EE stack](http://en.wikipedia.org/wiki/Java_Platform,_Enterprise_Edition "Java Platform - Enterprise Edition stack"), sometimes it’s quite a [PITA](http://en.wikipedia.org/wiki/Pain_in_the_ass "PITA") to develop against [JBoss](http://www.jboss.org/ "JBoss"). Despite that JBoss is good at maintaining dependencies and runtime environments, being stable and reliable, sometimes a developer needs to maintain a core project java class or library. JBoss then needs to restart its core to maintain the new dependecies.

### where the **pain** starts

JBoss needs about *10 to 120 seconds* to *fully restart* before any developer can view their changes. To extrapolate this:

1 developer x 1 change in code/hour = 60 seconds wait

On a normal project with everyday work of about eight hours and about 10 changes per hour this means

10 changes in code/hour * 8 hours * 60 second wait = 80 minutes

So let’s see, your pretty, nifty developer is waiting **about 40 minutes a day**? So lets break this down to a best-case, worst-case screnario:

best: 10 changes in code/hour * 8 hours * 60 second wait = 80 minutes

median: 30 changes in code/hour * 8 hours * 60 second wait = 240 minutes

worst: 60 changes in code/hour * 8 hours * 60 second wait = 480 minutes

### team breakdown

An average team of *five* developers on a project running about a full year with approximately 210 days would then waste…

median: 5 * 30 changes in code/hour * 210 days * 60 second wait = 31500 minutes

…about *~525 hours* work time! Thats about *~22 full days* (24h a day) or *~66 workdays* of pure waiting! Not to mention this is only the *median*!

<span style="line-height: 1.7;">To break this down: </span>*This is a full developer for one month!*



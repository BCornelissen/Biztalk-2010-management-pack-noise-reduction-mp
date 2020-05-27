# Biztalk-2010-management-pack-noise-reduction-mp
BICTT BTNR Biztalk 2010 management pack This management pack is created in order to reduce the noise in a multitude of alerts some people see after importing the Biztalk Server 2010 management packs

BICTT BTNR Biztalk 2010 management pack


This management pack is created in order to reduce the noise in a multitude of alerts some people see after importing the Biztalk Server 2010 management packs.

This management pack has the same version as the management pack it is meant to reduce noise from (which is 7.0.389.0 for this release). The download above contains the management pack and a pdf containing the below.

The BICTT BTNR management pack is depending on the Microsoft Biztalk Server 2010 management packs for their use. The Microsoft management pack for Biztalk Server 2010 can be found here: http://www.microsoft.com/download/en/details.aspx?displaylang=en&id=14897


What happened was that a number of rules check for events in the event logs of these BizTalk Servers for messages that got stuck. This would create one SCOM alert for every message that got stuck in a channel, because the message ID was specified in the alert and thus seen as unique. In multiple cases this caused hundreds or thousands of alerts in a very short time period if this happened on large volume systems. This thus caused the SCOM console to become very slow and operators could not scroll through the long list of alerts anymore to see what was going on. In some cases this resulted in a select-all and close action of operators in trying to clean up and thus throwing away other alerts as well which happened to be in their screen.

What this management pack does is to override the original rules which seem to cause this behavior and it holds exactly the same rules with one small change. It doesn’t
check the contents of what we see as the Alert Description to see if it is the same. So if one of these rules is triggered multiple times on the same machine on the same channel it will give you one alert and increase the repeat counter on it.


One additional note:

Always test management packs in a test environment and see if they work as expected. This management pack is made available as-is because we got a few requests
for it, but we do not provide any special support for it and do not assume any responsibility if you find negative results. Just make sure you test it yourself.

Find more on the background of this management pack over here:
https://blog.topqore.com/scom-biztalk-2010-noise-reduction/


Good luck and enjoy your monitoring!

Bob Cornelissen

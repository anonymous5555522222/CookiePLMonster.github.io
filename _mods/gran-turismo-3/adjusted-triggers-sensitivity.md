---
title: Adjusted triggers sensitivity
game-series: "gran-turismo-3"
order: 1
date: 04-03-2023
---

{:.credit}
Patch further improved by Aero_.
Ported to NTSC-J by xan1242.

Since Gran Turismo games have always offered full control remapping, it's possible to utilize triggers on modern controllers for throttle/brake,
much like most modern games do. However, unlike in newer Gran Turismos, doing this in the PS2 games results in a mediocre experience -- analog sensitivity
is tailored for analog buttons of the DualShock 2 controller, and therefore inputs are heavily scaled. In practice, this means that anything over ~half the trigger
press is already registered as a 100% input, so precise throttle control is hard. With this code, I've removed this scaling as much as reasonably possible,
so now 100% input registers from a near full press of the trigger, therefore making the experience closer to how the later Gran Turismo games handle it.

{% include setup-instructions.html platform="ps2" %}

***

<a {% include buttons/github-blob-url.html repo="CookiePLMonster/Console-Cheat-Codes" path="master/PS2/Gran%20Turismo%203/Adjusted%20triggers%20sensitivity/SCUS-97102_85AE91B3_triggers.pnach" %} class="button">{% include elements/flag.html flag="us" %} NTSC-U (v1.0, Original)</a>
<a {% include buttons/github-blob-url.html repo="CookiePLMonster/Console-Cheat-Codes" path="master/PS2/Gran%20Turismo%203/Adjusted%20triggers%20sensitivity/PBPX-95503_8AA991B0_triggers.pnach" %} class="button">{% include elements/flag.html flag="us" %} NTSC-U (v1.10, Bundle)</a>

<a {% include buttons/github-blob-url.html repo="CookiePLMonster/Console-Cheat-Codes" path="master/PS2/Gran%20Turismo%203/Adjusted%20triggers%20sensitivity/SCES-50294_B590CE04_triggers.pnach" %} class="button">{% include elements/flag.html flag="eu" %} PAL</a>

<a {% include buttons/github-blob-url.html repo="CookiePLMonster/Console-Cheat-Codes" path="master/PS2/Gran%20Turismo%203/Adjusted%20triggers%20sensitivity/SCPS-15009_9DE5CF65_triggers.pnach" %} class="button">{% include elements/flag.html flag="jp" %} NTSC-J</a>

<a href="https://github.com/CookiePLMonster/Console-Cheat-Codes/blob/master/PS2/Gran%20Turismo%203/Adjusted%20triggers%20sensitivity" class="button github" target="_blank">{{ site.theme_settings.github_icon }} See source on GitHub</a>
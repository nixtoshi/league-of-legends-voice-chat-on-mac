## LoL with Voice.app
#### Fix the Voice Chat issue on new MacOS releases with a simple .app executable instead of the official League of Legends launcher

##### Pre-requisites:
1. Haven an Intel-base Mac.
2. If you have an M1 and higher chip, it's possible that this fix won't work for you as some people have reported issues when using this fix on Macs with M1 and later. If this is the case for you, I would highly recommend that you and your friends use Discord, since Discord is usually up to date and bug-free on Macs and other operating systems.

##### The simple Solution:
1. Make sure you have League of Legends installed in this path: `/Applications/League of Legends.app`. This is the default installation path, so you will probably not have to do anything here, go to step 2.

2. Download and run the app I built.

3. Launch my app and go to `Settings > Voice` inside League of Legends.

4. Choose the right microphone (most often it will be your internal mic, or your headphone's mic), click on the Microphone symbol to Test the sound. This will show a pop-up that asks you if you want to give `LoL with Voice.app` permission to use your Microphone, simply click **Yes** or **Allow**. You only have to do this once.

5. Every time you want to use League with Voice Chat enabled you must run League of Legends from my app `LoL with Voice.app`. This will work on all future League of Legends updates as long as LoL doesn't change the location of their client's executable within its application package (unlikely).



<a href="https://github.com/dalovar/league-of-legends-voice-chat-on-mac/archive/master.zip"><img src="http://i.imgur.com/rLIFy4H.png" alt="drawing" width="250"/></a>

### Donations
If you found this useful I accept donations:

**PayPal:** https://paypal.me/nixtoshi

**Bitcoin:** 36dHn9jbaYcKKzvMSwKw2JjoHXiqWhaDvp



##### More About The Problem
For some time now since the release of MacOS Mojave in September of 2018, League of Legends players haven't been able to use the client's voice chat feature because the client doesn't ask Apple computers for permission to use their microphone.

##### The Long Term Solution
The real solution must come from Riot Games, they should simply request the permission to use the user's microphone in their future MacOS releases.

##### How does my temporary solution work?
The Automator-based app is simply acting as a container and running this bash script:
```sh
# Goes into the app's contents
cd '/Applications/League of Legends.app/Contents/LoL/'
# Runs the client
./LeagueClient.app/Contents/MacOS/LeagueClient
# Kills the script monitor that makes de the cog icon from the Automator task show
killAll ScriptMonitor
```
So what are we doing here? Yes, we are just running the client from a bash script, however, the Automator app container will ask the user for the permission to use the Microphone unlike League's official client, and the apps that the container runs inherit these permissions.

##### Will this add load on my PC or does this have any malware in it?
No and no. The added load from having a container app run another app is minimal, literally 0.00% impact on your PC's performance. This app doesn't contain any malware, in fact all the code is a template from Automator and my actual code is just 3 lines compacted into one non-obfuscated line of code, and since the code is open source here on Github, anyone can inspect and review it.


Good luck, have fun ;) 

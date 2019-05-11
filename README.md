## LoL with Voice.app
#### Fix the Voice Chat issue on Mojave with a simple .app executable instead of the official app

##### The Simple Temporary Solution
1. Make sure you have League of Legends installed in this path: `/Applications/League of Legends.app`. This is the default installation path, so you will probably not have to do anything here, go to step 2.

2. Download and run the app I built on Automator instead of the official launcher.

3. Launch my app and go to `Settings > Voice` inside League of Legends.

4. Choose the right microphone (most often it will be your internal mic, or your headphone's mic), click on the Microphone symbol to Test the sound. This will show a pop-up that asks you if you want to give `LoL with Voice.app` permission to use your Microphone, simply click **Yes** or **Allow**.

5. Every time you want to use League with Voice Chat enabled you must run League of Legends from my app which is called `LoL with Voice.app`. This will work on all future updates as well as long as LoL doesn't change the location of their client's executable within its application package.



<a href="https://github.com/dalovar/league-of-legends-voice-chat-on-mac/archive/master.zip"><img src="http://i.imgur.com/rLIFy4H.png" alt="drawing" width="250"/></a>

### Donations
If you found this useful I accept donations:

**PayPal:** www.paypal.me/daxlo

**Bitcoin:** 36dHn9jbaYcKKzvMSwKw2JjoHXiqWhaDvp



##### More About The Problem
For some time now since the release of MacOS Mojave in September of 2018, League of Legends players haven't been able to use the client's voice chat feature because the client doesn't ask Apple computers for permission to use the microphone.

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
No and no. The added load from having a container app run another app is minimal, literally 0.00% impact on your PC's performance. This app doesn't contain any malware, in fact all the code is a template from Automator and my actual code is just 3 lines compacted into one no-obfuscated line of code, and since the code is open source here on Github, anyone can inspect what they are downloading before they use it and report me if I was distributing malware. And I'm not.


Good luck, have fun ;)
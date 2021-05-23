# LB Clip It
 Extension for LioranBoard which lets you create clips and post them to Discord.      
 This is an updated version of the previous release in LioranBoard Discord.       
 The extension requires clips:edit scope to properly work. Make sure 'Create Clips' is ticked in the 'Link your Twitch' menu in LB Receiver and relink your Twitch account if needed. 


    
 **Clip It INIT button:**        
1. oauth_token = your broadcaster's oauth token 
2. channel_id = your broadcaster's channel ID you're going to create the clips from     
3. webhook = your Discord Webhook url. See [Here](https://docs.gitlab.com/ee/user/project/integrations/discord_notifications.html) how to create a Webhook for your own Discord channel.    
4. content = Discord post. It supports [Discord Markdown](https://support.discord.com/hc/en-us/articles/210298617-Markdown-Text-101-Chat-Formatting-Bold-Italic-Underline-) and the following custom parameters (will be automatically replaced by the extension):    
	* `<text>` (viewer's text)
	* `<author>` (viewer's name)
	* `<broadcaster>` (broadcaster's name)
	* `<category>` (game category)
	* `<title>` (stream title)
	* `<clip>` (clip url)
 	* `<n>` (new line)
5. username = username the Discord message will be posted under


 **Clip It button:**  
IMPORTANT: You MUST press the INIT button before triggering the Clip It button. 
You can use Math: Trigger pull to get your viewer's name and their message to post it on Discord together with your clip URL. 
1. author = your viewer's name
2. text = your viewer's text/title of the clip to post on Discord (this does NOT rename the clip on Twitch) 
3. discord post = whether you want it posted on Discord
4. variable = variable to save the newly created clip ID 
5. ext_trigger = extension trigger name
   - This will fire as soon as the clip creation is complete (or fails) and trigger !clip done button
   - The advantage is that you do not need to set up your own delay to make sure you don't post an empty clip URL in your chat 
6. trigger_enabled = whether you want to use the extension trigger (else you can manually add a delay)

**!clip done button:**        
This button will trigger as soon as the clip is created (or the extension fails creating it). 
1. math trigger pull value 1 = clip ID of your newly created clip (in the event it fails, it will be set to "error")
2. math trigger pull value 2 = your viewer's name
3. math trigger pull value 3 = your viewer's text/title      


The base url for Twitch clips is https://clips.twitch.tv/CLIPID.

* If a clip is successfully created, you will also receive a yellow notification message in your Receiver 'Clip creation successful'.
* If a clip is successfully created AND posted to Discord, you will receive another yellow notification message 'Clip successfully posted to Discord!'
* If there is any problem with creating a clip or posting it to Discord, you will receive a yellow notification message containing the error.  

*Note: Clip It button and !clip done button's commands can be merged into a single button using String: Get Trigger type and Skip if commands. *


Example: 
  
![Clip it example](https://i.imgur.com/3H4WAF4.png)


**How to install an extension:**
1. Download the .lbe extension file
2. Click on Install Extension in your LioranBoard Receiver
3. Select the extension file you downloaded 
4. Select your default Transmitter you are using. Make 100% sure it is the correct one. 
5. Refresh your Transmitter or close and reopen Lioranboard Receiver. 
6. Most extensions include a premade deck with buttons. If you do not see one, create a new button, add "Send to Extensions" command and select the extension you just installed. If you can only see the extension name with no input fields, it means it was not installed correctly. Repeat steps above.    

[![](https://github.com/christinna9031/LioranBoard-Files/blob/main/img/paypal.png?raw=true)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=3YWXYQE3HKWHQ)

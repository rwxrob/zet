# Would be cool to have keg node -> command converter

Now that keg nodes are relatively minimal I could actually create a system where the nodes in a keg that interlink could automatically be created into Twitch/Cloudbot/chatbox commands. Once we have the KEGML node parser its an absolutely trivial task to render any node under the maximum length of a chat message as a `!cmds` response. In fact, I could build a bot that automatically integrates with keg queries and shows the summary (first commands) of any keg node.

However, I think it's best to just create a keg just for Twitch commands, each under 380 bytes, and allow them to link directly to the https://rwx.gg/ URLs for more information about that topic. Then I can keep those nodes synced up with the command with more information rather easily. (And https://zet.rwx.gg will be entirely separate.)

* Twitch Chat Messages  
  https://dev.twitch.tv/docs/irc/send-receive-messages

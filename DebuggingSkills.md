> How to use different users to enter the game in the debugging environment

<p>
Minecraft provides a parameter to set the user name, but I don't like to use it because it requires modifying the parameter in the IDE, I use conditional breakpoints to do this.
</p>
<p>
Come to the net.minecraft.client.main.Main.run method, you can see a lot of OptionSpec at this time. They are Minecraft configurations, one of which is 'username', which will be the value we need to modify.
</p>
Find:
<code>
  OptionSet optionset = optionparser.parse(pArgs);
</code>
<p>
All configurations of Minecraft are parsed here, after which all Minecraft configurations are stored in optionset, including default configurations and specified configurations.
</p>
<p>
We set a conditional breakpoint on the next line of code in it, and uncheck the suspend and conditional options, and turn on the evaluate and log options. Write the following code
</p>
<code>
  optionset.optionsToArguments.get(optionspec10).set(0, "Your name").
</code>
<p>
This will use the new username instead of Dev the next time you boot.
</p>

**Tip: Note that optionspec10 in the code represents the username configuration, if it changes in the future, you need to set it to the new username configuration**

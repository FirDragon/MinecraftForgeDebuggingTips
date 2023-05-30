> NoClassDefFoundError appears when I add additional packages.

Because the mod developed by Forge is installed as a plug-in, which means that it will not carry its dependent library. This problem occurs if you use a package that does not exist in Minecraft. You need to use something like ShadowJar JarInJar to pack packages that the original MC doesn't have into the mod.
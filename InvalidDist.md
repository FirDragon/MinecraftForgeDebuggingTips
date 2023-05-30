>  Attempted to load class xxx for invalid dist DEDICATED_SERVER

You are trying to load or use an incorrect class in the environment.
Such as using Minecraft.getInstance().player in the server.
In general, you don't need to read the instructions here to solve this problem.
Because Java is lazy loading, it will only be loaded when it is used, so a simple if can solve this problem.
But in some cases classes will be loaded ahead of time. Such as all classes used in Mixin, they will load all the classes in the patched class at the same time as the patched code, so using if does not prevent incorrect classes from being loaded into the environment. Therefore you need to move this fragment out of the Mixin class.

If you need to make the entire method available only to the client, use @OnlyIn( Dist.CLIENT ) to mark your method.
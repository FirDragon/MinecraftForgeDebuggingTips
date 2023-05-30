> It always crashes at some random point and says I shouldn't be using it in multithreading

<p>Usually because you are trying to use the same LegacyRandomSource object from multiple threads, you need to ensure that they are only accessed by one thread at all times. This is commonly seen in servers, where the server's network message processing works in an extra thread, which means that if you try to access Player.random or Level.random indirectly or directly in the network message processing method will cause this problem. You need to execute these codes in context.enqueueWork, it will ensure that the code works in the correct thread.</p>

**There is a great MOD that can help you quickly find the problem.**
<p>https://github.com/RelativityMC/unsafe-world-random-access-detector</p>

<html lang="en">
<head>
<meta charset="UTF-8">
<title>Integra SDK Documentation</title>
<style>
    body {
        font-family: Arial, sans-serif;
        background: #0f1115;
        color: #e6e6e6;
        margin: 0;
        padding: 0;
    }
    header {
        background: #1a1d24;
        padding: 20px;
        font-size: 24px;
        font-weight: bold;
    }
    section {
        padding: 20px;
        border-bottom: 1px solid #2a2f3a;
    }
    h2 {
        color: #6ab0ff;
    }
    code {
        
        padding: 4px 6px;
        border-radius: 4px;
    }
    pre {
        background: #1e222a;
        padding: 10px;
        overflow-x: auto;
        border-radius: 6px;
    }
    .method {
        margin-bottom: 15px;
    }
</style>
</head>

<body>

<header>Integra SDK Documentation</header>

<section>
<h2>Getting Started</h2>
<p>Create a new instance of <code>Integra</code> to begin using the API:</p>

<pre>
Integra integra = new Integra();
</pre>

<p>The SDK initializes asynchronously. Features become available once initialization completes.</p>
</section>

<section>
<h2>Core Features</h2>

<div class="method">
<h3>toggleFly(boolean enabled)</h3>
<p>Enables or disables free-flight movement.</p>
<pre>integra.toggleFly(true);</pre>
</div>

<div class="method">
<h3>toggleSpin(boolean enabled)</h3>
<p>Applies continuous angular velocity to the local entity.</p>
</div>

<div class="method">
<h3>setSpinSpeed(float speed)</h3>
<p>Controls spin intensity.</p>
</div>

<div class="method">
<h3>toggleESP(boolean enabled)</h3>
<p>Enables on-screen overlay rendering.</p>
</div>

<div class="method">
<h3>setFlyMaxSpeed(int speed)</h3>
<p>Limits maximum velocity while flying.</p>
</div>

</section>

<section>
<h2>Movement & Physics</h2>

<div class="method">
<h3>setWalkspeed(float speed)</h3>
</div>

<div class="method">
<h3>setJumpHeight(float height)</h3>
</div>

<div class="method">
<h3>setJumpPower(float power)</h3>
</div>

<div class="method">
<h3>setVelocity(long instance, Vector3 velocity)</h3>
</div>

<div class="method">
<h3>setAngularVelocity(long instance, Vector3 velocity)</h3>
</div>

</section>

<section>
<h2>ESP / Overlay</h2>

<div class="method">
<h3>addESPTagColor(String tag, Color color)</h3>
</div>

<div class="method">
<h3>addESPTagIcon(String tag, BufferedImage image)</h3>
</div>

<div class="method">
<h3>espShowName(boolean enabled)</h3>
</div>

<div class="method">
<h3>espShowBox(boolean enabled)</h3>
</div>

<div class="method">
<h3>espShowIcon(boolean enabled)</h3>
</div>

</section>

<section>
<h2>Player & World Access</h2>

<div class="method">
<h3>getLocalPlayer()</h3>
<p>Returns the local player instance.</p>
</div>

<div class="method">
<h3>getPlayerList()</h3>
<p>Returns a list of active players.</p>
</div>

<div class="method">
<h3>getWorkspace()</h3>
<p>Returns current Workspace</p>
</div>

<div class="method">
<h3>getDataModel()</h3>
<p>Returns current DataModel</p>
</div>

<div class="method">
<h3>getService(String service)</h3>
<p>Returns Service from DataModel</p>
</div>

<div class="method">
<h3>rejoin()</h3>
<p>Rejoins the current instance using PlaceId</p>
</div>

<div class="method">
<h3>setWorkspaceGravity(float value)</h3>
</div>

</section>

<section>
<h2>Memory Utilities</h2>

<p>These methods provide low-level memory interaction capabilities.</p>

<div class="method">
<h3>read(long address, int size)</h3>
<p>Reads raw bytes from memory.</p>
</div>

<div class="method">
<h3>write(long address, byte[] data)</h3>
<p>Writes raw bytes to memory.</p>
</div>

<div class="method">
<h3>readFloat(long address)</h3>
</div>

<div class="method">
<h3>writeFloat(long address, float value)</h3>
</div>

<div class="method">
<h3>resolvePointer(long base, int... offsets)</h3>
<p>Follows pointer chains safely.</p>
</div>

<div class="method">
<h3>alloc(int size)</h3>
<p>Allocates memory in target process.</p>
</div>

</section>

<section>
<h2>Example Usage</h2>

<pre>
Integra integra = new Integra();

integra.toggleFly(true);
integra.setFlyMaxSpeed(50);

integra.toggleESP(true);
integra.setRGBColors(true);

integra.setWalkspeed(32f);
</pre>

</section>

<section>
<h2>Notes</h2>
<ul>
<li>All operations are asynchronous after initialization.</li>
<li>Ensure target process is available before calling features.</li>
<li>Use memory functions carefully — invalid addresses may fail silently.</li>
</ul>
</section>

</body>
</html>

SchematicCarpet 1.0.4  (Fabric, Minecraft 1.21.11, needs Litematica)
=====================================================================

BUILD
  1. Install Java 21 (JDK) if you don't have it. Internet is needed on the first build.
  2. Unzip this folder, open cmd inside it, run:

         gradlew build

  3. Your jar is in:   build\libs\schematiccarpet-1.0.4.jar
     (ignore the "-sources" jar)

  First build downloads Gradle, Minecraft and Fabric (a few minutes). Later builds are fast.

WHAT CHANGED vs 1.0.3
  The tick handler used to stop whenever the item in your hand was not a carpet.
  So when you held right-click and the last carpet of a color ran out (empty hand),
  nothing happened. Now an EMPTY hand is allowed too: while right-click is held and you
  aim at a spot where the schematic wants a carpet, the mod pulls the needed color
  from the hotbar, or swaps it in from the main inventory, and keeps placing.
  Holding any other non-carpet item (sword, etc.) is still ignored, like before.
  The change is in SchematicCarpetClient.onTick (search for "1.0.4").

NOTES
  * gradle/wrapper/gradle-wrapper.jar is a small custom replacement for the official
    wrapper (source in gradle/wrapper-src). It reads gradle/wrapper/gradle-wrapper.properties,
    downloads Gradle 9.2.1 once into your .gradle folder and runs it.
  * The unused Litematica "pick block" helper from 1.0.3 (disabled by a constant) was left out.

Networked Physics Demo: "Fiedler's Cubes"
Copyright © 2008-2010 Glenn Fiedler http://www.gafferongames.com/

Fiedlerʼs Cubes is a tech demo for a networking model which allows players to interact with a physically simulated world with no latency, while supporting late joins in an open-world game with no dedicated server.

The main techniques used in this demo are the authority scheme and corrections. Please see my GDC 2010 slides "Networking for Physics Programmers" for more information.

The player controls are:

arrow keys = movement
space = jump 
z = katamari

There are multiple demos included in this package. You may switch between each demo using the ALT-# keys:

alt-1 = singleplayer demo (default)
alt-2 = synchronization demo (two sims side by side w. one second simulated lag)
alt-3 = authority scheme demo
alt-4 = corrections demo

The two main demos are the authority demo and the corrections demo. Within these two demos the common controls are:

"1,2,3,4" = select player
5 = follow camera
6 = top down camera @ origin
enter = toggle splitscreen, quadscreen etc.
tab = cycle vis mode
ctrl-1,2,3 etc = latency

Inside the authority demo:

f1 = disable sync between players (default)
f2 = naive sync (feedback) 
f3 = tie break authority (fix feedback for non-player cubes)
f4 = interaction authority (fix latency when interacting with cubes)

Inside the correction demo:

f1 = disable sync between players (default)
f2 = interaction authority (equivalent to F4 in auth demo) 
f3 = corrections (supports late joins)
f4 = reverse corrections (not implemented!)

Remember that at any point you can press escape to reset the current demo.

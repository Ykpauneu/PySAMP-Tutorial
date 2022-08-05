# Commands, dialogs, objects

So, in this lesson we will write a simple mod, we will also learn how to create commands, objects, dialogs

## Writing code

First, we import everything we need

```python
from pysamp import on_gamemode_init, on_gamemode_exit, add_player_class, create_vehicle, send_death_message
from pysamp.commands import cmd
from pysamp import callbacks
from pysamp.object import Object
from pysamp.dialog import Dialog
from pysamp.player import Player
```

At the very bottom, let's write:

```python
callbacks.hook()
```

In the last lesson we wrote `add_player_class()` many times. Let's create a function that **creates 312 classes**. You'll be able to cut down the code a lot more. I will call this function `add_player_classes()`. Copy the spawning coordinates from me

```python
def add_player_classes():
    for i in range(1, 312):
        add_player_class(i, 410.6863, 2532.9053, 19.1484, 142.4334, 0, 0, 0, 0, 0, 0)
```

Let's start working with `@on_gamemode_init`. First, we just call our function `add_player_classes()`. Later I will show you how to create objects.

```python
@on_gamemode_init
def you_function():
    add_player_classes()
```

So let's start creating objects. We will use the class [`Object()`](https://pysamp.github.io/PySAMP/object.html). I advise you to read about them in the documentation. You should also read about [SA:MP Objects](https://open.mp/docs/scripting/resources/samp_objects). We will simply add `@on_gamemode_init`. Since we're making the gamemode without a specific purpose, you can create any objects (and wherever you want). I, on the other hand, prepared a couple of "blanks" for the tutorial.

```python
@on_gamemode_init
def you_function():
    ...
    Object.create(19129, 403.99963, 2443.17163, 15.49236, 0.00000, 0.00000, 0.00000)
    Object.create(19129, 393.18381, 2443.20361, 15.49236, 0.00000, 0.00000, 0.00000)
    Object.create(19129, 393.18381, 2443.20361, 15.49236, 0.00000, 0.00000, 0.00000)
    Object.create(19129, 416.11423, 2443.08496, 15.49236, 0.00000, 0.00000, 0.00000)
    Object.create(19129, 419.37088, 2463.21509, 15.48603, 0.00000, 0.00000, 0.00000)
    Object.create(19129, 393.37103, 2463.04346, 15.48603, 0.00000, 0.00000, 0.00000)
    Object.create(19129, 413.22226, 2463.03589, 15.48603, 0.00000, 0.00000, 0.00000)
    Object.create(16684, 101.17450, 2400.76733, 217.43260, 0.00000, 0.00000, 0.00000)
    Object.create(16684, 100.08610, 2505.90674, 217.43260, 0.00000, 0.00000, 0.00000)
    Object.create(16684, 99.22626, 2453.56982, 217.43260, 0.00000, 0.00000, 0.00000)
    Object.create(16684, 99.82460, 2349.00098, 217.43260, 0.00000, 0.00000, 0.00000)
    Object.create(16684, 332.55444, 2346.86353, 217.43260, 0.00000, 0.00000, 0.00000)
    Object.create(16684, 334.43445, 2398.62866, 217.43260, 0.00000, 0.00000, 0.00000)
    Object.create(16684, 332.85120, 2451.52319, 217.43260, 0.00000, 0.00000, 0.00000)
    Object.create(16684, 334.30051, 2503.73047, 217.43260, 0.00000, 0.00000, 0.00000)
    Object.create(4165, -84.31020, 2265.83765, 117.02019, 0.00000, 0.00000, 347.37650)
    Object.create(3852, 9.28331, 2244.30029, 126.99873, 0.00000, 0.00000, 253.70534)
    Object.create(979, 9.21947, 2254.90942, 126.43900, 0.00000, 0.00000, 262.15521)
    Object.create(979, 64.01063, 2257.62329, 122.17737, 0.00000, 0.00000, 311.16821)
    Object.create(979, 64.01063, 2257.62329, 122.17737, 0.00000, 0.00000, 311.16821)
    Object.create(979, 69.12370, 2250.51831, 122.17737, 0.00000, 0.00000, 301.10052)
    Object.create(979, 69.12370, 2250.51831, 122.17737, 0.00000, 0.00000, 301.10052)
    Object.create(979, 71.14312, 2242.31958, 122.17737, 0.00000, 0.00000, 268.87259)
    Object.create(979, 70.90059, 2235.35376, 122.17737, 0.00000, 0.00000, 268.87259)
    Object.create(979, 67.88044, 2227.77393, 122.17737, 0.00000, 0.00000, 230.83156)
    Object.create(979, 61.59558, 2221.47437, 122.17737, 0.00000, 0.00000, 220.75778)
    Object.create(979, 9.24136, 2255.10913, 124.20573, 0.00000, 0.00000, 262.15521)
    Object.create(979, 9.26339, 2255.31470, 125.32591, 0.00000, 0.00000, 262.21521)
    Object.create(979, 6.63041, 2237.80835, 126.43900, 0.00000, 0.00000, 262.15521)
    Object.create(979, 6.63041, 2237.80835, 124.20573, 0.00000, 0.00000, 262.15521)
    Object.create(979, 6.63041, 2237.80835, 125.32591, 0.00000, 0.00000, 262.21521)
    Object.create(3852, 10.41502, 2248.14893, 126.99873, 0.00000, 0.00000, 254.84923)
    Object.create(1696, -59.50026, 2259.41602, 117.84450, 0.00000, 0.00000, 75.46391)
    Object.create(19743, -149.47955, 2284.53174, 119.40632, 0.00000, 0.00000, 0.00000)
    Object.create(4165, -224.59308, 2297.00732, 121.28906, 0.00000, 0.00000, 347.61108)
    Object.create(1696, -149.82422, 2280.62329, 121.36243, 0.00000, 0.00000, 97.64449)
    Object.create(1632, -288.32315, 2311.31006, 122.29678, 0.00000, 0.00000, 76.05190)
    Object.create(19743, -297.44073, 2317.48364, 128.95149, 0.00000, 0.00000, 356.66553)
    Object.create(11011, -320.43436, 2319.09692, 134.88226, 0.00000, 0.00000, 70.09898)
    Object.create(1632, -429.48508, 2409.70874, 105.01433, 0.00000, 0.00000, 328.25586)
    Object.create(8171, -417.91156, 2357.05371, 107.45552, 0.00000, 0.00000, 67.77152)
    Object.create(8171, -359.72168, 2492.83936, 67.96587, 0.00000, 0.00000, 254.12608)
    Object.create(1632, -401.36041, 2466.20776, 107.79560,   18.00000, 0.00000, 0.00000)
    Object.create(11011, -407.40292, 2443.89453, 105.19183, 0.00000, 0.00000, 324.55353)
    Object.create(3852, -294.94669, 2468.58398, 66.72882,   20.00000, 0.00000, 69.00000)
    Object.create(11011, -137.77115, 2349.64160, 54.11441, 0.00000, 0.00000, 241.84035)
    Object.create(4165, -44.70510, 2297.37842, 56.71650, 0.00000, -11.00000, 330.00000)
    Object.create(16192, -264.98438, 2387.00781, 64.81250,   356.85840, 0.00000, 3.14159)
    Object.create(19743, 11.01302, 2275.76733, 123.56882, 0.00000, 0.00000, 241.67921)
    Object.create(19743, 10.78756, 2275.50024, 70.46212, 0.00000, 0.00000, 234.92473)
    Object.create(19743, 11.01302, 2275.76733, 75.25454, 0.00000, 0.00000, 241.67921)
    Object.create(19743, 11.01302, 2275.76733, 79.76695, 0.00000, 0.00000, 241.67921)
    Object.create(19743, 11.01302, 2275.76733, 84.24613, 0.00000, 0.00000, 241.67921)
    Object.create(19743, 11.01302, 2275.76733, 84.24613, 0.00000, 0.00000, 241.67921)
    Object.create(19743, 11.01302, 2275.76733, 89.09117, 0.00000, 0.00000, 241.67921)
    Object.create(19743, 11.01302, 2275.76733, 93.95583, 0.00000, 0.00000, 241.67921)
    Object.create(19743, 11.01302, 2275.76733, 98.84447, 0.00000, 0.00000, 241.67921)
    Object.create(19743, 11.01302, 2275.76733, 103.62634, 0.00000, 0.00000, 241.67921)
    Object.create(19743, 11.01302, 2275.76733, 108.65446, 0.00000, 0.00000, 241.67921)
    Object.create(19743, 11.01302, 2275.76733, 108.65446, 0.00000, 0.00000, 241.67921)
    Object.create(19743, 11.01302, 2275.76733, 113.67173, 0.00000, 0.00000, 241.67921)
    Object.create(19743, 11.01302, 2275.76733, 118.59940, 0.00000, 0.00000, 241.67921)
    Object.create(19746, 26.56523, 2271.82031, 126.99297, 0.00000, 0.00000, 246.62535)
    Object.create(19746, 17.23885, 2270.36865, 127.12430, 0.00000, 0.00000, 65.60780)
    Object.create(19746, 12.10795, 2278.18628, 127.19397, 0.00000, 0.00000, 244.83589)
```
Now we're going to start working with transport. Last time we used `add_static_vehicle()`. This time I will tell you about `create_vehicle()`. These functions are basically the same, so `add_static_vehicle()` is the same as `create_vehicle()`, but can also set the respawn time. Also, you cannot set the siren if you use `add_static_vehicle()`.

```python
@on_gamemode_init
def you_function():
    ...
    create_vehicle(562, 427.6521, 2407.5247, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(562, 426.9948, 2329.6785, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(562, 427.1009, 2335.4355, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(562, 427.0287, 2341.6104, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(562, 426.9461, 2347.5674, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(562, 426.9391, 2354.5225, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(562, 426.9360, 2362.7764, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(562, 427.3445, 2379.7361, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(562, 427.2170, 2386.5779, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(562, 427.8880, 2414.8000, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(562, 427.2889, 2431.7991, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(562, 427.2608, 2440.1528, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(562, 427.1466, 2448.0615, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(562, 427.5203, 2456.6636, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(562, 427.5203, 2456.6636, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(562, 427.9155, 2466.2290, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(562, 427.9155, 2466.2290, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(562, 427.9428, 2488.1235, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(562, 428.0578, 2495.2734, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(562, 428.0578, 2495.2734, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(562, 428.2232, 2502.1475, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(562, 428.3003, 2508.8806, 217.7867, 89.7443, -1, -1, 100) 
    create_vehicle(522, 56.2320, 2220.7876, 122.9160, 89.8582, -1, -1, 100) 
    create_vehicle(522, 62.7789, 2253.3777, 122.9160, 142.2508, -1, -1, 100) 
    create_vehicle(522, 63.5295, 2252.2156, 122.9160, 142.2508, -1, -1, 100) 
    create_vehicle(522, 61.9093, 2254.4028, 122.9160, 142.2508, -1, -1, 100) 
    create_vehicle(522, 61.2628, 2255.6284, 122.9160, 142.2508, -1, -1, 100) 
    create_vehicle(522, 59.6798, 2257.6565, 122.9160, 142.2508, -1, -1, 100) 
    create_vehicle(522, 64.8961, 2251.0657, 122.9160, 142.2508, -1, -1, 100) 
    create_vehicle(522, 65.8917, 2249.7156, 122.9160, 142.2508, -1, -1, 100) 
    create_vehicle(522, 67.1378, 2248.7537, 122.9160, 142.2508, -1, -1, 100) 
    create_vehicle(522, 67.7054, 2246.6873, 122.9160, 142.2508, -1, -1, 100) 
    create_vehicle(522, 67.2939, 2244.5217, 122.9160, 142.2508, -1, -1, 100) 
    create_vehicle(522, 67.4780, 2242.7498, 122.9160, 142.2508, -1, -1, 100) 
    create_vehicle(522, 66.9313, 2236.0713, 122.9160, 142.2508, -1, -1, 100) 
    create_vehicle(522, 66.9354, 2233.7954, 122.9160, 142.2508, -1, -1, 100) 
    create_vehicle(522, 66.9371, 2231.6235, 122.9160, 142.2508, -1, -1, 100) 
    create_vehicle(522, 64.5138, 2230.1721, 122.9160, 89.8582, -1, -1, 100) 
    create_vehicle(522, 63.4895, 2228.8477, 122.9160, 89.8582, -1, -1, 100) 
    create_vehicle(522, 62.3311, 2227.3850, 122.9160, 89.8582, -1, -1, 100) 
    create_vehicle(522, 61.1573, 2225.9023, 122.9160, 89.8582, -1, -1, 100) 
    create_vehicle(522, 61.1573, 2225.9023, 122.9160, 89.8582, -1, -1, 100) 
    create_vehicle(522, 60.0457, 2224.5142, 122.9160, 89.8582, -1, -1, 100) 
    create_vehicle(522, 58.9353, 2223.1479, 122.9160, 89.8582, -1, -1, 100) 
    create_vehicle(522, 57.6515, 2221.8889, 122.9160, 89.8582, -1, -1, 100) 
    create_vehicle(522, 57.6515, 2221.8889, 122.9160, 89.8582, -1, -1, 100) 
    create_vehicle(522, 60.6233, 2256.6470, 122.9160, 142.2508, -1, -1, 100) 
    create_vehicle(510, 1968.8058, 1603.8164, 23.2281, 0.0000, -1, -1, 100) 
    create_vehicle(510, 1965.8624, 1644.9558, 22.4234, 0.0000, -1, -1, 100) 
    create_vehicle(510, 1967.2640, 1646.6622, 22.4234, 0.0000, -1, -1, 100) 
    create_vehicle(510, 1974.4401, 1651.7084, 24.6395, 0.0000, -1, -1, 100) 
    create_vehicle(510, 1974.4401, 1651.7084, 24.6395, 0.0000, -1, -1, 100) 
    create_vehicle(510, 1962.3618, 1635.5594, 24.9486, 0.0000, -1, -1, 100) 
    create_vehicle(510, 1964.4153, 1625.5967, 27.1077, 0.0000, -1, -1, 100) 
    create_vehicle(510, 1964.4153, 1625.5967, 27.1077, 0.0000, -1, -1, 100) 
    create_vehicle(510, 1964.6984, 1622.1324, 27.1077, 0.0000, -1, -1, 100) 
    create_vehicle(510, 1964.6984, 1622.1324, 27.1077, 0.0000, -1, -1, 100) 
    create_vehicle(510, 1962.7498, 1615.2906, 27.1077, 0.0000, -1, -1, 100) 
    create_vehicle(487, 365.3704, 2537.3452, 17.1024, 0.0000, -1, -1, 100) 
    create_vehicle(511, 417.7538, 2492.8354, 19.7275, 90.6834, -1, -1, 100) 
    create_vehicle(511, 417.5456, 2514.8608, 19.7275, 90.6834, -1, -1, 100) 
    create_vehicle(447, 377.0984, 2537.8672, 16.9480, 0.0000, -1, -1, 100) 
    create_vehicle(557, 403.6370, 2531.4788, 17.1272, 178.3518, -1, -1, 100) 
    create_vehicle(557, 403.6716, 2545.3940, 17.1272, 178.3518, -1, -1, 100) 
    create_vehicle(557, 403.7107, 2538.3586, 17.1272, 178.3518, -1, -1, 100) 
    create_vehicle(562, 398.7544, 2532.0510, 16.3100, 178.3853, -1, -1, 100) 
    create_vehicle(562, 398.8716, 2546.1721, 16.3100, 178.3853, -1, -1, 100) 
    create_vehicle(562, 398.8713, 2539.0288, 16.3100, 178.3853, -1, -1, 100) 
    create_vehicle(562, 398.8713, 2539.0288, 16.3100, 178.3853, -1, -1, 100) 
    create_vehicle(522, 395.0026, 2530.5288, 16.6647, 91.0660, -1, -1, 100) 
    create_vehicle(522, 395.3730, 2546.9790, 16.6647, 91.0660, -1, -1, 100) 
    create_vehicle(522, 395.3332, 2545.3669, 16.6647, 91.0660, -1, -1, 100) 
    create_vehicle(522, 395.2083, 2543.7024, 16.6647, 91.0660, -1, -1, 100) 
    create_vehicle(522, 395.2083, 2543.7024, 16.6647, 91.0660, -1, -1, 100) 
    create_vehicle(522, 395.1592, 2542.1772, 16.6647, 91.0660, -1, -1, 100) 
    create_vehicle(522, 395.0958, 2540.4219, 16.6647, 91.0660, -1, -1, 100) 
    create_vehicle(522, 395.0709, 2538.6653, 16.6647, 91.0660, -1, -1, 100) 
    create_vehicle(522, 395.0548, 2537.0938, 16.6647, 91.0660, -1, -1, 100) 
    create_vehicle(522, 395.0347, 2535.4409, 16.6647, 91.0660, -1, -1, 100) 
```

Quickly set up a class selection and player spawn. Just take the code from the last lesson and change it a bit.

```python
@Player.on_request_class
def on_player_reques_class(player: Player, classid: int):
    player.set_interior(11)
    player.set_pos((508.7362, -87.4335, 998.9609))
    player.set_facing_angle(0.0)
    player.set_camera_position((508.7362, -83.4335, 998.9609))
    player.set_camera_look_at(508.7362, -87.4335, 998.960)

@Player.on_spawn 
def on_player_spawn(player: Player):
    player.set_interior(0)

```

Let's start working with dialogs. As I said before, the dialogues are a little different from the usual way, but there's nothing heavy about them. Let's start working with them. We will also work with the class [`Dialog()`](https://pysamp.github.io/PySAMP/dialog.html). I will show you several ways to create dialogs, also in this example I will create a `dialog_function()`. We will use the `show()` function to show the dialog to the player There is also a `hide()` function which hides the dialog.

### First way

```python
def dialog_function(player: Player):
    dialog = Dialog.create(0, "First dialog", "Text\nANOTHER TEXT!", "Close", "")
    dialog.show(player)
```

I purposely left the second button blank so that it would not appear.

### Second way

```python
def dialog_function(player: Player):
    Dialog.create(0, "First dialog", "Text\nANOTHER TEXT!", "Close", "").show(player)
```

As you can see, you can experiment with dialogues. A little later I will use the second way in commands. Now I will tell you about `on_response`. First, let's create a function, I will call it `response_function()`.

```python
def response_function(player: Player, response: int, list_item: int, input_text: str):
    if response:
        ...

    else:
        ...
```

As you can see, it's very similar to what we've done before. Let's now create another dialog, which will be of type 1 (text input) and use `on_response`.

```python
def dialog_function(player: Player):
    Dialog.create(1, "Input dialog", "Some text", "Enter", "", on_response=response_function).show(player)
```

Now let's go back to `response_function()` and use `Player.send_client_message()` when we get a response.

```python
def response_function(player: Player, response: int, list_item: int, input_text: str):
    if response:
        Player.send_client_message(-1, f"Your message is: {input_text}")

    else:
        Player.send_client_message(-1, "No response :(")
```

We only have to deal with `list_item`, after which we move on to the commands. Let's create another dialog, it will be type 2 (list)

```python
def dialog_function(player: Player):
    Dialog.create(1, "List dialog", "Option 1\nOption 2\nOption 3", "Enter", "", on_response=response_function).show(player)
```

Notice that `list_item` **starts with 0**

```python
def response_function(player: Player, response: int, list_item: int, input_text: str):
    if response:
        if list_item == 0:
            Player.send_client_message(-1, f"You chose option 1")

        if list_item == 1:
            Player.send_client_message(-1, f"You chose option 2")

        if list_item == 2:
            Player.send_client_message(-1, f"You chose option 3")

    else:
        Player.send_client_message(-1, "No response :(")
```

Let's start working with commands. They're very easy to create, we'll create a couple of simple commands and you'll completely understand how to create them.

To create a command, you need to write `@cmd` and then create a function. I will create a simple command that will teleport the player and sand him a message. After that you will see several ways to create them

```python
@cmd 
def stunt(player: Player):
    player.set_pos((57.9386, 2237.7283, 124.3677))
    player.send_client_message(0x33AA33AA, "You have been successfully teleported to the Stunt Arena.")
```

So this is what a simple command looks like, I think you have already guessed that you can write as many arguments as you want. Let's create a command `/kick` that will kick a player.

```python
@cmd
def kick(player: Player, playerid: int):
    kick(playerid)
```

It's also very simple. Now, what if you want to give a reason? To do that, we will write `*reason`, after which it will be necessary to convert the tuple into a string.

```python
@cmd
def kick(player: Player, playerid: int, *reason):
    reason = " ".join(reason)
    send_client_message(playerid, -1, f"You have been kicked. Reason: {reason}")
    kick(int(playerid))
```

Now let's learn how to work with `aliases`. To do this, let's write a simple command that will give health to the player.

```python
@cmd(aliases=("health", "restoreHealth"))
def heal(player: Player):
    player.set_health(100)
    player.set_armour(100)
    player.send_client_message(0x33AA33AA, "You have been successfully healed.")
```

As you can see, almost nothing changes, but now the command will be called not only on `/heal`, but also on `/health` and so on.

Now let's deal with `use_function_name`, it's probably all clear here, but I'll just say that if `use_function_name=False` then the command will not be called by the function name. You must also use `aliases` if `use_function_name=False`. Let's create a simple command that will issue weapons to the player.

```python
@cmd(aliases=("guns", "weapon"), use_function_name=False)
def weapon_function(player: Player):
    player.give_weapon(24, 500)
    player.give_weapon(26, 500)
    player.give_weapon(27, 500)
    player.give_weapon(34, 500)
    player.give_weapon(46, 1)
    player.send_client_message(0x33AA33AA, "You have successfully obtained weapons.")
```

As you can see, the command will not be called if the player enters `/weapon_function` in the chat.

## Conclusion

In this short tutorial you learned how to create commands, dialogues, and work with game objects. In the next tutorial you'll write a simple TDM mod, where you'll learn more new features, as well as creating a simple registration system on sqlite3
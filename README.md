# Simple Menu Framework for Unreal Engine 4

## What is Simple Menu Framework?

The Simple Menu Framework (SMF) is a framework which allows to implement menus in Unreal Engine game.  
SMF is built on top of UMG and it fixes a lot of issues a developer might encounter while working with it.
It is NOT an already made menu system, rather a backbone on which such system can be implemented, giving the developer
an absolute freedom on how the menu should look and work. 
However, there is an example project with full working menu system, which can be a solid base for a new menu system.

## What issues does it fix?

* Inconsistend behaviour of widgets when using mouse or keyboard or gamepad to navigate. SMF provides widgets which behave the same way when using different preferentials.

* Possibility of losing focus. If the game supports both mouse+keyboard and gamepad it is possible, that the focus will be lost (by moving mouse out of the widget).
  Losing focus might also be possible when switching between screens and popups unproperly. SMF is a guardian that won't allow the game to lose focus on the widget,
  so it always can be navigated using keyboard or gamepad.

* Undefined behaviour when switching between keyboard and gamepad. With SMF you can define how menus should behave when switching between keyboard and gamepad modes.
  You can change a menu layout, show/hide specifig buttons and it will always keep focus on proper widgets without a risk of stucking on unfocused screen.

* Invalid focus in ScrollBox when using nested widgets. Scroll Box works fine only if there are single widgets in it. If you put canvases with widgets inside of a Scroll Box
  it will stop scrolling properly, because it will try to focus on the to widget in the hierarchy only. SMF fixes this and allow Scroll Box to scroll properly no matter the
  widgets structure inside of it.

* Undefined behaviour of user input when entered menu. If player enters menu when having OnPressed event active on a character, the OnReleased event will never occur. SMF clears up
  the user input when entering menus to avoid buggy behavious.

* Keyboard and gamepad navigation in menu is fixed. With SMF you can decide which buttons should be used to navigate, accept and back/escape the menus.

* Sometimes unintuitive order of Events. The order of Events running with UMG can sometimes be counter intuitive and overwhelming in general. SMF gives a new set of Events
  which are easier to grasp, understand and to use.

## What SMF can do?

* It can open screens, children screens on top of each other and it allow to close them in the same order.
* Screens can be opened immediately or with a transition effect. Fade In/Out is a default effect, but it can be reprogrammed to whatever a developer want to.
* Screens are handled as soft references and they resides in a memory only when they are needed.
* Screens can also be handled as popups with a custom data as a result when they are closed.
* It provides a variety of widgets like Button, Checkpox, Selection List, Slider and even Input Key Selector. A developers can also implement their's own widgets.
* It allow to rebind navigation keys, so, for example, player can move through menu using W/A/S/D keys.
* It gives a ready to use solution for displaying pause menu (by pressing back button, defined in SMF settings)
* It provides function to detect if the player uses and changes mouse+keyboard or a gamepad (also what type of gamepad: xbox/ps/switch).
* It provides a rich-text with input key icons that changes when switching between mouse+keyboard and a different types of gamepads.
* It guarantees that focus will never be lost on a widget between switching screens, input periferials and during overall menu usage.
* It gives information about every aspect of the menu screen and widget state developer will ever need
* It provides a set of events useful when implementing a menu (with easier to understand flow than original UMG)

## Why use SMF instead of other menu libraries?

SMF gives tools to implement a menu system tailored specifically for a game made by a developer.
It requires minimal ingerention in the project and it doesn't impose a way the game should be made. 
Every core mechanic is implemented in C++, which makes it very performant and easy to update.

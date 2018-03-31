This workshop covers the basics of creating a simple Virtual Reality application with [Unity](https://store.unity.com/) and [VRTK](https://vrtoolkit.readme.io/).

We will go over how to run SteamVR, import SteamVR and VRTK packages, and use the Vive prefab.

And we will build a basic scene with objects to interact with.

### Run SteamVR
 - Open the Steam application. Click on the **VR button** on top right. This initializes SteamVR environment.

 - Check the status of the light stations, controllers and headsets. Everything should be in green.

 - Run a **room setup** to customize and calibrate the physical space you will experience VR in.

 <img src="https://github.com/mingwho/workshops/blob/master/VRTK_workshop/images/1SteamVR.png" alt="alt text" height="200"><img src="https://github.com/mingwho/workshops/blob/master/VRTK_workshop/images/2RoomSetup.png" alt="alt text" height="200">

### Import packages in Unity
 - Import **SteamVR package**

    - Open the Asset Store (`Window > Asset Store`) and search for **SteamVR**

    - Click **Import**. Once download is finished, click **Import** on the pop up window.

    - Now you should have a **SteamVR** folder under your **Assets** folder
    
    <img src="https://github.com/mingwho/workshops/blob/master/VRTK_workshop/images/3SteamVRPackage.png" alt="alt text" height="300">
 
 - Import **VRTK package**
    
    - Similarly, open the Asset Store (`Window > Asset Store`) and search for **VRTK**
   
    - Click **Import**. Once download is finished, click **Import** on the pop up window. 

    - Now you should have a **VRTK** folder under your **Assets** folder
    
    <img src="https://github.com/mingwho/workshops/blob/master/VRTK_workshop/images/4VRTKPackage.png" alt="alt text" height="300">

### Create a basic scene in Unity
 - Create a new Scene
    - **What is a scene?** Scenes contain the environments and menus of your game. Think of each unique Scene file as a unique level.
    - Create a scene: `File > New Scene`
 - Create Game Objects
    - **What is a GameObject?** GameObjects are the fundamental objects in Unity that represent characters, props and scenery. They do not accomplish much in themselves but they act as containers for Components, which implement the real functionality.
    - Create a plane: In Hierarchy `right click > 3D Object > Plane`
    - Create a sphere: In Hierarchy `right click > 3D Object > Sphere`
    <img src="https://github.com/mingwho/workshops/blob/master/VRTK_workshop/images/5CreatePlane.png" alt="alt text" height="300">


### Set up Vive prefabs and VRTK scripts
 - **What is a prefab?** Prefabs allow you to store a GameObject object complete with components and properties.
 - **What is a script?** Scripts allow you to trigger game events, modify Component properties over time and respond to user input in any way you like.
 - How to use VRTK with SteamVR prefab?
    - Create a new empty GameObject: In Hierarchy `right click > Create Empty`. We can rename it to be `VRTK_SDK Manager`.
    - Search for `VRTK_SDKManager.cs` script. Drag this script onto the `VRTK_SDK Manager` GameObject we just created (See image below)
    - Create another new empty GameObject as child: Select the GameObject `VRTK_SDK Manager` and `right click > Create Empty`.
    - For convenience we rename this GameObject to be `VRTK_SDK Setup`
    - Search for `VRTK_SDKSetup.cs` script and add this script to `VRTK_SDK Setup` GameObejct (See image below)
    - Change Quick Select option to `SteamVR` (Or `Simulator` if you are using a simulator) (See image below)
    - Search for `CameraRig` prefab and add this prefab to SteamVR
    - Search for `SteamVR` prefab and add this prefab to SteamVR
    - Select GameObject `VRTK_SDK Setup` and click `Populate Now` under `Object References` (See image below)
 
    <img src="https://github.com/mingwho/workshops/blob/master/VRTK_workshop/images/6VRTK_SDKManager.png" alt="alt text" height="200">
    <img src="https://github.com/mingwho/workshops/blob/master/VRTK_workshop/images/7VRTK_SDKSetup.png" alt="alt text" height="200">
    <img src="https://github.com/mingwho/workshops/blob/master/VRTK_workshop/images/8QuickSelect.png" alt="alt text" height="200">
 
 
### How to interact with gameObjects using Vive controllers?
 - Add scripts to the GameObjects to make them interactable. 
    - Select the GameObject you want to interact with.
    - `Window > VRTK > Set interactable object`
 - Add scripts to the controllers to allow touch and grab functions
    - Under `CameraRig` select **both controllers**. Click `Add Component` in inspector window.
    - Search for `VRTK_ControllerEvents` script and add it
    - Search for `VRTK_InteractGrab` script and add it
    - Search for `VRTK_InteractTouch` script and add it
    <img src="https://github.com/mingwho/workshops/blob/master/VRTK_workshop/images/9TwoControllers.png" alt="alt text" height="200">
    
    
 - Now you should be able to grab and throw away the existing sphere (or any GameObejct you made) with the two controllers.

### What else can I do?
  - Teleport to move around in the space
  - Instantiate GameObjects at run time
  - Make aesthetic changes: apply material, texture to GameObjects
  - Add lighting

# Development Documentation
## Required Software
### [Microsoft Visual Studio 2019](https://visualstudio.microsoft.com/downloads/)
- Within the install instructions, be sure to specifically install Xamarin as shown in [these instructions](https://docs.microsoft.com/en-us/xamarin/get-started/installation/windows)
- An Android device (Pixel 2 Pie 9.0) emulator must be installed into Visual Studio and optionally an iOS phone as well (if running on an Apple Device)
	- This is done by going to the run code dropdown and going to Android Device Manager to install an Android Device
### [Android SDK](https://developer.android.com/studio)
## Development Environment
### Cloning the code
- Follow [these instruction](https://support.atlassian.com/bitbucket-cloud/docs/clone-a-repository/) to make a local clone of the repo. Alternatively the code can be [cloned through Visual Studio 2019](https://docs.microsoft.com/en-us/visualstudio/get-started/tutorial-open-project-from-repo?view=vs-2019)
### Project Structure Overview
 - TrustAdminApp
	 - This is the main project location. This is where shared code between iOS and Android (according to Xamarin) is run and compiled into the Android and iOS versions respectively 
- TrustAdminApp.Android
	 - This is where the Android version of the application resides. Most of the functionality is drawn from the main project.
- TrustAdminApp.iOS
	 - This is where the iOS version of the application resides. Most of the functionality is drawn from the main project
### Main Application Structure
- Models
	- This is where our Models will go according to the [Model, View, ViewModel structure](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93viewmodel)
- Services
	- This is where Services for the application will be handled and stored
- ViewModels
	- This contains a View Model for every page along with a BaseViewModel which gives general structure to the other ViewModels
- Views
	- This is where the Main Views are written and stored for the application
- App.xaml
	- This is the main file of the application. It sets the default styling information for the application along with starting the application by running the AppShell.xaml
- AppShell.xaml
	- This handles the main hierarchy and navigation for the application via creation of the Taskbar
### Testing Your Environment
- To test if your environment is working, you should click the run button in visual studio, using your Android Emulator
- You should see (after the environment is built and running) a phone emulator with a log in page Use your Cheetah login information to log in and continue
-  You should then come to a blank page and four tabs at the bottom. You should be able to click through the different tabs to then see 2 blank pages and a Settings page along with an Accounts page
- The Settings page should have some options on it while the Accounts Page should show some accounts for the logged in user
- If everything worked, your environment is setup correctly
# Development Documentation
## Required Software
### [Microsoft Visual Studio 2019](https://visualstudio.microsoft.com/downloads/)
- Within the install instructions, be sure to specifically install Xamarin as shown in [these instructions](https://docs.microsoft.com/en-us/xamarin/get-started/installation/windows)
- An Android device (Pixel 2 Pie 9.0) emulator must be installed into Visual Studio and optionally an iOS phone as well (if running on an Apple Device)
	- This is done by going to the run code dropdown and going to Android Device Manager to install an Android Device
### [Android SDK](https://developer.android.com/studio)
### [XCode 12.1](https://developer.apple.com/xcode/)
 - This is the development information for iOS development in the situation that the developer is able to build and deploy code for iOS (requires an Apple Computer and publishing rights)
### ACS SDK
- This is an internal SDK provided to us for Cheetah API calls and communication with internal systems.
- To set this up, after gaining access to the SDK, you can follow [this guide](https://docs.microsoft.com/en-us/nuget/quickstart/install-and-use-a-package-in-visual-studio) to setup the package in Visual Studio
## Development Environment
### Cloning the code
- Follow [these instruction](https://support.atlassian.com/bitbucket-cloud/docs/clone-a-repository/) to make a local clone of the repo. Alternatively the code can be [cloned through Visual Studio 2019](https://docs.microsoft.com/en-us/visualstudio/get-started/tutorial-open-project-from-repo?view=vs-2019)
### Visual Studio Settings
- Disable Parallel project builds
	- On Windows, this is accessed through Tools > Options > Project and Solutions > Build and Run | Set Maxiumum number of parallel project builds to 1
	- On MAC OS/OS X, this is accessed through Visual Studio > Preferences > Build | Disable parallel project builds
### Project Structure Overview
 - TrustAdminApp
	 - This is the main project location. This is where shared code between iOS and Android (according to Xamarin) is run and compiled into the Android and iOS versions respectively 
- TrustAdminApp.Android
	 - This is where the Android version of the application resides. Most of the functionality is drawn from the main project.
- TrustAdminApp.iOS
	 - This is where the iOS version of the application resides. Most of the functionality is drawn from the main project
- UnitTests -> TrustAdminAppTests
	- This is where the automatic tests are written and stored.
- UITests
	- This is where automated UI tests are located. to work, the build mode "UIDebug" must be used
### Main Application Structure
- Models
	- This is where our Models go according to the [Model, View, ViewModel structure](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93viewmodel)
- Services
	- This is where Services for the application are handled and stored
- ViewModels
	- This contains a View Model for every page along with a BaseViewModel which gives general structure to the other ViewModels
- Views
	- This is where the Main Views are written and stored for the application
- App.xaml
	- This is the main file of the application. It sets the default styling information for the application along with starting the application by running the AppShell.xaml
- AppShell.xaml
	- This handles the main hierarchy and navigation for the application via creation of the Taskbar and the main Login Page
### Testing Your Environment
- Automated testing
	- Drop down the folder in the Solution Explorer Labeled "UnitTests"
	- Right click TrustAdminAppTests and build the project
	- After the build is complete, Right click the TrustAdminAppTests and click the "Run Tests" option.
	- This should open a Test Explorerer and all tests should pass
	- If it fails, it's because the IDE is configured to run buid processes in parellel, which will cause build issues. To disable parellel builds for Windows Visual Studio, select Tools > Options > Projects and Solutions > Build and Run > Set maximum number of parallel project builds to 1. For Mac, click Visual studio preferences, under Projects select Build, then uncheck `Enable parallel build of projects`.
		- After that fix, Clean all projects and rebuild all projects
- Testing your Emulator
	- To test if your environment is working, you should click the run button in visual studio, using your Android Emulator
	- You should see (after the environment is built and running) a phone emulator with a log in page Use your Cheetah login information to log in and continue
	-  You should then come to a blank page and four tabs at the bottom. You should be able to click through the different tabs to then see 2 blank pages and a Settings page along with an Accounts page
	- The Settings page should have a logout button, and the Accounts Page should show some accounts for the logged in user
	- If everything worked, your environment is setup correctly
- UI Testing
	- To run UI tests, you should begin by changing your build mode to "UIDebug"
	- Then build and deploy the app.
	- After that, keep the emulator open or open the emulator
	- Then run the UI tests through the Test Explorer.
	- This build environment can also be used for some basic offline testing

### Push Notifications
- Push notifications are a multitier architecture feature that can be built between Xamarin, Azure, and FireBase. Here is some [Microsoft documentation](https://docs.microsoft.com/en-us/azure/developer/mobile-apps/notification-hubs-backend-service-xamarin-forms) for building out this service. 
	- To avoid bloatware and excessive app sizes, we ommitted this feature because of lack of resources and access to backend company services. Accutech is aware of this update. 

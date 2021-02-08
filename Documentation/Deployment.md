# Deployment Documentation
## Technical requirements
Typically, when deploying a piece of software, there is a server/location where 
the DevOps part of the team would setup for a final destination for the production stage
of the software. 

The Trust Admin App is a `Xamarin` application written for 
`iOS` and `Android` devices and thus it's deployment route is different. 
There isn't a specific server configuration because the software is 
specifically written for mobile phones. 

The steps required for production deployment and future releases of
the Trust Admin App are well-documented in Microsoft's documentation for Xamarin. 
For ease of reading and as to not clutter this deployment documentation, here is the 
link to Microsoft's documentation for building, signing, and scheduling a build for a 
release on `iOS` and `Android`. 

[Publishing Xamarin.iOS apps to the App Store](https://docs.microsoft.com/en-us/xamarin/ios/deploy-test/app-distribution/app-store-distribution/publishing-to-the-app-store?tabs=macos)

[Publishing Xamarin.Android apps to Google Play](https://docs.microsoft.com/en-us/xamarin/ios/deploy-test/app-distribution/app-store-distribution/publishing-to-the-app-store?tabs=macos)

This app may not be published directly to the `App Store` for the public to use and could be meant only for in-house use. 
For this reason, here is the deployment route for direct deployment for `iOS`.

[Direct publishing Xamarin.iOS apps to iPhone](https://docs.microsoft.com/en-us/xamarin/ios/deploy-test/app-distribution/app-store-distribution/publishing-to-the-app-store?tabs=macos)

For Android direct deployment:
- Just set the solution to Release mode by right clicking your `Android` Main project > Properties > Android Options > Configuration > Release.
- Right Click your `Android` Main Project -> Export Android Package(.apk) on OSX, and `Android` Main project > Archive for Windows.
- Sign the APK in the Archive Manager using an Ad Hoc keystore or a Google Play keystore.
- Go to the bin\release Folder, you could find your app in apk format. Use application with Signed extension(Signed.apk)
- Install the apk on your device.

## Testing
- There is a second project in the main project called TrustAdminAppTests and it contains all the unit tests that cover the main project's functionaltiy. During development, building and running all the projects is a one click action in the IDE, but if an engineer wants to compile and run these from the command line, the step-by-step process is desribed in [Microsoft's MSBuild documentation](https://docs.microsoft.com/en-us/visualstudio/msbuild/walkthrough-using-msbuild?view=vs-2019)
## Troubleshooting
Assuming the development environment is set up correctly via the [Development Documentation](Development.md), if at any time
the deployment process fails, try:
1. Cleaning the project
2. Rebuilding the project
3. Verify that you have the latest version of iOS and Android installed on the target device. 
- `iOS` = `13.5` or greater
- `Android` = `Pie 9.0` or greater

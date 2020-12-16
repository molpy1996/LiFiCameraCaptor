==================================================================================================	       

				README LIFI CAMERA CAPTOR

==================================================================================================

In the Lifi Camera Captor Project :

	- I imported the Lifi library by placing camera-lifisdk-android-v1.0.0.aar
	in the //app/libs/directory 

	- I added the user permission in AndroidManifest.xml for CAMERA, READ_EXTERNAL_STORAGE 
	& WRITE_EXTERNAL_STORAGE to be able to use the camera with the Lifi functionnality
	
	- In the app-leve build.gradle file I added the dependency to the .aar file 
	placed in //app/libs/directory

	- In the global View I created a button to request user permission
	a Toast message is displayed at the start of the app for the user to know if the app has
	the permission to use Camera etc..
	If the user click on the Button but the permission has already been granted, a Toast
	message tell him that.

	- In the global View I also added a Textview to display the binary tag send by the light
	
	- In the onStart function, a LifiSdkManager object is created and instantiated with the
	current context of the app and the LifiCallback, and then we start the LifiSdkManager 
	object

	- Then 2 abstract functions are overridden (onLiFiPositionUpdate & onLiFiErrorUpdate)
	they both send something to the TextView to display. The 1st one sends the processed tag
	the second one sends an error message if it's necessary

	- In the onStop function we stop the LifiSdkManager object if it's been started, so that
	everything go back to normal.

==> when we run the code on a real Android Device, then place it under the light that sends the 
    good Lifi tag, the app displays '00001001' in the TextView !!

==================================================================================================
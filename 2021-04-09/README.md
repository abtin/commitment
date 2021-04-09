## ideas of the day

- I took a look at what3words yesterday. Interesting concepts but other than making a physical location easy to remember I'm still not sure what I would get on top of a service like google Location services.



## Today I learned (TIL)

I was testing a python code, which I deploy to GCP as cloudrun, to write to Firebase Firestore. While testing in <u>local</u> I was getting the confusing error of: `'invalid_grant: Token has been expired or revoked.'`. It's not unusual for GCP errors to be confusing, but in this case the reason for the error was trying to invoke a document.get() command from my laptop. The code worked when I deployed it to google cloud. The reason for the error was the firestore was configured as native and therefore a local client going to cloud was similar to a browser access, which was not permitted. 

It would have been less confusing if I got the error when initializing my client i.e. the call to`firebase_admin.initialize_app()`.  

Good luck debugging next issue!
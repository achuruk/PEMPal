# PEMPal
This repository contains the PEMPal application, built in Stanford's Bioengineering Capstone (BIOE141). 

Patients with long COVID experience high symptom burden with no clear treatment options or pathophysiological explanation. Various triggers can lead to post-exertional malaise (PEM) and severe relapse of chronic fatigue syndrome (CFS).<sup>1,2</sup> Of note, day-to-day physiological stressors are a major contributor, which can lead to an aggravation of symptoms lasting 14h to several days.<sup>2</sup> These episodes are particularly challenging to manage because they occur with a time delay, meaning there's no immediate feedback for patients whether they're overexerting themselves *in the moment*.<sup>2</sup> A wearable device to help patients track daily activities and alert as they approach the physical exertion threshold for PEM would help a) patients manage their activity level, and b) correlate ‘fatigue’ with tangible vitals measurements – giving physicians a way to track disease progression over time.

The current application is capable of:
1. storing individual patient information, 
2. querying for real time heart rate data in Apple Health,
3. changing an internal flag when patient self-reports PEM using the Report PEM button, and
4. updating home page UI to reflect the most recent PEM episode

## Application Structure
The PEMPal application is an IOS application with integrations to Apple Health vitals data using [HealthKit](https://developer.apple.com/documentation/healthkit). The current version contains two main pages (Onboarding page, Home page) and two prototype pages (FAQ, Update profile page). These pages are described in more detail below.

This version also has a prototype WatchOS application with a Report PEM button and a Risk description that changes on button press. Integrating an iPhone app with the watch is much more complicated than we initially thought for several reasons: the watch operates off a local HealthStore doesn't always sync data with the overarching HealthStore actively (watch and phone app might access different underlying data), the watch-phone integration requires significantly more work, and if any 3rd party hardware was used to collect non-heart rate data it would sync with the phone HealthStore rather than the watch.

> Since older versions of the Apple Watch don't measure SpO2 and even the Apple Watch 8 doesn't measure blood pressure or respiratory rate (when active), focusing our build on the iOS app means the PEMPal app would be cross-compatible with third party hardware. As long as external hardware syncs with Apple Health, we could measure blood pressure or respiratory rate, sync with Apple Health and the iOS HealthStore, and run our analyses. **These third party devices (and thus more complicated vitals) would not sync to the WatchOS app/watch HealthStore**

Within the scope of the class, we built out majority functionality in the iOS app and decided to retain a basic looks-like prototype for the WatchOS app.

This app was built using Xcode 14.1.0, Swift 5.7 and supports iOS 13 and above.

## Build and Run the Application
You can build and run the application using [Xcode](https://developer.apple.com/xcode/) by opening **PEMPal.1.0.xcodeproj**. Note that if the application is being tested on:

a) An XCode simulator - remember to manually add heart rate data into the Apple Health app in the simulator

b) A physical iPhone - start a workout on your connected Apple Watch, open Apple Health to make sure the watch is actively measuring heart rate data and feeding it to Apple Health. The PEMPal app make take a few seconds to update the HR value, try opening/closing the app (without ending the app process).

## Onboarding Page (Initialize View)
The <code>Onboarding Page</code> contains

Reason why we collect information is because…xyz article correlated with long covid 
Reason why we asked for this information 


## Home Page (Home Page View)

Home page–Showing heart rate etc for important
Justification for button and etc. 
Resets to 0 on button press

## FAQ (Help Page)


## Update Profile (Update Profile Page)
Update profile–nomrally weight and height might change 

## WatchOS Preview


## Dependencies
Xcode  
Swift   
HealthKit

## Authors
Feel free to contact us with any questions about our project!

Contributors names and contact info:  
Tim Wu - theredwuster@gmail.com   
Ian Hall – ihall3877@gmail.com  
Ahmed Yousif – ahmedyasiryousif123@gmail.com  
Andrew Churukian – drewchuruk@me.com  
Youngju Kim – youngju2001@gmail.com  

# Version History
1.0 - Initial Release of application tracking only heart rate measurements using the HealthKit AnchoredObjectQuery. Current deployment targets are for WatchOS 9.1 and iOS 16.2.

# Acknowledgments
Huge thanks to Paul Schmiedmayer, Oliver Aalami, and the [Stanford Biodesign Digital Health Group (BDHG)](https://biodesign.stanford.edu/programs/stanford-courses/biodesign-for-digital-health.html) teaching staff for their help and guidance throughout the course. This course also draws inspiration from the [Stanford BDHG Cardinal Kit Template](https://github.com/StanfordBDHG/CardinalKitTemplateApplication/tree/main/TemplateApplication) although the existing application and all associated functionality is built from scratch.

# References
1. Mackay, A. Front. Neurol. 2021 Aug; 12: 701419. [PubMed](https://pubmed.ncbi.nlm.nih.gov/34408721/)
2. Kedor, et al. Nature Comm. 2022 Aug; 13: 5104. [Nature](https://www.nature.com/articles/s41467-022-32507-6)
3. 
4. 
5. 


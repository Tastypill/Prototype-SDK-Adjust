Release Notes :

v1.0.1
    - Initial Release.
v1.0.2
    - Fixed Build issues.

    - SDK Versions :
        - Facebook SDK v9.2.0
        - Game Analytics SDK v6.5.7
        - Adjust SDK v4.29.1
        - Adjust Purchase SDK v1.0.3


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

NOTE :  This SDK Mannager Module Also supports GDPR Consent SDK. Incase you're not using GDPR Consent SDK or not requires,
        You do not need to take any action.  The build-in editor code will handle these automatically.

        Once you add GDPR Consent SDK, SDKManager will Initialize after consent verification. SDKManager code has already
        provisions to handle this thing. you don't need to take any action again.


Basic Settings :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

How to configure :

1.  Import StartUp SDKs unity Package.

2.  Go To Tastypill ~> SDK Manager ~> SDK Settings.

3.  Enter Valid Keys to Game Analytics Settings and Press Apply Settings Button.

4.  Enter Valid Keys to Facebook Settings and Press Apply Settings Button.

5.  Enter Valid Adjust App Tokens for android and iOS.

6.  Go To "Assets ~> Adjust ~> Check iOS 14 Support Status". if disabled, please enable it by Selecting "Assets ~> Adjust ~> Toggle iOS 14 Support Status"

7.  Go To "Assets ~> Adjust ~> Check Post Processing Status". if disabled, please enable it by Selecting "Assets ~> Adjust ~> Toggle Post Processing Status"

8.  Open First scene of game.

9.  Go To Tastypill ~> SDK Manager ~> Create SDK Manager.

10.  Setup Complete.


Game Analytics Additional Settings :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
GameAnalytics need to pass Level Progression events manually. Please use SDKManager script component to report level progression events. Below is example.

    Level Start :
    --------------------------------------------------------
    SDKManager.Instance.OnLevelStartedEvent(int levelIndex);
    --------------------------------------------------------

    Level Complete :
    --------------------------------------------------------
    SDKManager.Instance.OnLevelCompletedEvent(int levelIndex);
    --------------------------------------------------------

    Level Fail :
    --------------------------------------------------------
    SDKManager.Instance.OnLevelFailEvent(int levelIndex);
    --------------------------------------------------------
    
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Adjust Purchase SDK Reporting : 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Adjust Purchase SDK requires Unity IAP Sdk to be integrated within app. please follow below steps to configure and report
IAPs to adjust.

1.  Open SDK Manager Script and fill the "eventToken" values for all eventtoken. these event tokens can be grabbed from
    Adjust's dashboard.
    
2.  Upon successful purchase of IAP please call below method.
    SDKManager.Instance.ValidateIAP(Product product).   
     
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

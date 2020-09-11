Release Notes :

v1.0.0
    - Initial Release.

    - SDK Versions :
        - Facebook SDK v7.21.1
        - Game Analytics SDK v6.3.0
        - Tenjin SDK 1.9.2


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

5.  Enter Valid Tenjin SDK Key.

6.  Open First scene of game.

7.  Go To Tastypill ~> SDK Manager ~> Create SDK Manager.

8.  Setup Complete.


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


IAP Report to Tenjin :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Incase you wish to report IAP to tenjin please follow below steps.

1. Please confirm IAP SDK imported and configured correctly.
2. On each successful IAP Purchase please call below method to report IAP Purchase to tenjin.

    SDKManager.Instance.ReportIAPToTenjin(Product iapProduct);


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

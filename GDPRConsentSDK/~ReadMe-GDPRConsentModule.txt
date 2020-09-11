Release Notes :

v1.0.0
    - Initial Release.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

NOTE :  GDPR Consent SDK works with AppLovin MAX Sdk. Please be sure to import and setup AppLovin Max Sdk
        to active GDPR Consent SDK workflow. However, Consent workflow can be tested on editor and development
        builds by enabling "Force Apply GDPR Consent".


Setup :
1.  Please import GDPR Consent SDK unitypackage to project.

2.  Goto Tastypill ~> GDPR ~> Consent Settings from Menu item and configure settings.
 
3.  Open first (Initial) scene of unity project.

4.  Goto Tastypill ~> GDPR and Select "Create GDPR Consent Manager". This will generate GDPRConsent UI on your scene.
    It contains canvas on root. you can adjust render and sorting order as per your requirements. GDPRConsent UI Can
    be also generated from GameObject ~> Tastypill ~> GDPR ~> Create GDPR Consent Manager Menu option.

5.  Goto Tastypill ~> GDPR and Select "Create Manage Data Button". Manage Data Button used for allowing user to modify
    consent settings anytime. This button will get de-active/disabled automatically if GDPR Consent is not applicable to user.

6.  Please follow demo scene attached for detailed guidelines.

7.  GDPR Consent SDK compiles and execute under "TP_GDPR" scripting define symbol. Though will it be added automatically to player
    settings but verify incase GDPR Consent SDK do not execute. 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

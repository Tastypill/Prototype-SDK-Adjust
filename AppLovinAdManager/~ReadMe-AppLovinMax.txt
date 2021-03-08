Release Notes :

v1.0.1
    - Initial Release.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

NOTE :  AppLovin Max SDK is an ad network to serve ads using mediations. This module works along with AppLovin Max SDK
        To serve ads. please follow below guide to setup app to serve ads with AppLovin Max SDK.


Basic Settings :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

How to configure :

1.  Please import AppLovin Max SDK unitypackage to project. (This includes both Offical MaxSDK and a unitypackage made
    ready to serve ads with Max SDK.)

2.  Go To Tastypill ~> SDK AppLovinMax ~> Settings.

3.  Enter Valid SDK Key, Banner, Interstital and Rewarded Ad Unit Id for both Android and iOS repsctively.

3.  Open first (Initial) scene of unity project.

4.  Go To Tastypill ~> AppLovinMax  ~> Create AppLovin Ad Manager. Alternatively can be done from GameObject ~> Tastypill
    ~> AppLovinMax ~> Create AppLovin Ad Manager.

5.  Go To AppLovin ~> Integration Manager and Install Mediation networks as per your requirements. If you're installing
    Google AdMob Mediation Netork, be sure to apply AppId for both android and iOS on same window.

6.  See the demo scene to see how to serve ads.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

AppLovin SDK will be initialized automatically and will handle loading of ads automatically. You just need to show ads as
per your requirements.
    
Here is some details on how to serve and handle Ads.

    Show Banner Ad :
    --------------------------------------------------------
    AppLovinAdManager.Instance.ShowBanner();
    --------------------------------------------------------

    Hide Banner Ad :
    --------------------------------------------------------
    AppLovinAdManager.Instance.HideBanner();
    --------------------------------------------------------

    Check if interstital Ad Available to show :
    --------------------------------------------------------
    bool interstitialAvailable = AppLovinAdManager.Instance.IsInterstitialAvailable();
    --------------------------------------------------------

    Show Interstitial Ad :
    --------------------------------------------------------
    bool interstitialAvailable = AppLovinAdManager.Instance.IsInterstitialAvailable();

    if(interstitialAvailable) {
        AppLovinAdManager.Instance.ShowInterstitial();
    }

    You can also use inline delegates to handle ad load status. These are optional.
    --------------------------------------------------------
    bool interstitialAvailable = AppLovinAdManager.Instance.IsInterstitialAvailable();

    if(interstitialAvailable) {
        AppLovinAdManager.Instance.ShowInterstitial().OnInterstitialDismissed((adUnitId) => {
            // Do your stuff on interstital close.
        }).OnInterstitialFailedToDisplay((adUnitId, errorcode) => {
            // Do your stuff on interstital failed to display. Normally no action required here.
        });
    }
    --------------------------------------------------------


    Show Rewarded Ad :
    --------------------------------------------------------
    bool rewardedAvailable = AppLovinAdManager.Instance.IsRewardedAvailable();

    if(interstitialAvailable) {
        AppLovinAdManager.Instance.ShowInterstitial();
    }

    You can also use inline delegates to handle ad load status. These are optional.
    --------------------------------------------------------
     bool rewardedAvailable = AppLovinAdManager.Instance.IsRewardedAvailable();

    if(rewardedAvailable) {
        AppLovinAdManager.Instance.ShowRewarded().OnRewardedAdReceivedReward((adUnitId, reward) => {
            // Action to be taken on reward received. You can process ad reward here like give coins, rescue etc.
        }).OnRewardedAdDismissed((adUnitId) => {
            // Action to be taken on ad dismissed.
        }).OnRewardedAdFailedToDisplay((adUnitId, errorCode) => {
            // Do your stuff on rewarded failed to display. Normally no action required here.
        });
    }
    --------------------------------------------------------       

    
    For Premium/Ad Free users. If non rewarded ads not needed to show.
    --------------------------------------------------------
    AppLovinAdManager.Instance.SetShouldShowNonRewardedAds(false);

    Passing false means interstitial and banner ads won't be shown anymore. You need to call this method on each launch.
    
        


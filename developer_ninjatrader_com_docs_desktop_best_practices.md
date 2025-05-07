The following are what we suggest for best practices for distribution.

## [Do not deploy NinjaScript Source Files](https://developer.ninjatrader.com/docs/desktop/best_practices\#do-not-deploy-ninjascript-source-files)

If you are a commercial vendor, you should never distribute the NinjaScript .cs source code files even if your IP is contained within an assembly or proprietary DLL. Source code files are editable by users and can result in unnecessary support issues.

## [Naming Conventions](https://developer.ninjatrader.com/docs/desktop/best_practices\#naming-conventions)

Please use consistent naming convention with your indicators and strategies. We suggest adding a prefix to an indicator name. If your company name is "Hyper" you could name your indicators "HyperTrend" or "HyperOscillator" for example.

In the event that you provide NinjaScript export archives (zip files) as your means of distribution, NinjaTrader will automatically block incompatible scripts from importing so there will be no confusion by the user as to whether they are installing Version 7 or 8 scripts to their NinjaTrader installation. It is advisable to include the NinjaTrader version number in the export archive which will reduce potential support burden. For example, you could name your indicators “MyIndicator\_7.zip” and “MyIndicator\_8.zip”.

## [Clean up your resources](https://developer.ninjatrader.com/docs/desktop/best_practices\#clean-up-your-resources)

Always free up resources such as external windows DLL's or license management related resources. Resources should be freed within the [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) method in State.Terminate. NinjaTrader calls this method at the point at which a script is no longer used.

## [User Authentication Trigger](https://developer.ninjatrader.com/docs/desktop/best_practices\#user-authentication-trigger)

If you use a proprietary user authentication process, ensure that it is triggered within the [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) method in State.SetDefaults. This ensures that users are not forced to endure unnecessary delays on NinjaTrader start up or dialog windows that display available indicators and strategies as the windows are loaded. NinjaTrader, LLC provides a free licensing service for qualified 3rd party developers. For more information on this free service, contact your NinjaTrader Business Development representative.

## [User Authentication Check State](https://developer.ninjatrader.com/docs/desktop/best_practices\#user-authentication-check-state)

A license check should only be performed once and maintain its check state.

## [User Authentication Time Out](https://developer.ninjatrader.com/docs/desktop/best_practices\#user-authentication-time-out)

A license check should have a time out in case of internet issues, to enhance performance in this case.

## [Custom Installer](https://developer.ninjatrader.com/docs/desktop/best_practices\#custom-installer)

If you provide a custom installer, the installer should not overwrite any NinjaTrader deployed files, and you should provide an uninstall option which removes all installed files.

It is also preferred that you provide one installer that provides the user the option to install either a version 7 or version 8 compatible version of your product(s). Ensure that you only copy the correct files to the correct NinjaTrader installation folders since if you don’t it is possible that it could cause compile issues for the customer and it will be extremely difficult for all involved to isolate the cause.

These are the following folder names:

- `Documents\NinjaTrader 7\bin\Custom`
- `Documents\NinjaTrader 8\bin\Custom`

## [Test on Legacy Operating Systems](https://developer.ninjatrader.com/docs/desktop/best_practices\#test-on-legacy-operating-systems)

Some NinjaTrader customers run on older Operating Systems (such as Windows 7) and you should make sure that your indicators, custom installers and external DLLs (if any are used) properly run on these legacy operating systems.

## [Expose Indicator States](https://developer.ninjatrader.com/docs/desktop/best_practices\#expose-indicator-states)

If your proprietary indicator acts as a trend state (green bars are bullish, red bearish) its good practice to expose the indicators's state so that consumers of your indicators can use them within their own custom indicator or strategy.

The following are what we suggest for best practices for distribution.

## [Do not deploy NinjaScript Source Files](https://developer.ninjatrader.com/docs/desktop/best_practices\#do-not-deploy-ninjascript-source-files)

If you are a commercial vendor, you should never distribute the NinjaScript .cs source code files even if your IP is contained within an assembly or proprietary DLL. Source code files are editable by users and can result in unnecessary support issues.

## [Naming Conventions](https://developer.ninjatrader.com/docs/desktop/best_practices\#naming-conventions)

Please use consistent naming convention with your indicators and strategies. We suggest adding a prefix to an indicator name. If your company name is "Hyper" you could name your indicators "HyperTrend" or "HyperOscillator" for example.

In the event that you provide NinjaScript export archives (zip files) as your means of distribution, NinjaTrader will automatically block incompatible scripts from importing so there will be no confusion by the user as to whether they are installing Version 7 or 8 scripts to their NinjaTrader installation. It is advisable to include the NinjaTrader version number in the export archive which will reduce potential support burden. For example, you could name your indicators “MyIndicator\_7.zip” and “MyIndicator\_8.zip”.

## [Clean up your resources](https://developer.ninjatrader.com/docs/desktop/best_practices\#clean-up-your-resources)

Always free up resources such as external windows DLL's or license management related resources. Resources should be freed within the [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) method in State.Terminate. NinjaTrader calls this method at the point at which a script is no longer used.

## [User Authentication Trigger](https://developer.ninjatrader.com/docs/desktop/best_practices\#user-authentication-trigger)

If you use a proprietary user authentication process, ensure that it is triggered within the [OnStateChange()](https://developer.ninjatrader.com/docs/desktop/onstatechange) method in State.SetDefaults. This ensures that users are not forced to endure unnecessary delays on NinjaTrader start up or dialog windows that display available indicators and strategies as the windows are loaded. NinjaTrader, LLC provides a free licensing service for qualified 3rd party developers. For more information on this free service, contact your NinjaTrader Business Development representative.

## [User Authentication Check State](https://developer.ninjatrader.com/docs/desktop/best_practices\#user-authentication-check-state)

A license check should only be performed once and maintain its check state.

## [User Authentication Time Out](https://developer.ninjatrader.com/docs/desktop/best_practices\#user-authentication-time-out)

A license check should have a time out in case of internet issues, to enhance performance in this case.

## [Custom Installer](https://developer.ninjatrader.com/docs/desktop/best_practices\#custom-installer)

If you provide a custom installer, the installer should not overwrite any NinjaTrader deployed files, and you should provide an uninstall option which removes all installed files.

It is also preferred that you provide one installer that provides the user the option to install either a version 7 or version 8 compatible version of your product(s). Ensure that you only copy the correct files to the correct NinjaTrader installation folders since if you don’t it is possible that it could cause compile issues for the customer and it will be extremely difficult for all involved to isolate the cause.

These are the following folder names:

- `Documents\NinjaTrader 7\bin\Custom`
- `Documents\NinjaTrader 8\bin\Custom`

## [Test on Legacy Operating Systems](https://developer.ninjatrader.com/docs/desktop/best_practices\#test-on-legacy-operating-systems)

Some NinjaTrader customers run on older Operating Systems (such as Windows 7) and you should make sure that your indicators, custom installers and external DLLs (if any are used) properly run on these legacy operating systems.

## [Expose Indicator States](https://developer.ninjatrader.com/docs/desktop/best_practices\#expose-indicator-states)

If your proprietary indicator acts as a trend state (green bars are bullish, red bearish) its good practice to expose the indicators's state so that consumers of your indicators can use them within their own custom indicator or strategy.
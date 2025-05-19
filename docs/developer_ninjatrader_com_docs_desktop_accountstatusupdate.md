## [Definition](https://developer.ninjatrader.com/docs/desktop/accountstatusupdate\#definition)

AccountStatusUpdate can be used for subscribing to account status events from all accounts.

## Note

Remember to unsubscribe if you are no longer using the subscription.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/accountstatusupdate\#syntax)

`AccountStatusUpdate`

## [Examples](https://developer.ninjatrader.com/docs/desktop/accountstatusupdate\#examples)

```jsx-150469391 csharp
/* Example of subscribing/unsubscribing to account status update events from an Add On. The concept can be carried over
to any NinjaScript object you may be working on. */
public class MyAddOnTab : NTTabPage
{
     public MyAddOnTab()
     {
          // Subscribe to account status updates
          Account.AccountStatusUpdate += OnAccountStatusUpdate;
     }

     // This method is fired on any status change of any account
     private void OnAccountStatusUpdate(object sender, AccountStatusEventArgs e)
     {
          // Output the account name and status
          NinjaTrader.Code.Output.Process(string.Format("Account: {0} Status: {1}",
               e.Account.Name, e.Status), PrintTo.OutputTab1);
     }

     // Called by TabControl when tab is being removed or window is closed
     public override void Cleanup()
     {
          // Make sure to unsubscribe to the account status subscription
          Account.AccountStatusUpdate -= OnAccountStatusUpdate;
     }

     // Other required NTTabPage members left out for demonstration purposes. Be sure to add them in your own code.
}
```

## [Definition](https://developer.ninjatrader.com/docs/desktop/accountstatusupdate\#definition)

AccountStatusUpdate can be used for subscribing to account status events from all accounts.

## Note

Remember to unsubscribe if you are no longer using the subscription.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/accountstatusupdate\#syntax)

`AccountStatusUpdate`

## [Examples](https://developer.ninjatrader.com/docs/desktop/accountstatusupdate\#examples)

```jsx-150469391 csharp
/* Example of subscribing/unsubscribing to account status update events from an Add On. The concept can be carried over
to any NinjaScript object you may be working on. */
public class MyAddOnTab : NTTabPage
{
     public MyAddOnTab()
     {
          // Subscribe to account status updates
          Account.AccountStatusUpdate += OnAccountStatusUpdate;
     }

     // This method is fired on any status change of any account
     private void OnAccountStatusUpdate(object sender, AccountStatusEventArgs e)
     {
          // Output the account name and status
          NinjaTrader.Code.Output.Process(string.Format("Account: {0} Status: {1}",
               e.Account.Name, e.Status), PrintTo.OutputTab1);
     }

     // Called by TabControl when tab is being removed or window is closed
     public override void Cleanup()
     {
          // Make sure to unsubscribe to the account status subscription
          Account.AccountStatusUpdate -= OnAccountStatusUpdate;
     }

     // Other required NTTabPage members left out for demonstration purposes. Be sure to add them in your own code.
}
```
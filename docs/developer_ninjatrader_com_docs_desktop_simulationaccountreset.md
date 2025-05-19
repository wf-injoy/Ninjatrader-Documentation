## [Definition](https://developer.ninjatrader.com/docs/desktop/simulationaccountreset\#definition)

**SimulationAccountReset** can be used for subscribing to simulation account reset events. These resets occur whenever the user manually resets an account as well as when the user rewinds/fast forwards the Playback connection. When the reset occurs due to changes to the Playback connection it is important to recreate bar requests.

## Note

Remember to unsubscribe if you are no longer using the subscription.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/simulationaccountreset\#syntax)

`SimulationAccountReset`

## [Examples](https://developer.ninjatrader.com/docs/desktop/simulationaccountreset\#examples)

```jsx-150469391 csharp
/* Example of subscribing/unsubscribing to sim account reset events from an Add On. The concept can be carried over to any NinjaScript object you may be working on. */
public class MyAddOnTab : NTTabPage
{
     public MyAddOnTab()
     {
          // Subscribe to sim account resets
          Account.SimulationAccountReset += OnSimulationAccountReset;
     }

     /* This method is fired on sim account reset events. It is important to recreate bar requests
     after a reset on the Playback connection */
     private void OnSimulationAccountReset(object sender, EventArgs e)
     {
          Account simAccount = (sender as Account);

          // If the account was reset due to a rewind/fast forward of the Playback connection
          if (simAccount != null && simAccount.Provider == Provider.Playback)
          {
               // Redo our bars requests here
          }
     }

     // Called by **TabControl** when tab is being removed or window is closed
     public override void Cleanup()
     {
          // Make sure to unsubscribe to the simulation account reset subscription
          Account.SimulationAccountReset -= OnSimulationAccountReset;
     }

     // Other required **NTTabPage** members left out for demonstration purposes. Be sure to add them in your own code.
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/simulationaccountreset\#definition)

**SimulationAccountReset** can be used for subscribing to simulation account reset events. These resets occur whenever the user manually resets an account as well as when the user rewinds/fast forwards the Playback connection. When the reset occurs due to changes to the Playback connection it is important to recreate bar requests.

## Note

Remember to unsubscribe if you are no longer using the subscription.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/simulationaccountreset\#syntax)

`SimulationAccountReset`

## [Examples](https://developer.ninjatrader.com/docs/desktop/simulationaccountreset\#examples)

```jsx-150469391 csharp
/* Example of subscribing/unsubscribing to sim account reset events from an Add On. The concept can be carried over to any NinjaScript object you may be working on. */
public class MyAddOnTab : NTTabPage
{
     public MyAddOnTab()
     {
          // Subscribe to sim account resets
          Account.SimulationAccountReset += OnSimulationAccountReset;
     }

     /* This method is fired on sim account reset events. It is important to recreate bar requests
     after a reset on the Playback connection */
     private void OnSimulationAccountReset(object sender, EventArgs e)
     {
          Account simAccount = (sender as Account);

          // If the account was reset due to a rewind/fast forward of the Playback connection
          if (simAccount != null && simAccount.Provider == Provider.Playback)
          {
               // Redo our bars requests here
          }
     }

     // Called by **TabControl** when tab is being removed or window is closed
     public override void Cleanup()
     {
          // Make sure to unsubscribe to the simulation account reset subscription
          Account.SimulationAccountReset -= OnSimulationAccountReset;
     }

     // Other required **NTTabPage** members left out for demonstration purposes. Be sure to add them in your own code.
}

```
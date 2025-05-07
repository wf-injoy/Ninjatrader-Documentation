## [Definition](https://developer.ninjatrader.com/docs/desktop/newssubscription\#definition)

**NewsSubscription** can be used for subscribing to News events.

## Note

Remember to unsubscribe if you are no longer using the subscription.

## [Properties](https://developer.ninjatrader.com/docs/desktop/newssubscription\#properties)

| Update | Event handler for subscribing/unsubscribing to market depth events |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/newssubscription\#syntax)

`NewsSubscription`

## [Examples](https://developer.ninjatrader.com/docs/desktop/newssubscription\#examples)

```jsx-150469391 csharp
/* Example of subscribing/unsubscribing to news from an Add On. The concept can be carried over
to any NinjaScript object you may be working on. */
public class MyAddOnTab : NTTabPage
{
     private NewsSubscription newsSubscription;
     private NewsItems       newsItems;

     public MyAddOnTab()
     {
          // Subscribe to news
          newsSubscription         = new NewsSubscription();
          newsSubscription.Update += OnNews;
          newsItems               = new NewsItems(10);
     }

     // This method is fired as new News events come in. Old News events are not provided when you subscribe.
     private void OnNews(object sender, NewsEventArgs e)
     {
          // Print the headline of the news
          NinjaTrader.Code.Output.Process(string.Format("ID: {0} News Provider: {1} Headline: {2}",
               e.Id,
               e.NewsProvider,
               e.Headline), PrintTo.OutputTab1);

          // Maintain the news items
          newsItems.Update(e);
     }

     // Called by TabControl when tab is being removed or window is closed
     public override void Cleanup()
     {
          // Make sure to unsubscribe to the News subscription
          if (newsSubscription != null)
               newsSubscription.Update -= OnNews;
     }

     // Other required NTTabPage members left out for demonstration purposes. Be sure to add them in your own code.
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/newssubscription\#definition)

**NewsSubscription** can be used for subscribing to News events.

## Note

Remember to unsubscribe if you are no longer using the subscription.

## [Properties](https://developer.ninjatrader.com/docs/desktop/newssubscription\#properties)

| Update | Event handler for subscribing/unsubscribing to market depth events |

## [Syntax](https://developer.ninjatrader.com/docs/desktop/newssubscription\#syntax)

`NewsSubscription`

## [Examples](https://developer.ninjatrader.com/docs/desktop/newssubscription\#examples)

```jsx-150469391 csharp
/* Example of subscribing/unsubscribing to news from an Add On. The concept can be carried over
to any NinjaScript object you may be working on. */
public class MyAddOnTab : NTTabPage
{
     private NewsSubscription newsSubscription;
     private NewsItems       newsItems;

     public MyAddOnTab()
     {
          // Subscribe to news
          newsSubscription         = new NewsSubscription();
          newsSubscription.Update += OnNews;
          newsItems               = new NewsItems(10);
     }

     // This method is fired as new News events come in. Old News events are not provided when you subscribe.
     private void OnNews(object sender, NewsEventArgs e)
     {
          // Print the headline of the news
          NinjaTrader.Code.Output.Process(string.Format("ID: {0} News Provider: {1} Headline: {2}",
               e.Id,
               e.NewsProvider,
               e.Headline), PrintTo.OutputTab1);

          // Maintain the news items
          newsItems.Update(e);
     }

     // Called by TabControl when tab is being removed or window is closed
     public override void Cleanup()
     {
          // Make sure to unsubscribe to the News subscription
          if (newsSubscription != null)
               newsSubscription.Update -= OnNews;
     }

     // Other required NTTabPage members left out for demonstration purposes. Be sure to add them in your own code.
}

```
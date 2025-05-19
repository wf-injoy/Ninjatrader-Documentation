## [Definition](https://developer.ninjatrader.com/docs/desktop/connection_class\#definition)

The Connection class can be used to monitor connection related events as well as accessing connection related information.

## [Static Connection Class Events and Properties](https://developer.ninjatrader.com/docs/desktop/connection_class\#static-connection-class-events-and-properties)

| Method | Description |
| --- | --- |
| [CancelAllOrders()](https://developer.ninjatrader.com/docs/desktop/cancelallorders) | Cancels all orders |
| [Connect()](https://developer.ninjatrader.com/docs/desktop/connect) | Connects to a connection |
| [ConnectionStatusUpdate](https://developer.ninjatrader.com/docs/desktop/connectionstatusupdate) | Event handler for connection status updates |

## [Events and Properties from Connection instances](https://developer.ninjatrader.com/docs/desktop/connection_class\#events-and-properties-from-connection-instances)

| Property | Description |
| --- | --- |
| [Accounts](https://developer.ninjatrader.com/docs/desktop/account_class) | List of accounts from the connection |
| [Disconnect()](https://developer.ninjatrader.com/docs/desktop/disconnect) | Disconnects from the connection |
| [Options](https://developer.ninjatrader.com/docs/desktop/connectoptions) | The connection's configuration options |
| [PriceStatus](https://developer.ninjatrader.com/docs/desktop/pricestatus) | A ConnectionStatus representing the status of the price feed. Possible values are:<br>- ConnectionStatus.Connected<br>  <br>- ConnectionStatus.Connecting<br>  <br>- ConnectionStatus.ConnectionLost<br>  <br>- ConnectionStatus.Disconnecting<br>  <br>- ConnectionStatus.Disconnected |
| [Status](https://developer.ninjatrader.com/docs/desktop/status) | A ConnectionStatus representing the status of the order feed. Possible values are:<br>- ConnectionStatus.Connected<br>  <br>- ConnectionStatus.Connecting<br>  <br>- ConnectionStatus.ConnectionLost<br>  <br>- ConnectionStatus.Disconnecting<br>  <br>- ConnectionStatus.Disconnected |

## [Examples](https://developer.ninjatrader.com/docs/desktop/connection_class\#examples)

```jsx-150469391 csharp
// Example of accessing information on all connected connections
public class MyAddOnTab : NTTabPage
{
  public MyAddOnTab()
  {
    // Print information about all connected connections
    lock (Connection.Connections)
      foreach(Connection c in Connection.Connections)
          NinjaTrader.Code.Output.Process(string.Format("Connection: {0} Provider: {1}", c.Options.Name, c.Options.Provider), PrintTo.OutputTab1);

    // Other required NTTabPage members left out for demonstration purposes. Be sure to add them in your own code.
  }
}

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/connection_class\#definition)

The Connection class can be used to monitor connection related events as well as accessing connection related information.

## [Static Connection Class Events and Properties](https://developer.ninjatrader.com/docs/desktop/connection_class\#static-connection-class-events-and-properties)

| Method | Description |
| --- | --- |
| [CancelAllOrders()](https://developer.ninjatrader.com/docs/desktop/cancelallorders) | Cancels all orders |
| [Connect()](https://developer.ninjatrader.com/docs/desktop/connect) | Connects to a connection |
| [ConnectionStatusUpdate](https://developer.ninjatrader.com/docs/desktop/connectionstatusupdate) | Event handler for connection status updates |

## [Events and Properties from Connection instances](https://developer.ninjatrader.com/docs/desktop/connection_class\#events-and-properties-from-connection-instances)

| Property | Description |
| --- | --- |
| [Accounts](https://developer.ninjatrader.com/docs/desktop/account_class) | List of accounts from the connection |
| [Disconnect()](https://developer.ninjatrader.com/docs/desktop/disconnect) | Disconnects from the connection |
| [Options](https://developer.ninjatrader.com/docs/desktop/connectoptions) | The connection's configuration options |
| [PriceStatus](https://developer.ninjatrader.com/docs/desktop/pricestatus) | A ConnectionStatus representing the status of the price feed. Possible values are:<br>- ConnectionStatus.Connected<br>  <br>- ConnectionStatus.Connecting<br>  <br>- ConnectionStatus.ConnectionLost<br>  <br>- ConnectionStatus.Disconnecting<br>  <br>- ConnectionStatus.Disconnected |
| [Status](https://developer.ninjatrader.com/docs/desktop/status) | A ConnectionStatus representing the status of the order feed. Possible values are:<br>- ConnectionStatus.Connected<br>  <br>- ConnectionStatus.Connecting<br>  <br>- ConnectionStatus.ConnectionLost<br>  <br>- ConnectionStatus.Disconnecting<br>  <br>- ConnectionStatus.Disconnected |

## [Examples](https://developer.ninjatrader.com/docs/desktop/connection_class\#examples)

```jsx-150469391 csharp
// Example of accessing information on all connected connections
public class MyAddOnTab : NTTabPage
{
  public MyAddOnTab()
  {
    // Print information about all connected connections
    lock (Connection.Connections)
      foreach(Connection c in Connection.Connections)
          NinjaTrader.Code.Output.Process(string.Format("Connection: {0} Provider: {1}", c.Options.Name, c.Options.Provider), PrintTo.OutputTab1);

    // Other required NTTabPage members left out for demonstration purposes. Be sure to add them in your own code.
  }
}

```
## [Definition](https://developer.ninjatrader.com/docs/desktop/playsound\#definition)

Plays a .wav file while running on real-time data.

## Note

1. This method will only execute once the **State** has reached **State.Realtime**. Calls to this method during **State.Historical** will be ignored (in contrast to the implementation for **AddOns**).
2. The default behavior is to play the .wav file in an asynchronous manner, which can result in calls to **PlaySound()** to play over one another. Sound files can optionally be configured to execute in a synchronous manner by enabling the Tools > Options > Sounds > "Play consecutively" property.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/playsound\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/playsound\#syntax)

`PlaySound(string fileName)`

## Warning

The underlying framework used to play the sound requires the audio file to be in PCM .wav format. Using another file format will generate an error at runtime.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/playsound\#parameters)

| Parameter | Description |
| --- | --- |
| **fileName** | The absolute file path of the .wav file to play |

## Note

You can obtain the default NinjaTrader installation directory to access the sounds folder by using **NinjaTrader.Core.Globals.InstallDir** property. Please see the example below for usage.

## [Examples](https://developer.ninjatrader.com/docs/desktop/playsound\#examples)

```jsx-150469391 csharp
// Plays the wav file mySound.wav
PlaySound(@"C:\mySound.wav");

// Plays the default Alert1 sound that comes packaged with NinjaTrader
PlaySound(NinjaTrader.Core.Globals.InstallDir + @"\sounds\Alert1.wav");

```

## [Definition](https://developer.ninjatrader.com/docs/desktop/playsound\#definition)

Plays a .wav file while running on real-time data.

## Note

1. This method will only execute once the **State** has reached **State.Realtime**. Calls to this method during **State.Historical** will be ignored (in contrast to the implementation for **AddOns**).
2. The default behavior is to play the .wav file in an asynchronous manner, which can result in calls to **PlaySound()** to play over one another. Sound files can optionally be configured to execute in a synchronous manner by enabling the Tools > Options > Sounds > "Play consecutively" property.

## [Method Return Value](https://developer.ninjatrader.com/docs/desktop/playsound\#method-return-value)

This method does not return a value.

## [Syntax](https://developer.ninjatrader.com/docs/desktop/playsound\#syntax)

`PlaySound(string fileName)`

## Warning

The underlying framework used to play the sound requires the audio file to be in PCM .wav format. Using another file format will generate an error at runtime.

## [Parameters](https://developer.ninjatrader.com/docs/desktop/playsound\#parameters)

| Parameter | Description |
| --- | --- |
| **fileName** | The absolute file path of the .wav file to play |

## Note

You can obtain the default NinjaTrader installation directory to access the sounds folder by using **NinjaTrader.Core.Globals.InstallDir** property. Please see the example below for usage.

## [Examples](https://developer.ninjatrader.com/docs/desktop/playsound\#examples)

```jsx-150469391 csharp
// Plays the wav file mySound.wav
PlaySound(@"C:\mySound.wav");

// Plays the default Alert1 sound that comes packaged with NinjaTrader
PlaySound(NinjaTrader.Core.Globals.InstallDir + @"\sounds\Alert1.wav");

```
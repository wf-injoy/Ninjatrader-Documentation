NinjaTrader makes it easy to distribute complete packages for your clients. Not only can you distribute your indicators and strategies, but you can also seamlessly deploy your own custom assemblies, native DLLs, chart templates, and Market Analyzer templates to your clients.

## [Creating the distribution package](https://developer.ninjatrader.com/docs/desktop/distribution_procedure\#creating-the-distribution-package)

To create a distribution package, please follow the steps shown here for creating a Export file containing your NinjaScript indicators and/or strategies.

It is strongly recommended that you export your scripts as an assembly and use SecureTeam's Agile.NET. Only this process will provide you with the highest level of security possible in order to protect your intellectual property. For more information on using SecureTeam's Agile.NET please see the [Protection/DLL Security](https://developer.ninjatrader.com/docs/desktop/export) section.

After you finish using the Export utility you will find the distribution package as a .zip file located in My Documents\\NinjaTrader 8\\bin\\Custom\\ExportNinjaScript. If you only wanted to distribute your NinjaScript files then providing your customers with this .zip and having them go through the [Import process](https://developer.ninjatrader.com/docs/desktop/import) would install it on their machines. If you wish to add more custom files to your distribution package, please see the sections below.

## Warning

It is important to let your customers know that NinjaTrader 8 indicators and strategies are NOT necessarily compatible with NinjaTrader Version 7.

### Adding custom assemblies or native DLLs

1. Locate your base .zip distribution package
2. Open the .zip
3. Add to the .zip file your assemblies and/or your DLL files to the root directory of the .zip. These files cannot be behind any extra directory structures and must be directly in the root of the .zip

For custom assemblies, you will also need to add to the root of the .zip a .txt file called AdditionalReferences.txt:

1. Bring up the Windows Start Menu

2. Go to the Run field and type "notepad" without the quotes and press Enter

3. In Notepad, type the name of your custom assembly and then save the file as a text file with the name "AdditionalReferences".

Ex: If your custom assembly's name was MyCustomAssembly.dll and MyCustomAssembly.cs, in the AdditionalReferences.txt file you would type "MyCustomAssembly" without the quotes.


## Note

If you have multiple custom assemblies to add you can append each of the assembly's names into the same AdditionalReferences.txt file on new lines

### Adding templates

If you are distributing an indicator package, you may also want to distribute a prebuilt Chart Template that your customers can use to quickly bring up preferred settings for your chart setup. The same instructions here would work though for all other templates as well, i.e. MarketAnalyzer, DrawingTools - as long as the relative folder under templates is correctly set per the template category you're working with. The below steps run through the process for Chart templates.

1. Locate your base .zip distribution package
2. Open the .zip
3. Create a new directory called "templates" without the quotes
4. Navigate into the "templates" directory and create another new directory called "Chart"
5. Navigate into the "Chart" directory. Copy the .xml chart templates you wish to distribute from My Documents\\NinjaTrader 8\\templates\\Chart to this directory in the .zip

### Adding workspaces

If you are distributing an indicator package, you may also want to distribute a prebuilt Workspace that your customers can use to quickly bring up preferred settings for your workspace. The below steps run through the process for workspaces.

1. Locate your base .zip distribution package
2. Open the .zip
3. Create a new directory called "workspaces" without the quotes
4. Navigate into the "workspaces" directory. Copy the .xml workspace you wish to distribute from My Documents\\NinjaTrader 8\\workspaces to this directory in the .zip

### Adding custom resource files

You may run into the need to distribute other custom files such as pictures for buttons for use with your product as well. This can be achieved via the same approach as for the templates, as long as the resources folder is under the parent templates directory.

1. Locate your base .zip distribution package
2. Open the .zip
3. Create a new directory called "templates" without the quotes
4. Navigate into the "templates" directory and create another new directory, for example "MyResources"
5. Navigate to the directory where your files are stored. Copy the resource files you wish to distribute from this directory to your custom directory from step 4 in the .zip

## Note

When modifying the .zip archives, if your zip utility application has an option for storing or recreating relative paths please be sure to turn this off as it will cause problems when importing the archive to NinjaTrader.

NinjaTrader makes it easy to distribute complete packages for your clients. Not only can you distribute your indicators and strategies, but you can also seamlessly deploy your own custom assemblies, native DLLs, chart templates, and Market Analyzer templates to your clients.

## [Creating the distribution package](https://developer.ninjatrader.com/docs/desktop/distribution_procedure\#creating-the-distribution-package)

To create a distribution package, please follow the steps shown here for creating a Export file containing your NinjaScript indicators and/or strategies.

It is strongly recommended that you export your scripts as an assembly and use SecureTeam's Agile.NET. Only this process will provide you with the highest level of security possible in order to protect your intellectual property. For more information on using SecureTeam's Agile.NET please see the [Protection/DLL Security](https://developer.ninjatrader.com/docs/desktop/export) section.

After you finish using the Export utility you will find the distribution package as a .zip file located in My Documents\\NinjaTrader 8\\bin\\Custom\\ExportNinjaScript. If you only wanted to distribute your NinjaScript files then providing your customers with this .zip and having them go through the [Import process](https://developer.ninjatrader.com/docs/desktop/import) would install it on their machines. If you wish to add more custom files to your distribution package, please see the sections below.

## Warning

It is important to let your customers know that NinjaTrader 8 indicators and strategies are NOT necessarily compatible with NinjaTrader Version 7.

### Adding custom assemblies or native DLLs

1. Locate your base .zip distribution package
2. Open the .zip
3. Add to the .zip file your assemblies and/or your DLL files to the root directory of the .zip. These files cannot be behind any extra directory structures and must be directly in the root of the .zip

For custom assemblies, you will also need to add to the root of the .zip a .txt file called AdditionalReferences.txt:

1. Bring up the Windows Start Menu

2. Go to the Run field and type "notepad" without the quotes and press Enter

3. In Notepad, type the name of your custom assembly and then save the file as a text file with the name "AdditionalReferences".

Ex: If your custom assembly's name was MyCustomAssembly.dll and MyCustomAssembly.cs, in the AdditionalReferences.txt file you would type "MyCustomAssembly" without the quotes.


## Note

If you have multiple custom assemblies to add you can append each of the assembly's names into the same AdditionalReferences.txt file on new lines

### Adding templates

If you are distributing an indicator package, you may also want to distribute a prebuilt Chart Template that your customers can use to quickly bring up preferred settings for your chart setup. The same instructions here would work though for all other templates as well, i.e. MarketAnalyzer, DrawingTools - as long as the relative folder under templates is correctly set per the template category you're working with. The below steps run through the process for Chart templates.

1. Locate your base .zip distribution package
2. Open the .zip
3. Create a new directory called "templates" without the quotes
4. Navigate into the "templates" directory and create another new directory called "Chart"
5. Navigate into the "Chart" directory. Copy the .xml chart templates you wish to distribute from My Documents\\NinjaTrader 8\\templates\\Chart to this directory in the .zip

### Adding workspaces

If you are distributing an indicator package, you may also want to distribute a prebuilt Workspace that your customers can use to quickly bring up preferred settings for your workspace. The below steps run through the process for workspaces.

1. Locate your base .zip distribution package
2. Open the .zip
3. Create a new directory called "workspaces" without the quotes
4. Navigate into the "workspaces" directory. Copy the .xml workspace you wish to distribute from My Documents\\NinjaTrader 8\\workspaces to this directory in the .zip

### Adding custom resource files

You may run into the need to distribute other custom files such as pictures for buttons for use with your product as well. This can be achieved via the same approach as for the templates, as long as the resources folder is under the parent templates directory.

1. Locate your base .zip distribution package
2. Open the .zip
3. Create a new directory called "templates" without the quotes
4. Navigate into the "templates" directory and create another new directory, for example "MyResources"
5. Navigate to the directory where your files are stored. Copy the resource files you wish to distribute from this directory to your custom directory from step 4 in the .zip

## Note

When modifying the .zip archives, if your zip utility application has an option for storing or recreating relative paths please be sure to turn this off as it will cause problems when importing the archive to NinjaTrader.
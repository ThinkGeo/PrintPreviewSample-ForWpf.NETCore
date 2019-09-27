# Print Preview Sample for Wpf

### Description
In this sample we show you how to add robust printing support to your Map Suite applications for the desktop, WPF, web or services environments. Using the code in this sample, you'll be able to build a Print Preview interface that lets your users interactively arrange items (such as a map, scale line, labels, data grid or image) on a virtual page before printing the result to a printer, exporting to a bitmap image. Maps are printed using vector graphics so you can be sure the output will look great on anything. The printing system also includes low-level report building classes that make it easy to generate reports in the web or services environment. 

To help you understand the sample, as well as Map Suite's new printing system upon which it is based, check out our [instructional video](http://download.thinkgeo.com/Videos/Wiki/MapSuitePrintingSystemIntroduction.wmv) that will introduce you to all of these concepts and walk you through the sample solution. 

Please note that you will need version 5.0.102.0 or newer of Map Suite in order to use the new printing features. For more information on how to upgrade, see the [Map Suite Daily Builds Guide](http://wiki.thinkgeo.com/wiki/map_suite_daily_builds_guide). 

Note: Users of Map Suite Web and Services Editions will not have access to the interactive drag-and-drop page layout interface pictured here. However, these editions can still be used to programmatically design page layouts in code and then export them to a printer.

Please refer to [Wiki](http://wiki.thinkgeo.com/wiki/thinkgeo_desktop_for_wpf) for the details.

![Screenshot](https://github.com/ThinkGeo/PrintPreviewSample-ForWpf.NETCore/blob/master/Screenshot.png)

### Requirements
This sample makes use of the following NuGet Packages

[MapSuite 10.0.0](https://www.nuget.org/packages?q=ThinkGeo)

### About the Code
```csharp
Map1.ZoomLevelSet = new PrinterZoomLevelSet(Map1.MapUnit, PrinterHelper.GetPointsPerGeographyUnit(Map1.MapUnit));

PrinterInteractiveOverlay printerOverlay = new PrinterInteractiveOverlay();

Map1.InteractiveOverlays.Add("PrintPreviewOverlay", printerOverlay);
Map1.InteractiveOverlays.MoveToBottom("PrintPreviewOverlay");

PagePrinterLayer pagePrinterLayer = new PagePrinterLayer(PrinterPageSize.AnsiA, PrinterOrientation.Portrait);
pagePrinterLayer.Open();
printerOverlay.PrinterLayers.Add("PageLayer", pagePrinterLayer);
```
### Getting Help

[Map Suite Desktop for Wpf Wiki Resources](http://wiki.thinkgeo.com/wiki/thinkgeo_desktop_for_wpf)

[Map Suite Desktop for Wpf Product Description](https://thinkgeo.com/ui-controls#desktop-platforms)

[ThinkGeo Community Site](http://community.thinkgeo.com/)

[ThinkGeo Web Site](http://www.thinkgeo.com)

### Key APIs
This example makes use of the following APIs:

- [ThinkGeo.Core.PrinterZoomLevelSet](http://wiki.thinkgeo.com/wiki/12.0/apis/thinkgeo.core.printerzoomlevelset)
- [ThinkGeo.Core.PrinterHelper](http://wiki.thinkgeo.com/wiki/12.0/apis/thinkgeo.core.printerhelper)
- [ThinkGeo.Core.GeoSolidBrush](http://wiki.thinkgeo.com/wiki/12.0/apis/thinkgeo.core.geosolidbrush)
- [ThinkGeo.UI.Wpf.PrinterInteractiveOverlay](http://wiki.thinkgeo.com/wiki/12.0/apis/thinkgeo.ui.wpf.printerinteractiveoverlay)
- [ThinkGeo.Core.PagePrinterLayer](http://wiki.thinkgeo.com/wiki/12.0/apis/thinkgeo.core.pageprinterlayer)
- [ThinkGeo.Core.PrinterPageSize](http://wiki.thinkgeo.com/wiki/12.0/apis/thinkgeo.core.printerpagesize)
- [ThinkGeo.Core.PrinterOrientation](http://wiki.thinkgeo.com/wiki/12.0/apis/thinkgeo.core.printerorientation)

### About Map Suite
Map Suite is a set of powerful development components and services for the .Net Core.

### About ThinkGeo
ThinkGeo is a GIS (Geographic Information Systems) company founded in 2004 and located in Frisco, TX. Our clients are in more than 40 industries including agriculture, energy, transportation, government, engineering, software development, and defense.

# Print Preview Sample for Wpf

### Description
In this sample we show you how to add robust printing support to your Map Suite applications for the WPF. Using the code in this sample, you'll be able to build a Print Preview interface that lets your users interactively arrange items (such as a map, scale line, labels, data grid or image) on a virtual page before printing the result to a printer, exporting to a bitmap image. Maps are printed using vector graphics so you can be sure the output will look great on anything.

Please refer to [Wiki](http://wiki.thinkgeo.com/wiki/thinkgeo_desktop_for_wpf) for the details.

![Screenshot](https://github.com/ThinkGeo/PrintPreviewSample-ForWpf.NETCore/blob/master/Screenshot.png)

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

### About ThinkGeo
ThinkGeo is a GIS (Geographic Information Systems) company founded in 2004 and located in Frisco, TX. Our clients are in more than 40 industries including agriculture, energy, transportation, government, engineering, software development, and defense.

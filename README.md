# Getting Started with .NET MAUI BadgeView (SfBadgeView)

This section provides a quick overview for working with the SfBadgeView for .NET MAUI. Walk through the entire process of creating a real world of this control.

## Creating an application using the .NET MAUI Badge View
 1. Create a new .NET MAUI application in Visual Studio.
 2. Syncfusion .NET MAUI components are available on [nuget.org](https://www.nuget.org/). To add SfBadgeView to your project, open the NuGet package manager in Visual Studio, search for Syncfusion.Maui.Core and then install it.

## Register the handler

To use this control inside an application, you must register the handler for Syncfusion® core.

```C#

using Microsoft.Extensions.Logging;
using Syncfusion.Maui.Core.Hosting;

namespace BadgeViewGettingStarted
{
    public static class MauiProgram
    {
        public static MauiApp CreateMauiApp()
        {
            var builder = MauiApp.CreateBuilder();
            builder
                .UseMauiApp<App>()
                .ConfigureSyncfusionCore()
                .ConfigureFonts(fonts =>
                {
                    fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
                    fonts.AddFont("OpenSans-Semibold.ttf", "OpenSansSemibold");
                });

#if DEBUG
    		builder.Logging.AddDebug();
#endif

            return builder.Build();
        }
    }
}

```

## Add a basic Badge View
1. Import the control namespace `Syncfusion.Maui.Core` in XAML or C# code.
2. Initialize the [SfBadgeView](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Core.SfBadgeView.html) control and Add text to Badge View using the BadgeText property.

```xml
<ContentPage   
    . . .
    xmlns:badgeView="clr-namespace:Syncfusion.Maui.Core;assembly=Syncfusion.Maui.Core">

   <badgeView:SfBadgeView>        
    <badgeView:SfBadgeView BadgeText="20" />          
</badgeView:SfBadgeView>
</ContentPage>
```



```C#
using Syncfusion.Maui.Core;
. . .

public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
       SfBadgeView badgeView = new SfBadgeView();
       //Adding text to the badge view.
       badgeView.BadgeText = "20";
       this.Content = badgeView;
    }
}
```

## Adding a content in .NET MAUI Badge View

```
<badgeView:SfBadgeView HorizontalOptions="Center" VerticalOptions="Center" BadgeText="20">
        <badgeView:SfBadgeView.Content>
            <Button Text="Primary" WidthRequest="120"  HeightRequest="60"/>
        </badgeView:SfBadgeView.Content>
</badgeView:SfBadgeView>

```

Run the application to render the following output:

![Getting started with .NET MAUI Badge View](maui_badge_view_getting_started.png)

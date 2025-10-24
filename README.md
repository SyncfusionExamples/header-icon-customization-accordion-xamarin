# header-icon-customization-accordion-xamarin

This sample demonstrates how to customize the header icon of a Syncfusion `SfAccordion` (Xamarin.Forms) control by using a custom converter and placing an `Image` inside each `AccordionItem.Header` template. The project shows a small and focused pattern: the accordion header uses a binding to the `AccordionItem.IsExpanded` property and a value converter (`ExpanderIconConverter`) to present different icons depending on expansion state.

To learn more about SfAccordion, check out the official user guide topics:

- [Getting Started with Xamarin Accordion (SfAccordion)](https://help.syncfusion.com/xamarin/accordion/getting-started)


## What this sample shows

- How to include a custom image in the `AccordionItem.Header` and bind its `Source` to `IsExpanded` via a converter.
- How to remove the default header icon by setting `HeaderIconPosition="None"` on `SfAccordion` so you can fully control the icon layout.

## XAML 

The XAML below shows the `SfAccordion` declaration where each `AccordionItem` header is a `Grid` with a `Label` (text) and an `Image` whose `Source` is bound to the item's `IsExpanded` property and converted by `ExpanderIconConverter`:

```
<ContentPage.Resources>
    <ResourceDictionary>
        <helper:ExpanderIconConverter x:Key="ExpanderIconConverter"/>
    </ResourceDictionary>
</ContentPage.Resources>

<ContentPage.Content>
    <syncfusion:SfAccordion Grid.Row="1" HeaderIconPosition="None">
        <syncfusion:SfAccordion.Items>
            <syncfusion:AccordionItem x:Name="accordionItem1">
                <syncfusion:AccordionItem.Header>
                    <Grid HeightRequest="50">
                        <Label TextColor="#495F6E" Text="Cheese burger" VerticalTextAlignment="Center" Padding="5,0,0,0"/>
                        <Image Margin="10" HorizontalOptions="End" Source="{Binding IsExpanded,Source={x:Reference accordionItem1},Converter={StaticResource ExpanderIconConverter}}" HeightRequest="20" WidthRequest="20"/>
                    </Grid>
                </syncfusion:AccordionItem.Header>
                <syncfusion:AccordionItem.Content>
                    <Grid Padding="10,10,10,10" BackgroundColor="#FFFFFF">
                        <Label TextColor="#303030" Text="Hamburger accompanied with melted cheese. The term itself is a portmanteau of the words cheese and hamburger. The cheese is usually sliced, then added a short time before the hamburger finishes cooking to allow it to melt." VerticalTextAlignment="Center"/>
                    </Grid>
                </syncfusion:AccordionItem.Content>
            </syncfusion:AccordionItem>
            <syncfusion:AccordionItem x:Name="accordionItem2">
                <syncfusion:AccordionItem.Header>
                    <Grid HeightRequest="50">
                        <Label TextColor="#495F6E" Text="Veggie burger" VerticalTextAlignment="Center" Padding="5,0,0,0"/>
                        <Image Margin="10" HorizontalOptions="End" Source="{Binding IsExpanded,Source={x:Reference accordionItem2},Converter={StaticResource ExpanderIconConverter}}" HeightRequest="20" WidthRequest="20"/>
                    </Grid>
                </syncfusion:AccordionItem.Header>
                <syncfusion:AccordionItem.Content>
                    <Grid Padding="10,10,10,10" BackgroundColor="#FFFFFF">
                        <Label TextColor="#303030" Text="Veggie burger, garden burger, or tofu burger uses a meat analogue, a meat substitute such as tofu, textured vegetable protein, seitan (wheat gluten), Quorn, beans, grains or an assortment of vegetables, which are ground up and formed into patties." VerticalTextAlignment="Center"/>
                    </Grid>
                </syncfusion:AccordionItem.Content>
            </syncfusion:AccordionItem>
            <syncfusion:AccordionItem x:Name="accordionItem3">
                <syncfusion:AccordionItem.Header>
                    <Grid HeightRequest="50">
                        <Label TextColor="#495F6E" Text="Barbecue burger" VerticalTextAlignment="Center" Padding="5,0,0,0"/>
                        <Image Margin="10" HorizontalOptions="End" Source="{Binding IsExpanded,Source={x:Reference accordionItem3},Converter={StaticResource ExpanderIconConverter}}" HeightRequest="20" WidthRequest="20"/>
                    </Grid>
                </syncfusion:AccordionItem.Header>
                <syncfusion:AccordionItem.Content>
                    <Grid Padding="10,10,10,10" BackgroundColor="#FFFFFF">
                        <Label TextColor="#303030" Text="Prepared with ground beef, mixed with onions and barbecue sauce, and then grilled. Once the meat has been turned once, barbecue sauce is spread on top and grilled until the sauce caramelizes." VerticalTextAlignment="Center"/>
                    </Grid>
                </syncfusion:AccordionItem.Content>
            </syncfusion:AccordionItem>
            <syncfusion:AccordionItem x:Name="accordionItem4">
                <syncfusion:AccordionItem.Header>
                    <Grid HeightRequest="50">
                        <Label TextColor="#495F6E" Text="Chili burger" VerticalTextAlignment="Center" Padding="5,0,0,0"/>
                        <Image Margin="10" HorizontalOptions="End" Source="{Binding IsExpanded,Source={x:Reference accordionItem4},Converter={StaticResource ExpanderIconConverter}}" HeightRequest="20" WidthRequest="20"/>
                    </Grid>
                </syncfusion:AccordionItem.Header>
                <syncfusion:AccordionItem.Content>
                    <Grid Padding="10,10,10,10" BackgroundColor="#FFFFFF">
                        <Label TextColor="#303030" Text="Consists of a hamburger, with the patty topped with chili con carne." VerticalTextAlignment="Center"/>
                    </Grid>
                </syncfusion:AccordionItem.Content>
            </syncfusion:AccordionItem>
        </syncfusion:SfAccordion.Items>
    </syncfusion:SfAccordion>
</ContentPage.Content>
```

## How it works

1. Each `AccordionItem` exposes an `IsExpanded` bindable property that reflects whether the item is expanded.
2. The header template binds the `Image.Source` to that `IsExpanded` property using `x:Reference` to the same `AccordionItem` instance.
3. The `ExpanderIconConverter` maps the boolean to the appropriate image resource path.


##### Conclusion

I hope you enjoyed learning about how to customize the header icon in Xamarin.Forms (SfAccordion). 

You can refer to our  [Xamarin.Forms Accordion feature tour](https://www.syncfusion.com/xamarin-ui-controls/xamarin-accordion) page to know about its other groundbreaking feature representations and [documentation](https://help.syncfusion.com/xamarin/accordion/getting-started), and how to quickly get started for configuration specifications. You can also explore our [Xamarin.Forms Accordion example](https://www.syncfusion.com/demos/xamarin) to understand how to create and manipulate data.

For current customers, you can check out our Document Processing Libraries from the [License and Downloads](https://www.syncfusion.com/account/login) page. If you are new to Syncfusion, you can try our 30-day [free trial](https://www.syncfusion.com/downloads) to check out our controls.

If you have any queries or require clarifications, please let us know in the comments section below. You can also contact us through our [support forums](https://www.syncfusion.com/forums) or [Direct-trac](https://support.syncfusion.com/create). We are always happy to assist you!



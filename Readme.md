# WinUI and iOS. InputTransparent does not work. MAUI bug [#15087](https://github.com/dotnet/maui/issues/15087)


If a Label with `InputTransparent="True"` is drawn over another Control, the other control does not get input.  

## Repro steps:
1. Create a File->New MAUI app.
2. Replace the MainPage.xaml content with this:
```xaml
<Grid>
    <Switch />
    <Label Text="hello" InputTransparent="True"/>
</Grid>
```
3. Remove the click-handler in MainPage.xaml.cs

Observe that on Android the Switch can be toggled. WinUI and iOS cannot toggle the switch.

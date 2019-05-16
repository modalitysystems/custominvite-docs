## Template Cheat Sheet

### Adding Images
Although images embedded in HTML can be blocked by Outlook when recieved it is fine to embed images when creating an email.  Outlook will ensure that the inline embedded images is replaced with a more reliable format when the meeting invitation is sent.

#### Steps
1. Use an online embedding tool such as https://codebeautify.org/image-to-base64-converter to create an ````<img>```` tag with 64bit encoded image data in it.
1. Provide a suitable alt element value.

````
<img scr="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEoAAABXCAIAAAAs+kRjAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAADsMAAA7DAcdvqGQAAAKSSURBVHhe7dBLjtwwDAXA3P/Sk1mUABG2u2WTUncC1ZLP4sd/fv5r+7yn/lwQL1E/zBEDPJipcoatb/J4jpruNk3QqFpBXwumaVcq29RqF3zUEVzwUZ1UR0sdiF/y6YG4yPN21olkwzyLZBUqzxPc5HFHUOErdtKiI0irOU81QaNGNW2fd2CFRjVNu0Y1Z593YH6jmqZdo5qzzzswv1FN065RzdnnnbFCo5qgUaOats87Y4uO4BEtOoK0540s0hHc5HFHUKHyvF+yYZ5FsgqpXtY5EL/k0wNxkWw7S53xxYH4jC/qFHS0Wpp2pWqaWjBBo2qVfW16n/cT1Le28gAPZpr55y6Il5g+zE2N6ir7vBxnNaqr7PNynNWorrLPy3FWo7rK+Ty7fDe7vnTykdf/Ahtf2+d9MRtfO//C6+9m15eGPsqwS6O6yj4vx1mN6ir7vBxnNaqr7PNynNWorrLPy3FWo7rKPi/HWY3qKvu8BDd1BKtMnOegSLbKrHmuOeOLJaYMc8c13833mfN++XSy+jHW71wVFygeY/eO4EMXVs6wdSR7l05SNsC+kaxRjWRz1HS3aSSLZJFsgoLWdoxkZ3zREUyQbW3BSHbNdx1BtVRfq0Wyd3zdEZQqPk8wwINIVud5Rxt1BMM8i2RFHrazS0dwk8cdQZEn7SzSETyiRUdQ4XYvK0Syp3TpCNLuNTI8kiVoFMlybnQxNpKlaRfJEkZbGBjJimjaESQMtTAtkpXSuiN46v17cyLZBAZ0BI88OU8whxmR7L43L7XvCGYyKZLd9OqZxh3BfOZFsjsu32gZyZYwsiO44/yNfpFsIYM7gmEnD3SKZGuZHcnGDJ0n+AQbdARj3p+n+jn2aFRH/Pz8BWYzb+pkFjhEAAAAAElFTkSuQmCC" alt="Stick Man Images" />
````

### Is SfB PSTN Conferencing Enabled
* To test if PSTN Conferencing is enabled
````
@if(Model.Sfbs.IsPstnEnabled)
{
   ...template code for enabled PSTN Conferencing
}
````
* To test if PSTN Conferencing is not enabled
````
@if(Model.Sfbs.IsPstnEnabled == false)
{
   ...template code for disabled PSTN Conferencing
}
````

### Display available VTC details
````
@if(Model.Teams.Pexip.IsEnabled)
{
    VTC Conference ID: @Model.Teams.Pexip.ConferenceId
   @Model.Teams.Pexip.SipAddress
   <a href="@Model.Teams.Pexip.DialingInstructionsUrl">Alternate VTC dialing instructions</a>
}
````

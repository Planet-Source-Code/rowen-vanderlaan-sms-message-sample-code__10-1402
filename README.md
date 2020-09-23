<div align="center">

## SMS message sample code


</div>

### Description

Send an SMS message through SMSC service provider. There are hundreds of SMSC service providers all over the world
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Rowen VanderLaan](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/rowen-vanderlaan.md)
**Level**          |Beginner
**User Rating**    |4.7 (14 globes from 3 users)
**Compatibility**  |VB\.NET, ASP\.NET
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__10-1.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/rowen-vanderlaan-sms-message-sample-code__10-1402/archive/master.zip)





### Source Code

```
' You need the freeware ASMSCTRL.DLL to run the sample.
' Download it from http://www.vahland.com/pub/asmsctrl.dll
' and register it on your machine.
' Then, choose 'Add Reference' from your Solutions Window,
' and add the ActiveSocket Type Library.
'
' Read http://www.vahland.com/pub/asmsctrl.htm for more info.
Imports ASMSCTRLLib
Module Module1
  Sub Main()
    Dim objSmsTool As ASMSCTRLLib.SMSC
    Dim strReceived As String
    Dim nCounter As Integer
    Console.WriteLine("Be sure To have the freeware asmsctrl.dll registered on your system,")
    Console.WriteLine("and add the 'ActiveXperts SMS and Pager Toolkit' to your references.")
    Console.WriteLine("")
    Console.WriteLine("This sample connects through a SMSC service provider to send out the SMS message")
    Console.WriteLine("Please check out www.activexperts.com/activsms/smsclist for a complete list of SMSC providers world wide")
    Console.WriteLine("")
    objSmsTool = New ASMSCTRLLib.SMSCClass()
    objSmsTool.PortID = 3
    objSmsTool.MessageText = "Hello, this is a test message"
    objSmsTool.Recipient = "0624896641"
    objSmsTool.ProviderDialString = "0,0653141414" ' The SMSC provider
    Console.WriteLine("Sending message...")
    objSmsTool.SendMessage(True)  ' TRUE means: through service provider
    If objSmsTool.LastError = 0 Then
      ' YES, connection established.
      Console.WriteLine("Message successfully delivered")
    Else
      Console.WriteLine("Message delivery failed, error: " + objSmsTool.LastError)
    End If
  End Sub
End Module
```


<div align="center">

## How do I prevent a form from being submitted, until all required fields are correct ?


</div>

### Description

How do I prevent a form from being submitted, until all required fields are correct ?

Only one field is used in the example.

Every time the user clicks the OK button, the onClick event fires. If it passes the test the form will submit, else the focus will be placed on the textbox, an alert will appear and the submit button will be disabled, which stops the submit process.

The onMouseMove event is used to enable the button again. I just added the error handling code in case an error comes up. It is actually not necessary, you can just enable the button again.

I use the onControlSelect event on the submit button, because sometimes after being disabled, the button looks like it is embedded in the page. The above event fixes it.

The above can be applied to multiple textboxes, and multiple conditions and arguments can be used.

It saves time and space as the validation is done on the current page, before the form is submitted.

Otherwise the user has to go through the laborious task of clicking the back button on the posting page to be redirected to the previous page, and fix a simple mistake. I've had comments that the JavaScript return false statement is a better solution. Unfortunately the return false; statement doesn't seem to work when you are using frames.

I hope you find this usefull !.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[iNet1](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/inet1.md)
**Level**          |Intermediate
**User Rating**    |4.4 (22 globes from 5 users)
**Compatibility**  |VbScript \(browser/client side\)

**Category**       |[Controls/ Forms/ Dialogs/ Menus](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/controls-forms-dialogs-menus__4-3.md)
**World**          |[ASP / VbScript](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/asp-vbscript.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/inet1-how-do-i-prevent-a-form-from-being-submitted-until-all-required-fields-are-correct__4-6462/archive/master.zip)





### Source Code

```
<xmp>
<html>
<head>
<title>Test</title>
<script language="VBScript">
sub cmdOK_onClick
 If Len(document.form1.txtEmpNo.value) > 8 Then
 	document.form1.txtEmpNo.focus
	alert"You have entered an invalid Employee number !"
	document.form1.cmdOK.disabled = True
end sub
sub Enable
 On Error Resume Next
 document.form1.cmdOK.disabled = False
end sub
</script>
</head>
<body onMouseMove="Enable">
<form name="form1" method="POST" action="test.htm">
<input type="text" name="txtEmpNo">
<input type="submit" name="cmdOK" value="OK" onControlSelect="cmdOK_onClick">
</form>
</body>
</html>
</xmp>
```


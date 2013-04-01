---
layout: post
published: true
title: Sending Spam with SWT
permalink: /sending-spam-with-swt/
wordpress_id: 505
categories:
- News
- AJAX
- Crack
- Java
- JavaScript
- html
---


<code lang='Java'>
import org.eclipse.swt.*;
import org.eclipse.swt.ole.win32.*;
import org.eclipse.swt.widgets.*;
 
public class Spam {
  public static void main(String args[]) {
    // Only needed to obtain an OleFrame
    Display display = new Display();
    Shell shell = new Shell(display);
    // Only needed to get a site
    OleFrame frame = new OleFrame(shell, SWT.NONE);
    OleClientSite site = new OleClientSite(frame, SWT.NONE, "Outlook.Application");
    // Activate Outlook
    site.doVerb(OLE.OLEIVERB_INPLACEACTIVATE);
    OleAutomation outlook = new OleAutomation(site);
    OleAutomation mail = invoke(outlook,"CreateItem",0 /*Mail item*/).getAutomation();
    setProperty(mail,"To","spam");
    setProperty(mail,"BodyFormat",2 /* HTML */);
    setProperty(mail,"Subject","Spam freshly made");
    setProperty(mail,"HtmlBody","<html><h1>Spam4U</h1></html>");
    invoke(mail,"Display" /* or "Send" */ );
    outlook.dispose();
    shell.dispose();
    display.dispose();
  }
  // These helper methods facilitate writing the OLE apps
  private static Variant invoke(OleAutomation auto, String command) {
    return auto.invoke(property(auto,command));
  }
  private static Variant invoke(OleAutomation auto, String command, String value) {
    return auto.invoke(property(auto,command), 
      new Variant[] { new Variant(value)});
  }
  private static Variant invoke(OleAutomation auto, String command, int value) {
    return auto.invoke(property(auto,command), 
      new Variant[] { new Variant(value)});
  }
  private static boolean setProperty(OleAutomation auto, String name, String value) {
    return auto.setProperty(property(auto,name), new Variant(value));
  }
  private static boolean setProperty(OleAutomation auto, String name, int value) {
    return auto.setProperty(property(auto,name), new Variant(value));
  }
  private static int property(OleAutomation auto, String name) {
    return auto.getIDsOfNames(new String[] { name })[0];
  }
}

```

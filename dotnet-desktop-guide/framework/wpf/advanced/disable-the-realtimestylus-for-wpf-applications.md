---
title: Disabilitare il Metodo RealTimeStylus
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: c2500b494f76c85e4b23823a44a180d85d5092ff
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966379"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>Disabilitare RealTimeStylus per le applicazioni WPF

Windows Presentation Foundation (WPF) ha integrato il supporto per l'elaborazione dell'input tocco di Windows 7. Il supporto deriva dall'input dello stilo in tempo reale della piattaforma Tablet <xref:System.Windows.UIElement.OnStylusDown%2A> come <xref:System.Windows.UIElement.OnStylusUp%2A> eventi, e <xref:System.Windows.UIElement.OnStylusMove%2A> . Windows 7 fornisce inoltre input multitocco come messaggi della finestra WM_TOUCH Win32. Queste due API si escludono a vicenda nello stesso HWND. L'abilitazione dell'input tocco tramite la piattaforma Tablet (impostazione predefinita per le applicazioni WPF) Disabilita i messaggi di WM_TOUCH. Di conseguenza, per usare WM_TOUCH per ricevere messaggi di tocco da una finestra WPF, è necessario disabilitare il supporto dello stilo incorporato in WPF. Questa operazione è applicabile in uno scenario come una finestra WPF che ospita un componente che usa WM_TOUCH.  
  
 Per disabilitare l'ascolto dell'input dello stilo in WPF, rimuovere il supporto per Tablet aggiunto dalla finestra WPF.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrato come rimuovere il supporto predefinito della piattaforma Tablet utilizzando la reflection.  
  
```csharp  
public static void DisableWPFTabletSupport()  
{  
    // Get a collection of the tablet devices for this window.
    TabletDeviceCollection devices = System.Windows.Input.Tablet.TabletDevices;  
  
    if (devices.Count > 0)  
    {
        // Get the Type of InputManager.  
        Type inputManagerType = typeof(System.Windows.Input.InputManager);  
  
        // Call the StylusLogic method on the InputManager.Current instance.  
        object stylusLogic = inputManagerType.InvokeMember("StylusLogic",  
                    BindingFlags.GetProperty | BindingFlags.Instance | BindingFlags.NonPublic,  
                    null, InputManager.Current, null);  
  
        if (stylusLogic != null)  
        {  
            //  Get the type of the stylusLogic returned from the call to StylusLogic.  
            Type stylusLogicType = stylusLogic.GetType();  
  
            // Loop until there are no more devices to remove.  
            while (devices.Count > 0)  
            {  
                // Remove the first tablet device in the devices collection.  
                stylusLogicType.InvokeMember("OnTabletRemoved",  
                        BindingFlags.InvokeMethod | BindingFlags.Instance | BindingFlags.NonPublic,  
                        null, stylusLogic, new object[] { (uint)0 });  
            }
        }  
  
    }  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- [Intercettazione dell'input dello stilo](intercepting-input-from-the-stylus.md)

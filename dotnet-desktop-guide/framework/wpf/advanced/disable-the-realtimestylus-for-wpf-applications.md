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
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="f04bf-102">Disabilitare RealTimeStylus per le applicazioni WPF</span><span class="sxs-lookup"><span data-stu-id="f04bf-102">Disable the RealTimeStylus for WPF Applications</span></span>

<span data-ttu-id="f04bf-103">Windows Presentation Foundation (WPF) ha integrato il supporto per l'elaborazione dell'input tocco di Windows 7.</span><span class="sxs-lookup"><span data-stu-id="f04bf-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.</span></span> <span data-ttu-id="f04bf-104">Il supporto deriva dall'input dello stilo in tempo reale della piattaforma Tablet <xref:System.Windows.UIElement.OnStylusDown%2A> come <xref:System.Windows.UIElement.OnStylusUp%2A> eventi, e <xref:System.Windows.UIElement.OnStylusMove%2A> .</span><span class="sxs-lookup"><span data-stu-id="f04bf-104">The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="f04bf-105">Windows 7 fornisce inoltre input multitocco come messaggi della finestra WM_TOUCH Win32.</span><span class="sxs-lookup"><span data-stu-id="f04bf-105">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="f04bf-106">Queste due API si escludono a vicenda nello stesso HWND.</span><span class="sxs-lookup"><span data-stu-id="f04bf-106">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="f04bf-107">L'abilitazione dell'input tocco tramite la piattaforma Tablet (impostazione predefinita per le applicazioni WPF) Disabilita i messaggi di WM_TOUCH.</span><span class="sxs-lookup"><span data-stu-id="f04bf-107">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="f04bf-108">Di conseguenza, per usare WM_TOUCH per ricevere messaggi di tocco da una finestra WPF, è necessario disabilitare il supporto dello stilo incorporato in WPF.</span><span class="sxs-lookup"><span data-stu-id="f04bf-108">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="f04bf-109">Questa operazione è applicabile in uno scenario come una finestra WPF che ospita un componente che usa WM_TOUCH.</span><span class="sxs-lookup"><span data-stu-id="f04bf-109">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="f04bf-110">Per disabilitare l'ascolto dell'input dello stilo in WPF, rimuovere il supporto per Tablet aggiunto dalla finestra WPF.</span><span class="sxs-lookup"><span data-stu-id="f04bf-110">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f04bf-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="f04bf-111">Example</span></span>  
 <span data-ttu-id="f04bf-112">Nell'esempio di codice seguente viene illustrato come rimuovere il supporto predefinito della piattaforma Tablet utilizzando la reflection.</span><span class="sxs-lookup"><span data-stu-id="f04bf-112">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f04bf-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f04bf-113">See also</span></span>

- [<span data-ttu-id="f04bf-114">Intercettazione dell'input dello stilo</span><span class="sxs-lookup"><span data-stu-id="f04bf-114">Intercepting Input from the Stylus</span></span>](intercepting-input-from-the-stylus.md)

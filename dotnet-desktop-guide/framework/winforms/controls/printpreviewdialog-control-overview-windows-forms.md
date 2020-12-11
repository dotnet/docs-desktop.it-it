---
title: Panoramica del controllo PrintPreviewDialog
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
ms.openlocfilehash: c7576beb56cd10a691a850969c132a2d33ad8870
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951431"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="880c9-102">Cenni preliminari sul controllo PrintPreviewDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="880c9-102">PrintPreviewDialog control overview (Windows Forms)</span></span>

<span data-ttu-id="880c9-103">Il <xref:System.Windows.Forms.PrintPreviewDialog> controllo Windows Forms è una finestra di dialogo preconfigurata utilizzata per visualizzare il modo in cui viene visualizzato un [PrintDocument](printdocument-component-windows-forms.md) quando viene stampato.</span><span class="sxs-lookup"><span data-stu-id="880c9-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="880c9-104">Utilizzarlo all'interno dell'applicazione basata su Windows come soluzione semplice anziché configurare la propria finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="880c9-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="880c9-105">Il controllo contiene pulsanti per la stampa, l'ingrandimento, la visualizzazione di una o più pagine e la chiusura della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="880c9-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>

## <a name="key-properties-and-methods"></a><span data-ttu-id="880c9-106">Proprietà e metodi chiave</span><span class="sxs-lookup"><span data-stu-id="880c9-106">Key properties and methods</span></span>

<span data-ttu-id="880c9-107">La proprietà chiave del controllo è <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A> , che imposta il documento da visualizzare in anteprima.</span><span class="sxs-lookup"><span data-stu-id="880c9-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="880c9-108">Il documento deve essere un <xref:System.Drawing.Printing.PrintDocument> oggetto.</span><span class="sxs-lookup"><span data-stu-id="880c9-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="880c9-109">Per visualizzare la finestra di dialogo, è necessario chiamare il relativo <xref:System.Windows.Forms.Form.ShowDialog%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="880c9-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="880c9-110">L'anti-aliasing può rendere il testo più semplice, ma può anche rendere più lenta la visualizzazione. per usarlo, impostare la <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> proprietà su `true` .</span><span class="sxs-lookup"><span data-stu-id="880c9-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>

<span data-ttu-id="880c9-111">Determinate proprietà sono disponibili tramite l'oggetto <xref:System.Windows.Forms.PrintPreviewControl> contenuto nell'oggetto <xref:System.Windows.Forms.PrintPreviewDialog> .</span><span class="sxs-lookup"><span data-stu-id="880c9-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="880c9-112">Non è necessario aggiungerlo <xref:System.Windows.Forms.PrintPreviewControl> al form. viene automaticamente contenuto all'interno di <xref:System.Windows.Forms.PrintPreviewDialog> quando si aggiunge la finestra di dialogo al form. Esempi di proprietà disponibili tramite <xref:System.Windows.Forms.PrintPreviewControl> sono le <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> proprietà e <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> , che determinano il numero di pagine visualizzate orizzontalmente e verticalmente sul controllo.</span><span class="sxs-lookup"><span data-stu-id="880c9-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="880c9-113">È possibile accedere alla <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> proprietà come `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C# o `printPreviewDialog1->PrintPreviewControl->Columns` in Visual C++.</span><span class="sxs-lookup"><span data-stu-id="880c9-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#, or `printPreviewDialog1->PrintPreviewControl->Columns` in Visual C++.</span></span>

## <a name="printpreviewdialog-performance"></a><span data-ttu-id="880c9-114">Prestazioni di PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="880c9-114">PrintPreviewDialog performance</span></span>

<span data-ttu-id="880c9-115">Nelle condizioni seguenti, il <xref:System.Windows.Forms.PrintPreviewDialog> controllo viene inizializzato molto lentamente:</span><span class="sxs-lookup"><span data-stu-id="880c9-115">Under the following conditions, the <xref:System.Windows.Forms.PrintPreviewDialog> control initializes very slowly:</span></span>

- <span data-ttu-id="880c9-116">Viene utilizzata una stampante di rete.</span><span class="sxs-lookup"><span data-stu-id="880c9-116">A network printer is used.</span></span>
- <span data-ttu-id="880c9-117">Vengono modificate le preferenze utente per questa stampante, ad esempio le impostazioni duplex.</span><span class="sxs-lookup"><span data-stu-id="880c9-117">User preferences for this printer, such as duplex settings, are modified.</span></span>

<span data-ttu-id="880c9-118">Per le app in esecuzione nel .NET Framework 4.5.2, è possibile aggiungere la chiave seguente alla \<appSettings> sezione del file di configurazione per migliorare le prestazioni dell' <xref:System.Windows.Forms.PrintPreviewDialog> inizializzazione del controllo:</span><span class="sxs-lookup"><span data-stu-id="880c9-118">For apps running on the .NET Framework 4.5.2, you can add the following key to the \<appSettings> section of your configuration file to improve the performance of <xref:System.Windows.Forms.PrintPreviewDialog> control initialization:</span></span>

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```

<span data-ttu-id="880c9-119">Se la `EnablePrintPreviewOptimization` chiave è impostata su qualsiasi altro valore o se la chiave non è presente, l'ottimizzazione non viene applicata.</span><span class="sxs-lookup"><span data-stu-id="880c9-119">If the `EnablePrintPreviewOptimization` key is set to any other value, or if the key is not present, the optimization is not applied.</span></span>

<span data-ttu-id="880c9-120">Per le app in esecuzione in .NET Framework 4,6 o versioni successive, è possibile aggiungere l'opzione seguente all' [\<AppContextSwitchOverrides>](/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) elemento nella [\<runtime>](/dotnet/framework/configure-apps/file-schema/runtime/index) sezione del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="880c9-120">For apps running on the .NET Framework 4.6 or later versions, you can add the following switch to the [\<AppContextSwitchOverrides>](/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) element in the [\<runtime>](/dotnet/framework/configure-apps/file-schema/runtime/index) section of your app config file:</span></span>

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
```

<span data-ttu-id="880c9-121">Se l'opzione non è presente o è impostata su un altro valore, l'ottimizzazione non viene applicata.</span><span class="sxs-lookup"><span data-stu-id="880c9-121">If the switch is not present or if it is set to any other value, the optimization is not applied.</span></span>

<span data-ttu-id="880c9-122">Se si utilizza l' <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> evento per modificare le impostazioni della stampante, le prestazioni del <xref:System.Windows.Forms.PrintPreviewDialog> controllo non miglioreranno anche se è impostata un'opzione di configurazione dell'ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="880c9-122">If you use the <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> event to modify printer settings, the performance of the <xref:System.Windows.Forms.PrintPreviewDialog> control will not improve even if an optimization configuration switch is set.</span></span>

## <a name="see-also"></a><span data-ttu-id="880c9-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="880c9-123">See also</span></span>

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [<span data-ttu-id="880c9-124">Panoramica del controllo PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="880c9-124">PrintPreviewControl Control Overview</span></span>](printpreviewcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="880c9-125">Controllo PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="880c9-125">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="880c9-126">Controlli e componenti della finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="880c9-126">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)

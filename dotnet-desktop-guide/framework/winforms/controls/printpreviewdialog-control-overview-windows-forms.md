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
# <a name="printpreviewdialog-control-overview-windows-forms"></a>Cenni preliminari sul controllo PrintPreviewDialog (Windows Forms)

Il <xref:System.Windows.Forms.PrintPreviewDialog> controllo Windows Forms è una finestra di dialogo preconfigurata utilizzata per visualizzare il modo in cui viene visualizzato un [PrintDocument](printdocument-component-windows-forms.md) quando viene stampato. Utilizzarlo all'interno dell'applicazione basata su Windows come soluzione semplice anziché configurare la propria finestra di dialogo. Il controllo contiene pulsanti per la stampa, l'ingrandimento, la visualizzazione di una o più pagine e la chiusura della finestra di dialogo.

## <a name="key-properties-and-methods"></a>Proprietà e metodi chiave

La proprietà chiave del controllo è <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A> , che imposta il documento da visualizzare in anteprima. Il documento deve essere un <xref:System.Drawing.Printing.PrintDocument> oggetto. Per visualizzare la finestra di dialogo, è necessario chiamare il relativo <xref:System.Windows.Forms.Form.ShowDialog%2A> metodo. L'anti-aliasing può rendere il testo più semplice, ma può anche rendere più lenta la visualizzazione. per usarlo, impostare la <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> proprietà su `true` .

Determinate proprietà sono disponibili tramite l'oggetto <xref:System.Windows.Forms.PrintPreviewControl> contenuto nell'oggetto <xref:System.Windows.Forms.PrintPreviewDialog> . Non è necessario aggiungerlo <xref:System.Windows.Forms.PrintPreviewControl> al form. viene automaticamente contenuto all'interno di <xref:System.Windows.Forms.PrintPreviewDialog> quando si aggiunge la finestra di dialogo al form. Esempi di proprietà disponibili tramite <xref:System.Windows.Forms.PrintPreviewControl> sono le <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> proprietà e <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> , che determinano il numero di pagine visualizzate orizzontalmente e verticalmente sul controllo. È possibile accedere alla <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> proprietà come `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C# o `printPreviewDialog1->PrintPreviewControl->Columns` in Visual C++.

## <a name="printpreviewdialog-performance"></a>Prestazioni di PrintPreviewDialog

Nelle condizioni seguenti, il <xref:System.Windows.Forms.PrintPreviewDialog> controllo viene inizializzato molto lentamente:

- Viene utilizzata una stampante di rete.
- Vengono modificate le preferenze utente per questa stampante, ad esempio le impostazioni duplex.

Per le app in esecuzione nel .NET Framework 4.5.2, è possibile aggiungere la chiave seguente alla \<appSettings> sezione del file di configurazione per migliorare le prestazioni dell' <xref:System.Windows.Forms.PrintPreviewDialog> inizializzazione del controllo:

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```

Se la `EnablePrintPreviewOptimization` chiave è impostata su qualsiasi altro valore o se la chiave non è presente, l'ottimizzazione non viene applicata.

Per le app in esecuzione in .NET Framework 4,6 o versioni successive, è possibile aggiungere l'opzione seguente all' [\<AppContextSwitchOverrides>](/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) elemento nella [\<runtime>](/dotnet/framework/configure-apps/file-schema/runtime/index) sezione del file di configurazione dell'app:

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
```

Se l'opzione non è presente o è impostata su un altro valore, l'ottimizzazione non viene applicata.

Se si utilizza l' <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> evento per modificare le impostazioni della stampante, le prestazioni del <xref:System.Windows.Forms.PrintPreviewDialog> controllo non miglioreranno anche se è impostata un'opzione di configurazione dell'ottimizzazione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [Panoramica del controllo PrintPreviewControl](printpreviewcontrol-control-overview-windows-forms.md)
- [Controllo PrintPreviewDialog](printpreviewdialog-control-windows-forms.md)
- [Controlli e componenti della finestra di dialogo](dialog-box-controls-and-components-windows-forms.md)

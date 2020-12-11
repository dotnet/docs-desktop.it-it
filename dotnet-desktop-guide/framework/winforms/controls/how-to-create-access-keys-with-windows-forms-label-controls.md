---
title: Creare chiavi di accesso con controlli Label
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- Label control [Windows Forms], creating access keys
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- Windows Forms controls, access keys
- UseMnemonic property [Windows Forms], Label control
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
ms.openlocfilehash: 800afc03e71435e2721456b93bb9704af01f714a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961963"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a>Procedura: Creare tasti di scelta con i controlli Label di Windows Forms
<xref:System.Windows.Forms.Label>È possibile utilizzare i controlli Windows Forms per definire le chiavi di accesso per altri controlli. Quando si definisce una chiave di accesso in un controllo etichetta, l'utente può premere il tasto ALT più il carattere designato per spostare lo stato attivo sul controllo che lo segue nell'ordine di tabulazione. Poiché le etichette non possono ricevere lo stato attivo, lo stato attivo passa automaticamente al controllo successivo nell'ordine di tabulazione. Usare questa tecnica per assegnare chiavi di accesso a caselle di testo, caselle combinate, caselle di riepilogo e griglie di dati.  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a>Per assegnare una chiave di accesso a un controllo con un'etichetta  
  
1. Creare prima l'etichetta, quindi creare l'altro controllo.  
  
     -oppure-  
  
     Creare i controlli in qualsiasi ordine e impostare la <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà dell'etichetta su uno minore dell'altro controllo.  
  
2. Impostare la proprietà dell'etichetta <xref:System.Windows.Forms.Label.UseMnemonic%2A> su `true` .  
  
3. Usare una e commerciale (&) nella proprietà dell'etichetta <xref:System.Windows.Forms.Label.Text%2A> per assegnare la chiave di accesso per l'etichetta. Per ulteriori informazioni, vedere [creazione di chiavi di accesso per controlli Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md).  
  
    > [!NOTE]
    > È possibile che si desideri visualizzare le e commerciali in un controllo etichetta, anziché usarle per creare chiavi di accesso. Questo problema può verificarsi se si associa un controllo Label a un campo in un recordset in cui i dati includono le e commerciali. Per visualizzare le e commerciali in un controllo Label, impostare la <xref:System.Windows.Forms.Label.UseMnemonic%2A> proprietà su `false` . Se si desidera visualizzare le e commerciali e avere anche una chiave di accesso, impostare la <xref:System.Windows.Forms.Label.UseMnemonic%2A> proprietà su `true` e indicare la chiave di accesso con una e commerciale (&) e la e commerciale da visualizzare con due e commerciali.  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Ridimensionare un controllo Label di Windows Forms in base al contenuto](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [Panoramica del controllo Label](label-control-overview-windows-forms.md)
- [Controllo Label](label-control-windows-forms.md)

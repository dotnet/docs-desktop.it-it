---
title: 'Procedura: Definire il ridimensionamento e il posizionamento in una finestra divisa'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
ms.openlocfilehash: 8cdcfdfaa135a92ed6a6e96d4a72de2c97f2493d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961915"
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a>Procedura: Definire il ridimensionamento e il posizionamento in una finestra divisa
I pannelli del <xref:System.Windows.Forms.SplitContainer> controllo si prestano bene a essere ridimensionati e modificati dagli utenti. Tuttavia, in alcuni casi sarà necessario controllare a livello di codice la barra di divisione, ovvero la posizione in cui è posizionata e il grado di spostamento.  
  
 La <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> proprietà e le altre proprietà del <xref:System.Windows.Forms.SplitContainer> controllo consentono di controllare in modo preciso il comportamento dell'interfaccia utente in base alle esigenze. Queste proprietà sono elencate nella tabella seguente.  
  
|Name|Descrizione|  
|----------|-----------------|  
|Proprietà<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>|Determina se la barra di divisione è mobile per mezzo della tastiera o del mouse.|  
|Proprietà<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>|Determina la distanza in pixel dal bordo sinistro o superiore alla barra di divisione mobile.|  
|Proprietà<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>|Determina la distanza minima, in pixel, che la barra di divisione può spostare dall'utente.|  
  
 Nell'esempio seguente la proprietà viene modificata in <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> modo da creare un effetto barra di divisione "blocco". quando l'utente trascina il separatore, viene incrementato in unità di 10 pixel invece che nel valore predefinito 1.  
  
### <a name="to-define-splitcontainer-resize-behavior"></a>Per definire il comportamento di ridimensionamento di SplitContainer  
  
1. In una routine, impostare la <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> proprietà sulla dimensione desiderata, in modo da ottenere il comportamento "blocco" della barra di divisione.  
  
     Nell'esempio di codice seguente, nell'evento del form <xref:System.Windows.Forms.Form.Load> , la barra di divisione all'interno del <xref:System.Windows.Forms.SplitContainer> controllo viene impostata in modo da saltare 10 pixel quando viene trascinata.  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles MyBase.Load  
        Dim splitSnapper as new SplitContainer()  
        splitSnapper.SplitterIncrement = 10  
        splitSnapper.Dock = DockStyle.Fill  
        splitSnapper.Parent = me  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Load(System.Object sender, System.EventArgs e)  
    {  
        SplitContainer splitSnapper = new SplitContainer();  
        splitSnapper.SplitterIncrement = 10;  
        splitSnapper.Dock = DockStyle.Fill;  
        splitSnapper.Parent = this;  
    }  
    ```  
  
     (Visual C#) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     Il passaggio di un separatore leggermente a sinistra o a destra non avrà alcun effetto visibile; Tuttavia, quando il puntatore del mouse passa 10 pixel in entrambe le direzioni, la barra di divisione si blocca sulla nuova posizione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>

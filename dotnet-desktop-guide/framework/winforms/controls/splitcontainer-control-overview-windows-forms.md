---
title: Panoramica del controllo SplitContainer
ms.date: 03/30/2017
f1_keywords:
- SplitContainer
helpviewer_keywords:
- SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
ms.openlocfilehash: f697629020342d534265c633707fed8c4a460e20
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964288"
---
# <a name="splitcontainer-control-overview-windows-forms"></a>Cenni preliminari sul controllo SplitContainer (Windows Form)

Il controllo <xref:System.Windows.Forms.SplitContainer> Windows Form può essere considerato un oggetto composto, poiché è costituito da due pannelli separati da una barra mobile. Quando il puntatore del mouse viene posizionato sopra la barra, assume una forma diversa per indicare che la barra è mobile.  
  
> [!IMPORTANT]
> Nella **casella degli strumenti** il <xref:System.Windows.Forms.SplitContainer> controllo sostituisce il <xref:System.Windows.Forms.Splitter> controllo presente nella versione precedente di Visual Studio. È consigliabile usare il controllo <xref:System.Windows.Forms.SplitContainer> anziché il controllo <xref:System.Windows.Forms.Splitter>. La classe <xref:System.Windows.Forms.Splitter> è ancora inclusa in .NET Framework per assicurare la compatibilità con le applicazioni esistenti, ma per i nuovi progetti si consiglia di usare il controllo <xref:System.Windows.Forms.SplitContainer>.  
  
 Con il <xref:System.Windows.Forms.SplitContainer> controllo è possibile creare interfacce utente complesse. spesso una selezione in un pannello determina quali oggetti vengono visualizzati nell'altro pannello. Questa disposizione è particolarmente efficace per la visualizzazione e la ricerca di informazioni. La presenza di due pannelli che consentono di aggregare le informazioni in aree, la barra o il "Splitter" consente agli utenti di ridimensionare facilmente i pannelli.  
  
 <xref:System.Windows.Forms.SplitContainer>È anche possibile annidare più di un controllo, con il secondo <xref:System.Windows.Forms.SplitContainer> controllo orientato orizzontalmente, per creare i pannelli superiore e inferiore.  
  
 Tenere presente che il <xref:System.Windows.Forms.SplitContainer> controllo è accessibile da tastiera per impostazione predefinita; gli utenti possono premere i tasti di direzione per spostare la barra di divisione se la <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> proprietà è impostata su `false` .  
  
 La <xref:System.Windows.Forms.SplitContainer.Orientation%2A> proprietà del <xref:System.Windows.Forms.SplitContainer> controllo determina la direzione della barra di divisione, non del controllo stesso. Di conseguenza, quando questa proprietà è impostata su <xref:System.Windows.Forms.Orientation.Vertical> , la barra di divisione viene eseguita dall'alto verso il basso, creando pannelli di sinistra e destra.  
  
 Inoltre, tenere presente che il valore della <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> proprietà varia a seconda del valore della <xref:System.Windows.Forms.SplitContainer.Orientation%2A> Proprietà. Per ulteriori informazioni, vedere <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> Property.  
  
 È anche possibile limitare le dimensioni e lo spostamento del <xref:System.Windows.Forms.SplitContainer> controllo. La <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> proprietà determina quale pannello rimarrà invariato dopo il <xref:System.Windows.Forms.SplitContainer> ridimensionamento del controllo e la <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> proprietà determina se la barra di divisione è mobile mediante la tastiera o il mouse.  
  
> [!NOTE]
> Anche se la <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> proprietà è impostata su `true` , la barra di divisione può comunque essere spostata a livello di codice, ad esempio usando la <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> Proprietà.  
  
 Infine, ogni pannello del <xref:System.Windows.Forms.SplitContainer> controllo dispone di proprietà per determinarne le singole dimensioni.  
  
## <a name="commonly-used-properties-methods-and-events"></a>Proprietà, metodi ed eventi usati comunemente  
  
|Name|Descrizione|  
|----------|-----------------|  
|Proprietà<xref:System.Windows.Forms.SplitContainer.FixedPanel%2A>|Determina quale pannello rimarrà le stesse dimensioni dopo il <xref:System.Windows.Forms.SplitContainer> ridimensionamento del controllo.|  
|Proprietà<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>|Determina se la barra di divisione può essere spostata con la tastiera o il mouse.|  
|Proprietà<xref:System.Windows.Forms.SplitContainer.Orientation%2A>|Determina se la barra di divisione è disposta verticalmente o orizzontalmente.|  
|Proprietà<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>|Determina la distanza in pixel dal bordo sinistro o superiore alla barra di divisione mobile.|  
|Proprietà<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>|Determina la distanza minima, in pixel, che la barra di divisione può spostare dall'utente.|  
|Proprietà<xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A>|Determina lo spessore, in pixel, della barra di divisione.|  
|Evento<xref:System.Windows.Forms.SplitContainer.SplitterMoving>|Si verifica quando la barra di divisione viene spostato.|  
|Evento<xref:System.Windows.Forms.SplitContainer.SplitterMoved>|Si verifica quando la barra di divisione viene spostata.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.SplitContainer>
- [Controllo SplitContainer](splitcontainer-control-windows-forms.md)
- [Esempio di controllo SplitContainer](/previous-versions/visualstudio/visual-studio-2008/0ffz7d1b(v=vs.90))

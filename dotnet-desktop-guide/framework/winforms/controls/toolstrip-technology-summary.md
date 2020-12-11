---
title: Riepilogo della tecnologia ToolStrip
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], technology summary
- status bars [Windows Forms], technology summary
- toolbars [Windows Forms], technology summary
- menus [Windows Forms], technology summary
ms.assetid: e8d61973-7af9-429f-9df5-05a899c15a7b
ms.openlocfilehash: 65d271fe7cfb79975844a75e7b12b05eee7896a9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966562"
---
# <a name="toolstrip-technology-summary"></a>Riepilogo della tecnologia ToolStrip

Questo argomento riepiloga le informazioni relative al controllo `ToolStrip` e alle classi che ne supportano l'uso.  
  
 Il controllo `ToolStrip` e le classi associate forniscono una soluzione completa per creare barre degli strumenti, barre di stato e menu.  
  
## <a name="namespaces"></a>Spazi dei nomi  

 <xref:System.Windows.Forms?displayProperty=nameWithType>  
  
## <a name="background"></a>Background  

 Con il controllo `ToolStrip` e le classi associate, è possibile creare funzionalità avanzate della barra degli strumenti con un aspetto e un comportamento coerenti e professionali. Il controllo `ToolStrip` e le classi offrono i seguenti vantaggi rispetto ai controlli precedenti:  
  
- Un modello di eventi più coerente.  
  
- Un comportamento più coerente in fase di progettazione, contenente elenchi di attività ed editor della raccolta di elementi.  
  
- Rendering personalizzato con `ToolStripManager` e `ToolStripRenderer`.  
  
- Raggruppamento verticale/orizzontale incorporato di funzionalità (condivisione di spazio orizzontale o verticale nell'area strumenti, se ancorata) con `ToolStripContainer` e `ToolStripPanel`.  
  
- Raggruppamento degli elementi in fase di progettazione e in fase di esecuzione con la proprietà <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>.  
  
- Rilocazione degli elementi in un menu di overflow con la proprietà <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>.  
  
- Posizione del controllo completamente configurabile con `ToolStripContainer`, `ToolStripPanel`e `ToolStripContentPanel`.  
  
- Hosting di controlli `ToolStrip`, tradizionali o personalizzati con `ToolStripControlHost`.  
  
- Unione di controlli `ToolStrip` con `ToolStripPanel`.  
  
 `ToolStrip` è la classe base estendibile per `MenuStrip`, `ContextMenuStrip` e `StatusStrip`. Questi controlli sono contenitori <xref:System.Windows.Forms.ToolStripItem> che ereditano il comportamento comune e la gestione degli eventi, estesi in modo tale che ogni implementazione gestisca il comportamento appropriato. I controlli derivati da <xref:System.Windows.Forms.ToolStripItem> sono elencati nella seguente tabella. La classe base `ToolStrip` gestisce il disegno, l'input utente e gli eventi di trascinamento della selezione per questi controlli.  
  
 I controlli `ToolStrip`, `MenuStrip`, `ContextMenuStrip` e `StatusStrip` sostituiscono le barre degli strumenti, i menu, i menu di scelta rapida e le barre di stato precedenti, anche se tali controlli vengono mantenuti per compatibilità con le versioni precedenti.  
  
## <a name="toolstrip-classes-at-a-glance"></a>Introduzione alle classi ToolStrip  

 La tabella seguente illustra le classi ToolStrip raggruppate per area tecnologica.  
  
|Area tecnologica|Classe|  
|---------------------|-----------|  
|Contenitori di barre di stato, stati e menu|<xref:System.Windows.Forms.ToolStrip><br /><br /> <xref:System.Windows.Forms.MenuStrip><br /><br /> <xref:System.Windows.Forms.ContextMenuStrip><br /><br /> <xref:System.Windows.Forms.StatusStrip><br /><br /> <xref:System.Windows.Forms.ToolStripDropDownMenu>|  
|Elementi ToolStrip|<xref:System.Windows.Forms.ToolStripLabel><br /><br /> <xref:System.Windows.Forms.ToolStripDropDownItem><br /><br /> <xref:System.Windows.Forms.ToolStripMenuItem><br /><br /> <xref:System.Windows.Forms.ToolStripButton><br /><br /> <xref:System.Windows.Forms.ToolStripStatusLabel><br /><br /> <xref:System.Windows.Forms.ToolStripSeparator><br /><br /> <xref:System.Windows.Forms.ToolStripControlHost><br /><br /> <xref:System.Windows.Forms.ToolStripComboBox><br /><br /> <xref:System.Windows.Forms.ToolStripTextBox><br /><br /> <xref:System.Windows.Forms.ToolStripProgressBar><br /><br /> <xref:System.Windows.Forms.ToolStripDropDownButton><br /><br /> <xref:System.Windows.Forms.ToolStripSplitButton>|  
|Percorso|<xref:System.Windows.Forms.ToolStripContainer><br /><br /> <xref:System.Windows.Forms.ToolStripContentPanel><br /><br /> <xref:System.Windows.Forms.ToolStripPanel>|  
|Presentazione e rendering|<xref:System.Windows.Forms.ToolStripManager><br /><br /> <xref:System.Windows.Forms.ToolStripRenderer><br /><br /> <xref:System.Windows.Forms.ToolStripProfessionalRenderer><br /><br /> <xref:System.Windows.Forms.ToolStripRenderMode><br /><br /> <xref:System.Windows.Forms.ToolStripManagerRenderMode>|  
  
## <a name="toolstrip-design-time-features"></a>Funzionalità di ToolStrip in fase di progettazione  

 La famiglia di controlli <xref:System.Windows.Forms.ToolStrip> offre un'ampia gamma di strumenti e modelli per la modifica sul posto e la definizione degli elementi fondamentali dell'interfaccia utente, per poter creare rapidamente un'applicazione funzionante.  
  
### <a name="task-dialog-boxes"></a>Finestre di dialogo delle attività  

 In Visual Studio, facendo clic sullo smart tag di un controllo nella finestra di progettazione, viene visualizzato un elenco di attività che permette di accedere facilmente a molti comandi usati di frequente.  
  
- [Finestra di dialogo Attività di MenuStrip](/previous-versions/visualstudio/visual-studio-2010/ms233645(v=vs.100))  
  
- [Finestra di dialogo Attività di ToolStrip](/previous-versions/visualstudio/visual-studio-2010/ms233648(v=vs.100))  
  
- [Finestra di dialogo Attività di ContextMenuStrip](/previous-versions/visualstudio/visual-studio-2010/ms233646(v=vs.100))  
  
- [Finestra di dialogo Attività di StatusStrip](/previous-versions/visualstudio/visual-studio-2010/ms233642(v=vs.100))  
  
- [Finestra di dialogo Attività di ToolStripContainer](/previous-versions/visualstudio/visual-studio-2010/ms233647(v=vs.100))  
  
### <a name="items-collection-editors"></a>Editor della raccolta Items  

 In Visual Studio, quando si fa clic su **modifica elementi** nell'elenco attività o si fa clic con il pulsante destro del mouse sul controllo e si sceglie **modifica elementi** nel menu di scelta rapida, viene visualizzato l'editor della raccolta per il controllo. Gli Editor della raccolta permettono di aggiungere, rimuovere e riordinare gli elementi contenuti nel controllo. Si possono anche visualizzare e cambiare le proprietà per il controllo e per gli elementi del controllo.  
  
- [MenuStrip (editor della raccolta Items)](/previous-versions/visualstudio/visual-studio-2010/ms233625(v=vs.100))  
  
- [StatusStrip (editor della raccolta Items)](/previous-versions/visualstudio/visual-studio-2010/ms233631(v=vs.100))  
  
- [Editor della raccolta Items di ContextMenuStrip](/previous-versions/visualstudio/visual-studio-2010/ms233641(v=vs.100))  
  
- [Editor della raccolta Items di ToolStrip](/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100))  
  
## <a name="hosting-controls"></a>Hosting di controlli  

 La classe <xref:System.Windows.Forms.ToolStripControlHost> fornisce wrapper predefiniti per i controlli <xref:System.Windows.Forms.ToolStripComboBox>, <xref:System.Windows.Forms.ToolStripTextBox>e <xref:System.Windows.Forms.ToolStripProgressBar>. È anche possibile ospitare qualsiasi altri controllo esistente o COM in <xref:System.Windows.Forms.ToolStripControlHost>.  
  
 Per un esempio di hosting dei controlli, vedere [procedura: eseguire il wrapping di un controllo Windows Forms con ToolStripControlHost](how-to-wrap-a-windows-forms-control-with-toolstripcontrolhost.md).  
  
## <a name="rendering"></a>Rendering  

 La classi <xref:System.Windows.Forms.ToolStrip> implementano uno schema di rendering molto diverso da quello di altri controlli Windows Form. Con questo schema, è possibile applicare facilmente stili e temi.  
  
 Per applicare uno stile a <xref:System.Windows.Forms.ToolStrip> e a tutti gli oggetti <xref:System.Windows.Forms.ToolStripItem> in esso contenuti, non è necessario gestire l'evento <xref:System.Windows.Forms.ToolStripItem.Paint> per ogni elemento. È invece possibile impostare la proprietà <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> su un valore di <xref:System.Windows.Forms.ToolStripRenderMode> diverso da <xref:System.Windows.Forms.ToolStripRenderMode.Custom>. In alternativa, è possibile impostare <xref:System.Windows.Forms.ToolStrip.Renderer%2A> direttamente su una classe che eredita dalla classe <xref:System.Windows.Forms.ToolStripRenderer>. Impostando questa proprietà, viene automaticamente impostato <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>.  
  
 È possibile applicare lo stesso stile a più oggetti <xref:System.Windows.Forms.ToolStrip> nella stessa applicazione impostando <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> su <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode> e impostando la proprietà <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A> o <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> rispettivamente sul valore <xref:System.Windows.Forms.ToolStripManagerRenderMode> desiderato o sul valore <xref:System.Windows.Forms.ToolStripRenderer>.  
  
 Per esempi di rendering, vedere [procedura: creare e impostare un renderer personalizzato per il controllo ToolStrip in Windows Forms](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md).  
  
## <a name="styles-and-themes"></a>Stili e temi  

 <xref:System.Windows.Forms.ToolStrip> e le classi associate permettono di supportare facilmente stili di visualizzazione e un aspetto personalizzato che non richiedono l'override dei metodi <xref:System.Windows.Forms.ToolStripItem.OnPaint%2A> per ogni elemento. Usare le proprietà <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>, <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> e <xref:System.Windows.Forms.ToolStrip.Renderer%2A>.  
  
## <a name="rafting-and-docking"></a>Raggruppamento e ancoraggio  

 È possibile raggruppare, ancorare o posizionare in modo assoluto i controlli <xref:System.Windows.Forms.ToolStrip>. Gli elementi <xref:System.Windows.Forms.ToolStrip> vengono disposti in base alla proprietà <xref:System.Windows.Forms.ToolStrip.LayoutEngine%2A> del contenitore.  
  
 Il *raggruppamento* è la capacità delle barre degli strumenti di condividere lo spazio orizzontale o verticale. Un Windows Form può contenere un oggetto <xref:System.Windows.Forms.ToolStripContainer> che a sua volta contiene dei pannelli sui lati sinistro, destro, superiore e inferiore del form per posizionare e raggruppare i controlli <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.StatusStrip>. Più controlli <xref:System.Windows.Forms.ToolStrip> vengono raggruppati verticalmente se li si inserisce nell'oggetto <xref:System.Windows.Forms.ToolStripContainer> di sinistra o di destra. Vengono raggruppati orizzontalmente se li si inserisce nell'oggetto <xref:System.Windows.Forms.ToolStripContainer> in alto o in basso. È possibile usare l'oggetto <xref:System.Windows.Forms.ToolStripContentPanel> centrale di <xref:System.Windows.Forms.ToolStripContainer> per posizionare i tradizionali controlli sul form.  
  
 Alcuni o tutti i controlli <xref:System.Windows.Forms.ToolStripContainer> sono direttamente selezionabili in fase di progettazione e possono essere eliminati. <xref:System.Windows.Forms.ToolStripContainer> è estendibile e comprimibile e viene ridimensionato con i controlli in esso contenuti.  
  
 L' *ancoraggio* è l'oggetto che specifica la posizione semplice di un controllo sul lato sinistro, destro, superiore o inferiore del form.  
  
 Il vantaggio del raggruppamento rispetto all'ancoraggio è che i controlli <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.StatusStrip> possono condividere lo spazio orizzontale o verticale con altri controlli.  
  
 La maggior parte dei controlli <xref:System.Windows.Forms.ToolStrip> può essere ancorata al form come gli altri controlli, invece di usare il raggruppamento. Si può anche specificare che un <xref:System.Windows.Forms.ToolStrip> controllo possa essere liberamente posizionato sul form rimuovendolo dall'oggetto <xref:System.Windows.Forms.ToolStripContainer> e impostandone la proprietà `Dock` su `None` oppure se ne può specificare la posizione assoluta impostando la rispettiva proprietà <xref:System.Windows.Forms.Control.Location%2A>. Vedere [procedura: spostare un controllo ToolStrip da un oggetto ToolStripContainer a un form](how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form.md).  
  
 Usare uno o più controlli <xref:System.Windows.Forms.ToolStripPanel> per avere più flessibilità, soprattutto per le applicazioni con interfaccia a documenti multipli (MDI) o se non è necessario un oggetto <xref:System.Windows.Forms.ToolStripContainer>. <xref:System.Windows.Forms.ToolStripPanel> fornisce uno spazio ancorabile in cui posizionare e ancorare i controlli <xref:System.Windows.Forms.ToolStrip>, ma non i controlli tradizionali. Per impostazione predefinita, non <xref:System.Windows.Forms.ToolStripPanel> viene visualizzato nella **casella degli strumenti** della finestra di progettazione, ma è possibile inserirlo facendo clic con il pulsante destro del mouse sulla **casella degli strumenti**, quindi **scegliere Scegli elementi**. Si può accedere a <xref:System.Windows.Forms.ToolStripPanel> anche a livello di codice, come a qualsiasi altra classe.  
  
 <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.StatusStrip> consentono l'overflow degli elementi. Il comportamento di questi elementi è simile a quello che hanno sulle barre degli strumenti di Microsoft Office.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica del controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Architettura del controllo ToolStrip](toolstrip-control-architecture.md)

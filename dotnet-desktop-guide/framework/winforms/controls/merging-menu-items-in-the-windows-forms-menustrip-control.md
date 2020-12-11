---
title: Unione delle voci di menu nel controllo MenuStrip
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- merging [Windows Forms], general concepts
ms.assetid: 95e113ba-f362-4dda-8a76-6d95ddc45cee
ms.openlocfilehash: 9fc2b40ef23d72db51853c124095b734a7646cda
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965041"
---
# <a name="merging-menu-items-in-the-windows-forms-menustrip-control"></a>Unione delle voci di menu nel controllo MenuStrip Windows Form
Se si dispone di un'applicazione con interfaccia a documenti multipli (MDI), è possibile unire voci di menu o menu interi dal form figlio nei menu del form padre.  
  
 In questo argomento vengono descritti i concetti di base associati all'Unione delle voci di menu in un'applicazione MDI.  
  
## <a name="general-concepts"></a>Concetti generali  
 Le procedure di Unione coinvolgono sia una destinazione sia un controllo del codice sorgente:  
  
- La destinazione è il <xref:System.Windows.Forms.MenuStrip> controllo nel form padre principale o MDI in cui si uniscono le voci di menu.  
  
- L'origine è il <xref:System.Windows.Forms.MenuStrip> controllo nel form figlio MDI che contiene le voci di menu che si desidera unire nel menu di destinazione.  
  
 La <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> proprietà identifica la voce di menu il cui elenco a discesa viene popolato con i titoli dei figli MDI del form padre MDI corrente. Ad esempio, in genere si elencano elementi figlio MDI attualmente aperti nel menu **finestra** .  
  
 La <xref:System.Windows.Forms.ToolStripMenuItem.IsMdiWindowListEntry%2A> proprietà identifica le voci di menu provenienti da un oggetto <xref:System.Windows.Forms.MenuStrip> in un form figlio MDI.  
  
 È possibile unire le voci di menu in modo manuale o automatico. Le voci di menu si uniscono nello stesso modo per entrambi i metodi, ma il merge viene attivato in modo diverso, come illustrato nelle sezioni "Unione manuale" e "Unione automatica" più avanti in questo argomento. Nell'Unione manuale e automatica, ogni azione di merge influiscono sull'azione di unione successiva.  
  
 <xref:System.Windows.Forms.MenuStrip> l'Unione sposta le voci di menu da una <xref:System.Windows.Forms.ToolStrip> a un'altra anziché clonarle, come nel caso di <xref:System.Windows.Forms.MainMenu> .  
  
## <a name="mergeaction-values"></a>Valori MergeAction  
 Per impostare l'azione merge sulle voci di menu nell'origine <xref:System.Windows.Forms.MenuStrip> , utilizzare la <xref:System.Windows.Forms.MergeAction> Proprietà.  
  
 Nella tabella seguente viene descritto il significato e l'utilizzo tipico delle azioni di merge disponibili.  
  
|Valore MergeAction|Descrizione|Utilizzo tipico|  
|-----------------------|-----------------|-----------------|  
|<xref:System.Windows.Forms.MergeAction.Append>|Predefinita Aggiunge l'elemento di origine alla fine della raccolta dell'elemento di destinazione.|Aggiunta di voci di menu alla fine del menu quando viene attivata una parte del programma.|  
|<xref:System.Windows.Forms.MergeAction.Insert>|Aggiunge l'elemento di origine alla raccolta dell'elemento di destinazione, nella posizione specificata dal <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> set di proprietà per l'elemento di origine.|Aggiunta di voci di menu al centro o all'inizio del menu quando viene attivata una parte del programma.<br /><br /> Se il valore di <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> è lo stesso per entrambe le voci di menu, viene aggiunto in ordine inverso. Impostare <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> in modo appropriato per mantenere l'ordine originale.|  
|<xref:System.Windows.Forms.MergeAction.Replace>|Trova una corrispondenza di testo o utilizza il <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> valore se non viene trovata alcuna corrispondenza di testo, quindi sostituisce la voce di menu di destinazione corrispondente con la voce di menu di origine.|Sostituzione di una voce di menu di destinazione con una voce di menu di origine con lo stesso nome che esegue un'operazione differente.|  
|<xref:System.Windows.Forms.MergeAction.MatchOnly>|Trova una corrispondenza di testo o usa il <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> valore se non viene trovata alcuna corrispondenza di testo, quindi aggiunge tutti gli elementi a discesa dall'origine alla destinazione.|Compilazione di una struttura di menu che inserisce o aggiunge voci di menu in un sottomenu o rimuove le voci di menu da un sottomenu. Ad esempio, è possibile aggiungere una voce di menu da un figlio MDI a un <xref:System.Windows.Forms.MenuStrip> menu principale **Salva con nome** .<br /><br /> <xref:System.Windows.Forms.MergeAction.MatchOnly> consente di spostarsi nella struttura dei menu senza eseguire alcuna azione. Fornisce un modo per valutare gli elementi successivi.|  
|<xref:System.Windows.Forms.MergeAction.Remove>|Trova una corrispondenza di testo o usa il <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> valore se non viene trovata alcuna corrispondenza di testo e quindi rimuove l'elemento dalla destinazione.|Rimozione di una voce di menu dalla destinazione <xref:System.Windows.Forms.MenuStrip> .|  
  
## <a name="manual-merging"></a>Unione manuale  
 Solo i <xref:System.Windows.Forms.MenuStrip> controlli partecipano all'Unione automatica. Per combinare gli elementi di altri controlli, ad esempio <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.StatusStrip> i controlli e, è necessario unirli manualmente, chiamando i <xref:System.Windows.Forms.ToolStripManager.Merge%2A> <xref:System.Windows.Forms.ToolStripManager.RevertMerge%2A> metodi e nel codice in base alle esigenze.  
  
## <a name="automatic-merging"></a>Unione automatica  
 È possibile utilizzare l'Unione automatica per le applicazioni MDI attivando il modulo di origine. Per usare un oggetto <xref:System.Windows.Forms.MenuStrip> in un'applicazione MDI, impostare la <xref:System.Windows.Forms.Form.MainMenuStrip%2A> proprietà sulla destinazione <xref:System.Windows.Forms.MenuStrip> in modo che le azioni di unione eseguite sull'origine <xref:System.Windows.Forms.MenuStrip> vengano riflesse nella destinazione <xref:System.Windows.Forms.MenuStrip> .  
  
 È possibile attivare l'Unione automatica attivando sull' <xref:System.Windows.Forms.MenuStrip> origine MDI. Al momento dell'attivazione, l'origine <xref:System.Windows.Forms.MenuStrip> viene unita nella destinazione MDI. Quando un nuovo form diventa attivo, l'Unione viene ripristinata nell'ultimo form e attivata nel nuovo form. È possibile controllare questo comportamento impostando la <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> Proprietà in base alle esigenze <xref:System.Windows.Forms.ToolStripItem> e impostando la <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> proprietà su ogni oggetto <xref:System.Windows.Forms.MenuStrip> .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.MenuStrip>
- [Controllo MenuStrip](menustrip-control-windows-forms.md)
- [Procedura: Creare un elenco di finestre di interfaccia a documenti multipli con MenuStrip](how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)
- [Procedura: Configurare l'unione automatica dei menu per applicazioni con interfaccia a documenti multipli](how-to-set-up-automatic-menu-merging-for-mdi-applications.md)

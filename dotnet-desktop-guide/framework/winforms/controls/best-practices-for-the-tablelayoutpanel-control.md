---
title: Suggerimenti per il controllo TableLayoutPanel
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- TableLayoutPanel control [Windows Forms], best practices
- forms [Windows Forms], best practices
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- layout [Windows Forms], AutoSize
- layout [Windows Forms], best practices
- best practices [Windows Forms], tableLayoutPanel control
- sizing [Windows Forms], automatic
- automatic sizing
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
ms.openlocfilehash: e46d0fe6913bec61bd56199b7cb56a9b24d15bd0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962242"
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a>Suggerimenti per il controllo TableLayoutPanel
Il <xref:System.Windows.Forms.TableLayoutPanel> controllo fornisce potenti funzionalità di layout che è opportuno prendere in considerazione prima di utilizzare nel Windows Forms.

## <a name="recommendations"></a>Consigli
 I suggerimenti seguenti consentono di usare il <xref:System.Windows.Forms.TableLayoutPanel> controllo per il migliore vantaggio.

### <a name="targeted-use"></a>Utilizzo mirato
 Utilizzare il <xref:System.Windows.Forms.TableLayoutPanel> controllo con moderazione. Non è consigliabile usarlo in tutte le situazioni che richiedono un layout ridimensionabile. Nell'elenco seguente vengono descritti i layout che traggono vantaggio dalla maggior parte dell'utilizzo del <xref:System.Windows.Forms.TableLayoutPanel> controllo:

- Layout in cui sono presenti più parti del modulo che si ridimensionano in modo proporzionale.

- Layout che verranno modificati o generati dinamicamente in fase di esecuzione, ad esempio moduli di immissione dati con campi personalizzabili dall'utente aggiunti o sottratti in base alle preferenze.

- Layout che devono rimanere a una dimensione complessiva fissa. Ad esempio, è possibile disporre di una finestra di dialogo che deve rimanere inferiore a 800 x 600, ma è necessario supportare le stringhe localizzate.

 Nell'elenco seguente vengono descritti i layout che non traggono un vantaggio notevole dall'utilizzo del <xref:System.Windows.Forms.TableLayoutPanel> controllo:

- Moduli di immissione dati semplici con una singola colonna di etichette e una singola colonna di aree di immissione di testo.

- Moduli con un'unica area di visualizzazione di grandi dimensioni che riempie tutto lo spazio disponibile quando si verifica un ridimensionamento. Un esempio è un modulo che visualizza un singolo <xref:System.Windows.Forms.PropertyGrid> controllo. In questo caso, usare l'ancoraggio, perché non è necessario espandere nient'altro quando il form viene ridimensionato.

 Scegliere con attenzione quali controlli devono trovarsi in un <xref:System.Windows.Forms.TableLayoutPanel> controllo. Se è possibile aumentare il 30% del testo usando l'ancoraggio, provare a usare <xref:System.Windows.Forms.Control.Anchor%2A> solo la proprietà. Se è possibile stimare lo spazio richiesto dal layout, l'utilizzo di <xref:System.Windows.Forms.Control.Dock%2A> e <xref:System.Windows.Forms.Control.Anchor%2A> risulta più semplice rispetto alla stima dei dettagli dello spazio e del comportamento rimanenti <xref:System.Windows.Forms.Control.AutoSize%2A> .

 In generale, quando si progetta il layout con il <xref:System.Windows.Forms.TableLayoutPanel> controllo, è possibile semplificare la progettazione.

### <a name="use-the-document-outline-window"></a>Utilizzare la finestra Struttura documento
 La finestra Struttura documento fornisce una visualizzazione albero del layout, che è possibile utilizzare per modificare le relazioni tra l'ordine z e l'elemento padre-figlio dei controlli. Scegliere **altre finestre** dal **menu Visualizza**, quindi **struttura documento**.

### <a name="avoid-nesting"></a>Evitare l'annidamento
 Evitare di annidare altri <xref:System.Windows.Forms.TableLayoutPanel> controlli all'interno di un <xref:System.Windows.Forms.TableLayoutPanel> controllo. Il debug di layout annidati può essere difficile.

### <a name="avoid-visual-inheritance"></a>Evitare l'ereditarietà visiva
 Il <xref:System.Windows.Forms.TableLayoutPanel> controllo non supporta l'ereditarietà visiva nell'progettazione Windows Form in Visual Studio. Un <xref:System.Windows.Forms.TableLayoutPanel> controllo in una classe derivata viene visualizzato come "bloccato" in fase di progettazione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>

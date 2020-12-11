---
title: Modificare il ritardo del componente della descrizione comando
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
ms.openlocfilehash: 8ab0b0760e8c82d752eaada19f14cae57fa63fdc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963958"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a>Procedura: Modificare il ritardo del componente ToolTip di Windows Forms
Sono disponibili più valori di ritardo che è possibile impostare per un <xref:System.Windows.Forms.ToolTip> componente Windows Forms. L'unità di misura per tutte queste proprietà è in millisecondi. La <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> proprietà determina per quanto tempo l'utente deve puntare al controllo associato affinché venga visualizzata la stringa della descrizione comando. La <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> proprietà imposta il numero di millisecondi necessari per la visualizzazione delle stringhe di descrizione comando successive quando il mouse passa da un controllo associato alla descrizione comando a un altro. La <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> proprietà determina il periodo di tempo in cui viene visualizzata la stringa della descrizione comando. È possibile impostare questi valori singolarmente oppure impostando il valore della <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> Proprietà. le altre proprietà delay vengono impostate in base al valore assegnato alla <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> Proprietà. Ad esempio, quando <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> è impostato su un valore n, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> viene impostato su n, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> viene impostato sul valore di <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> diviso per cinque (o N/5) e <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> viene impostato su un valore che corrisponde a cinque volte il valore della <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> Proprietà (o 5N).  
  
### <a name="to-set-the-delay"></a>Per impostare il ritardo  
  
1. Impostare le proprietà seguenti, come illustrato in questo esempio.  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica del componente ToolTip](tooltip-component-overview-windows-forms.md)
- [Procedura: Impostare le descrizioni comando per i controlli in un Windows Form in fase di progettazione](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [Componente ToolTip](tooltip-component-windows-forms.md)

---
title: Ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox
ms.date: 03/30/2017
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
ms.openlocfilehash: dee969d777edf76434622fe632f7e934987a1dc3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960964"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Procedura: Ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox di Windows Forms
I controlli Windows Forms non vengono ordinati quando sono associati a dati. Per visualizzare i dati ordinati, utilizzare un'origine dei dati che supporti l'ordinamento e quindi fare in modo che l'origine dati venga ordinata. Le origini dati che supportano l'ordinamento sono viste dati, gestori visualizzazione dati e matrici ordinate.  
  
 Se il controllo non è associato a dati, è possibile ordinarlo.  
  
### <a name="to-sort-the-list"></a>Per ordinare l'elenco  
  
1. Impostare la proprietà `Sorted` su `true`.  
  
     Questa impostazione riposiziona tutti gli elementi dell'elenco esistenti in base all'ordinamento.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [Data binding di Windows Form](../windows-forms-data-binding.md)
- [Procedura: Aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox di Windows Forms](add-and-remove-items-from-a-wf-combobox.md)
- [Quando utilizzare un controllo ComboBox Windows Form anziché un controllo ListBox](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [Controlli Windows Form usati per elencare opzioni](windows-forms-controls-used-to-list-options.md)

---
title: 'Procedura: impostare la proprietà di sola lettura per un controllo TextBox'
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 45fda33b5840bd89dac8d9e99f7dd1a8dd065838
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966631"
---
# <a name="how-to-make-a-textbox-control-read-only"></a>Procedura: impostare la proprietà di sola lettura per un controllo TextBox
Questo esempio illustra come configurare un <xref:System.Windows.Controls.TextBox> controllo in modo da non consentire l'input o la modifica dell'utente.  
  
## <a name="example"></a>Esempio  
 Per impedire agli utenti di modificare il contenuto di un <xref:System.Windows.Controls.TextBox> controllo, impostare l' <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attributo su **true**.  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 L' <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attributo influisce solo sull'input dell'utente e non influisce sul set di testo nella [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] Descrizione di un <xref:System.Windows.Controls.TextBox> controllo o su un set di testo a livello di codice tramite la <xref:System.Windows.Controls.TextBox.Text%2A> Proprietà.  
  
 Il valore predefinito di <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> è **false**.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
- [Cenni generali sul controllo RichTextBox](richtextbox-overview.md)

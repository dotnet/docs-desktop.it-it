---
title: 'Procedura: attivare i caratteri di tabulazione in un controllo TextBox'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], enabling tab characters
- tab characters [WPF], enabling
ms.assetid: 14b1b064-61f7-4958-be63-88d85b868d03
ms.openlocfilehash: 9a01ae93d1b75c604fbe4f15f720e0a84086bd1a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967360"
---
# <a name="how-to-enable-tab-characters-in-a-textbox-control"></a>Procedura: attivare i caratteri di tabulazione in un controllo TextBox
Questo esempio illustra come abilitare l'accettazione dei caratteri di tabulazione come input normale in un <xref:System.Windows.Controls.TextBox> controllo.  
  
## <a name="example"></a>Esempio  
 Per consentire l'accettazione dei caratteri di tabulazione come input in un <xref:System.Windows.Controls.TextBox> controllo, impostare l' <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsTab%2A> attributo su **true**.  
  
 [!code-xaml[TextBox_EnablingTab#_AcceptsTab](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_EnablingTab/CS/Window1.xaml#_acceptstab)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
- [Cenni generali sul controllo RichTextBox](richtextbox-overview.md)

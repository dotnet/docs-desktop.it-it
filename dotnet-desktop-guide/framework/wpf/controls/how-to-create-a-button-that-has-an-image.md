---
title: "Procedura: creare un pulsante con un'immagine"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
ms.openlocfilehash: 5be928ac75ad727feabcde07ac0c6dc76ed130e6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969481"
---
# <a name="how-to-create-a-button-that-has-an-image"></a>Procedura: creare un pulsante con un'immagine
Questo esempio illustra come includere un'immagine in un oggetto <xref:System.Windows.Controls.Button> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono creati due <xref:System.Windows.Controls.Button> controlli. Una <xref:System.Windows.Controls.Button> contiene testo e l'altra contiene un'immagine. L'immagine si trova in una cartella denominata data, ovvero una sottocartella della cartella del progetto dell'esempio. Quando un utente fa clic sull'oggetto <xref:System.Windows.Controls.Button> con l'immagine, lo sfondo e il testo dell'altra <xref:System.Windows.Controls.Button> modifica.  
  
 Questo esempio crea <xref:System.Windows.Controls.Button> controlli usando il markup, ma usa il codice per scrivere i <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestori eventi.  
  
 [!code-xaml[BtnColor#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Controlli](index.md)
- [Libreria di controlli](control-library.md)

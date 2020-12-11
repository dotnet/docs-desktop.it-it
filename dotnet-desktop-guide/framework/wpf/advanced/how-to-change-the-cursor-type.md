---
title: 'Procedura: modificare il tipo di cursore'
description: Modificare il cursore del puntatore del mouse per un elemento e per un'applicazione in Windows Presentation Foundation. Questo esempio è costituito da XAML e da un file code-behind.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
ms.openlocfilehash: 54b4dcbed1b92164d3ed9b4c1c9f9a9f8c760ae7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965002"
---
# <a name="how-to-change-the-cursor-type"></a>Procedura: modificare il tipo di cursore
Questo esempio illustra come modificare l'oggetto <xref:System.Windows.Input.Cursor> del puntatore del mouse per un elemento specifico e per l'applicazione.  
  
 Questo esempio è costituito da un file [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] e da un file code-behind.  
  
## <a name="example"></a>Esempio  
 Viene creata l'interfaccia utente, costituita da un oggetto <xref:System.Windows.Controls.ComboBox> per selezionare l'oggetto desiderato <xref:System.Windows.Input.Cursor> , una coppia di <xref:System.Windows.Controls.RadioButton> oggetti per determinare se la modifica del cursore viene applicata solo a un singolo elemento o si applica all'intera applicazione e a un oggetto <xref:System.Windows.Controls.Border> che è l'elemento a cui viene applicato il nuovo cursore.  
  
 [!code-xaml[cursors#ChangeCursorsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 Il codice sottostante seguente crea un <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> gestore eventi che viene chiamato quando il tipo di cursore viene modificato in <xref:System.Windows.Controls.ComboBox> .  Un'istruzione switch filtra sul nome del cursore e imposta la <xref:System.Windows.FrameworkElement.Cursor%2A> proprietà nell'oggetto, <xref:System.Windows.Controls.Border> denominato *DisplayArea*.  
  
 Se la modifica del cursore è impostata su "intera applicazione", la <xref:System.Windows.Input.Mouse.OverrideCursor%2A> proprietà viene impostata sulla <xref:System.Windows.FrameworkElement.Cursor%2A> proprietà del <xref:System.Windows.Controls.Border> controllo.  In questo modo si impone la modifica del cursore per l'intera applicazione.  
  
 [!code-csharp[cursors#ChangeCursorsSample](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'input](input-overview.md)

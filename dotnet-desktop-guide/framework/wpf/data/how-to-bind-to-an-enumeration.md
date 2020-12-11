---
title: "Procedura: eseguire l'associazione a un'enumerazione"
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: c92f1f00aa3feb37b70aa9a3647265236a1625b2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951619"
---
# <a name="how-to-bind-to-an-enumeration"></a>Procedura: eseguire l'associazione a un'enumerazione
In questo esempio viene illustrato come eseguire l'associazione a un'enumerazione mediante l'associazione al metodo GetValues dell'enumerazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente <xref:System.Windows.Controls.ListBox> viene visualizzato l'elenco dei valori di <xref:System.Windows.HorizontalAlignment> enumerazione tramite Data Binding. <xref:System.Windows.Controls.ListBox>E <xref:System.Windows.Controls.Button> sono associati in modo che sia possibile modificare il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> valore della proprietà dell'oggetto <xref:System.Windows.Controls.Button> selezionando un valore in <xref:System.Windows.Controls.ListBox> .  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a>Vedere anche

- [Eseguire l'associazione a un metodo](how-to-bind-to-a-method.md)
- [Panoramica sul data binding](/dotnet/desktop-wpf/data/data-binding-overview)
- [Procedure](data-binding-how-to-topics.md)

---
title: 'Procedura: associare un controllo ListBox ai dati'
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
ms.openlocfilehash: 4dea53a524247d18628b3e7e7b2c06906dced53d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969529"
---
# <a name="how-to-bind-a-listbox-to-data"></a>Procedura: associare un controllo ListBox ai dati
Uno sviluppatore di applicazioni può creare <xref:System.Windows.Controls.ListBox> controlli senza specificarne il contenuto <xref:System.Windows.Controls.ListBoxItem> separatamente. È possibile utilizzare data binding per associare i dati ai singoli elementi.  
  
 Nell'esempio seguente viene illustrato come creare un oggetto <xref:System.Windows.Controls.ListBox> che popola gli <xref:System.Windows.Controls.ListBoxItem> elementi per data binding a un'origine dati denominata *colori*. In questo caso non è necessario usare <xref:System.Windows.Controls.ListBoxItem> i tag per specificare il contenuto di ogni elemento.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[ListBoxEvent#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.Controls.ListBoxItem>
- [Controlli](../advanced/optimizing-performance-controls.md)

---
title: 'Procedura: utilizzare il modello Master-Details con dati XML gerarchici'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: 0fe42d57fcaf4acee09340fdb3f5df73d7291566
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964555"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a>Procedura: utilizzare il modello Master-Details con dati XML gerarchici
In questo esempio viene illustrato come implementare lo scenario Master-Details con i dati XML.  
  
## <a name="example"></a>Esempio  
 Questo esempio è la versione dei dati XML dell'esempio illustrato in [usare il modello di Master-Detail con i dati gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-data.md). In questo esempio, i dati sono dal file `League.xml` . Si noti come il terzo <xref:System.Windows.Controls.ListBox> controllo tiene traccia delle modifiche apportate alla selezione nella seconda <xref:System.Windows.Controls.ListBox> associazione alla relativa <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> Proprietà.  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.HierarchicalDataTemplate>
- [Procedure](data-binding-how-to-topics.md)

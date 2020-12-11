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
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="b4c94-102">Procedura: utilizzare il modello Master-Details con dati XML gerarchici</span><span class="sxs-lookup"><span data-stu-id="b4c94-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="b4c94-103">In questo esempio viene illustrato come implementare lo scenario Master-Details con i dati XML.</span><span class="sxs-lookup"><span data-stu-id="b4c94-103">This example shows how to implement the master-detail scenario with XML data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4c94-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="b4c94-104">Example</span></span>  
 <span data-ttu-id="b4c94-105">Questo esempio è la versione dei dati XML dell'esempio illustrato in [usare il modello di Master-Detail con i dati gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span><span class="sxs-lookup"><span data-stu-id="b4c94-105">This example is the XML data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="b4c94-106">In questo esempio, i dati sono dal file `League.xml` .</span><span class="sxs-lookup"><span data-stu-id="b4c94-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="b4c94-107">Si noti come il terzo <xref:System.Windows.Controls.ListBox> controllo tiene traccia delle modifiche apportate alla selezione nella seconda <xref:System.Windows.Controls.ListBox> associazione alla relativa <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="b4c94-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="b4c94-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4c94-108">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="b4c94-109">Procedure</span><span class="sxs-lookup"><span data-stu-id="b4c94-109">How-to Topics</span></span>](data-binding-how-to-topics.md)

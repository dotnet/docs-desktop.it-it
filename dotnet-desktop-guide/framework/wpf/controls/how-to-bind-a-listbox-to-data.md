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
# <a name="how-to-bind-a-listbox-to-data"></a><span data-ttu-id="06411-102">Procedura: associare un controllo ListBox ai dati</span><span class="sxs-lookup"><span data-stu-id="06411-102">How to: Bind a ListBox to Data</span></span>
<span data-ttu-id="06411-103">Uno sviluppatore di applicazioni può creare <xref:System.Windows.Controls.ListBox> controlli senza specificarne il contenuto <xref:System.Windows.Controls.ListBoxItem> separatamente.</span><span class="sxs-lookup"><span data-stu-id="06411-103">An application developer can create <xref:System.Windows.Controls.ListBox> controls without specifying the contents of each <xref:System.Windows.Controls.ListBoxItem> separately.</span></span> <span data-ttu-id="06411-104">È possibile utilizzare data binding per associare i dati ai singoli elementi.</span><span class="sxs-lookup"><span data-stu-id="06411-104">You can use data binding to bind data to the individual items.</span></span>  
  
 <span data-ttu-id="06411-105">Nell'esempio seguente viene illustrato come creare un oggetto <xref:System.Windows.Controls.ListBox> che popola gli <xref:System.Windows.Controls.ListBoxItem> elementi per data binding a un'origine dati denominata *colori*.</span><span class="sxs-lookup"><span data-stu-id="06411-105">The following example shows how to create a <xref:System.Windows.Controls.ListBox> that populates the <xref:System.Windows.Controls.ListBoxItem> elements by data binding to a data source called *Colors*.</span></span> <span data-ttu-id="06411-106">In questo caso non è necessario usare <xref:System.Windows.Controls.ListBoxItem> i tag per specificare il contenuto di ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="06411-106">In this case it is not necessary to use <xref:System.Windows.Controls.ListBoxItem> tags to specify the content of each item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06411-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="06411-107">Example</span></span>  
 [!code-xaml[ListBoxEvent#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="06411-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06411-108">See also</span></span>

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.Controls.ListBoxItem>
- [<span data-ttu-id="06411-109">Controlli</span><span class="sxs-lookup"><span data-stu-id="06411-109">Controls</span></span>](../advanced/optimizing-performance-controls.md)

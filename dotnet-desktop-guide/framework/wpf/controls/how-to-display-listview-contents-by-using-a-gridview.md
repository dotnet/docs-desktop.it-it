---
title: 'Procedura: visualizzare il contenuto di ListView utilizzando un oggetto GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 9b467c95d541c326a41d1ed4bd9eb5c87e25bd5c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968593"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a><span data-ttu-id="665f8-102">Procedura: visualizzare il contenuto di ListView utilizzando un oggetto GridView</span><span class="sxs-lookup"><span data-stu-id="665f8-102">How to: Display ListView Contents by Using a GridView</span></span>
<span data-ttu-id="665f8-103">Questo esempio illustra come definire una <xref:System.Windows.Controls.GridView> modalità di visualizzazione per un <xref:System.Windows.Controls.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="665f8-103">This example shows how to define a <xref:System.Windows.Controls.GridView> view mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="665f8-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="665f8-104">Example</span></span>  
 <span data-ttu-id="665f8-105">È possibile definire la modalità di visualizzazione di un oggetto <xref:System.Windows.Controls.GridView> specificando <xref:System.Windows.Controls.GridViewColumn> gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="665f8-105">You can define the view mode of a <xref:System.Windows.Controls.GridView> by specifying <xref:System.Windows.Controls.GridViewColumn> objects.</span></span> <span data-ttu-id="665f8-106">Nell'esempio seguente viene illustrato come definire <xref:System.Windows.Controls.GridViewColumn> gli oggetti che si associano al contenuto di dati specificato per il <xref:System.Windows.Controls.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="665f8-106">The following example shows how to define <xref:System.Windows.Controls.GridViewColumn> objects that bind to the data content that is specified for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="665f8-107"><xref:System.Windows.Controls.GridView>In questo esempio vengono specificati tre <xref:System.Windows.Controls.GridViewColumn> oggetti che vengono mappati ai `FirstName` `LastName` campi, e `EmployeeNumber` dell'oggetto `EmployeeInfoDataSource` impostato come del <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="665f8-107">This <xref:System.Windows.Controls.GridView> example specifies three <xref:System.Windows.Controls.GridViewColumn> objects that map to the `FirstName`, `LastName`, and `EmployeeNumber` fields of the `EmployeeInfoDataSource` that is set as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> of the <xref:System.Windows.Controls.ListView> control.</span></span>  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 <span data-ttu-id="665f8-108">Nell'illustrazione seguente viene illustrato come viene visualizzato questo esempio.</span><span class="sxs-lookup"><span data-stu-id="665f8-108">The following illustration shows how this example appears.</span></span>  
  
 ![Screenshot che mostra un ListView con l'output di GridView.](./media/gridview-overview/listview-gridview-output.jpg)  
  
## <a name="see-also"></a><span data-ttu-id="665f8-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="665f8-110">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="665f8-111">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="665f8-111">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="665f8-112">Cenni preliminari su GridView</span><span class="sxs-lookup"><span data-stu-id="665f8-112">GridView Overview</span></span>](gridview-overview.md)
- [<span data-ttu-id="665f8-113">Procedure</span><span class="sxs-lookup"><span data-stu-id="665f8-113">How-to Topics</span></span>](listview-how-to-topics.md)

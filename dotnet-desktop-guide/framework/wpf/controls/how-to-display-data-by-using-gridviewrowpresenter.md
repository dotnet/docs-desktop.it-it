---
title: 'Procedura: visualizzare i dati utilizzando GridViewRowPresenter'
ms.date: 03/30/2017
helpviewer_keywords:
- displaying data with GridViewRowPresenter [WPF]
- GridViewRowPresenter [WPF]
ms.assetid: bdb785a5-a262-44d5-a517-ea14383e5f70
ms.openlocfilehash: 0e471df3ab6fd10417fc58ece4cdb8ff1c457c95
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968617"
---
# <a name="how-to-display-data-by-using-gridviewrowpresenter"></a><span data-ttu-id="c14ce-102">Procedura: visualizzare i dati utilizzando GridViewRowPresenter</span><span class="sxs-lookup"><span data-stu-id="c14ce-102">How to: Display Data by Using GridViewRowPresenter</span></span>
<span data-ttu-id="c14ce-103">Questo esempio illustra come usare gli <xref:System.Windows.Controls.GridViewRowPresenter> oggetti e <xref:System.Windows.Controls.GridViewHeaderRowPresenter> per visualizzare i dati nelle colonne.</span><span class="sxs-lookup"><span data-stu-id="c14ce-103">This example shows how to use the <xref:System.Windows.Controls.GridViewRowPresenter> and <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objects to display data in columns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c14ce-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c14ce-104">Example</span></span>  
 <span data-ttu-id="c14ce-105">Nell'esempio seguente viene illustrato come specificare un <xref:System.Windows.Controls.GridViewColumnCollection> oggetto che visualizza <xref:System.DateTime.DayOfWeek%2A> e <xref:System.DateTime.Year%2A> di un <xref:System.DateTime> oggetto utilizzando <xref:System.Windows.Controls.GridViewRowPresenter> <xref:System.Windows.Controls.GridViewHeaderRowPresenter> gli oggetti e.</span><span class="sxs-lookup"><span data-stu-id="c14ce-105">The following example shows how to specify a <xref:System.Windows.Controls.GridViewColumnCollection> that displays the <xref:System.DateTime.DayOfWeek%2A> and <xref:System.DateTime.Year%2A> of a <xref:System.DateTime> object by using <xref:System.Windows.Controls.GridViewRowPresenter> and <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objects.</span></span> <span data-ttu-id="c14ce-106">Nell'esempio viene inoltre definito un oggetto <xref:System.Windows.Style> per l'oggetto <xref:System.Windows.Controls.GridViewColumn.Header%2A> di un oggetto <xref:System.Windows.Controls.GridViewColumn> .</span><span class="sxs-lookup"><span data-stu-id="c14ce-106">The example also defines a <xref:System.Windows.Style> for the <xref:System.Windows.Controls.GridViewColumn.Header%2A> of a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[GridViewRowPresenterSample#GridViewRowPresenter](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## <a name="see-also"></a><span data-ttu-id="c14ce-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c14ce-107">See also</span></span>

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewColumnCollection>
- [<span data-ttu-id="c14ce-108">Cenni preliminari su GridView</span><span class="sxs-lookup"><span data-stu-id="c14ce-108">GridView Overview</span></span>](gridview-overview.md)

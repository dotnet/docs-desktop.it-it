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
# <a name="how-to-display-data-by-using-gridviewrowpresenter"></a>Procedura: visualizzare i dati utilizzando GridViewRowPresenter
Questo esempio illustra come usare gli <xref:System.Windows.Controls.GridViewRowPresenter> oggetti e <xref:System.Windows.Controls.GridViewHeaderRowPresenter> per visualizzare i dati nelle colonne.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare un <xref:System.Windows.Controls.GridViewColumnCollection> oggetto che visualizza <xref:System.DateTime.DayOfWeek%2A> e <xref:System.DateTime.Year%2A> di un <xref:System.DateTime> oggetto utilizzando <xref:System.Windows.Controls.GridViewRowPresenter> <xref:System.Windows.Controls.GridViewHeaderRowPresenter> gli oggetti e. Nell'esempio viene inoltre definito un oggetto <xref:System.Windows.Style> per l'oggetto <xref:System.Windows.Controls.GridViewColumn.Header%2A> di un oggetto <xref:System.Windows.Controls.GridViewColumn> .  
  
 [!code-xaml[GridViewRowPresenterSample#GridViewRowPresenter](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewColumnCollection>
- [Cenni preliminari su GridView](gridview-overview.md)

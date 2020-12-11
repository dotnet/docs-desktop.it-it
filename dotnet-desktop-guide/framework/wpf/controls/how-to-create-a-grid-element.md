---
title: 'Procedura: creare un elemento Grid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
ms.openlocfilehash: c87ca1d6642bd18fa85806c92caab049d259d45e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969454"
---
# <a name="how-to-create-a-grid-element"></a>Procedura: creare un elemento Grid
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare e utilizzare un'istanza di utilizzando <xref:System.Windows.Controls.Grid> o il [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] codice. In questo esempio vengono utilizzati tre <xref:System.Windows.Controls.ColumnDefinition> oggetti e tre <xref:System.Windows.Controls.RowDefinition> oggetti per creare una griglia con nove celle, ad esempio in un foglio di foglio. Ogni cella contiene un <xref:System.Windows.Controls.TextBlock> elemento che rappresenta i dati e la riga superiore contiene un oggetto <xref:System.Windows.Controls.TextBlock> con la <xref:System.Windows.Controls.Grid.ColumnSpan%2A> proprietà applicata. Per visualizzare i limiti di ogni cella, la <xref:System.Windows.Controls.Grid.ShowGridLines%2A> proprietà è abilitata.  
  
 [!code-csharp[Grid#3](~/samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](~/samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
  Entrambi gli approcci genereranno un'interfaccia utente simile a quella riportata di seguito.

  ![una schermata illustra un'interfaccia utente WPF che contiene una griglia suddivisa in tre colonne.  Contiene il titolo "prodotti 2018 spediti" spanning di tutte le colonne della prima riga e tre colonne ognuna con le cifre di vendita per un determinato trimestre.  Il testo della riga inferiore è esteso a due colonne con il messaggio "Total Units: 300.000"](././media/how-to-create-a-grid-element/how-to-create-a-grid-element.png)
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Grid>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)

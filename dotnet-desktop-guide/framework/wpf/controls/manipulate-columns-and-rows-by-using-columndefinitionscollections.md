---
title: 'Procedura: modificare colonne e righe utilizzando ColumnDefinitionsCollection e RowDefinitionsCollection'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Grid class
- Grid control [WPF], ColumnDefinitionCollection class
- Grid control [WPF], RowDefinitionCollection class
ms.assetid: bfc7160a-45f2-4e17-9961-df414dfb13c5
ms.openlocfilehash: 2f6d174fd54dca3744e5967f198c645e01a94fe5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966952"
---
# <a name="how-to-manipulate-columns-and-rows-by-using-columndefinitionscollections-and-rowdefinitionscollections"></a>Procedura: modificare colonne e righe utilizzando ColumnDefinitionsCollection e RowDefinitionsCollection
Questo esempio illustra come usare i metodi delle <xref:System.Windows.Controls.ColumnDefinitionCollection> <xref:System.Windows.Controls.RowDefinitionCollection> classi e per eseguire azioni come l'aggiunta, la cancellazione o il conteggio del contenuto di righe o colonne. Ad esempio, è possibile <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A> , <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A> o <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> gli elementi inclusi in un oggetto <xref:System.Windows.Controls.ColumnDefinition> o <xref:System.Windows.Controls.RowDefinition> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un <xref:System.Windows.Controls.Grid> elemento con un valore <xref:System.Windows.FrameworkElement.Name%2A> di `grid1` . <xref:System.Windows.Controls.Grid>Contiene un oggetto <xref:System.Windows.Controls.StackPanel> che contiene <xref:System.Windows.Controls.Button> elementi, ciascuno controllato da un metodo di raccolta diverso. Quando si fa clic su un oggetto <xref:System.Windows.Controls.Button> , viene attivata una chiamata al metodo nel file code-behind.  
  
 [!code-xaml[ColumnDefinitionsGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml#1)]  
  
 Questo esempio definisce una serie di metodi personalizzati, ognuno corrispondente a un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento nel [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file. È possibile modificare il numero di colonne e righe in <xref:System.Windows.Controls.Grid> in diversi modi, tra cui l'aggiunta o la rimozione di righe e colonne e il conteggio del numero totale di righe e colonne. Per evitare <xref:System.ArgumentOutOfRangeException> <xref:System.ArgumentException> eccezioni e, è possibile utilizzare la funzionalità di controllo degli errori <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> fornita dal metodo.  
  
 [!code-csharp[ColumnDefinitionsGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ColumnDefinitionsGrid#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ColumnDefinitionsGrid/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.ColumnDefinitionCollection>
- <xref:System.Windows.Controls.RowDefinitionCollection>

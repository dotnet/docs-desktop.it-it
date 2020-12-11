---
title: 'Procedura: condividere le proprietà di ridimensionamento tra griglie'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
ms.openlocfilehash: d5ab2ac612d55c8cbc34ae6d7d9d63b9f8aa23e7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969571"
---
# <a name="how-to-share-sizing-properties-between-grids"></a>Procedura: condividere le proprietà di ridimensionamento tra griglie
Questo esempio illustra come condividere i dati di ridimensionamento di colonne e righe tra <xref:System.Windows.Controls.Grid> gli elementi per garantire la coerenza del ridimensionamento.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono introdotti due <xref:System.Windows.Controls.Grid> elementi come elementi figlio di un elemento padre <xref:System.Windows.Controls.DockPanel> . La <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> proprietà associata di <xref:System.Windows.Controls.Grid> è definita nell'elemento padre <xref:System.Windows.Controls.DockPanel> .  
  
 Nell'esempio viene modificato il valore della proprietà utilizzando due <xref:System.Windows.Controls.Button> elementi; ogni elemento rappresenta uno dei valori della proprietà booleana. Quando il <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> valore della proprietà è impostato su `true` , ogni membro di colonna o di riga di un oggetto <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> condivide informazioni sul dimensionamento, indipendentemente dal contenuto di una riga o di una colonna.  
  
 [!code-xaml[gridIssharedsizescopeProp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 ...  
  
 [!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 Il seguente esempio di code-behind gestisce i metodi generati dall' <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento Button. Nell'esempio vengono scritti i risultati di queste chiamate di metodo a <xref:System.Windows.Controls.TextBlock> elementi che utilizzano metodi Get correlati per restituire i nuovi valori di proprietà come stringhe.  
  
 [!code-csharp[gridIssharedsizescopeProp#3](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)

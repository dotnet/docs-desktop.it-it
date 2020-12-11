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
# <a name="how-to-share-sizing-properties-between-grids"></a><span data-ttu-id="36da3-102">Procedura: condividere le proprietà di ridimensionamento tra griglie</span><span class="sxs-lookup"><span data-stu-id="36da3-102">How to: Share Sizing Properties Between Grids</span></span>
<span data-ttu-id="36da3-103">Questo esempio illustra come condividere i dati di ridimensionamento di colonne e righe tra <xref:System.Windows.Controls.Grid> gli elementi per garantire la coerenza del ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="36da3-103">This example shows how to share the sizing data of columns and rows between <xref:System.Windows.Controls.Grid> elements in order to keep sizing consistent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36da3-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="36da3-104">Example</span></span>  
 <span data-ttu-id="36da3-105">Nell'esempio seguente vengono introdotti due <xref:System.Windows.Controls.Grid> elementi come elementi figlio di un elemento padre <xref:System.Windows.Controls.DockPanel> .</span><span class="sxs-lookup"><span data-stu-id="36da3-105">The following example introduces two <xref:System.Windows.Controls.Grid> elements as child elements of a parent <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="36da3-106">La <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> proprietà associata di <xref:System.Windows.Controls.Grid> è definita nell'elemento padre <xref:System.Windows.Controls.DockPanel> .</span><span class="sxs-lookup"><span data-stu-id="36da3-106">The <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> attached property of <xref:System.Windows.Controls.Grid> is defined on the parent <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="36da3-107">Nell'esempio viene modificato il valore della proprietà utilizzando due <xref:System.Windows.Controls.Button> elementi; ogni elemento rappresenta uno dei valori della proprietà booleana.</span><span class="sxs-lookup"><span data-stu-id="36da3-107">The example manipulates the property value by using two <xref:System.Windows.Controls.Button> elements; each element represents one of the Boolean property values.</span></span> <span data-ttu-id="36da3-108">Quando il <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> valore della proprietà è impostato su `true` , ogni membro di colonna o di riga di un oggetto <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> condivide informazioni sul dimensionamento, indipendentemente dal contenuto di una riga o di una colonna.</span><span class="sxs-lookup"><span data-stu-id="36da3-108">When the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> property value is set to `true`, each column or row member of a <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> shares sizing information, regardless of the content of a row or column.</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="36da3-109">...</span><span class="sxs-lookup"><span data-stu-id="36da3-109">...</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="36da3-110">Il seguente esempio di code-behind gestisce i metodi generati dall' <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento Button.</span><span class="sxs-lookup"><span data-stu-id="36da3-110">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event raises.</span></span> <span data-ttu-id="36da3-111">Nell'esempio vengono scritti i risultati di queste chiamate di metodo a <xref:System.Windows.Controls.TextBlock> elementi che utilizzano metodi Get correlati per restituire i nuovi valori di proprietà come stringhe.</span><span class="sxs-lookup"><span data-stu-id="36da3-111">The example writes the results of these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridIssharedsizescopeProp#3](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="36da3-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36da3-112">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>
- [<span data-ttu-id="36da3-113">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="36da3-113">Panels Overview</span></span>](panels-overview.md)

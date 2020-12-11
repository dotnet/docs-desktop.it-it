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
# <a name="how-to-manipulate-columns-and-rows-by-using-columndefinitionscollections-and-rowdefinitionscollections"></a><span data-ttu-id="f589c-102">Procedura: modificare colonne e righe utilizzando ColumnDefinitionsCollection e RowDefinitionsCollection</span><span class="sxs-lookup"><span data-stu-id="f589c-102">How to: Manipulate Columns and Rows by Using ColumnDefinitionsCollections and RowDefinitionsCollections</span></span>
<span data-ttu-id="f589c-103">Questo esempio illustra come usare i metodi delle <xref:System.Windows.Controls.ColumnDefinitionCollection> <xref:System.Windows.Controls.RowDefinitionCollection> classi e per eseguire azioni come l'aggiunta, la cancellazione o il conteggio del contenuto di righe o colonne.</span><span class="sxs-lookup"><span data-stu-id="f589c-103">This example shows how to use the methods in the <xref:System.Windows.Controls.ColumnDefinitionCollection> and <xref:System.Windows.Controls.RowDefinitionCollection> classes to perform actions like adding, clearing, or counting the contents of rows or columns.</span></span> <span data-ttu-id="f589c-104">Ad esempio, è possibile <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A> , <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A> o <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> gli elementi inclusi in un oggetto <xref:System.Windows.Controls.ColumnDefinition> o <xref:System.Windows.Controls.RowDefinition> .</span><span class="sxs-lookup"><span data-stu-id="f589c-104">For example, you can <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>, or <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> the items that are included in a <xref:System.Windows.Controls.ColumnDefinition> or <xref:System.Windows.Controls.RowDefinition>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f589c-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="f589c-105">Example</span></span>  
 <span data-ttu-id="f589c-106">Nell'esempio seguente viene creato un <xref:System.Windows.Controls.Grid> elemento con un valore <xref:System.Windows.FrameworkElement.Name%2A> di `grid1` .</span><span class="sxs-lookup"><span data-stu-id="f589c-106">The following example creates a <xref:System.Windows.Controls.Grid> element with a <xref:System.Windows.FrameworkElement.Name%2A> of `grid1`.</span></span> <span data-ttu-id="f589c-107"><xref:System.Windows.Controls.Grid>Contiene un oggetto <xref:System.Windows.Controls.StackPanel> che contiene <xref:System.Windows.Controls.Button> elementi, ciascuno controllato da un metodo di raccolta diverso.</span><span class="sxs-lookup"><span data-stu-id="f589c-107">The <xref:System.Windows.Controls.Grid> contains a <xref:System.Windows.Controls.StackPanel> that holds <xref:System.Windows.Controls.Button> elements, each controlled by a different collection method.</span></span> <span data-ttu-id="f589c-108">Quando si fa clic su un oggetto <xref:System.Windows.Controls.Button> , viene attivata una chiamata al metodo nel file code-behind.</span><span class="sxs-lookup"><span data-stu-id="f589c-108">When you click a <xref:System.Windows.Controls.Button>, it activates a method call in the code-behind file.</span></span>  
  
 [!code-xaml[ColumnDefinitionsGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="f589c-109">Questo esempio definisce una serie di metodi personalizzati, ognuno corrispondente a un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento nel [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file.</span><span class="sxs-lookup"><span data-stu-id="f589c-109">This example defines a series of custom methods, each corresponding to a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event in the [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="f589c-110">È possibile modificare il numero di colonne e righe in <xref:System.Windows.Controls.Grid> in diversi modi, tra cui l'aggiunta o la rimozione di righe e colonne e il conteggio del numero totale di righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="f589c-110">You can change the number of columns and rows in the <xref:System.Windows.Controls.Grid> in several ways, which includes adding or removing rows and columns; and counting the total number of rows and columns.</span></span> <span data-ttu-id="f589c-111">Per evitare <xref:System.ArgumentOutOfRangeException> <xref:System.ArgumentException> eccezioni e, è possibile utilizzare la funzionalità di controllo degli errori <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> fornita dal metodo.</span><span class="sxs-lookup"><span data-stu-id="f589c-111">To prevent <xref:System.ArgumentOutOfRangeException> and <xref:System.ArgumentException> exceptions, you can use the error-checking functionality that the <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> method provides.</span></span>  
  
 [!code-csharp[ColumnDefinitionsGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ColumnDefinitionsGrid#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ColumnDefinitionsGrid/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="f589c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f589c-112">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.ColumnDefinitionCollection>
- <xref:System.Windows.Controls.RowDefinitionCollection>

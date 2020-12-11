---
title: 'Procedura: creare controlli TreeView semplici o complessi'
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], creating
- Control class [WPF], TreeView [WPF], creating
ms.assetid: 1defbb78-b8e7-4c0e-b650-576453ac828d
ms.openlocfilehash: 7edb4933ebcc0f0d2cb02754238c2342ee9dd4a2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968632"
---
# <a name="how-to-create-simple-or-complex-treeviews"></a><span data-ttu-id="5d1b2-102">Procedura: creare controlli TreeView semplici o complessi</span><span class="sxs-lookup"><span data-stu-id="5d1b2-102">How to: Create Simple or Complex TreeViews</span></span>
<span data-ttu-id="5d1b2-103">Questo esempio illustra come creare controlli semplici o complessi <xref:System.Windows.Controls.TreeView> .</span><span class="sxs-lookup"><span data-stu-id="5d1b2-103">This example shows how to create simple or complex <xref:System.Windows.Controls.TreeView> controls.</span></span>  
  
 <span data-ttu-id="5d1b2-104">Un oggetto <xref:System.Windows.Controls.TreeView> è costituito da una gerarchia di <xref:System.Windows.Controls.TreeViewItem> controlli, che può contenere semplici stringhe di testo e contenuto più complesso, ad esempio <xref:System.Windows.Controls.Button> controlli o un oggetto <xref:System.Windows.Controls.StackPanel> con contenuto incorporato.</span><span class="sxs-lookup"><span data-stu-id="5d1b2-104">A <xref:System.Windows.Controls.TreeView> consists of a hierarchy of <xref:System.Windows.Controls.TreeViewItem> controls, which can contain simple text strings and also more complex content, such as <xref:System.Windows.Controls.Button> controls or a <xref:System.Windows.Controls.StackPanel> with embedded content.</span></span> <span data-ttu-id="5d1b2-105">È possibile definire in modo esplicito il <xref:System.Windows.Controls.TreeView> contenuto o un'origine dati in grado di fornire il contenuto.</span><span class="sxs-lookup"><span data-stu-id="5d1b2-105">You can explicitly define the <xref:System.Windows.Controls.TreeView> content or a data source can provide the content.</span></span> <span data-ttu-id="5d1b2-106">In questo argomento vengono forniti esempi di questi concetti.</span><span class="sxs-lookup"><span data-stu-id="5d1b2-106">This topic provides examples of these concepts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d1b2-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="5d1b2-107">Example</span></span>  
 <span data-ttu-id="5d1b2-108">La <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> proprietà di <xref:System.Windows.Controls.TreeViewItem> contiene il contenuto <xref:System.Windows.Controls.TreeView> visualizzato da per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="5d1b2-108">The <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property of the <xref:System.Windows.Controls.TreeViewItem> contains the content that the <xref:System.Windows.Controls.TreeView> displays for that item.</span></span> <span data-ttu-id="5d1b2-109">Un oggetto <xref:System.Windows.Controls.TreeViewItem> può inoltre disporre <xref:System.Windows.Controls.TreeViewItem> di controlli come elementi figlio ed è possibile definire questi elementi figlio utilizzando la <xref:System.Windows.Controls.ItemsControl.Items%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="5d1b2-109">A <xref:System.Windows.Controls.TreeViewItem> can also have <xref:System.Windows.Controls.TreeViewItem> controls as its child elements and you can define these child elements by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="5d1b2-110">Nell'esempio seguente viene illustrato come definire in modo esplicito <xref:System.Windows.Controls.TreeViewItem> il contenuto impostando la <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> proprietà su una stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="5d1b2-110">The following example shows how to explicitly define <xref:System.Windows.Controls.TreeViewItem> content by setting the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property to a text string.</span></span>  
  
 [!code-xaml[TreeViewSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="5d1b2-111">Nell'esempio seguente viene illustrato come definire elementi figlio di un oggetto <xref:System.Windows.Controls.TreeViewItem> definendo <xref:System.Windows.Controls.ItemsControl.Items%2A> i <xref:System.Windows.Controls.Button> controlli.</span><span class="sxs-lookup"><span data-stu-id="5d1b2-111">The following example show how to define child elements of a <xref:System.Windows.Controls.TreeViewItem> by defining <xref:System.Windows.Controls.ItemsControl.Items%2A> that are <xref:System.Windows.Controls.Button> controls.</span></span>  
  
 [!code-xaml[TreeViewSimple#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#3)]  
  
 <span data-ttu-id="5d1b2-112">Nell'esempio seguente viene illustrato come creare un oggetto in <xref:System.Windows.Controls.TreeView> cui un oggetto <xref:System.Windows.Data.XmlDataProvider> fornisce <xref:System.Windows.Controls.TreeViewItem> contenuto e un oggetto che <xref:System.Windows.HierarchicalDataTemplate> definisce l'aspetto del contenuto.</span><span class="sxs-lookup"><span data-stu-id="5d1b2-112">The following example shows how to create a <xref:System.Windows.Controls.TreeView> where an <xref:System.Windows.Data.XmlDataProvider> provides <xref:System.Windows.Controls.TreeViewItem> content and a <xref:System.Windows.HierarchicalDataTemplate> defines the appearance of the content.</span></span>  
  
 [!code-xaml[TreeViewSimple#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#6)]  
  
 [!code-xaml[TreeViewSimple#7](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#7)]  
  
 [!code-xaml[TreeViewSimple#5](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#5)]  
  
 <span data-ttu-id="5d1b2-113">Nell'esempio seguente viene illustrato come creare un oggetto in <xref:System.Windows.Controls.TreeView> cui il <xref:System.Windows.Controls.TreeViewItem> contenuto contiene <xref:System.Windows.Controls.DockPanel> controlli con contenuto incorporato.</span><span class="sxs-lookup"><span data-stu-id="5d1b2-113">The following example shows how to create a <xref:System.Windows.Controls.TreeView> where the <xref:System.Windows.Controls.TreeViewItem> content contains <xref:System.Windows.Controls.DockPanel> controls that have embedded content.</span></span>  
  
 [!code-xaml[TreeViewSimple#9](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#9)]  
  
## <a name="see-also"></a><span data-ttu-id="5d1b2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d1b2-114">See also</span></span>

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [<span data-ttu-id="5d1b2-115">Cenni preliminari sul controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="5d1b2-115">TreeView Overview</span></span>](treeview-overview.md)
- [<span data-ttu-id="5d1b2-116">Procedure</span><span class="sxs-lookup"><span data-stu-id="5d1b2-116">How-to Topics</span></span>](treeview-how-to-topics.md)

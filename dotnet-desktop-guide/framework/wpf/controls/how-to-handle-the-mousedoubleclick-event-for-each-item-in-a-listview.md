---
title: "Procedura: gestire l'evento MouseDoubleClick per ciascun elemento di ListView"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 58c17697c5053be267893834e8364c531c1db4de
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968518"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a><span data-ttu-id="8138f-102">Procedura: gestire l'evento MouseDoubleClick per ciascun elemento di ListView</span><span class="sxs-lookup"><span data-stu-id="8138f-102">How to: Handle the MouseDoubleClick Event for Each Item in a ListView</span></span>
<span data-ttu-id="8138f-103">Per gestire un evento per un elemento in un oggetto <xref:System.Windows.Controls.ListView> , è necessario aggiungere un gestore eventi a ognuno di essi <xref:System.Windows.Controls.ListViewItem> .</span><span class="sxs-lookup"><span data-stu-id="8138f-103">To handle an event for an item in a <xref:System.Windows.Controls.ListView>, you need to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span> <span data-ttu-id="8138f-104">Quando un oggetto <xref:System.Windows.Controls.ListView> è associato a un'origine dati, non si crea in modo esplicito un oggetto <xref:System.Windows.Controls.ListViewItem> , ma è possibile gestire l'evento per ogni elemento aggiungendo un oggetto <xref:System.Windows.EventSetter> a uno stile di un oggetto <xref:System.Windows.Controls.ListViewItem> .</span><span class="sxs-lookup"><span data-stu-id="8138f-104">When a <xref:System.Windows.Controls.ListView> is bound to a data source, you don't explicitly create a <xref:System.Windows.Controls.ListViewItem>, but you can handle the event for each item by adding an <xref:System.Windows.EventSetter> to a style of a <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8138f-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="8138f-105">Example</span></span>  
 <span data-ttu-id="8138f-106">Nell'esempio seguente viene creato un oggetto con associazione <xref:System.Windows.Controls.ListView> a dati e viene creato un oggetto <xref:System.Windows.Style> per aggiungere un gestore eventi a ognuno di essi <xref:System.Windows.Controls.ListViewItem> .</span><span class="sxs-lookup"><span data-stu-id="8138f-106">The following example creates a data-bound <xref:System.Windows.Controls.ListView> and creates a <xref:System.Windows.Style> to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="8138f-107">Nell'esempio seguente viene gestito l' <xref:System.Windows.Controls.Control.MouseDoubleClick> evento.</span><span class="sxs-lookup"><span data-stu-id="8138f-107">The following example handles the <xref:System.Windows.Controls.Control.MouseDoubleClick> event.</span></span>  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> <span data-ttu-id="8138f-108">Sebbene sia più comune associare un oggetto <xref:System.Windows.Controls.ListView> a un'origine dati, è possibile utilizzare uno stile per aggiungere un gestore eventi a ogni oggetto <xref:System.Windows.Controls.ListViewItem> in un non associato a dati <xref:System.Windows.Controls.ListView> indipendentemente dal fatto che si crei in modo esplicito un oggetto <xref:System.Windows.Controls.ListViewItem> .</span><span class="sxs-lookup"><span data-stu-id="8138f-108">Although it is most common to bind a <xref:System.Windows.Controls.ListView> to a data source, you can use a style to add an event handler to each <xref:System.Windows.Controls.ListViewItem> in a non-data-bound <xref:System.Windows.Controls.ListView> regardless of whether you explicitly create a <xref:System.Windows.Controls.ListViewItem>.</span></span>  <span data-ttu-id="8138f-109">Per ulteriori informazioni sui controlli creati in modo esplicito e implicito <xref:System.Windows.Controls.ListViewItem> , vedere <xref:System.Windows.Controls.ItemsControl> .</span><span class="sxs-lookup"><span data-stu-id="8138f-109">For more information about explicitly and implicitly created <xref:System.Windows.Controls.ListViewItem> controls, see <xref:System.Windows.Controls.ItemsControl>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8138f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8138f-110">See also</span></span>

- <xref:System.Xml.XmlElement>
- [<span data-ttu-id="8138f-111">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="8138f-111">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="8138f-112">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="8138f-112">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="8138f-113">Eseguire l'associazione a dati XML tramite un oggetto XMLDataProvider e query XPath</span><span class="sxs-lookup"><span data-stu-id="8138f-113">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="8138f-114">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="8138f-114">ListView Overview</span></span>](listview-overview.md)

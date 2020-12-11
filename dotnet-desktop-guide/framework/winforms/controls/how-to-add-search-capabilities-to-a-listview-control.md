---
title: 'Procedura: Aggiungere funzionalità di ricerca a un controllo ListView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- lists [Windows Forms], enabling searching
- list views [Windows Forms], enabling searching
- ListView control [Windows Forms], adding search capabilities
- searching [Windows Forms], adding search capabilities to ListView control
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
ms.openlocfilehash: d5d4dae55fc9f0613ab6535b2fe57e262d0ef141
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963637"
---
# <a name="how-to-add-search-capabilities-to-a-listview-control"></a><span data-ttu-id="dbe1d-102">Procedura: Aggiungere funzionalità di ricerca a un controllo ListView</span><span class="sxs-lookup"><span data-stu-id="dbe1d-102">How to: Add Search Capabilities to a ListView Control</span></span>
<span data-ttu-id="dbe1d-103">Spesso quando si utilizza un elenco di elementi di un controllo di grandi dimensioni <xref:System.Windows.Forms.ListView> , si desidera offrire funzionalità di ricerca all'utente.</span><span class="sxs-lookup"><span data-stu-id="dbe1d-103">Oftentimes when working with a large list of items in a <xref:System.Windows.Forms.ListView> control, you want to offer search capabilities to the user.</span></span> <span data-ttu-id="dbe1d-104">Il <xref:System.Windows.Forms.ListView> controllo offre questa funzionalità in due modi diversi: corrispondenza del testo e ricerca nella posizione.</span><span class="sxs-lookup"><span data-stu-id="dbe1d-104">The <xref:System.Windows.Forms.ListView> control offers this capability in two different ways: text matching and location searching.</span></span>  
  
 <span data-ttu-id="dbe1d-105">Il <xref:System.Windows.Forms.ListView.FindItemWithText%2A> metodo consente di eseguire una ricerca di testo in un <xref:System.Windows.Forms.ListView> elenco o in una visualizzazione dettagli, data una stringa di ricerca e un indice facoltativo iniziale e finale.</span><span class="sxs-lookup"><span data-stu-id="dbe1d-105">The <xref:System.Windows.Forms.ListView.FindItemWithText%2A> method allows you to perform a text search on a <xref:System.Windows.Forms.ListView> in list or details view, given a search string and an optional starting and ending index.</span></span> <span data-ttu-id="dbe1d-106">Al contrario, il <xref:System.Windows.Forms.ListView.FindNearestItem%2A> metodo consente di trovare un elemento in una <xref:System.Windows.Forms.ListView> visualizzazione icona o affiancata, in base a un set di coordinate x e y e a una direzione per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="dbe1d-106">In contrast, the <xref:System.Windows.Forms.ListView.FindNearestItem%2A> method allows you to find an item in a <xref:System.Windows.Forms.ListView> in icon or tile view, given a set of x- and y-coordinates and a direction to search.</span></span>  
  
### <a name="to-find-an-item-using-text"></a><span data-ttu-id="dbe1d-107">Per trovare un elemento usando il testo</span><span class="sxs-lookup"><span data-stu-id="dbe1d-107">To find an item using text</span></span>  
  
1. <span data-ttu-id="dbe1d-108">Creare un oggetto <xref:System.Windows.Forms.ListView> con la <xref:System.Windows.Forms.ListView.View%2A> proprietà impostata su <xref:System.Windows.Forms.View.Details> o <xref:System.Windows.Forms.View.List> , quindi popolare con gli <xref:System.Windows.Forms.ListView> elementi.</span><span class="sxs-lookup"><span data-stu-id="dbe1d-108">Create a <xref:System.Windows.Forms.ListView> with the <xref:System.Windows.Forms.ListView.View%2A> property set to <xref:System.Windows.Forms.View.Details> or <xref:System.Windows.Forms.View.List>, and then populate the <xref:System.Windows.Forms.ListView> with items.</span></span>  
  
2. <span data-ttu-id="dbe1d-109">Chiamare il <xref:System.Windows.Forms.ListView.FindItemWithText%2A> metodo, passando il testo dell'elemento che si desidera trovare.</span><span class="sxs-lookup"><span data-stu-id="dbe1d-109">Call the <xref:System.Windows.Forms.ListView.FindItemWithText%2A> method, passing the text of the item you would like to find.</span></span>  
  
3. <span data-ttu-id="dbe1d-110">Nell'esempio di codice seguente viene illustrato come creare un <xref:System.Windows.Forms.ListView> oggetto di base, compilarlo con gli elementi e utilizzare l'input di testo dall'utente per trovare un elemento nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="dbe1d-110">The following code example demonstrates how to create a basic <xref:System.Windows.Forms.ListView>, populate it with items, and use text input from the user to find an item in the list.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### <a name="to-find-an-item-using-x--and-y-coordinates"></a><span data-ttu-id="dbe1d-111">Per trovare un elemento usando le coordinate x e y</span><span class="sxs-lookup"><span data-stu-id="dbe1d-111">To find an item using x- and y-coordinates</span></span>  
  
1. <span data-ttu-id="dbe1d-112">Creare un oggetto <xref:System.Windows.Forms.ListView> con la <xref:System.Windows.Forms.View> proprietà impostata su <xref:System.Windows.Forms.View.SmallIcon> o <xref:System.Windows.Forms.View.LargeIcon> , quindi popolare con gli <xref:System.Windows.Forms.ListView> elementi.</span><span class="sxs-lookup"><span data-stu-id="dbe1d-112">Create a <xref:System.Windows.Forms.ListView> with the <xref:System.Windows.Forms.View> property set to <xref:System.Windows.Forms.View.SmallIcon> or <xref:System.Windows.Forms.View.LargeIcon>, and then populate the <xref:System.Windows.Forms.ListView> with items.</span></span>  
  
2. <span data-ttu-id="dbe1d-113">Chiamare il <xref:System.Windows.Forms.ListView.FindNearestItem%2A> metodo, passando le coordinate x e y desiderate e la direzione in cui si desidera eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="dbe1d-113">Call the <xref:System.Windows.Forms.ListView.FindNearestItem%2A> method, passing the desired x- and y-coordinates and the direction you would like to search.</span></span>  
  
3. <span data-ttu-id="dbe1d-114">Nell'esempio di codice seguente viene illustrato come creare un'icona di base <xref:System.Windows.Forms.ListView> , compilarla con gli elementi e acquisire l' <xref:System.Windows.Forms.Control.MouseDown> evento per trovare l'elemento più vicino nella direzione verso l'alto.</span><span class="sxs-lookup"><span data-stu-id="dbe1d-114">The following code example demonstrates how to create a basic icon <xref:System.Windows.Forms.ListView>, populate it with items, and capture the <xref:System.Windows.Forms.Control.MouseDown> event to find the nearest item in the up direction.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="dbe1d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbe1d-115">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.FindItemWithText%2A>
- <xref:System.Windows.Forms.ListView.FindNearestItem%2A>
- [<span data-ttu-id="dbe1d-116">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="dbe1d-116">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="dbe1d-117">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="dbe1d-117">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="dbe1d-118">Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dbe1d-118">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)

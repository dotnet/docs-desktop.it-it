---
title: 'Procedura: applicare uno stile a una riga in un ListView che usa GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 586c549cca6ef3089b37427c7983bb39e56509bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951882"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="63fad-102">Procedura: applicare uno stile a una riga in un ListView che implementa una GridView</span><span class="sxs-lookup"><span data-stu-id="63fad-102">How to: Style a Row in a ListView That Implements a GridView</span></span>
<span data-ttu-id="63fad-103">Questo esempio illustra come applicare uno stile a una riga in un <xref:System.Windows.Controls.ListView> controllo che usa una <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> modalità.</span><span class="sxs-lookup"><span data-stu-id="63fad-103">This example shows how to style a row in a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63fad-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="63fad-104">Example</span></span>  
 <span data-ttu-id="63fad-105">È possibile applicare uno stile a una riga in un controllo impostando <xref:System.Windows.Controls.ListView> un oggetto <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> sul <xref:System.Windows.Controls.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="63fad-105">You can style a row in a <xref:System.Windows.Controls.ListView> control by setting an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> on the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="63fad-106">Impostare lo stile per gli elementi rappresentati come <xref:System.Windows.Controls.ListViewItem> oggetti.</span><span class="sxs-lookup"><span data-stu-id="63fad-106">Set the style for its items that are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span> <span data-ttu-id="63fad-107"><xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>Fa riferimento agli <xref:System.Windows.Controls.ControlTemplate> oggetti utilizzati per visualizzare il contenuto della riga.</span><span class="sxs-lookup"><span data-stu-id="63fad-107">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references the <xref:System.Windows.Controls.ControlTemplate> objects that are used to display the row content.</span></span>  
  
 <span data-ttu-id="63fad-108">Nell'esempio completo, da cui vengono estratti gli esempi seguenti, viene visualizzata una raccolta di informazioni sui brani archiviate in un database XML.</span><span class="sxs-lookup"><span data-stu-id="63fad-108">The complete sample, which the following examples are extracted from, displays a collection of song information that is stored in an XML database.</span></span> <span data-ttu-id="63fad-109">Ogni brano nel database include un campo di classificazione e il valore di questo campo specifica la modalità di visualizzazione di una riga di informazioni relative al brano.</span><span class="sxs-lookup"><span data-stu-id="63fad-109">Each song in the database has a rating field and the value of this field specifies how to display a row of song information.</span></span>  
  
 <span data-ttu-id="63fad-110">Nell'esempio seguente viene illustrato come definire <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> per gli <xref:System.Windows.Controls.ListViewItem> oggetti che rappresentano i brani della raccolta Song.</span><span class="sxs-lookup"><span data-stu-id="63fad-110">The following example shows how to define <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> for the <xref:System.Windows.Controls.ListViewItem> objects that represent the songs in the song collection.</span></span> <span data-ttu-id="63fad-111"><xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>Fa riferimento a <xref:System.Windows.Controls.ControlTemplate> oggetti che specificano come visualizzare una riga di informazioni sul brano.</span><span class="sxs-lookup"><span data-stu-id="63fad-111">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references <xref:System.Windows.Controls.ControlTemplate> objects that specify how to display a row of song information.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 <span data-ttu-id="63fad-112">Nell'esempio seguente viene illustrato un oggetto <xref:System.Windows.Controls.ControlTemplate> che aggiunge la stringa `"Strongly Recommended"` di testo alla riga.</span><span class="sxs-lookup"><span data-stu-id="63fad-112">The following example shows a <xref:System.Windows.Controls.ControlTemplate> that adds the text string `"Strongly Recommended"` to the row.</span></span> <span data-ttu-id="63fad-113">Questo modello viene usato come riferimento in <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> e viene visualizzato quando la classificazione del brano ha un valore pari a 5 (cinque).</span><span class="sxs-lookup"><span data-stu-id="63fad-113">This template is referenced in the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> and displays when the song's rating has a value of 5 (five).</span></span> <span data-ttu-id="63fad-114"><xref:System.Windows.Controls.ControlTemplate>Include un <xref:System.Windows.Controls.GridViewRowPresenter> oggetto che imposta il contenuto della riga in colonne in base a quanto definito dalla <xref:System.Windows.Controls.GridView> modalità di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="63fad-114">The <xref:System.Windows.Controls.ControlTemplate> includes a <xref:System.Windows.Controls.GridViewRowPresenter> object that lays out the contents of the row in columns as defined by the <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 <span data-ttu-id="63fad-115">Nell'esempio seguente viene definito <xref:System.Windows.Controls.GridView> .</span><span class="sxs-lookup"><span data-stu-id="63fad-115">The following example defines <xref:System.Windows.Controls.GridView>.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a><span data-ttu-id="63fad-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63fad-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="63fad-117">Procedure</span><span class="sxs-lookup"><span data-stu-id="63fad-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="63fad-118">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="63fad-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="63fad-119">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="63fad-119">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)

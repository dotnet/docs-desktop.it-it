---
title: 'Procedura: Definire un oggetto Table tramite XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
ms.openlocfilehash: 709e977670b867f6513bf166918d3bcba0a8c62c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964606"
---
# <a name="how-to-define-a-table-with-xaml"></a><span data-ttu-id="bda73-102">Procedura: Definire un oggetto Table tramite XAML</span><span class="sxs-lookup"><span data-stu-id="bda73-102">How to: Define a Table with XAML</span></span>
<span data-ttu-id="bda73-103">Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Documents.Table> utilizzando [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bda73-103">The following example demonstrates how to define a <xref:System.Windows.Documents.Table> using [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)].</span></span>  <span data-ttu-id="bda73-104">La tabella di esempio contiene quattro colonne (rappresentate da <xref:System.Windows.Documents.TableColumn> elementi) e varie righe (rappresentate da <xref:System.Windows.Documents.TableRow> elementi) contenenti dati, nonché informazioni relative a titolo, intestazione e piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="bda73-104">The example table has four columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and several rows (represented by <xref:System.Windows.Documents.TableRow> elements) containing data as well as title, header, and footer information.</span></span>  <span data-ttu-id="bda73-105">Le righe devono essere contenute in un <xref:System.Windows.Documents.TableRowGroup> elemento.</span><span class="sxs-lookup"><span data-stu-id="bda73-105">Rows must be contained in a <xref:System.Windows.Documents.TableRowGroup> element.</span></span>  <span data-ttu-id="bda73-106">Ogni riga della tabella è costituita da una o più celle (rappresentate da <xref:System.Windows.Documents.TableCell> elementi).</span><span class="sxs-lookup"><span data-stu-id="bda73-106">Each row in the table is comprised of one or more cells (represented by <xref:System.Windows.Documents.TableCell> elements).</span></span>  <span data-ttu-id="bda73-107">Il contenuto di una cella della tabella deve essere contenuto in un <xref:System.Windows.Documents.Block> elemento; in questo caso <xref:System.Windows.Documents.Paragraph> vengono usati gli elementi.</span><span class="sxs-lookup"><span data-stu-id="bda73-107">Content in a table cell must be contained in a <xref:System.Windows.Documents.Block> element; in this case <xref:System.Windows.Documents.Paragraph> elements are used.</span></span>  <span data-ttu-id="bda73-108">La tabella ospita anche un collegamento ipertestuale (rappresentato dall' <xref:System.Windows.Documents.Hyperlink> elemento) nella riga del piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="bda73-108">The table also hosts a hyperlink (represented by the <xref:System.Windows.Documents.Hyperlink> element) in the footer row.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bda73-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="bda73-109">Example</span></span>  
 [!code-xaml[TableSnippetsXAML#_TableXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 <span data-ttu-id="bda73-110">Nella figura seguente viene illustrato il rendering della tabella definita in questo esempio:</span><span class="sxs-lookup"><span data-stu-id="bda73-110">The following figure shows how the table defined in this example renders:</span></span>  
  
 ![Screenshot di una tabella definita con XAML.](./media/how-to-define-a-table-with-xaml/planetary-information-xaml-table.png)

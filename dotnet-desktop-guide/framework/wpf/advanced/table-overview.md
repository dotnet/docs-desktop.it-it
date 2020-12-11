---
title: Cenni preliminari sull'elemento Table
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], Table
- documents [WPF], tables
- tables [WPF]
ms.assetid: 5e1105f4-8fc4-473a-ba55-88c8e71386e6
ms.openlocfilehash: 3923e39fce021d815a1b2218c95a70f5c4ef4853
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961426"
---
# <a name="table-overview"></a><span data-ttu-id="43860-102">Cenni preliminari sull'elemento Table</span><span class="sxs-lookup"><span data-stu-id="43860-102">Table Overview</span></span>
<span data-ttu-id="43860-103"><xref:System.Windows.Documents.Table> è un elemento a livello di blocco che supporta la presentazione basata su griglia del contenuto del documento dinamico.</span><span class="sxs-lookup"><span data-stu-id="43860-103"><xref:System.Windows.Documents.Table> is a block level element that supports grid-based presentation of Flow document content.</span></span> <span data-ttu-id="43860-104">La flessibilità di questo elemento lo rende molto utile, ma al contempo ne complica la comprensione e l'uso corretto.</span><span class="sxs-lookup"><span data-stu-id="43860-104">The flexibility of this element makes it very useful, but also makes it more complicated to understand and use correctly.</span></span>  
  
 <span data-ttu-id="43860-105">In questo argomento sono contenute le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="43860-105">This topic contains the following sections.</span></span>  
  
- [<span data-ttu-id="43860-106">Nozioni di base su Table</span><span class="sxs-lookup"><span data-stu-id="43860-106">Table Basics</span></span>](#table_basics)  
  
- [<span data-ttu-id="43860-107">Differenze tra Table e Grid</span><span class="sxs-lookup"><span data-stu-id="43860-107">How is Table Different then Grid?</span></span>](#table_vs_Grid)  
  
- [<span data-ttu-id="43860-108">Struttura di base di Table</span><span class="sxs-lookup"><span data-stu-id="43860-108">Basic Table Structure</span></span>](#basic_table_structure)  
  
- [<span data-ttu-id="43860-109">Contenimento di Table</span><span class="sxs-lookup"><span data-stu-id="43860-109">Table Containment</span></span>](#table_containment)  
  
- [<span data-ttu-id="43860-110">Raggruppamenti di righe</span><span class="sxs-lookup"><span data-stu-id="43860-110">Row Groupings</span></span>](#row_groupings)  
  
- [<span data-ttu-id="43860-111">Precedenza del rendering dello sfondo</span><span class="sxs-lookup"><span data-stu-id="43860-111">Background Rendering Precedence</span></span>](#rendering_precedence)  
  
- [<span data-ttu-id="43860-112">Estensione su più righe o colonne</span><span class="sxs-lookup"><span data-stu-id="43860-112">Spanning Rows or Columns</span></span>](#spanning_rows_or_columns)  
  
- [<span data-ttu-id="43860-113">Compilazione di un elemento Table con codice</span><span class="sxs-lookup"><span data-stu-id="43860-113">Building a Table With Code</span></span>](#building_a_table_with_code)  
  
- <span data-ttu-id="43860-114">[Argomenti correlati]</span><span class="sxs-lookup"><span data-stu-id="43860-114">[Related Topics]</span></span>
  
<a name="table_basics"></a>
## <a name="table-basics"></a><span data-ttu-id="43860-115">Nozioni di base su Table</span><span class="sxs-lookup"><span data-stu-id="43860-115">Table Basics</span></span>  
  
<a name="table_vs_Grid"></a>
### <a name="how-is-table-different-then-grid"></a><span data-ttu-id="43860-116">Differenze tra Table e Grid</span><span class="sxs-lookup"><span data-stu-id="43860-116">How is Table Different then Grid?</span></span>  
 <span data-ttu-id="43860-117"><xref:System.Windows.Documents.Table> e <xref:System.Windows.Controls.Grid> condividono alcune funzionalità comuni, ma ognuna è più adatta per scenari diversi.</span><span class="sxs-lookup"><span data-stu-id="43860-117"><xref:System.Windows.Documents.Table> and <xref:System.Windows.Controls.Grid> share some common functionality, but each is best suited for different scenarios.</span></span> <span data-ttu-id="43860-118">Un <xref:System.Windows.Documents.Table> è progettato per l'uso all'interno del contenuto di flusso. per altre informazioni sul contenuto dinamico, vedere [Cenni preliminari sui documenti dinamici](flow-document-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="43860-118">A <xref:System.Windows.Documents.Table> is designed for use within flow content (see [Flow Document Overview](flow-document-overview.md) for more information on flow content).</span></span> <span data-ttu-id="43860-119">Gli elementi Grid sono particolarmente adatti all'interno di moduli (in generale in un qualsiasi punto all'esterno del contenuto dinamico).</span><span class="sxs-lookup"><span data-stu-id="43860-119">Grids are best used inside of forms (basically anywhere outside of flow content).</span></span> <span data-ttu-id="43860-120">All'interno di un <xref:System.Windows.Documents.FlowDocument> , <xref:System.Windows.Documents.Table> supporta i comportamenti del contenuto di flusso come paginazione, riflusso di colonne e selezione di contenuto, mentre a non <xref:System.Windows.Controls.Grid> lo è.</span><span class="sxs-lookup"><span data-stu-id="43860-120">Within a <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> supports flow content behaviors like pagination, column reflow, and content selection while a <xref:System.Windows.Controls.Grid> does not.</span></span> <span data-ttu-id="43860-121"><xref:System.Windows.Controls.Grid>È invece consigliabile usare un oggetto <xref:System.Windows.Documents.FlowDocument> per molti motivi, tra cui l'aggiunta di <xref:System.Windows.Controls.Grid> elementi in base a un indice di riga e colonna <xref:System.Windows.Documents.Table> .</span><span class="sxs-lookup"><span data-stu-id="43860-121">A <xref:System.Windows.Controls.Grid> on the other hand is best used outside of a <xref:System.Windows.Documents.FlowDocument> for many reasons including <xref:System.Windows.Controls.Grid> adds elements based on a row and column index, <xref:System.Windows.Documents.Table> does not.</span></span> <span data-ttu-id="43860-122">L' <xref:System.Windows.Controls.Grid> elemento consente la sovrapposizione di contenuto figlio, consentendo l'esistenza di più di un elemento all'interno di una singola "cella".</span><span class="sxs-lookup"><span data-stu-id="43860-122">The <xref:System.Windows.Controls.Grid> element allows layering of child content, allowing more than one element to exist within a single "cell."</span></span> <span data-ttu-id="43860-123"><xref:System.Windows.Documents.Table> non supporta la sovrapposizione.</span><span class="sxs-lookup"><span data-stu-id="43860-123"><xref:System.Windows.Documents.Table> does not support layering.</span></span> <span data-ttu-id="43860-124">Gli elementi figlio di un oggetto <xref:System.Windows.Controls.Grid> possono essere posizionati in modo assoluto rispetto all'area dei limiti "Cell".</span><span class="sxs-lookup"><span data-stu-id="43860-124">Child elements of a <xref:System.Windows.Controls.Grid> can be absolutely positioned relative to the area of their "cell" boundaries.</span></span> <span data-ttu-id="43860-125"><xref:System.Windows.Documents.Table> non supporta questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="43860-125"><xref:System.Windows.Documents.Table> does not support this feature.</span></span> <span data-ttu-id="43860-126">Infine, un <xref:System.Windows.Controls.Grid> richiede un minor numero di risorse, quindi è <xref:System.Windows.Documents.Table> consigliabile utilizzare <xref:System.Windows.Controls.Grid> per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="43860-126">Finally, a <xref:System.Windows.Controls.Grid> requires less resources then a <xref:System.Windows.Documents.Table> so consider using a <xref:System.Windows.Controls.Grid> to improve performance.</span></span>  
  
<a name="basic_table_structure"></a>
### <a name="basic-table-structure"></a><span data-ttu-id="43860-127">Struttura di base di Table</span><span class="sxs-lookup"><span data-stu-id="43860-127">Basic Table Structure</span></span>  
 <span data-ttu-id="43860-128"><xref:System.Windows.Documents.Table> fornisce una presentazione basata su griglia costituita da colonne (rappresentate da <xref:System.Windows.Documents.TableColumn> elementi) e da righe (rappresentate da <xref:System.Windows.Documents.TableRow> elementi).</span><span class="sxs-lookup"><span data-stu-id="43860-128"><xref:System.Windows.Documents.Table> provides a grid-based presentation consisting of columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and rows (represented by <xref:System.Windows.Documents.TableRow> elements).</span></span> <span data-ttu-id="43860-129"><xref:System.Windows.Documents.TableColumn> gli elementi non ospitano il contenuto; definiscono semplicemente le colonne e le caratteristiche delle colonne.</span><span class="sxs-lookup"><span data-stu-id="43860-129"><xref:System.Windows.Documents.TableColumn> elements do not host content; they simply define columns and characteristics of columns.</span></span> <span data-ttu-id="43860-130"><xref:System.Windows.Documents.TableRow> gli elementi devono essere ospitati in un <xref:System.Windows.Documents.TableRowGroup> elemento, che definisce un raggruppamento di righe per la tabella.</span><span class="sxs-lookup"><span data-stu-id="43860-130"><xref:System.Windows.Documents.TableRow> elements must be hosted in a <xref:System.Windows.Documents.TableRowGroup> element, which defines a grouping of rows for the table.</span></span> <span data-ttu-id="43860-131"><xref:System.Windows.Documents.TableCell> gli elementi, che contengono il contenuto effettivo presentato dalla tabella, devono essere ospitati in un <xref:System.Windows.Documents.TableRow> elemento.</span><span class="sxs-lookup"><span data-stu-id="43860-131"><xref:System.Windows.Documents.TableCell> elements, which contain the actual content to be presented by the table, must be hosted in a <xref:System.Windows.Documents.TableRow> element.</span></span> <span data-ttu-id="43860-132"><xref:System.Windows.Documents.TableCell> può contenere solo elementi che derivano da <xref:System.Windows.Documents.Block> .</span><span class="sxs-lookup"><span data-stu-id="43860-132"><xref:System.Windows.Documents.TableCell> may only contain elements that derive from <xref:System.Windows.Documents.Block>.</span></span>  <span data-ttu-id="43860-133">Gli elementi figlio validi per un' <xref:System.Windows.Documents.TableCell> inclusione.</span><span class="sxs-lookup"><span data-stu-id="43860-133">Valid child elements for a <xref:System.Windows.Documents.TableCell> include.</span></span>  
  
- <xref:System.Windows.Documents.BlockUIContainer>  
  
- <xref:System.Windows.Documents.List>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
> <span data-ttu-id="43860-134"><xref:System.Windows.Documents.TableCell> gli elementi non possono ospitare direttamente contenuto di testo.</span><span class="sxs-lookup"><span data-stu-id="43860-134"><xref:System.Windows.Documents.TableCell> elements may not directly host text content.</span></span> <span data-ttu-id="43860-135">Per altre informazioni sulle regole di contenimento per gli elementi di contenuto del flusso come <xref:System.Windows.Documents.TableCell> , vedere [Cenni preliminari sui documenti dinamici](flow-document-overview.md).</span><span class="sxs-lookup"><span data-stu-id="43860-135">For more information about the containment rules for flow content elements like <xref:System.Windows.Documents.TableCell>, see [Flow Document Overview](flow-document-overview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="43860-136"><xref:System.Windows.Documents.Table> è simile all' <xref:System.Windows.Controls.Grid> elemento ma ha più funzionalità e, di conseguenza, richiede un sovraccarico di risorse maggiore.</span><span class="sxs-lookup"><span data-stu-id="43860-136"><xref:System.Windows.Documents.Table> is similar to the <xref:System.Windows.Controls.Grid> element but has more capabilities and, therefore, requires greater resource overhead.</span></span>  
  
 <span data-ttu-id="43860-137">Nell'esempio seguente viene definita una semplice tabella 2 x 3 con XAML.</span><span class="sxs-lookup"><span data-stu-id="43860-137">The following example defines a simple 2 x 3 table with XAML.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 <span data-ttu-id="43860-138">La figura seguente illustra il rendering di questo esempio.</span><span class="sxs-lookup"><span data-stu-id="43860-138">The following figure shows how this example renders.</span></span>  
  
 ![Screenshot che illustra come viene eseguito il rendering di una tabella di base.](./media/table-overview/basic-table-render-example.png)  
  
<a name="table_containment"></a>
### <a name="table-containment"></a><span data-ttu-id="43860-140">Contenimento di Table</span><span class="sxs-lookup"><span data-stu-id="43860-140">Table Containment</span></span>  
 <span data-ttu-id="43860-141"><xref:System.Windows.Documents.Table> deriva dall' <xref:System.Windows.Documents.Block> elemento e rispetta le regole comuni per <xref:System.Windows.Documents.Block> gli elementi di livello.</span><span class="sxs-lookup"><span data-stu-id="43860-141"><xref:System.Windows.Documents.Table> derives from the <xref:System.Windows.Documents.Block> element, and adheres to the common rules for <xref:System.Windows.Documents.Block> level elements.</span></span>  <span data-ttu-id="43860-142">Un <xref:System.Windows.Documents.Table> elemento può essere contenuto da uno qualsiasi degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="43860-142">A <xref:System.Windows.Documents.Table> element may be contained by any of the following elements:</span></span>  
  
- <xref:System.Windows.Documents.FlowDocument>  
  
- <xref:System.Windows.Documents.TableCell>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>
### <a name="row-groupings"></a><span data-ttu-id="43860-143">Raggruppamenti di righe</span><span class="sxs-lookup"><span data-stu-id="43860-143">Row Groupings</span></span>  
 <span data-ttu-id="43860-144">L' <xref:System.Windows.Documents.TableRowGroup> elemento consente di raggruppare in modo arbitrario le righe all'interno di una tabella. ogni riga di una tabella deve appartenere a un raggruppamento di righe.</span><span class="sxs-lookup"><span data-stu-id="43860-144">The <xref:System.Windows.Documents.TableRowGroup> element provides a way to arbitrarily group rows within a table; every row in a table must belong to a row grouping.</span></span>  <span data-ttu-id="43860-145">Spesso, le righe appartenenti allo stesso gruppo condividono un intento comune ed è possibile usare uno stile comune per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="43860-145">Rows within a row group often share a common intent, and may be styled as a group.</span></span>  <span data-ttu-id="43860-146">Un uso tipico dei raggruppamenti di righe consiste nel separare le righe con scopi specifici, ad esempio le righe di titolo, intestazione e piè di pagina, dal contenuto principale della tabella.</span><span class="sxs-lookup"><span data-stu-id="43860-146">A common use for row groupings is to separate special-purpose rows, such as a title, header, and footer rows, from the primary content contained by the table.</span></span>  
  
 <span data-ttu-id="43860-147">Nell'esempio seguente viene usato XAML per definire una tabella con righe di intestazione e piè di pagina con stile.</span><span class="sxs-lookup"><span data-stu-id="43860-147">The following example uses XAML to define a table with styled header and footer rows.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 <span data-ttu-id="43860-148">La figura seguente illustra il rendering di questo esempio.</span><span class="sxs-lookup"><span data-stu-id="43860-148">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="43860-149">![Schermata: gruppi di righe di tabella](./media/table-rowgroups.png "Table_RowGroups")</span><span class="sxs-lookup"><span data-stu-id="43860-149">![Screenshot: Table row groups](./media/table-rowgroups.png "Table_RowGroups")</span></span>  
  
<a name="rendering_precedence"></a>
### <a name="background-rendering-precedence"></a><span data-ttu-id="43860-150">Precedenza del rendering dello sfondo</span><span class="sxs-lookup"><span data-stu-id="43860-150">Background Rendering Precedence</span></span>  
 <span data-ttu-id="43860-151">Il rendering di elementi Table viene eseguito nell'ordine seguente (z order dal più basso al più alto).</span><span class="sxs-lookup"><span data-stu-id="43860-151">Table elements render in the following order (z-order from lowest to highest).</span></span> <span data-ttu-id="43860-152">Quest'ordine non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="43860-152">This order cannot be changed.</span></span> <span data-ttu-id="43860-153">Ad esempio, per questi elementi non esiste una proprietà "z order" che è possibile usare per l'override dell'ordine stabilito.</span><span class="sxs-lookup"><span data-stu-id="43860-153">For example, there is no "Z-order" property for these elements that you can use to override this established order.</span></span>  
  
1. <xref:System.Windows.Documents.Table>  
  
2. <xref:System.Windows.Documents.TableColumn>  
  
3. <xref:System.Windows.Documents.TableRowGroup>  
  
4. <xref:System.Windows.Documents.TableRow>  
  
5. <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="43860-154">L'esempio seguente definisce i colori di sfondo per ogni elemento all'interno di una tabella.</span><span class="sxs-lookup"><span data-stu-id="43860-154">Consider the following example, which defines background colors for each of these elements within a table.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 <span data-ttu-id="43860-155">La figura seguente illustra il rendering di questo esempio (visualizzazione dei soli colori di sfondo).</span><span class="sxs-lookup"><span data-stu-id="43860-155">The following figure shows how this example renders (showing background colors only).</span></span>  
  
 <span data-ttu-id="43860-156">![Schermata: ordine di&#45;della tabella z](./media/table-zorder.png "Table_ZOrder")</span><span class="sxs-lookup"><span data-stu-id="43860-156">![Screenshot: Table z&#45;order](./media/table-zorder.png "Table_ZOrder")</span></span>  
  
<a name="spanning_rows_or_columns"></a>
### <a name="spanning-rows-or-columns"></a><span data-ttu-id="43860-157">Estensione su più righe o colonne</span><span class="sxs-lookup"><span data-stu-id="43860-157">Spanning Rows or Columns</span></span>  
 <span data-ttu-id="43860-158">È possibile configurare le celle della tabella in modo che si estendano su più righe o colonne utilizzando <xref:System.Windows.Documents.TableCell.RowSpan%2A> <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> rispettivamente gli attributi o.</span><span class="sxs-lookup"><span data-stu-id="43860-158">Table cells may be configured to span multiple rows or columns by using the <xref:System.Windows.Documents.TableCell.RowSpan%2A> or <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> attributes, respectively.</span></span>  
  
 <span data-ttu-id="43860-159">L'esempio seguente definisce una cella che si estende su tre colonne.</span><span class="sxs-lookup"><span data-stu-id="43860-159">Consider the following example, in which a cell spans three columns.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 <span data-ttu-id="43860-160">La figura seguente illustra il rendering di questo esempio.</span><span class="sxs-lookup"><span data-stu-id="43860-160">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="43860-161">![Schermata: cella che si estende su tutte e tre colonne](./media/table-columnspan.png "Table_ColumnSpan")</span><span class="sxs-lookup"><span data-stu-id="43860-161">![Screenshot: Cell spanning all three columns](./media/table-columnspan.png "Table_ColumnSpan")</span></span>  
  
<a name="building_a_table_with_code"></a>
## <a name="building-a-table-with-code"></a><span data-ttu-id="43860-162">Compilazione di un elemento Table con codice</span><span class="sxs-lookup"><span data-stu-id="43860-162">Building a Table With Code</span></span>  
 <span data-ttu-id="43860-163">Negli esempi seguenti viene illustrato come creare un oggetto a livello di codice <xref:System.Windows.Documents.Table> e compilarlo con il contenuto.</span><span class="sxs-lookup"><span data-stu-id="43860-163">The following examples show how to programmatically create a <xref:System.Windows.Documents.Table> and populate it with content.</span></span> <span data-ttu-id="43860-164">Il contenuto della tabella è ripartito in cinque righe (rappresentate da <xref:System.Windows.Documents.TableRow> oggetti contenuti in un <xref:System.Windows.Documents.Table.RowGroups%2A> oggetto) e sei colonne (rappresentate da <xref:System.Windows.Documents.TableColumn> oggetti).</span><span class="sxs-lookup"><span data-stu-id="43860-164">The contents of the table are apportioned into five rows (represented by <xref:System.Windows.Documents.TableRow> objects contained in a <xref:System.Windows.Documents.Table.RowGroups%2A> object) and six columns (represented by <xref:System.Windows.Documents.TableColumn> objects).</span></span> <span data-ttu-id="43860-165">Le righe vengono usate per scopi di presentazione diversi, ad esempio una riga è destinata a contenere il titolo dell'intera tabella, una riga di intestazione a descrivere le colonne di dati nella tabella e una riga di piè di pagina a fornire informazioni di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="43860-165">The rows are used for different presentation purposes, including a title row intended to title the entire table, a header row to describe the columns of data in the table, and a footer row with summary information.</span></span>  <span data-ttu-id="43860-166">Si noti che i concetti di righe di "titolo", "intestazione" e "piè di pagina" non sono inerenti alla tabella, ma fanno semplicemente riferimento a righe con caratteristiche diverse.</span><span class="sxs-lookup"><span data-stu-id="43860-166">Note that the notion of "title", "header", and "footer" rows are not inherent to the table; these are simply rows with different characteristics.</span></span> <span data-ttu-id="43860-167">Le celle della tabella contengono il contenuto effettivo, che può essere costituito da testo, immagini o quasi tutti gli altri [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] elementi.</span><span class="sxs-lookup"><span data-stu-id="43860-167">Table cells contain the actual content, which can be comprised of text, images, or nearly any other [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] element.</span></span>  
  
 <span data-ttu-id="43860-168">Viene innanzitutto creato un oggetto <xref:System.Windows.Documents.FlowDocument> per ospitare l'oggetto <xref:System.Windows.Documents.Table> e viene creato un nuovo oggetto che <xref:System.Windows.Documents.Table> viene aggiunto al contenuto di <xref:System.Windows.Documents.FlowDocument> .</span><span class="sxs-lookup"><span data-stu-id="43860-168">First, a <xref:System.Windows.Documents.FlowDocument> is created to host the <xref:System.Windows.Documents.Table>, and a new <xref:System.Windows.Documents.Table> is created and added to the contents of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 <span data-ttu-id="43860-169">Successivamente, <xref:System.Windows.Documents.TableColumn> vengono creati sei oggetti e aggiunti alla raccolta della tabella <xref:System.Windows.Documents.Table.Columns%2A> , con una formattazione applicata.</span><span class="sxs-lookup"><span data-stu-id="43860-169">Next, six <xref:System.Windows.Documents.TableColumn> objects are created and added to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection, with some formatting applied.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="43860-170">Si noti che la raccolta della tabella <xref:System.Windows.Documents.Table.Columns%2A> Usa l'indicizzazione standard in base zero.</span><span class="sxs-lookup"><span data-stu-id="43860-170">Note that the table's <xref:System.Windows.Documents.Table.Columns%2A> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 <span data-ttu-id="43860-171">Viene quindi creata una riga del titolo che viene aggiunta alla tabella con l'applicazione di alcuni elementi di formattazione.</span><span class="sxs-lookup"><span data-stu-id="43860-171">Next, a title row is created and added to the table with some formatting applied.</span></span>  <span data-ttu-id="43860-172">La riga del titolo può contenere una sola cella che si estende su tutte e sei le colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="43860-172">The title row happens to contain a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 <span data-ttu-id="43860-173">Successivamente, viene creata e aggiunta alla tabella una riga di intestazione, per la quale vengono create celle in cui viene inserito contenuto.</span><span class="sxs-lookup"><span data-stu-id="43860-173">Next, a header row is created and added to the table, and the cells in the header row are created and populated with content.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 <span data-ttu-id="43860-174">Successivamente, viene creata e aggiunta alla tabella una riga per i dati, per la quale vengono create celle in cui viene inserito contenuto.</span><span class="sxs-lookup"><span data-stu-id="43860-174">Next, a row for data is created and added to the table, and the cells in this row are created and populated with content.</span></span>  <span data-ttu-id="43860-175">La compilazione di questa riga è simile alla compilazione della riga di intestazione, con l'applicazione di una formattazione leggermente diversa.</span><span class="sxs-lookup"><span data-stu-id="43860-175">Building this row is similar to building the header row, with slightly different formatting applied.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 <span data-ttu-id="43860-176">Infine, viene creata, aggiunta e formattata una riga di piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="43860-176">Finally, a footer row is created, added, and formatted.</span></span>  <span data-ttu-id="43860-177">Analogamente alla riga del titolo, il piè di pagina contiene una sola cella che si estende su tutte e sei le colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="43860-177">Like the title row, the footer contains a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a><span data-ttu-id="43860-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43860-178">See also</span></span>

- [<span data-ttu-id="43860-179">Cenni preliminari sui documenti dinamici</span><span class="sxs-lookup"><span data-stu-id="43860-179">Flow Document Overview</span></span>](flow-document-overview.md)
- [<span data-ttu-id="43860-180">Definire una tabella tramite XAML</span><span class="sxs-lookup"><span data-stu-id="43860-180">Define a Table with XAML</span></span>](how-to-define-a-table-with-xaml.md)
- [<span data-ttu-id="43860-181">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="43860-181">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="43860-182">Usare elementi di contenuto di flusso</span><span class="sxs-lookup"><span data-stu-id="43860-182">Use Flow Content Elements</span></span>](how-to-use-flow-content-elements.md)

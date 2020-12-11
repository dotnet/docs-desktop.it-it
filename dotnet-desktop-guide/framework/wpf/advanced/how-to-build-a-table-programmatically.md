---
title: 'Procedura: Compilare oggetti Table a livello di codice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tables [WPF], creating programmatically
ms.assetid: e3ca88f3-6e94-4b61-82fc-42104c10b761
ms.openlocfilehash: 586bff2e0aa1a545dc070a8bab2cdc6ed9a104ce
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964051"
---
# <a name="how-to-build-a-table-programmatically"></a><span data-ttu-id="3c843-102">Procedura: Compilare oggetti Table a livello di codice</span><span class="sxs-lookup"><span data-stu-id="3c843-102">How to: Build a Table Programmatically</span></span>
<span data-ttu-id="3c843-103">Negli esempi seguenti viene illustrato come creare un oggetto a livello di codice <xref:System.Windows.Documents.Table> e compilarlo con il contenuto.</span><span class="sxs-lookup"><span data-stu-id="3c843-103">The following examples show how to programmatically create a <xref:System.Windows.Documents.Table> and populate it with content.</span></span> <span data-ttu-id="3c843-104">Il contenuto della tabella è ripartito in cinque righe (rappresentate da <xref:System.Windows.Documents.TableRow> oggetti contenuti in un <xref:System.Windows.Documents.Table.RowGroups%2A> oggetto) e sei colonne (rappresentate da <xref:System.Windows.Documents.TableColumn> oggetti).</span><span class="sxs-lookup"><span data-stu-id="3c843-104">The contents of the table are apportioned into five rows (represented by <xref:System.Windows.Documents.TableRow> objects contained in a <xref:System.Windows.Documents.Table.RowGroups%2A> object) and six columns (represented by <xref:System.Windows.Documents.TableColumn> objects).</span></span> <span data-ttu-id="3c843-105">Le righe vengono usate per scopi di presentazione diversi, ad esempio una riga è destinata a contenere il titolo dell'intera tabella, una riga di intestazione a descrivere le colonne di dati nella tabella e una riga di piè di pagina a fornire informazioni di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="3c843-105">The rows are used for different presentation purposes, including a title row intended to title the entire table, a header row to describe the columns of data in the table, and a footer row with summary information.</span></span>  <span data-ttu-id="3c843-106">Si noti che i concetti di righe di "titolo", "intestazione" e "piè di pagina" non sono inerenti alla tabella, ma fanno semplicemente riferimento a righe con caratteristiche diverse.</span><span class="sxs-lookup"><span data-stu-id="3c843-106">Note that the notion of "title", "header", and "footer" rows are not inherent to the table; these are simply rows with different characteristics.</span></span> <span data-ttu-id="3c843-107">Le celle della tabella contengono il contenuto effettivo, che può essere costituito da testo, immagini o quasi tutti gli altri [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] elementi.</span><span class="sxs-lookup"><span data-stu-id="3c843-107">Table cells contain the actual content, which can be comprised of text, images, or nearly any other [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c843-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="3c843-108">Example</span></span>  
 <span data-ttu-id="3c843-109">Viene innanzitutto creato un oggetto <xref:System.Windows.Documents.FlowDocument> per ospitare l'oggetto <xref:System.Windows.Documents.Table> e viene creato un nuovo oggetto che <xref:System.Windows.Documents.Table> viene aggiunto al contenuto di <xref:System.Windows.Documents.FlowDocument> .</span><span class="sxs-lookup"><span data-stu-id="3c843-109">First, a <xref:System.Windows.Documents.FlowDocument> is created to host the <xref:System.Windows.Documents.Table>, and a new <xref:System.Windows.Documents.Table> is created and added to the contents of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
## <a name="example"></a><span data-ttu-id="3c843-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="3c843-110">Example</span></span>  
 <span data-ttu-id="3c843-111">Successivamente, <xref:System.Windows.Documents.TableColumn> vengono creati sei oggetti e aggiunti alla raccolta della tabella <xref:System.Windows.Documents.Table.Columns%2A> , con una formattazione applicata.</span><span class="sxs-lookup"><span data-stu-id="3c843-111">Next, six <xref:System.Windows.Documents.TableColumn> objects are created and added to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection, with some formatting applied.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3c843-112">Si noti che la raccolta della tabella <xref:System.Windows.Documents.Table.Columns%2A> Usa l'indicizzazione standard in base zero.</span><span class="sxs-lookup"><span data-stu-id="3c843-112">Note that the table's <xref:System.Windows.Documents.Table.Columns%2A> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
## <a name="example"></a><span data-ttu-id="3c843-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="3c843-113">Example</span></span>  
 <span data-ttu-id="3c843-114">Viene quindi creata una riga del titolo che viene aggiunta alla tabella con l'applicazione di alcuni elementi di formattazione.</span><span class="sxs-lookup"><span data-stu-id="3c843-114">Next, a title row is created and added to the table with some formatting applied.</span></span>  <span data-ttu-id="3c843-115">La riga del titolo può contenere una sola cella che si estende su tutte e sei le colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="3c843-115">The title row happens to contain a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
## <a name="example"></a><span data-ttu-id="3c843-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="3c843-116">Example</span></span>  
 <span data-ttu-id="3c843-117">Successivamente, viene creata e aggiunta alla tabella una riga di intestazione, per la quale vengono create celle in cui viene inserito contenuto.</span><span class="sxs-lookup"><span data-stu-id="3c843-117">Next, a header row is created and added to the table, and the cells in the header row are created and populated with content.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
## <a name="example"></a><span data-ttu-id="3c843-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="3c843-118">Example</span></span>  
 <span data-ttu-id="3c843-119">Successivamente, viene creata e aggiunta alla tabella una riga per i dati, per la quale vengono create celle in cui viene inserito contenuto.</span><span class="sxs-lookup"><span data-stu-id="3c843-119">Next, a row for data is created and added to the table, and the cells in this row are created and populated with content.</span></span>  <span data-ttu-id="3c843-120">La compilazione di questa riga è simile alla compilazione della riga di intestazione, con l'applicazione di una formattazione leggermente diversa.</span><span class="sxs-lookup"><span data-stu-id="3c843-120">Building this row is similar to building the header row, with slightly different formatting applied.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
## <a name="example"></a><span data-ttu-id="3c843-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="3c843-121">Example</span></span>  
 <span data-ttu-id="3c843-122">Infine, viene creata, aggiunta e formattata una riga di piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="3c843-122">Finally, a footer row is created, added, and formatted.</span></span>  <span data-ttu-id="3c843-123">Analogamente alla riga del titolo, il piè di pagina contiene una sola cella che si estende su tutte e sei le colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="3c843-123">Like the title row, the footer contains a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a><span data-ttu-id="3c843-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c843-124">See also</span></span>

- [<span data-ttu-id="3c843-125">Cenni preliminari sull'elemento Table</span><span class="sxs-lookup"><span data-stu-id="3c843-125">Table Overview</span></span>](table-overview.md)

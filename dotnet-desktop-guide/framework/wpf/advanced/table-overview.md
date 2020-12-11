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
# <a name="table-overview"></a>Cenni preliminari sull'elemento Table
<xref:System.Windows.Documents.Table> è un elemento a livello di blocco che supporta la presentazione basata su griglia del contenuto del documento dinamico. La flessibilità di questo elemento lo rende molto utile, ma al contempo ne complica la comprensione e l'uso corretto.  
  
 In questo argomento sono contenute le sezioni seguenti.  
  
- [Nozioni di base su Table](#table_basics)  
  
- [Differenze tra Table e Grid](#table_vs_Grid)  
  
- [Struttura di base di Table](#basic_table_structure)  
  
- [Contenimento di Table](#table_containment)  
  
- [Raggruppamenti di righe](#row_groupings)  
  
- [Precedenza del rendering dello sfondo](#rendering_precedence)  
  
- [Estensione su più righe o colonne](#spanning_rows_or_columns)  
  
- [Compilazione di un elemento Table con codice](#building_a_table_with_code)  
  
- [Argomenti correlati]
  
<a name="table_basics"></a>
## <a name="table-basics"></a>Nozioni di base su Table  
  
<a name="table_vs_Grid"></a>
### <a name="how-is-table-different-then-grid"></a>Differenze tra Table e Grid  
 <xref:System.Windows.Documents.Table> e <xref:System.Windows.Controls.Grid> condividono alcune funzionalità comuni, ma ognuna è più adatta per scenari diversi. Un <xref:System.Windows.Documents.Table> è progettato per l'uso all'interno del contenuto di flusso. per altre informazioni sul contenuto dinamico, vedere [Cenni preliminari sui documenti dinamici](flow-document-overview.md) . Gli elementi Grid sono particolarmente adatti all'interno di moduli (in generale in un qualsiasi punto all'esterno del contenuto dinamico). All'interno di un <xref:System.Windows.Documents.FlowDocument> , <xref:System.Windows.Documents.Table> supporta i comportamenti del contenuto di flusso come paginazione, riflusso di colonne e selezione di contenuto, mentre a non <xref:System.Windows.Controls.Grid> lo è. <xref:System.Windows.Controls.Grid>È invece consigliabile usare un oggetto <xref:System.Windows.Documents.FlowDocument> per molti motivi, tra cui l'aggiunta di <xref:System.Windows.Controls.Grid> elementi in base a un indice di riga e colonna <xref:System.Windows.Documents.Table> . L' <xref:System.Windows.Controls.Grid> elemento consente la sovrapposizione di contenuto figlio, consentendo l'esistenza di più di un elemento all'interno di una singola "cella". <xref:System.Windows.Documents.Table> non supporta la sovrapposizione. Gli elementi figlio di un oggetto <xref:System.Windows.Controls.Grid> possono essere posizionati in modo assoluto rispetto all'area dei limiti "Cell". <xref:System.Windows.Documents.Table> non supporta questa funzionalità. Infine, un <xref:System.Windows.Controls.Grid> richiede un minor numero di risorse, quindi è <xref:System.Windows.Documents.Table> consigliabile utilizzare <xref:System.Windows.Controls.Grid> per migliorare le prestazioni.  
  
<a name="basic_table_structure"></a>
### <a name="basic-table-structure"></a>Struttura di base di Table  
 <xref:System.Windows.Documents.Table> fornisce una presentazione basata su griglia costituita da colonne (rappresentate da <xref:System.Windows.Documents.TableColumn> elementi) e da righe (rappresentate da <xref:System.Windows.Documents.TableRow> elementi). <xref:System.Windows.Documents.TableColumn> gli elementi non ospitano il contenuto; definiscono semplicemente le colonne e le caratteristiche delle colonne. <xref:System.Windows.Documents.TableRow> gli elementi devono essere ospitati in un <xref:System.Windows.Documents.TableRowGroup> elemento, che definisce un raggruppamento di righe per la tabella. <xref:System.Windows.Documents.TableCell> gli elementi, che contengono il contenuto effettivo presentato dalla tabella, devono essere ospitati in un <xref:System.Windows.Documents.TableRow> elemento. <xref:System.Windows.Documents.TableCell> può contenere solo elementi che derivano da <xref:System.Windows.Documents.Block> .  Gli elementi figlio validi per un' <xref:System.Windows.Documents.TableCell> inclusione.  
  
- <xref:System.Windows.Documents.BlockUIContainer>  
  
- <xref:System.Windows.Documents.List>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
> <xref:System.Windows.Documents.TableCell> gli elementi non possono ospitare direttamente contenuto di testo. Per altre informazioni sulle regole di contenimento per gli elementi di contenuto del flusso come <xref:System.Windows.Documents.TableCell> , vedere [Cenni preliminari sui documenti dinamici](flow-document-overview.md).  
  
> [!NOTE]
> <xref:System.Windows.Documents.Table> è simile all' <xref:System.Windows.Controls.Grid> elemento ma ha più funzionalità e, di conseguenza, richiede un sovraccarico di risorse maggiore.  
  
 Nell'esempio seguente viene definita una semplice tabella 2 x 3 con XAML.  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 La figura seguente illustra il rendering di questo esempio.  
  
 ![Screenshot che illustra come viene eseguito il rendering di una tabella di base.](./media/table-overview/basic-table-render-example.png)  
  
<a name="table_containment"></a>
### <a name="table-containment"></a>Contenimento di Table  
 <xref:System.Windows.Documents.Table> deriva dall' <xref:System.Windows.Documents.Block> elemento e rispetta le regole comuni per <xref:System.Windows.Documents.Block> gli elementi di livello.  Un <xref:System.Windows.Documents.Table> elemento può essere contenuto da uno qualsiasi degli elementi seguenti:  
  
- <xref:System.Windows.Documents.FlowDocument>  
  
- <xref:System.Windows.Documents.TableCell>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>
### <a name="row-groupings"></a>Raggruppamenti di righe  
 L' <xref:System.Windows.Documents.TableRowGroup> elemento consente di raggruppare in modo arbitrario le righe all'interno di una tabella. ogni riga di una tabella deve appartenere a un raggruppamento di righe.  Spesso, le righe appartenenti allo stesso gruppo condividono un intento comune ed è possibile usare uno stile comune per il gruppo.  Un uso tipico dei raggruppamenti di righe consiste nel separare le righe con scopi specifici, ad esempio le righe di titolo, intestazione e piè di pagina, dal contenuto principale della tabella.  
  
 Nell'esempio seguente viene usato XAML per definire una tabella con righe di intestazione e piè di pagina con stile.  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 La figura seguente illustra il rendering di questo esempio.  
  
 ![Schermata: gruppi di righe di tabella](./media/table-rowgroups.png "Table_RowGroups")  
  
<a name="rendering_precedence"></a>
### <a name="background-rendering-precedence"></a>Precedenza del rendering dello sfondo  
 Il rendering di elementi Table viene eseguito nell'ordine seguente (z order dal più basso al più alto). Quest'ordine non può essere modificato. Ad esempio, per questi elementi non esiste una proprietà "z order" che è possibile usare per l'override dell'ordine stabilito.  
  
1. <xref:System.Windows.Documents.Table>  
  
2. <xref:System.Windows.Documents.TableColumn>  
  
3. <xref:System.Windows.Documents.TableRowGroup>  
  
4. <xref:System.Windows.Documents.TableRow>  
  
5. <xref:System.Windows.Documents.TableCell>  
  
 L'esempio seguente definisce i colori di sfondo per ogni elemento all'interno di una tabella.  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 La figura seguente illustra il rendering di questo esempio (visualizzazione dei soli colori di sfondo).  
  
 ![Schermata: ordine di&#45;della tabella z](./media/table-zorder.png "Table_ZOrder")  
  
<a name="spanning_rows_or_columns"></a>
### <a name="spanning-rows-or-columns"></a>Estensione su più righe o colonne  
 È possibile configurare le celle della tabella in modo che si estendano su più righe o colonne utilizzando <xref:System.Windows.Documents.TableCell.RowSpan%2A> <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> rispettivamente gli attributi o.  
  
 L'esempio seguente definisce una cella che si estende su tre colonne.  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 La figura seguente illustra il rendering di questo esempio.  
  
 ![Schermata: cella che si estende su tutte e tre colonne](./media/table-columnspan.png "Table_ColumnSpan")  
  
<a name="building_a_table_with_code"></a>
## <a name="building-a-table-with-code"></a>Compilazione di un elemento Table con codice  
 Negli esempi seguenti viene illustrato come creare un oggetto a livello di codice <xref:System.Windows.Documents.Table> e compilarlo con il contenuto. Il contenuto della tabella è ripartito in cinque righe (rappresentate da <xref:System.Windows.Documents.TableRow> oggetti contenuti in un <xref:System.Windows.Documents.Table.RowGroups%2A> oggetto) e sei colonne (rappresentate da <xref:System.Windows.Documents.TableColumn> oggetti). Le righe vengono usate per scopi di presentazione diversi, ad esempio una riga è destinata a contenere il titolo dell'intera tabella, una riga di intestazione a descrivere le colonne di dati nella tabella e una riga di piè di pagina a fornire informazioni di riepilogo.  Si noti che i concetti di righe di "titolo", "intestazione" e "piè di pagina" non sono inerenti alla tabella, ma fanno semplicemente riferimento a righe con caratteristiche diverse. Le celle della tabella contengono il contenuto effettivo, che può essere costituito da testo, immagini o quasi tutti gli altri [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] elementi.  
  
 Viene innanzitutto creato un oggetto <xref:System.Windows.Documents.FlowDocument> per ospitare l'oggetto <xref:System.Windows.Documents.Table> e viene creato un nuovo oggetto che <xref:System.Windows.Documents.Table> viene aggiunto al contenuto di <xref:System.Windows.Documents.FlowDocument> .  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 Successivamente, <xref:System.Windows.Documents.TableColumn> vengono creati sei oggetti e aggiunti alla raccolta della tabella <xref:System.Windows.Documents.Table.Columns%2A> , con una formattazione applicata.  
  
> [!NOTE]
> Si noti che la raccolta della tabella <xref:System.Windows.Documents.Table.Columns%2A> Usa l'indicizzazione standard in base zero.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 Viene quindi creata una riga del titolo che viene aggiunta alla tabella con l'applicazione di alcuni elementi di formattazione.  La riga del titolo può contenere una sola cella che si estende su tutte e sei le colonne della tabella.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 Successivamente, viene creata e aggiunta alla tabella una riga di intestazione, per la quale vengono create celle in cui viene inserito contenuto.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 Successivamente, viene creata e aggiunta alla tabella una riga per i dati, per la quale vengono create celle in cui viene inserito contenuto.  La compilazione di questa riga è simile alla compilazione della riga di intestazione, con l'applicazione di una formattazione leggermente diversa.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 Infine, viene creata, aggiunta e formattata una riga di piè di pagina.  Analogamente alla riga del titolo, il piè di pagina contiene una sola cella che si estende su tutte e sei le colonne della tabella.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sui documenti dinamici](flow-document-overview.md)
- [Definire una tabella tramite XAML](how-to-define-a-table-with-xaml.md)
- [Documenti in WPF](documents-in-wpf.md)
- [Usare elementi di contenuto di flusso](how-to-use-flow-content-elements.md)

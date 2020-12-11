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
# <a name="how-to-define-a-table-with-xaml"></a>Procedura: Definire un oggetto Table tramite XAML
Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Documents.Table> utilizzando [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] .  La tabella di esempio contiene quattro colonne (rappresentate da <xref:System.Windows.Documents.TableColumn> elementi) e varie righe (rappresentate da <xref:System.Windows.Documents.TableRow> elementi) contenenti dati, nonché informazioni relative a titolo, intestazione e piè di pagina.  Le righe devono essere contenute in un <xref:System.Windows.Documents.TableRowGroup> elemento.  Ogni riga della tabella è costituita da una o più celle (rappresentate da <xref:System.Windows.Documents.TableCell> elementi).  Il contenuto di una cella della tabella deve essere contenuto in un <xref:System.Windows.Documents.Block> elemento; in questo caso <xref:System.Windows.Documents.Paragraph> vengono usati gli elementi.  La tabella ospita anche un collegamento ipertestuale (rappresentato dall' <xref:System.Windows.Documents.Hyperlink> elemento) nella riga del piè di pagina.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[TableSnippetsXAML#_TableXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 Nella figura seguente viene illustrato il rendering della tabella definita in questo esempio:  
  
 ![Screenshot di una tabella definita con XAML.](./media/how-to-define-a-table-with-xaml/planetary-information-xaml-table.png)

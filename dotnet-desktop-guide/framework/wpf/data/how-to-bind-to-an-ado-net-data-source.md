---
title: "Procedura: eseguire l'associazione a un'origine dati ADO.NET"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to ADO.NET data sources
- ADO.NET data sources [WPF], binding to
- binding [WPF], to ADO.NET data sources
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
ms.openlocfilehash: d7ffaae472d89ebc23804c4032a75253756dc871
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951622"
---
# <a name="how-to-bind-to-an-adonet-data-source"></a><span data-ttu-id="b598b-102">Procedura: eseguire l'associazione a un'origine dati ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b598b-102">How to: Bind to an ADO.NET Data Source</span></span>

<span data-ttu-id="b598b-103">Questo esempio illustra come associare un [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> controllo a un ADO.NET `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="b598b-103">This example shows how to bind a [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> control to an ADO.NET `DataSet`.</span></span>

## <a name="example"></a><span data-ttu-id="b598b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="b598b-104">Example</span></span>

<span data-ttu-id="b598b-105">In questo esempio viene usato un oggetto `OleDbConnection` per la connessione all'origine dati che è un file `Access MDB` specificato nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="b598b-105">In this example, an `OleDbConnection` object is used to connect to the data source which is an `Access MDB` file that is specified in the connection string.</span></span> <span data-ttu-id="b598b-106">Dopo aver stabilito la connessione viene creato l'oggetto `OleDbDataAdapter` .</span><span class="sxs-lookup"><span data-stu-id="b598b-106">After the connection is established, an `OleDbDataAdapter` object is created.</span></span> <span data-ttu-id="b598b-107">L' `OleDbDataAdapter` oggetto esegue un'istruzione select Structured Query Language (SQL) per recuperare il recordset dal database.</span><span class="sxs-lookup"><span data-stu-id="b598b-107">The `OleDbDataAdapter` object executes a select Structured Query Language (SQL) statement to retrieve the recordset from the database.</span></span> <span data-ttu-id="b598b-108">I risultati del comando SQL vengono archiviati in un oggetto `DataTable` di `DataSet` chiamando il `Fill` metodo dell'oggetto `OleDbDataAdapter` .</span><span class="sxs-lookup"><span data-stu-id="b598b-108">The results from the SQL command are stored in a `DataTable` of the `DataSet` by calling the `Fill` method of the `OleDbDataAdapter`.</span></span> <span data-ttu-id="b598b-109">`DataTable` in questo esempio è denominato `BookTable`.</span><span class="sxs-lookup"><span data-stu-id="b598b-109">The `DataTable` in this example is named `BookTable`.</span></span> <span data-ttu-id="b598b-110">Nell'esempio viene quindi impostata la <xref:System.Windows.FrameworkElement.DataContext%2A> proprietà di sull' <xref:System.Windows.Controls.ListBox> `DataSet` oggetto.</span><span class="sxs-lookup"><span data-stu-id="b598b-110">The example then sets the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the <xref:System.Windows.Controls.ListBox> to the `DataSet` object.</span></span>

[!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
[!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]

<span data-ttu-id="b598b-111">È quindi possibile associare la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà di <xref:System.Windows.Controls.ListBox> a `BookTable` del `DataSet` :</span><span class="sxs-lookup"><span data-stu-id="b598b-111">We can then bind the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to `BookTable` of the `DataSet`:</span></span>

[!code-xaml[ADODataSet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]

<span data-ttu-id="b598b-112">`BookItemTemplate` è l'oggetto <xref:System.Windows.DataTemplate> che definisce come vengono visualizzati i dati:</span><span class="sxs-lookup"><span data-stu-id="b598b-112">`BookItemTemplate` is the <xref:System.Windows.DataTemplate> that defines how the data appears:</span></span>

[!code-xaml[ADODataSet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]

<span data-ttu-id="b598b-113">`IntColorConverter` converte un oggetto `int` in un colore.</span><span class="sxs-lookup"><span data-stu-id="b598b-113">The `IntColorConverter` converts an `int` to a color.</span></span> <span data-ttu-id="b598b-114">Con l'uso di questo convertitore, il <xref:System.Windows.Controls.TextBlock.Background%2A> colore del terzo <xref:System.Windows.Controls.TextBlock> viene visualizzato in verde se il valore di `NumPages` è minore di 350 e rosso in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="b598b-114">With the use of this converter, the <xref:System.Windows.Controls.TextBlock.Background%2A> color of the third <xref:System.Windows.Controls.TextBlock> appears green if the value of `NumPages` is less than 350 and red otherwise.</span></span> <span data-ttu-id="b598b-115">L'implementazione del convertitore non viene visualizzata qui.</span><span class="sxs-lookup"><span data-stu-id="b598b-115">The implementation of the converter is not shown here.</span></span>

## <a name="see-also"></a><span data-ttu-id="b598b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b598b-116">See also</span></span>

- <xref:System.Windows.Data.BindingListCollectionView>
- [<span data-ttu-id="b598b-117">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="b598b-117">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="b598b-118">Procedure</span><span class="sxs-lookup"><span data-stu-id="b598b-118">How-to Topics</span></span>](data-binding-how-to-topics.md)

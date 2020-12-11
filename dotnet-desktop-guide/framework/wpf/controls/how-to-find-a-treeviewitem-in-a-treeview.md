---
title: 'Procedura: trovare un oggetto TreeViewItem in un oggetto TreeView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], finding a TreeViewItem
- TreeViewItem [WPF], finding
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
ms.openlocfilehash: ad72c7a7fb11dfe605db4119dde831b47dd7c5a4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961402"
---
# <a name="how-to-find-a-treeviewitem-in-a-treeview"></a>Procedura: trovare un oggetto TreeViewItem in un oggetto TreeView
Il <xref:System.Windows.Controls.TreeView> controllo fornisce un modo pratico per visualizzare i dati gerarchici. Se il <xref:System.Windows.Controls.TreeView> è associato a un'origine dati, la <xref:System.Windows.Controls.TreeView.SelectedItem%2A> proprietà rappresenta un modo pratico per recuperare rapidamente l'oggetto dati selezionato. In genere è consigliabile usare l'oggetto dati sottostante, ma in alcuni casi potrebbe essere necessario modificare a livello di codice i dati che contengono <xref:System.Windows.Controls.TreeViewItem> . Ad esempio, potrebbe essere necessario espandere a livello di codice <xref:System.Windows.Controls.TreeViewItem> o selezionare un altro elemento in <xref:System.Windows.Controls.TreeView> .  
  
 Per trovare un <xref:System.Windows.Controls.TreeViewItem> oggetto che contiene un oggetto dati specifico, è necessario attraversare ogni livello di <xref:System.Windows.Controls.TreeView> . Gli elementi in un oggetto <xref:System.Windows.Controls.TreeView> possono anche essere virtualizzati per migliorare le prestazioni. Nel caso in cui gli elementi potrebbero essere virtualizzati, è necessario anche realizzare un <xref:System.Windows.Controls.TreeViewItem> per verificare se contiene l'oggetto dati.  
  
## <a name="example"></a>Esempio  
  
## <a name="description"></a>Descrizione  
 Nell'esempio seguente viene eseguita la ricerca di un <xref:System.Windows.Controls.TreeView> oggetto specifico e viene restituito il contenitore dell'oggetto <xref:System.Windows.Controls.TreeViewItem> . L'esempio garantisce che <xref:System.Windows.Controls.TreeViewItem> venga creata un'istanza di ogni oggetto in modo che sia possibile cercare i relativi elementi figlio. Questo esempio funziona anche se <xref:System.Windows.Controls.TreeView> non usa elementi virtualizzati.  
  
> [!NOTE]
> Nell'esempio seguente viene utilizzato per qualsiasi <xref:System.Windows.Controls.TreeView> , indipendentemente dal modello di dati sottostante, e viene eseguita una ricerca ogni <xref:System.Windows.Controls.TreeViewItem> finché l'oggetto non viene trovato. Un'altra tecnica che offre prestazioni migliori consiste nel cercare il modello di dati per l'oggetto specificato, tenere traccia della relativa posizione all'interno della gerarchia dei dati e quindi trovare il corrispondente <xref:System.Windows.Controls.TreeViewItem> in <xref:System.Windows.Controls.TreeView> . Tuttavia, la tecnica che offre prestazioni migliori richiede la conoscenza del modello di dati e non può essere generalizzata per un dato <xref:System.Windows.Controls.TreeView> .  
  
## <a name="code"></a>Codice  
 [!code-csharp[TreeViewFindTVI#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 Il codice precedente si basa su un oggetto personalizzato <xref:System.Windows.Controls.VirtualizingStackPanel> che espone un metodo denominato `BringIntoView` . Il codice seguente definisce l'oggetto personalizzato <xref:System.Windows.Controls.VirtualizingStackPanel> .  
  
 [!code-csharp[TreeViewFindTVI#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 Nel codice XAML seguente viene illustrato come creare un oggetto <xref:System.Windows.Controls.TreeView> che utilizza l'oggetto personalizzato <xref:System.Windows.Controls.VirtualizingStackPanel> .  
  
 [!code-xaml[TreeViewFindTVI#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Migliorare le prestazioni di un controllo TreeView](how-to-improve-the-performance-of-a-treeview.md)

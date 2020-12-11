---
title: 'Procedura: creare controlli TreeView semplici o complessi'
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], creating
- Control class [WPF], TreeView [WPF], creating
ms.assetid: 1defbb78-b8e7-4c0e-b650-576453ac828d
ms.openlocfilehash: 7edb4933ebcc0f0d2cb02754238c2342ee9dd4a2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968632"
---
# <a name="how-to-create-simple-or-complex-treeviews"></a>Procedura: creare controlli TreeView semplici o complessi
Questo esempio illustra come creare controlli semplici o complessi <xref:System.Windows.Controls.TreeView> .  
  
 Un oggetto <xref:System.Windows.Controls.TreeView> è costituito da una gerarchia di <xref:System.Windows.Controls.TreeViewItem> controlli, che può contenere semplici stringhe di testo e contenuto più complesso, ad esempio <xref:System.Windows.Controls.Button> controlli o un oggetto <xref:System.Windows.Controls.StackPanel> con contenuto incorporato. È possibile definire in modo esplicito il <xref:System.Windows.Controls.TreeView> contenuto o un'origine dati in grado di fornire il contenuto. In questo argomento vengono forniti esempi di questi concetti.  
  
## <a name="example"></a>Esempio  
 La <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> proprietà di <xref:System.Windows.Controls.TreeViewItem> contiene il contenuto <xref:System.Windows.Controls.TreeView> visualizzato da per l'elemento. Un oggetto <xref:System.Windows.Controls.TreeViewItem> può inoltre disporre <xref:System.Windows.Controls.TreeViewItem> di controlli come elementi figlio ed è possibile definire questi elementi figlio utilizzando la <xref:System.Windows.Controls.ItemsControl.Items%2A> Proprietà.  
  
 Nell'esempio seguente viene illustrato come definire in modo esplicito <xref:System.Windows.Controls.TreeViewItem> il contenuto impostando la <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> proprietà su una stringa di testo.  
  
 [!code-xaml[TreeViewSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#1)]  
  
 Nell'esempio seguente viene illustrato come definire elementi figlio di un oggetto <xref:System.Windows.Controls.TreeViewItem> definendo <xref:System.Windows.Controls.ItemsControl.Items%2A> i <xref:System.Windows.Controls.Button> controlli.  
  
 [!code-xaml[TreeViewSimple#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#3)]  
  
 Nell'esempio seguente viene illustrato come creare un oggetto in <xref:System.Windows.Controls.TreeView> cui un oggetto <xref:System.Windows.Data.XmlDataProvider> fornisce <xref:System.Windows.Controls.TreeViewItem> contenuto e un oggetto che <xref:System.Windows.HierarchicalDataTemplate> definisce l'aspetto del contenuto.  
  
 [!code-xaml[TreeViewSimple#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#6)]  
  
 [!code-xaml[TreeViewSimple#7](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#7)]  
  
 [!code-xaml[TreeViewSimple#5](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#5)]  
  
 Nell'esempio seguente viene illustrato come creare un oggetto in <xref:System.Windows.Controls.TreeView> cui il <xref:System.Windows.Controls.TreeViewItem> contenuto contiene <xref:System.Windows.Controls.DockPanel> controlli con contenuto incorporato.  
  
 [!code-xaml[TreeViewSimple#9](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#9)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [Cenni preliminari sul controllo TreeView](treeview-overview.md)
- [Procedure](treeview-how-to-topics.md)

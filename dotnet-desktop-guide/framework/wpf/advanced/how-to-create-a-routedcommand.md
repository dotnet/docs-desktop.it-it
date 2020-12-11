---
title: 'Procedura: creare un oggetto RoutedCommand'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- RoutedCommand class [WPF], creating
ms.assetid: aaf6979f-69ab-406f-979f-5766daa85fa0
ms.openlocfilehash: d433658a3039c262d2f682eff09df646d978018c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967792"
---
# <a name="how-to-create-a-routedcommand"></a>Procedura: creare un oggetto RoutedCommand
Questo esempio illustra come creare un oggetto personalizzato <xref:System.Windows.Input.RoutedCommand> e come implementare il comando personalizzato creando un oggetto <xref:System.Windows.Input.ExecutedRoutedEventHandler> e aggiungendolo <xref:System.Windows.Input.CanExecuteRoutedEventHandler> a un oggetto <xref:System.Windows.Input.CommandBinding> .  Per ulteriori informazioni sui comandi, vedere [Cenni preliminari sui comandi](commanding-overview.md).  
  
## <a name="example"></a>Esempio  
 Il primo passaggio nella creazione di un oggetto <xref:System.Windows.Input.RoutedCommand> è la definizione del comando e la creazione di un'istanza.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 Per utilizzare il comando in un'applicazione, è necessario creare i gestori eventi che definiscono il comportamento del comando  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 Viene quindi creato un oggetto  <xref:System.Windows.Input.CommandBinding> che associa il comando ai gestori eventi. <xref:System.Windows.Input.CommandBinding>Viene creato per un oggetto specifico.  Questo oggetto definisce l'ambito di <xref:System.Windows.Input.CommandBinding> nell'albero degli elementi  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 Il passaggio finale consiste nel richiamare il comando.  Un modo per richiamare un comando consiste nell'associarlo a un oggetto <xref:System.Windows.Input.ICommandSource> , ad esempio <xref:System.Windows.Controls.Button> .  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 Quando si fa clic sul pulsante, <xref:System.Windows.Input.RoutedCommand.Execute%2A> viene chiamato il metodo sull'oggetto personalizzato <xref:System.Windows.Input.RoutedCommand> .  <xref:System.Windows.Input.RoutedCommand>Genera gli <xref:System.Windows.Input.CommandManager.PreviewExecuted> <xref:System.Windows.Input.CommandManager.Executed> eventi indirizzati e.  Questi eventi attraversano l'albero degli elementi cercando un oggetto <xref:System.Windows.Input.CommandBinding> per questo particolare comando.  Se <xref:System.Windows.Input.CommandBinding> viene trovato un oggetto, <xref:System.Windows.Input.ExecutedRoutedEventHandler> viene chiamato l'oggetto associato a <xref:System.Windows.Input.CommandBinding> .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Input.RoutedCommand>
- [Cenni preliminari sull'esecuzione di comandi](commanding-overview.md)

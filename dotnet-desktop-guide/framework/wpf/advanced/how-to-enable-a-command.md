---
title: 'Procedura: attivare un comando'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CommandBindings [WPF]
- commanding [WPF]
ms.assetid: d8016266-58d9-48f7-8298-a86b7ed49fbd
ms.openlocfilehash: a2044f9504b3f2ee05ccaa63fa5e0277e2798b60
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967783"
---
# <a name="how-to-enable-a-command"></a>Procedura: attivare un comando
Nell'esempio seguente viene illustrato come utilizzare i comandi in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] .  Nell'esempio viene illustrato come associare un oggetto <xref:System.Windows.Input.RoutedCommand> a un oggetto <xref:System.Windows.Controls.Button> , creare un oggetto <xref:System.Windows.Input.CommandBinding> e creare i gestori eventi che implementano <xref:System.Windows.Input.RoutedCommand> .  Per ulteriori informazioni sui comandi, vedere [Cenni preliminari sui comandi](commanding-overview.md).  
  
## <a name="example"></a>Esempio  
 Nella prima sezione del codice viene creato [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] , che è costituito da un oggetto <xref:System.Windows.Controls.Button> e un oggetto <xref:System.Windows.Controls.StackPanel> , e viene creato un oggetto <xref:System.Windows.Input.CommandBinding> che associa i gestori del comando a <xref:System.Windows.Input.RoutedCommand> .  
  
 La <xref:System.Windows.Input.ICommandSource.Command%2A> proprietà di <xref:System.Windows.Controls.Button> è associata al <xref:System.Windows.Input.ApplicationCommands.Close%2A> comando.  
  
 L'oggetto <xref:System.Windows.Input.CommandBinding> viene aggiunto all'oggetto <xref:System.Windows.Input.CommandBindingCollection> della radice <xref:System.Windows.Window> . I <xref:System.Windows.Input.CommandBinding.Executed> <xref:System.Windows.Input.CommandBinding.CanExecute> gestori di eventi e sono allegati a questa associazione e associati al <xref:System.Windows.Input.ApplicationCommands.Close%2A> comando.  
  
 Senza la <xref:System.Windows.Input.CommandBinding> logica del comando, solo un meccanismo per richiamare il comando.  Quando <xref:System.Windows.Controls.Button> si fa clic su, <xref:System.Windows.Input.CommandManager.PreviewExecuted> <xref:System.Windows.RoutedEvent> viene generato l'oggetto sulla destinazione del comando seguito da <xref:System.Windows.Input.CommandManager.Executed> <xref:System.Windows.RoutedEvent> .  Questi eventi attraversano l'albero degli elementi cercando un oggetto <xref:System.Windows.Input.CommandBinding> per quel particolare comando.  Vale la pena notare che, poiché <xref:System.Windows.RoutedEvent> tunnel e Bubble attraversano l'albero degli elementi, è necessario prestare attenzione nel punto in cui <xref:System.Windows.Input.CommandBinding> viene inserito.   Se l'oggetto <xref:System.Windows.Input.CommandBinding> si trova in un elemento di pari livello della destinazione del comando o in un altro nodo che non si trova nella route di <xref:System.Windows.RoutedEvent> , non sarà possibile accedere a <xref:System.Windows.Input.CommandBinding> .  
  
 [!code-xaml[EnableCloseCommand#CloseCommandBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml#closecommandbinding)]  
  
 [!code-csharp[EnableCloseCommand#CloseCommandBindingCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandbindingcodebehind)]
 [!code-vb[EnableCloseCommand#CloseCommandBindingCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandbindingcodebehind)]  
  
 La sezione successiva del codice implementa i <xref:System.Windows.Input.CommandManager.Executed> <xref:System.Windows.Input.CommandBinding.CanExecute> gestori eventi e.  
  
 Il <xref:System.Windows.Input.CommandManager.Executed> gestore chiama un metodo per chiudere il file aperto.  Il <xref:System.Windows.Input.CommandBinding.CanExecute> gestore chiama un metodo per determinare se un file è aperto.  Se un file è aperto, <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> è impostato su `true` ; in caso contrario, è impostato su `false` .  
  
 [!code-csharp[EnableCloseCommand#CloseCommandHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandhandler)]
 [!code-vb[EnableCloseCommand#CloseCommandHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandhandler)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'esecuzione di comandi](commanding-overview.md)

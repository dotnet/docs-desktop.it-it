---
title: 'Procedura: implementare ICommandSource'
ms.date: 12/05/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 2d8238eb4e008b8032ca0c22da44a554438765fc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964969"
---
# <a name="how-to-implement-icommandsource"></a>Procedura: implementare ICommandSource

Questo esempio illustra come creare un'origine comando implementando <xref:System.Windows.Input.ICommandSource> . Un'origine comando è un oggetto che sa come richiamare un comando. L' <xref:System.Windows.Input.ICommandSource> interfaccia espone tre membri:

- <xref:System.Windows.Input.ICommandSource.Command%2A>: comando che verrà richiamato.
- <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: tipo di dati definito dall'utente che viene passato dall'origine del comando al metodo che gestisce il comando.
- <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: oggetto in cui viene eseguito il comando.

In questo esempio viene creata una classe che eredita dal <xref:System.Windows.Controls.Slider> controllo e implementa l'  <xref:System.Windows.Input.ICommandSource> interfaccia.
  
## <a name="example"></a>Esempio

WPF fornisce varie classi che implementano <xref:System.Windows.Input.ICommandSource> , ad esempio <xref:System.Windows.Controls.Button> , <xref:System.Windows.Controls.MenuItem> e <xref:System.Windows.Documents.Hyperlink> . Un'origine comando definisce il modo in cui richiama un comando. Queste classi richiamano un comando quando vengono selezionate e diventano solo un'origine di comando quando la relativa <xref:System.Windows.Input.ICommandSource.Command%2A> proprietà è impostata.

In questo esempio verrà richiamato il comando quando il dispositivo di scorrimento viene spostato o più accuratamente quando la <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> proprietà viene modificata.

Di seguito è riportata la definizione della classe:

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

Il passaggio successivo consiste nell'implementare i <xref:System.Windows.Input.ICommandSource> membri. In questo esempio, le proprietà vengono implementate come <xref:System.Windows.DependencyProperty> oggetti. Questo consente alle proprietà di utilizzare data binding. Per ulteriori informazioni sulla <xref:System.Windows.DependencyProperty> classe, vedere [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md). Per ulteriori informazioni su data binding, vedere [Cenni preliminari sull'associazione dati](/dotnet/desktop-wpf/data/data-binding-overview).

<xref:System.Windows.Input.ICommandSource.Command%2A>Qui viene mostrata solo la proprietà.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
Di seguito è riportato il <xref:System.Windows.DependencyProperty> callback delle modifiche:

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

Il passaggio successivo consiste nell'aggiungere e rimuovere il comando associato all'origine del comando. La <xref:System.Windows.Input.ICommandSource.Command%2A> proprietà non può essere semplicemente sovrascritta quando viene aggiunto un nuovo comando, perché i gestori eventi associati al comando precedente, se presente, devono essere rimossi per primi.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

Il passaggio successivo consiste nel creare la logica per il <xref:System.Windows.Input.ICommand.CanExecuteChanged> gestore.

L' <xref:System.Windows.Input.ICommand.CanExecuteChanged> evento notifica all'origine del comando che è possibile che la capacità del comando da eseguire sulla destinazione corrente del comando sia stata modificata. Quando l'origine di un comando riceve questo evento, in genere chiama il <xref:System.Windows.Input.ICommand.CanExecute%2A> metodo sul comando. Se non è possibile eseguire il comando sulla destinazione del comando corrente, l'origine comando si disabilita in genere. Se il comando può essere eseguito sulla destinazione del comando corrente, l'origine del comando in genere lo Abilita.

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

L'ultimo passaggio è il <xref:System.Windows.Input.ICommand.Execute%2A> metodo. Se il comando è un <xref:System.Windows.Input.RoutedCommand> , <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> viene chiamato il metodo; in caso contrario, <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> viene chiamato il metodo.

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [Cenni preliminari sull'esecuzione di comandi](commanding-overview.md)

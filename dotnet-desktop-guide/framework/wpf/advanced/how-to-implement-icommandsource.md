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
# <a name="how-to-implement-icommandsource"></a><span data-ttu-id="7b022-102">Procedura: implementare ICommandSource</span><span class="sxs-lookup"><span data-stu-id="7b022-102">How to: Implement ICommandSource</span></span>

<span data-ttu-id="7b022-103">Questo esempio illustra come creare un'origine comando implementando <xref:System.Windows.Input.ICommandSource> .</span><span class="sxs-lookup"><span data-stu-id="7b022-103">This example shows how to create a command source by implementing <xref:System.Windows.Input.ICommandSource>.</span></span> <span data-ttu-id="7b022-104">Un'origine comando è un oggetto che sa come richiamare un comando.</span><span class="sxs-lookup"><span data-stu-id="7b022-104">A command source is an object that knows how to invoke a command.</span></span> <span data-ttu-id="7b022-105">L' <xref:System.Windows.Input.ICommandSource> interfaccia espone tre membri:</span><span class="sxs-lookup"><span data-stu-id="7b022-105">The <xref:System.Windows.Input.ICommandSource> interface exposes three members:</span></span>

- <span data-ttu-id="7b022-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: comando che verrà richiamato.</span><span class="sxs-lookup"><span data-stu-id="7b022-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: the command that will be invoked.</span></span>
- <span data-ttu-id="7b022-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: tipo di dati definito dall'utente che viene passato dall'origine del comando al metodo che gestisce il comando.</span><span class="sxs-lookup"><span data-stu-id="7b022-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: a user-defined data type which is passed from the command source to the method that handles the command.</span></span>
- <span data-ttu-id="7b022-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: oggetto in cui viene eseguito il comando.</span><span class="sxs-lookup"><span data-stu-id="7b022-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: the object that the command is being executed on.</span></span>

<span data-ttu-id="7b022-109">In questo esempio viene creata una classe che eredita dal <xref:System.Windows.Controls.Slider> controllo e implementa l'  <xref:System.Windows.Input.ICommandSource> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7b022-109">In this example, a class is created that inherits from the <xref:System.Windows.Controls.Slider> control and implements the  <xref:System.Windows.Input.ICommandSource> interface.</span></span>
  
## <a name="example"></a><span data-ttu-id="7b022-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="7b022-110">Example</span></span>

<span data-ttu-id="7b022-111">WPF fornisce varie classi che implementano <xref:System.Windows.Input.ICommandSource> , ad esempio <xref:System.Windows.Controls.Button> , <xref:System.Windows.Controls.MenuItem> e <xref:System.Windows.Documents.Hyperlink> .</span><span class="sxs-lookup"><span data-stu-id="7b022-111">WPF provides a number of classes which implement <xref:System.Windows.Input.ICommandSource>, such as <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>, and <xref:System.Windows.Documents.Hyperlink>.</span></span> <span data-ttu-id="7b022-112">Un'origine comando definisce il modo in cui richiama un comando.</span><span class="sxs-lookup"><span data-stu-id="7b022-112">A command source defines how it invokes a command.</span></span> <span data-ttu-id="7b022-113">Queste classi richiamano un comando quando vengono selezionate e diventano solo un'origine di comando quando la relativa <xref:System.Windows.Input.ICommandSource.Command%2A> proprietà è impostata.</span><span class="sxs-lookup"><span data-stu-id="7b022-113">These classes invoke a command when they're clicked and they only become a command source when their <xref:System.Windows.Input.ICommandSource.Command%2A> property is set.</span></span>

<span data-ttu-id="7b022-114">In questo esempio verrà richiamato il comando quando il dispositivo di scorrimento viene spostato o più accuratamente quando la <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> proprietà viene modificata.</span><span class="sxs-lookup"><span data-stu-id="7b022-114">In this example, you'll invoke the command when the slider is moved, or more accurately, when the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property is changed.</span></span>

<span data-ttu-id="7b022-115">Di seguito è riportata la definizione della classe:</span><span class="sxs-lookup"><span data-stu-id="7b022-115">The following is the class definition:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

<span data-ttu-id="7b022-116">Il passaggio successivo consiste nell'implementare i <xref:System.Windows.Input.ICommandSource> membri.</span><span class="sxs-lookup"><span data-stu-id="7b022-116">The next step is to implement the <xref:System.Windows.Input.ICommandSource> members.</span></span> <span data-ttu-id="7b022-117">In questo esempio, le proprietà vengono implementate come <xref:System.Windows.DependencyProperty> oggetti.</span><span class="sxs-lookup"><span data-stu-id="7b022-117">In this example, the properties are implemented as <xref:System.Windows.DependencyProperty> objects.</span></span> <span data-ttu-id="7b022-118">Questo consente alle proprietà di utilizzare data binding.</span><span class="sxs-lookup"><span data-stu-id="7b022-118">This enables the properties to use data binding.</span></span> <span data-ttu-id="7b022-119">Per ulteriori informazioni sulla <xref:System.Windows.DependencyProperty> classe, vedere [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7b022-119">For more information about the <xref:System.Windows.DependencyProperty> class, see the [Dependency Properties Overview](dependency-properties-overview.md).</span></span> <span data-ttu-id="7b022-120">Per ulteriori informazioni su data binding, vedere [Cenni preliminari sull'associazione dati](/dotnet/desktop-wpf/data/data-binding-overview).</span><span class="sxs-lookup"><span data-stu-id="7b022-120">For more information about data binding, see the [Data Binding Overview](/dotnet/desktop-wpf/data/data-binding-overview).</span></span>

<span data-ttu-id="7b022-121"><xref:System.Windows.Input.ICommandSource.Command%2A>Qui viene mostrata solo la proprietà.</span><span class="sxs-lookup"><span data-stu-id="7b022-121">Only the <xref:System.Windows.Input.ICommandSource.Command%2A> property is shown here.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
<span data-ttu-id="7b022-122">Di seguito è riportato il <xref:System.Windows.DependencyProperty> callback delle modifiche:</span><span class="sxs-lookup"><span data-stu-id="7b022-122">The following is the <xref:System.Windows.DependencyProperty> change callback:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

<span data-ttu-id="7b022-123">Il passaggio successivo consiste nell'aggiungere e rimuovere il comando associato all'origine del comando.</span><span class="sxs-lookup"><span data-stu-id="7b022-123">The next step is to add and remove the command which is associated with the command source.</span></span> <span data-ttu-id="7b022-124">La <xref:System.Windows.Input.ICommandSource.Command%2A> proprietà non può essere semplicemente sovrascritta quando viene aggiunto un nuovo comando, perché i gestori eventi associati al comando precedente, se presente, devono essere rimossi per primi.</span><span class="sxs-lookup"><span data-stu-id="7b022-124">The <xref:System.Windows.Input.ICommandSource.Command%2A> property cannot simply be overwritten when a new command is added, because the event handlers associated with the previous command, if there was one, must be removed first.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

<span data-ttu-id="7b022-125">Il passaggio successivo consiste nel creare la logica per il <xref:System.Windows.Input.ICommand.CanExecuteChanged> gestore.</span><span class="sxs-lookup"><span data-stu-id="7b022-125">The next step is to create logic for the <xref:System.Windows.Input.ICommand.CanExecuteChanged> handler.</span></span>

<span data-ttu-id="7b022-126">L' <xref:System.Windows.Input.ICommand.CanExecuteChanged> evento notifica all'origine del comando che è possibile che la capacità del comando da eseguire sulla destinazione corrente del comando sia stata modificata.</span><span class="sxs-lookup"><span data-stu-id="7b022-126">The <xref:System.Windows.Input.ICommand.CanExecuteChanged> event notifies the command source that the ability of the command to execute on the current command target may have changed.</span></span> <span data-ttu-id="7b022-127">Quando l'origine di un comando riceve questo evento, in genere chiama il <xref:System.Windows.Input.ICommand.CanExecute%2A> metodo sul comando.</span><span class="sxs-lookup"><span data-stu-id="7b022-127">When a command source receives this event, it typically calls the <xref:System.Windows.Input.ICommand.CanExecute%2A> method on the command.</span></span> <span data-ttu-id="7b022-128">Se non è possibile eseguire il comando sulla destinazione del comando corrente, l'origine comando si disabilita in genere.</span><span class="sxs-lookup"><span data-stu-id="7b022-128">If the command cannot execute on the current command target, the command source will typically disable itself.</span></span> <span data-ttu-id="7b022-129">Se il comando può essere eseguito sulla destinazione del comando corrente, l'origine del comando in genere lo Abilita.</span><span class="sxs-lookup"><span data-stu-id="7b022-129">If the command can execute on the current command target, the command source will typically enable itself.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

<span data-ttu-id="7b022-130">L'ultimo passaggio è il <xref:System.Windows.Input.ICommand.Execute%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="7b022-130">The last step is the <xref:System.Windows.Input.ICommand.Execute%2A> method.</span></span> <span data-ttu-id="7b022-131">Se il comando è un <xref:System.Windows.Input.RoutedCommand> , <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> viene chiamato il metodo; in caso contrario, <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="7b022-131">If the command is a <xref:System.Windows.Input.RoutedCommand>, the <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> method is called; otherwise, the <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> method is called.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a><span data-ttu-id="7b022-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b022-132">See also</span></span>

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [<span data-ttu-id="7b022-133">Cenni preliminari sull'esecuzione di comandi</span><span class="sxs-lookup"><span data-stu-id="7b022-133">Commanding Overview</span></span>](commanding-overview.md)

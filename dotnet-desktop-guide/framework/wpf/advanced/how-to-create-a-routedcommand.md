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
# <a name="how-to-create-a-routedcommand"></a><span data-ttu-id="1da43-102">Procedura: creare un oggetto RoutedCommand</span><span class="sxs-lookup"><span data-stu-id="1da43-102">How to: Create a RoutedCommand</span></span>
<span data-ttu-id="1da43-103">Questo esempio illustra come creare un oggetto personalizzato <xref:System.Windows.Input.RoutedCommand> e come implementare il comando personalizzato creando un oggetto <xref:System.Windows.Input.ExecutedRoutedEventHandler> e aggiungendolo <xref:System.Windows.Input.CanExecuteRoutedEventHandler> a un oggetto <xref:System.Windows.Input.CommandBinding> .</span><span class="sxs-lookup"><span data-stu-id="1da43-103">This example shows how to create a custom <xref:System.Windows.Input.RoutedCommand> and how to implement the custom command by creating a <xref:System.Windows.Input.ExecutedRoutedEventHandler> and a <xref:System.Windows.Input.CanExecuteRoutedEventHandler> and attaching them to a <xref:System.Windows.Input.CommandBinding>.</span></span>  <span data-ttu-id="1da43-104">Per ulteriori informazioni sui comandi, vedere [Cenni preliminari sui comandi](commanding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1da43-104">For more information on commanding, see the [Commanding Overview](commanding-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1da43-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="1da43-105">Example</span></span>  
 <span data-ttu-id="1da43-106">Il primo passaggio nella creazione di un oggetto <xref:System.Windows.Input.RoutedCommand> è la definizione del comando e la creazione di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="1da43-106">The first step in creating a <xref:System.Windows.Input.RoutedCommand> is defining the command and instantiating it.</span></span>  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 <span data-ttu-id="1da43-107">Per utilizzare il comando in un'applicazione, è necessario creare i gestori eventi che definiscono il comportamento del comando</span><span class="sxs-lookup"><span data-stu-id="1da43-107">In order to use the command in an application, event handlers which define what the command does must be created</span></span>  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 <span data-ttu-id="1da43-108">Viene quindi creato un oggetto  <xref:System.Windows.Input.CommandBinding> che associa il comando ai gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="1da43-108">Next, a  <xref:System.Windows.Input.CommandBinding> is created which associates the command with the event handlers.</span></span> <span data-ttu-id="1da43-109"><xref:System.Windows.Input.CommandBinding>Viene creato per un oggetto specifico.</span><span class="sxs-lookup"><span data-stu-id="1da43-109">The <xref:System.Windows.Input.CommandBinding> is created on a specific object.</span></span>  <span data-ttu-id="1da43-110">Questo oggetto definisce l'ambito di <xref:System.Windows.Input.CommandBinding> nell'albero degli elementi</span><span class="sxs-lookup"><span data-stu-id="1da43-110">This object defines the scope of the <xref:System.Windows.Input.CommandBinding> in the element tree</span></span>  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 <span data-ttu-id="1da43-111">Il passaggio finale consiste nel richiamare il comando.</span><span class="sxs-lookup"><span data-stu-id="1da43-111">The final step is invoking the command.</span></span>  <span data-ttu-id="1da43-112">Un modo per richiamare un comando consiste nell'associarlo a un oggetto <xref:System.Windows.Input.ICommandSource> , ad esempio <xref:System.Windows.Controls.Button> .</span><span class="sxs-lookup"><span data-stu-id="1da43-112">One way to invoke a command is to associate it with a <xref:System.Windows.Input.ICommandSource>, such as a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 <span data-ttu-id="1da43-113">Quando si fa clic sul pulsante, <xref:System.Windows.Input.RoutedCommand.Execute%2A> viene chiamato il metodo sull'oggetto personalizzato <xref:System.Windows.Input.RoutedCommand> .</span><span class="sxs-lookup"><span data-stu-id="1da43-113">When the Button is clicked, the <xref:System.Windows.Input.RoutedCommand.Execute%2A> method on the custom <xref:System.Windows.Input.RoutedCommand> is called.</span></span>  <span data-ttu-id="1da43-114"><xref:System.Windows.Input.RoutedCommand>Genera gli <xref:System.Windows.Input.CommandManager.PreviewExecuted> <xref:System.Windows.Input.CommandManager.Executed> eventi indirizzati e.</span><span class="sxs-lookup"><span data-stu-id="1da43-114">The <xref:System.Windows.Input.RoutedCommand> raises the <xref:System.Windows.Input.CommandManager.PreviewExecuted> and <xref:System.Windows.Input.CommandManager.Executed> routed events.</span></span>  <span data-ttu-id="1da43-115">Questi eventi attraversano l'albero degli elementi cercando un oggetto <xref:System.Windows.Input.CommandBinding> per questo particolare comando.</span><span class="sxs-lookup"><span data-stu-id="1da43-115">These events traverse the element tree looking for a <xref:System.Windows.Input.CommandBinding> for this particular command.</span></span>  <span data-ttu-id="1da43-116">Se <xref:System.Windows.Input.CommandBinding> viene trovato un oggetto, <xref:System.Windows.Input.ExecutedRoutedEventHandler> viene chiamato l'oggetto associato a <xref:System.Windows.Input.CommandBinding> .</span><span class="sxs-lookup"><span data-stu-id="1da43-116">If a <xref:System.Windows.Input.CommandBinding> is found, the <xref:System.Windows.Input.ExecutedRoutedEventHandler> associated with <xref:System.Windows.Input.CommandBinding> is called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1da43-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1da43-117">See also</span></span>

- <xref:System.Windows.Input.RoutedCommand>
- [<span data-ttu-id="1da43-118">Cenni preliminari sull'esecuzione di comandi</span><span class="sxs-lookup"><span data-stu-id="1da43-118">Commanding Overview</span></span>](commanding-overview.md)

---
title: "Procedura: salvare in modo permanente e ripristinare le proprietà con ambito applicazione tra le sessioni di un'applicazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application-scope properties [WPF], persisting
- persisting application-scope properties [WPF]
- properties [WPF], persisting
- restoring application-scope properties [WPF]
- properties [WPF], restoring
- application-scope properties [WPF], restoring
ms.assetid: 55d5904a-f444-4eb5-abd3-6bc74dd14226
ms.openlocfilehash: d9c2dda2745e7528902b6b1c4f46d17264d1a8d8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967237"
---
# <a name="how-to-persist-and-restore-application-scope-properties-across-application-sessions"></a><span data-ttu-id="0a100-102">Procedura: salvare in modo permanente e ripristinare le proprietà con ambito applicazione tra le sessioni di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="0a100-102">How to: Persist and Restore Application-Scope Properties Across Application Sessions</span></span>
<span data-ttu-id="0a100-103">Questo esempio illustra come salvare in modo permanente le proprietà dell'ambito dell'applicazione quando un'applicazione viene arrestata e come ripristinare le proprietà dell'ambito dell'applicazione al successivo avvio di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0a100-103">This example shows how to persist application-scope properties when an application shuts down, and how to restore application-scope properties when an application is next launch.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a100-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="0a100-104">Example</span></span>  
 <span data-ttu-id="0a100-105">L'applicazione salva in modo permanente le proprietà dell'ambito dell'applicazione e le ripristina dallo spazio di memorizzazione isolato.</span><span class="sxs-lookup"><span data-stu-id="0a100-105">The application persists application-scope properties to, and restores them from, isolated storage.</span></span> <span data-ttu-id="0a100-106">Lo spazio di memorizzazione isolato è un'area di archiviazione protetta che può essere usata in modo sicuro dalle applicazioni senza autorizzazione di accesso ai file.</span><span class="sxs-lookup"><span data-stu-id="0a100-106">Isolated storage is a protected storage area that can safely be used by applications without file access permission.</span></span>  <span data-ttu-id="0a100-107">Il file *app. XAML* definisce il `App_Startup` metodo come gestore per l' <xref:System.Windows.Application.Startup?displayProperty=nameWithType> evento e il `App_Exit` metodo come gestore per l'  <xref:System.Windows.Application.Exit?displayProperty=nameWithType> evento, come illustrato nelle righe evidenziate del primo esempio.</span><span class="sxs-lookup"><span data-stu-id="0a100-107">The *App.xaml* file defines the `App_Startup` method as the handler for the <xref:System.Windows.Application.Startup?displayProperty=nameWithType> event, and the `App_Exit` method as the handler for the  <xref:System.Windows.Application.Exit?displayProperty=nameWithType> event, as shown in the highlighted lines of the first example.</span></span> <span data-ttu-id="0a100-108">Nel secondo esempio viene illustrata una parte dei file *app.XAML.cs* e *app. XAML. vb* che evidenzia il codice per il `App_Startup` metodo, che consente di ripristinare le proprietà dell'ambito dell'applicazione e il `App_Exit` metodo, che salva le proprietà dell'ambito dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0a100-108">The second example shows a portion of the *App.xaml.cs* and *App.xaml.vb* files that highlights the code for the `App_Startup` method, which restores application-scope properties, and the `App_Exit` method, which saves application-scope properties.</span></span>

 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=17-55)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb?highlight=14-45)]

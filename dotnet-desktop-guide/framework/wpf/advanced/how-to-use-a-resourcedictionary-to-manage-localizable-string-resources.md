---
title: 'Procedura: Usare un oggetto ResourceDictionary per gestire le risorse di tipo stringa localizzabili'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resources [WPF], packaging string resources
- packaging string resources [WPF]
- ResourceDictionary [WPF]
- localization [WPF], packaging string resources
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
ms.openlocfilehash: 3e7a6813497a6a4a7251b49382ed32e4a7b521da
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963730"
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="bf810-102">Procedura: Usare un oggetto ResourceDictionary per gestire le risorse di tipo stringa localizzabili</span><span class="sxs-lookup"><span data-stu-id="bf810-102">How to: Use a ResourceDictionary to Manage Localizable String Resources</span></span>
<span data-ttu-id="bf810-103">Questo esempio illustra come usare un oggetto <xref:System.Windows.ResourceDictionary> per creare un pacchetto di risorse di stringa localizzabili per applicazioni Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="bf810-103">This example shows how to use a <xref:System.Windows.ResourceDictionary> to package localizable string resources for Windows Presentation Foundation (WPF) applications.</span></span>  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="bf810-104">Per usare un oggetto ResourceDictionary per gestire le risorse di tipo stringa localizzabili</span><span class="sxs-lookup"><span data-stu-id="bf810-104">To use a ResourceDictionary to manage localizable string resources</span></span>  
  
1. <span data-ttu-id="bf810-105">Creare un oggetto contenente <xref:System.Windows.ResourceDictionary> le stringhe che si desidera localizzare.</span><span class="sxs-lookup"><span data-stu-id="bf810-105">Create a <xref:System.Windows.ResourceDictionary> that contains the strings you would like to localize.</span></span> <span data-ttu-id="bf810-106">Il codice seguente mostra un esempio.</span><span class="sxs-lookup"><span data-stu-id="bf810-106">The following code shows an example.</span></span>  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     <span data-ttu-id="bf810-107">Questo codice definisce una risorsa `localizedMessage` di tipo stringa,, di tipo <xref:System.String> , dallo <xref:System> spazio dei nomi in mscorlib.dll.</span><span class="sxs-lookup"><span data-stu-id="bf810-107">This code defines a string resource, `localizedMessage`, of type <xref:System.String>, from the <xref:System> namespace in mscorlib.dll.</span></span>  
  
2. <span data-ttu-id="bf810-108">Aggiungere all' <xref:System.Windows.ResourceDictionary> applicazione usando il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="bf810-108">Add the <xref:System.Windows.ResourceDictionary> to your application, using the following code.</span></span>  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3. <span data-ttu-id="bf810-109">Usare la risorsa di tipo stringa dal markup, usando come indicato di [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] seguito.</span><span class="sxs-lookup"><span data-stu-id="bf810-109">Use the string resource from markup, using [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] like the following.</span></span>  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4. <span data-ttu-id="bf810-110">Usare la risorsa di tipo stringa dal code-behind, usando un codice analogo al seguente.</span><span class="sxs-lookup"><span data-stu-id="bf810-110">Use the string resource from code-behind, using code like the following.</span></span>  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5. <span data-ttu-id="bf810-111">Localizzare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bf810-111">Localize the application.</span></span> <span data-ttu-id="bf810-112">Per altre informazioni, vedere [localizzare un'applicazione](how-to-localize-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="bf810-112">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>

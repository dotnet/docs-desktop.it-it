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
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a>Procedura: Usare un oggetto ResourceDictionary per gestire le risorse di tipo stringa localizzabili
Questo esempio illustra come usare un oggetto <xref:System.Windows.ResourceDictionary> per creare un pacchetto di risorse di stringa localizzabili per applicazioni Windows Presentation Foundation (WPF).  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a>Per usare un oggetto ResourceDictionary per gestire le risorse di tipo stringa localizzabili  
  
1. Creare un oggetto contenente <xref:System.Windows.ResourceDictionary> le stringhe che si desidera localizzare. Il codice seguente mostra un esempio.  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     Questo codice definisce una risorsa `localizedMessage` di tipo stringa,, di tipo <xref:System.String> , dallo <xref:System> spazio dei nomi in mscorlib.dll.  
  
2. Aggiungere all' <xref:System.Windows.ResourceDictionary> applicazione usando il codice seguente.  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3. Usare la risorsa di tipo stringa dal markup, usando come indicato di [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] seguito.  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4. Usare la risorsa di tipo stringa dal code-behind, usando un codice analogo al seguente.  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5. Localizzare l'applicazione. Per altre informazioni, vedere [localizzare un'applicazione](how-to-localize-an-application.md).

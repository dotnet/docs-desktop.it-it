---
title: 'Procedura: spostarsi indietro nella cronologia di navigazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: 53b32e145390d7052262042c7a793699c163b373
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967252"
---
# <a name="how-to-navigate-back-through-navigation-history"></a>Procedura: spostarsi indietro nella cronologia di navigazione
Questo esempio illustra come passare alle voci nella cronologia di navigazione indietro.  
  
## <a name="example"></a>Esempio  
 Il codice eseguito dal contenuto ospitato in un oggetto <xref:System.Windows.Navigation.NavigationWindow> , <xref:System.Windows.Controls.Frame> utilizzando <xref:System.Windows.Navigation.NavigationService> o Internet Explorer può tornare alla cronologia di navigazione, una voce alla volta.  
  
 Per spostarsi indietro di una voce è necessario prima verificare che siano presenti voci nella cronologia di navigazione indietro, controllando la proprietà **CanGoBack** , prima di tornare indietro di una voce, chiamando il metodo **GoBack** . Questo è illustrato nell'esempio seguente:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoBack** e **GoBack** sono implementati da <xref:System.Windows.Navigation.NavigationWindow> , <xref:System.Windows.Controls.Frame> e <xref:System.Windows.Navigation.NavigationService> .  
  
> [!NOTE]
> Se si chiama **GoBack** e non sono presenti voci nella cronologia di navigazione indietro, <xref:System.InvalidOperationException> viene generato un oggetto.

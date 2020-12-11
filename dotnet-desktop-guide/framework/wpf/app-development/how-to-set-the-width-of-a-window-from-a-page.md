---
title: 'Procedura: impostare la larghezza di una finestra da una pagina'
ms.date: 03/30/2017
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
ms.openlocfilehash: 1e16b75ecb85550facdf24a5b9e341cf0c061178
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951303"
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a>Procedura: impostare la larghezza di una finestra da una pagina
Questo esempio illustra come impostare la larghezza della finestra da un oggetto <xref:System.Windows.Controls.Page> .  
  
## <a name="example"></a>Esempio  
 Un oggetto <xref:System.Windows.Controls.Page> può impostare la larghezza della finestra host impostando <xref:System.Windows.Controls.Page.WindowWidth%2A> . Questa proprietà consente <xref:System.Windows.Controls.Page> a di non avere una conoscenza esplicita del tipo di finestra che la ospita.  
  
> [!NOTE]
> Per impostare la larghezza di una finestra utilizzando <xref:System.Windows.Controls.Page.WindowWidth%2A> , un oggetto <xref:System.Windows.Controls.Page> deve essere l'elemento figlio di una finestra.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]

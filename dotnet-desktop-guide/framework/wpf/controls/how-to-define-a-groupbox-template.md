---
title: 'Procedura: definire un modello GroupBox'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: f04e4a7e3feb4bd7c5dac1b4127d48923fb7ea62
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968626"
---
# <a name="how-to-define-a-groupbox-template"></a>Procedura: definire un modello GroupBox

Questo esempio illustra come creare un modello per un <xref:System.Windows.Controls.GroupBox> controllo.  
  
## <a name="example"></a>Esempio  

 Nell'esempio seguente viene definito un <xref:System.Windows.Controls.GroupBox> modello di controllo utilizzando un <xref:System.Windows.Controls.Grid> controllo per il layout. Il modello utilizza un oggetto <xref:System.Windows.Controls.BorderGapMaskConverter> per definire il bordo di in <xref:System.Windows.Controls.GroupBox> modo che il bordo non nasconda il <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> contenuto.  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.GroupBox>
- [Procedura: creare un oggetto GroupBox](/previous-versions/dotnet/netframework-3.5/ms748321(v=vs.90))

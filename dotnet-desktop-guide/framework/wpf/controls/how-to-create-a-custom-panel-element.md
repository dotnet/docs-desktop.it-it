---
title: 'Procedura: creare un elemento Panel personalizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
ms.openlocfilehash: 31edc75114c5dad613e5b65e7d8b051e2c3713af
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969466"
---
# <a name="how-to-create-a-custom-panel-element"></a>Procedura: creare un elemento Panel personalizzato
## <a name="example"></a>Esempio  
 Questo esempio illustra come eseguire l'override del comportamento di layout predefinito dell' <xref:System.Windows.Controls.Panel> elemento e creare elementi di layout personalizzati derivati da <xref:System.Windows.Controls.Panel> .  
  
 Nell'esempio viene definito un semplice <xref:System.Windows.Controls.Panel> elemento personalizzato denominato `PlotPanel` , che posiziona gli elementi figlio in base a due coordinate x e y hardcoded. In questo esempio, `x` e `y` sono entrambi impostati su `50` ; pertanto, tutti gli elementi figlio vengono posizionati in corrispondenza di tale posizione sugli assi x e y.  
  
 Per implementare <xref:System.Windows.Controls.Panel> comportamenti personalizzati, nell'esempio vengono utilizzati i <xref:System.Windows.FrameworkElement.MeasureOverride%2A> <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> metodi e. Ogni metodo restituisce i <xref:System.Windows.Size> dati necessari per posizionare ed eseguire il rendering degli elementi figlio.  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Panel>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)

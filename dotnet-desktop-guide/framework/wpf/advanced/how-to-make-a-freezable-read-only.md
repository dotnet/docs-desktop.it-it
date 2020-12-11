---
title: 'Procedura: impostare la proprietà di sola lettura per un oggetto Freezable'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: b8dcbec18977d46bd47b82f528deb2eeccc4e441
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965617"
---
# <a name="how-to-make-a-freezable-read-only"></a>Procedura: impostare la proprietà di sola lettura per un oggetto Freezable
Questo esempio illustra come creare un oggetto <xref:System.Windows.Freezable> di sola lettura chiamando il relativo <xref:System.Windows.Freezable.Freeze%2A> metodo.  
  
 Non è possibile bloccare un <xref:System.Windows.Freezable> oggetto se si verifica una delle condizioni seguenti `true` per l'oggetto:  
  
- Dispone di proprietà animate o con associazione a dati.  
  
- Dispone di proprietà impostate da una risorsa dinamica. Per ulteriori informazioni sulle risorse dinamiche, vedere le [risorse XAML](/dotnet/desktop-wpf/fundamentals/xaml-resources-define).  
  
- Contiene <xref:System.Windows.Freezable> oggetti secondari che non possono essere bloccati.  
  
 Se queste condizioni si riferiscono all' `false` <xref:System.Windows.Freezable> oggetto e non si intende modificarlo, provare a bloccarlo per ottenere vantaggi in termini di prestazioni.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene bloccato un <xref:System.Windows.Media.SolidColorBrush> oggetto, che è un tipo di <xref:System.Windows.Freezable> oggetto.  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 Per ulteriori informazioni sugli <xref:System.Windows.Freezable> oggetti, vedere [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md)
- [Procedure](base-elements-how-to-topics.md)

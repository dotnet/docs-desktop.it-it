---
title: 'Procedura: determinare se un oggetto Freezable è bloccato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
ms.openlocfilehash: 6a63862d35f2c40289ea6445eb3dab8a2abe4a61
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964975"
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a>Procedura: determinare se un oggetto Freezable è bloccato
Questo esempio illustra come determinare se un <xref:System.Windows.Freezable> oggetto è bloccato. Se si tenta di modificare un <xref:System.Windows.Freezable> oggetto bloccato, viene generata un'eccezione <xref:System.InvalidOperationException> . Per evitare di generare questa eccezione, utilizzare la <xref:System.Windows.Freezable.IsFrozen%2A> proprietà dell' <xref:System.Windows.Freezable> oggetto per determinare se è bloccata.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene bloccato un oggetto <xref:System.Windows.Media.SolidColorBrush> , quindi viene testato utilizzando la <xref:System.Windows.Freezable.IsFrozen%2A> proprietà per determinare se è bloccato.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 Per ulteriori informazioni sugli <xref:System.Windows.Freezable> oggetti, vedere [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.IsFrozen%2A>
- [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md)
- [Procedure](base-elements-how-to-topics.md)

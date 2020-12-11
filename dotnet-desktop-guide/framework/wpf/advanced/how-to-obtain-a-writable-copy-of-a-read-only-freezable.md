---
title: 'Procedura: ottenere una copia scrivibile di un oggetto Freezable di sola lettura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
ms.openlocfilehash: 910c5dada6ca82f68992722e4df6b35f9f7497c7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968419"
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a>Procedura: ottenere una copia scrivibile di un oggetto Freezable di sola lettura
Questo esempio illustra come usare il <xref:System.Windows.Freezable.Clone%2A> metodo per creare una copia scrivibile di un oggetto di sola lettura <xref:System.Windows.Freezable> .  
  
 Dopo che un <xref:System.Windows.Freezable> oggetto è stato contrassegnato come di sola lettura ("bloccato"), non è possibile modificarlo. Tuttavia, è possibile usare il <xref:System.Windows.Freezable.Clone%2A> metodo per creare un clone modificabile dell'oggetto bloccato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un clone modificabile di un <xref:System.Windows.Media.SolidColorBrush> oggetto bloccato.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 Per ulteriori informazioni sugli <xref:System.Windows.Freezable> oggetti, vedere [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CloneCurrentValue%2A>
- [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md)
- [Procedure](base-elements-how-to-topics.md)

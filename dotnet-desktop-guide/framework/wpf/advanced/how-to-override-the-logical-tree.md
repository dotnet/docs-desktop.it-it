---
title: "Procedura: Eseguire l'override dell'albero logico"
ms.date: 03/30/2017
helpviewer_keywords:
- overriding the logical tree [WPF]
- logical tree [WPF], overriding
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
ms.openlocfilehash: bf3459fff1a90326794d6713dd39c73596b0e960
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968416"
---
# <a name="how-to-override-the-logical-tree"></a>Procedura: Eseguire l'override dell'albero logico
Benché nella maggior parte dei casi non sia necessario, gli autori di controlli avanzati hanno la possibilità di eseguire l'override dell'albero logico.  
  
## <a name="example"></a>Esempio  
 Questo esempio illustra come sottoclasse <xref:System.Windows.Controls.StackPanel> per eseguire l'override dell'albero logico, in questo caso per applicare un comportamento che il pannello può avere solo ed eseguirà il rendering di un singolo elemento figlio. Benché non si tratti necessariamente di un comportamento utile, viene presentato come mezzo per illustrare lo scenario di override del normale albero logico di un elemento.  
  
 [!code-csharp[LogicalOverride#SingletonPanel](~/samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 Per altre informazioni sull'albero logico, vedere [Strutture ad albero in WPF](trees-in-wpf.md).

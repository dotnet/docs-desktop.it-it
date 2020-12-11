---
title: 'Procedura: definire un ambito del nome'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- name scope [WPF], defining
- Storyboards [WPF], animating in procedural code
- animation [WPF], Storyboards [WPF], in procedural code
ms.assetid: 4f361925-6a08-40dc-8231-a61111c6b28b
ms.openlocfilehash: a03f477dd31909e8cb9dde9cd29da6f38d665758
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951591"
---
# <a name="how-to-define-a-name-scope"></a>Procedura: definire un ambito del nome
Per eseguire un'animazione con <xref:System.Windows.Media.Animation.Storyboard> nel codice, è necessario creare <xref:System.Windows.NameScope> e registrare i nomi degli oggetti di destinazione con l'elemento proprietario dell'ambito del nome. Nell'esempio seguente <xref:System.Windows.NameScope> viene creato un oggetto per `myMainPanel` . Due pulsanti, `button1` e `button2` , vengono aggiunti al pannello e i relativi nomi sono registrati. Vengono create diverse animazioni e una <xref:System.Windows.Media.Animation.Storyboard> . Il metodo dello storyboard <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> viene usato per avviare le animazioni.  
  
 Poiché `button1` , `button2` e `myMainPanel` condividono tutti lo stesso ambito dei nomi, è possibile usare uno qualsiasi di essi con il <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo per avviare le animazioni.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## <a name="see-also"></a>Vedere anche

- [Aggiungere un'animazione a una proprietà usando uno storyboard](how-to-animate-a-property-by-using-a-storyboard.md)
- [Cenni preliminari sull'animazione](animation-overview.md)

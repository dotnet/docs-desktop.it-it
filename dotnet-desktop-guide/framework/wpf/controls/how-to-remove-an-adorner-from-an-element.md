---
title: 'Procedura: rimuovere uno strumento decorativo da un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
ms.openlocfilehash: 256dd6fa0117f88aec2ef6b60c6dcd4c33b57855
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966175"
---
# <a name="how-to-remove-an-adorner-from-an-element"></a>Procedura: rimuovere uno strumento decorativo da un elemento
Questo esempio Mostra come rimuovere a livello di codice uno strumento decorativo specifico da un oggetto specificato <xref:System.Windows.UIElement> .  
  
## <a name="example"></a>Esempio  
 Questo esempio di codice dettagliato rimuove il primo strumento decorativo nella matrice degli Adorner restituiti da <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> .  Questo esempio si verifica per recuperare gli strumenti decorativi in un oggetto <xref:System.Windows.UIElement> denominato *TextBox*.  Se l'elemento specificato nella chiamata a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> non dispone di strumenti decorativi, `null` viene restituito.  Questo codice verifica in modo esplicito la presenza di una matrice null ed è ideale per le applicazioni in cui è prevista una matrice null relativamente comune.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a>Esempio  
 Questo esempio di codice condensato è funzionalmente equivalente all'esempio dettagliato illustrato in precedenza. Questo codice non verifica in modo esplicito la presenza di una matrice null, pertanto è possibile che venga <xref:System.NullReferenceException> generata un'eccezione.  Questo codice è ideale per le applicazioni in cui è prevista una matrice di valori null.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sugli strumenti decorativi visuali](adorners-overview.md)

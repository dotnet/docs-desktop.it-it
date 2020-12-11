---
title: 'Procedura: rimuovere tutti gli strumenti decorativi visuali da un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
ms.openlocfilehash: 8504bb1ec70de188033b2b092bbb66cf9da3dc11
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969742"
---
# <a name="how-to-remove-all-adorners-from-an-element"></a>Procedura: rimuovere tutti gli strumenti decorativi visuali da un elemento
In questo esempio viene illustrato come rimuovere a livello di codice tutti gli strumenti decorativi da un oggetto specificato <xref:System.Windows.UIElement> .  
  
## <a name="example"></a>Esempio  
 Questo esempio di codice dettagliato consente di rimuovere tutti gli strumenti decorativi nella matrice degli Adorner restituiti da <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> .  Questo esempio si verifica per recuperare gli strumenti decorativi in un oggetto <xref:System.Windows.UIElement> denominato *TextBox*.  Se l'elemento specificato nella chiamata a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> non dispone di strumenti decorativi, `null` viene restituito.  Questo codice verifica in modo esplicito la presenza di una matrice null ed è ideale per le applicazioni in cui è prevista una matrice null relativamente comune.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## <a name="example"></a>Esempio  
 Questo esempio di codice condensato è funzionalmente equivalente all'esempio dettagliato illustrato in precedenza. Questo codice non verifica in modo esplicito la presenza di una matrice null, pertanto è possibile che venga <xref:System.NullReferenceException> generata un'eccezione.  Questo codice è ideale per le applicazioni in cui è prevista una matrice di valori null.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sugli strumenti decorativi visuali](adorners-overview.md)

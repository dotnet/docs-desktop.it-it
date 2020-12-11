---
title: 'Procedura: Eseguire il rendering di un elemento dello stile visivo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- visual themes [Windows Forms], applying to elements of Windows Forms applications
- professional appearance [Windows Forms], applying to elements of Windows Forms applications
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: a207781b-1baa-4ce9-b788-1e951bd4b5df
ms.openlocfilehash: a2b9524b6a3e3c77d3c68c4d9e138b8c0e2a9373
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961687"
---
# <a name="how-to-render-a-visual-style-element"></a>Procedura: Eseguire il rendering di un elemento dello stile visivo
Lo <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> spazio dei nomi espone <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> oggetti che rappresentano gli elementi dell'interfaccia utente di Windows supportati dagli stili di visualizzazione. In questo argomento viene illustrato come utilizzare la <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> classe per eseguire il rendering dell'oggetto <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> che rappresenta i pulsanti **Disconnetti** e **Arresta** il menu Start.  
  
### <a name="to-render-a-visual-style-element"></a>Per eseguire il rendering di un elemento dello stile di visualizzazione  
  
1. Creare un oggetto <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> e impostarlo sull'elemento che si desidera creare. Si noti l'uso della <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> proprietà e del <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> metodo. il <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> costruttore genererà un'eccezione se gli stili di visualizzazione sono disabilitati o un elemento non è definito.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#4)]  
  
2. Chiamare il <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> metodo per eseguire il rendering dell'elemento <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> rappresentato attualmente da.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#6)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Controllo personalizzato derivato dalla <xref:System.Windows.Forms.Control> classe.  
  
- Oggetto <xref:System.Windows.Forms.Form> che ospita il controllo personalizzato.  
  
- Riferimenti agli <xref:System?displayProperty=nameWithType> <xref:System.Drawing?displayProperty=nameWithType> <xref:System.Windows.Forms?displayProperty=nameWithType> <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> spazi dei nomi,, e.  
  
## <a name="see-also"></a>Vedere anche

- [Rendering dei controlli con stili visivi](rendering-controls-with-visual-styles.md)

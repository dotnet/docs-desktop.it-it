---
title: 'Procedura: Impostare il colore di un oggetto Pen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
ms.openlocfilehash: ee2d3f8cdf6dd10ca2a9ff0dd3e66b164c84f21b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963253"
---
# <a name="how-to-set-the-color-of-a-pen"></a>Procedura: Impostare il colore di un oggetto Pen
Questo esempio Mostra come modificare il colore di un oggetto preesistente <xref:System.Drawing.Pen>  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- <xref:System.Drawing.Pen>Oggetto denominato `myPen` .  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 È necessario chiamare <xref:System.Drawing.Pen.Dispose%2A> sugli oggetti che utilizzano risorse di sistema, ad esempio oggetti, al <xref:System.Drawing.Pen> termine dell'utilizzo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Pen>
- [Guida introduttiva alla programmazione grafica](getting-started-with-graphics-programming.md)
- [Procedura: Creare un oggetto Pen](how-to-create-a-pen.md)
- [Uso di una penna per disegnare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
- [Penne, linee e rettangoli in GDI+](pens-lines-and-rectangles-in-gdi.md)

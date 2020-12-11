---
title: Utilizzo della trasformazione di tipo World
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], world transformation
- world transformation [Windows Forms], examples
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
ms.openlocfilehash: f40d7e8cb814344365e8b88c2659751903b79d77
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962380"
---
# <a name="using-the-world-transformation"></a>Utilizzo della trasformazione di tipo World
La trasformazione globale è una proprietà della <xref:System.Drawing.Graphics> classe. I numeri che specificano la trasformazione globale vengono archiviati in un <xref:System.Drawing.Drawing2D.Matrix> oggetto, che rappresenta una matrice 3 × 3. Le <xref:System.Drawing.Drawing2D.Matrix> <xref:System.Drawing.Graphics> classi e hanno diversi metodi per impostare i numeri nella matrice di trasformazione mondiale.  
  
## <a name="different-types-of-transformations"></a>Tipi diversi di trasformazioni  
 Nell'esempio seguente, il codice crea prima un rettangolo 50 × 50 e lo individua all'origine (0,0). L'origine si trova nell'angolo superiore sinistro dell'area client.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 Il codice seguente applica una trasformazione di ridimensionamento che espande il rettangolo per un fattore di 1,75 nella direzione x e compatta il rettangolo per un fattore di 0,5 nella direzione y:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 Il risultato è un rettangolo più lungo nella direzione x e più breve nella direzione y rispetto all'originale.  
  
 Per ruotare il rettangolo anziché ridimensionarlo, usare il codice seguente:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 Per tradurre il rettangolo, usare il codice seguente:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Drawing2D.Matrix>
- [Sistemi di coordinate e trasformazioni](coordinate-systems-and-transformations.md)
- [Utilizzo di trasformazioni nel codice gestito GDI+](using-transformations-in-managed-gdi.md)

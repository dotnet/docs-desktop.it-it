---
title: "Procedura: Eseguire l'hit testing usando una regione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 136f15f1364fb2aed791b4a61d0f11411b055967
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962446"
---
# <a name="how-to-use-hit-testing-with-a-region"></a>Procedura: Eseguire l'hit testing usando una regione
Lo scopo dell'hit testing è determinare se il cursore si trova su un determinato oggetto, ad esempio un'icona o un pulsante.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creata un'area con più forme formando l'Unione di due aree rettangolari. Si supponga che la variabile `point` contenga il percorso del clic più recente. Il codice verifica se `point` è nell'area a forma di più. Se il punto si trova nell'area (un hit), l'area viene riempita con un pennello rosso opaco. In caso contrario, l'area viene riempita con un pennello rosso semitrasparente.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Region>
- [Regioni in GDI+](regions-in-gdi.md)
- [Procedura: Usare il ritaglio per definire una regione](how-to-use-clipping-with-a-region.md)

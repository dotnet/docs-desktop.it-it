---
title: 'Procedura: Inserire un elemento in un testo a livello di codice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Text Animation sample [WPF]
- elements [WPF], inserting into text
- inserting elements into text [WPF]
- TextPointer objects [WPF]
- text [WPF], inserting elements
ms.assetid: 97bd950a-25ac-4e42-a311-94b6420d4136
ms.openlocfilehash: ea9850c8490ec37032d4565c6b3375e3116d4313
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966967"
---
# <a name="how-to-insert-an-element-into-text-programmatically"></a>Procedura: Inserire un elemento in un testo a livello di codice
Nell'esempio seguente viene illustrato come utilizzare due <xref:System.Windows.Documents.TextPointer> oggetti per specificare un intervallo all'interno del testo a cui applicare un <xref:System.Windows.Documents.Span> elemento.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/CSharp/InsertInlineIntoTextExample.cs#insertinlineintotextexamplewholepage)]
 [!code-vb[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/VisualBasic/InsertInlineIntoTextExample.vb#insertinlineintotextexamplewholepage)]  
  
 Nella figura riportata di seguito viene illustrato l'esempio in questione.  
  
 ![Elemento Span applicato a un intervallo di testo](./media/flow-insertelementintotextprogrammatically.png "Flow_InsertElementIntoTextProgrammatically")  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sui documenti dinamici](flow-document-overview.md)

---
title: Creare un bordo intorno a un controllo usando la spaziatura interna
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins
- controls [Windows Forms], Margin property
- padding [Windows Forms], Windows Forms
- controls [Windows Forms], Padding property
- controls [Windows Forms], outlining
- Padding property [Windows Forms]
- margins [Windows Forms], Windows Forms
- Margin property [Windows Forms]
ms.assetid: bac7ed4d-a163-4259-98bd-155a36345890
ms.openlocfilehash: 114186ab5784cf892cb01e9fe2648ce22cecc4b7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963925"
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a>Procedura: Creare un bordo intorno a un controllo di Windows Forms usando la spaziatura
Nell'esempio di codice riportato di seguito viene illustrato come creare un bordo o un contorno attorno a un <xref:System.Windows.Forms.RichTextBox> controllo. Nell'esempio viene impostato il valore della <xref:System.Windows.Forms.Panel> proprietà di un controllo <xref:System.Windows.Forms.Padding> su 5 e la <xref:System.Windows.Forms.Control.Dock%2A> proprietà di un controllo figlio viene impostata <xref:System.Windows.Forms.RichTextBox> su <xref:System.Windows.Forms.DockStyle.Fill> . L'oggetto <xref:System.Windows.Forms.Control.BackColor%2A> del <xref:System.Windows.Forms.Panel> controllo è impostato su <xref:System.Drawing.Color.Blue%2A> , che crea un bordo blu attorno al <xref:System.Windows.Forms.RichTextBox> controllo.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.Padding#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Padding>
- [Margini e spaziatura nei controlli Windows Form](margin-and-padding-in-windows-forms-controls.md)

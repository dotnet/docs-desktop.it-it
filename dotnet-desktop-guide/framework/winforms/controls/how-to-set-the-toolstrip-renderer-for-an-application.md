---
title: "Procedura: Impostare il renderer ToolStrip per un'applicazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Renderer property [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], customizing
ms.assetid: 46acef3e-9844-4ae8-9a2e-3006fe99cadf
ms.openlocfilehash: c9250b723e68ac97d1486a896392bf64c66cdfbc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965203"
---
# <a name="how-to-set-the-toolstrip-renderer-for-an-application"></a>Procedura: Impostare il renderer ToolStrip per un'applicazione
È possibile personalizzare l'aspetto dei singoli controlli <xref:System.Windows.Forms.ToolStrip> o di tutti i controlli <xref:System.Windows.Forms.ToolStrip> presenti nell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice riportato di seguito viene dimostrato come applicare selettivamente un renderer personalizzato a un controllo <xref:System.Windows.Forms.ToolStrip> e a un controllo <xref:System.Windows.Forms.MenuStrip>.  
  
 Per usare questo esempio di codice, compilare ed eseguire l'applicazione, quindi selezionare l'ambito del rendering personalizzato dal controllo <xref:System.Windows.Forms.ComboBox>. Scegliere **Applica** per impostare il renderer.  
  
 Per visualizzare il rendering della voce di menu personalizzata, selezionare l' <xref:System.Windows.Forms.MenuStrip> opzione nel <xref:System.Windows.Forms.ComboBox> controllo, fare clic su **applica**, quindi aprire la voce di menu **file** .  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#70)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#70)]  
  
 Impostare la proprietà <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> per applicare un renderer personalizzato a tutti i controlli <xref:System.Windows.Forms.ToolStrip> dell'applicazione.  
  
 Impostare la proprietà <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> per applicare un renderer personalizzato a un singolo controllo <xref:System.Windows.Forms.ToolStrip>.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System.Design, System.Drawing e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- [Controllo ToolStrip](toolstrip-control-windows-forms.md)

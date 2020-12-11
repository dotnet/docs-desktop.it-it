---
title: 'Procedura: Elencare i decodificatori installati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
ms.openlocfilehash: 961862d6212b7e76812fc222d3a99f08528d9a16
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962599"
---
# <a name="how-to-list-installed-decoders"></a>Procedura: Elencare i decodificatori installati
Potrebbe essere necessario elencare i decodificatori di immagini disponibili in un computer per determinare se l'applicazione può leggere un formato di file di immagine specifico. La <xref:System.Drawing.Imaging.ImageCodecInfo> classe fornisce i <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> metodi statici per poter determinare quali decodificatori di immagini sono disponibili. <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> Restituisce una matrice di <xref:System.Drawing.Imaging.ImageCodecInfo> oggetti.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene restituito l'elenco di decodificatori installati e i relativi valori delle proprietà.  
  
 [!code-csharp[UsingImageEncodersDecoders#2](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Applicazione Windows Forms.  
  
- Oggetto <xref:System.Windows.Forms.PaintEventArgs> , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Elencare i codificatori installati](how-to-list-installed-encoders.md)
- [Utilizzo di codificatori e decodificatori di immagini nel codice gestito GDI+](using-image-encoders-and-decoders-in-managed-gdi.md)

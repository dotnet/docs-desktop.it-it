---
title: 'Procedura: Elencare i codificatori installati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
ms.openlocfilehash: 2634dd96b3aa5edcecde092919eb328b7f3dadc3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963364"
---
# <a name="how-to-list-installed-encoders"></a>Procedura: Elencare i codificatori installati
Potrebbe essere necessario elencare i codificatori di immagini disponibili in un computer per determinare se l'applicazione può essere salvata in un formato di file di immagine specifico. La <xref:System.Drawing.Imaging.ImageCodecInfo> classe fornisce i <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> metodi statici per poter determinare quali codificatori di immagini sono disponibili. <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> Restituisce una matrice di <xref:System.Drawing.Imaging.ImageCodecInfo> oggetti.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene restituito l'elenco dei codificatori installati e i relativi valori delle proprietà.  
  
 [!code-csharp[UsingImageEncodersDecoders#1](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Applicazione Windows Forms.  
  
- Oggetto <xref:System.Windows.Forms.PaintEventArgs> , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Elencare i decodificatori installati](how-to-list-installed-decoders.md)
- [Utilizzo di codificatori e decodificatori di immagini nel codice gestito GDI+](using-image-encoders-and-decoders-in-managed-gdi.md)

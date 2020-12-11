---
title: Linee e riempimenti con fusione alfa
ms.date: 03/30/2017
helpviewer_keywords:
- lines [Windows Forms], adding transparency
- examples [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with lines
- alpha blending
- lines [Windows Forms], alpha blending
- fills [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with fills
- shapes [Windows Forms], adding transparency
ms.assetid: 5440f48c-3ac9-44c3-b170-c1c110bdbab8
ms.openlocfilehash: 66061341ee6539e2172c537a0b2a6ec9ff87565c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952254"
---
# <a name="alpha-blending-lines-and-fills"></a>Linee e riempimenti con fusione alfa
In GDI+, un colore è un valore a 32 bit con 8 bit ciascuno per Alpha, rosso, verde e blu. Il valore alfa indica la trasparenza del colore, ovvero la misura in cui il colore viene mescolato con il colore di sfondo. I valori alfa variano da 0 a 255, dove 0 rappresenta un colore completamente trasparente e 255 rappresenta un colore completamente opaco.  
  
 La fusione alfa è una combinazione pixel per pixel dei dati di origine e di colore di sfondo. Ognuno dei tre componenti (rosso, verde, blu) di un determinato colore di origine viene mescolato con il componente corrispondente del colore di sfondo in base alla formula seguente:  
  
 displayColor = sourceColor × Alpha/255 + backgroundColor × (255 – Alpha)/255  
  
 Si supponga, ad esempio, che il componente rosso del colore di origine sia 150 e che il componente rosso del colore di sfondo sia 100. Se il valore alfa è 200, il componente rosso del colore risultante viene calcolato come segue:  
  
 150 × 200 / 255 + 100 × (255 – 200) / 255 = 139  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: Disegnare linee opache e semitrasparenti](how-to-draw-opaque-and-semitransparent-lines.md)  
 Viene illustrato come creare linee con Blend alfa.  
  
 [Procedura: Disegnare con pennelli opachi e semitrasparenti](how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 Viene illustrato come alfa-blend con i pennelli.  
  
 [Procedura: Usare la modalità di composizione per controllare la fusione alfa](how-to-use-compositing-mode-to-control-alpha-blending.md)  
 Viene descritto come controllare la fusione alfa usando <xref:System.Drawing.Drawing2D.CompositingMode> .  
  
 [Procedura: Usare una matrice di colori per impostare i valori alfa nelle immagini](how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 Viene illustrato come usare un <xref:System.Drawing.Imaging.ColorMatrix> oggetto per controllare la fusione alfa.

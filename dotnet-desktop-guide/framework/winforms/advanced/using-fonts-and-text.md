---
title: Utilizzo di tipi di carattere e testo
ms.date: 03/30/2017
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing in Windows Forms
- examples [Windows Forms], fonts and text
- fonts [Windows Forms], using in Windows Forms
- strings [Windows Forms], drawing in Windows Forms
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
ms.openlocfilehash: 73a4af5fe7367e777fcb83af8c84c09be91e5b1e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963034"
---
# <a name="using-fonts-and-text"></a>Utilizzo di tipi di carattere e testo
Sono disponibili diverse classi offerte da GDI+ e GDI per il disegno di testo in Windows Forms. La <xref:System.Drawing.Graphics> classe GDI+ dispone di diversi <xref:System.Drawing.Graphics.DrawString%2A> metodi che consentono di specificare varie caratteristiche del testo, ad esempio la posizione, il rettangolo di delimitazione, il tipo di carattere e il formato. Inoltre, è possibile creare e misurare il testo con GDI usando i <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodi statici e <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> offerti dalla `TextRenderer` classe. I metodi GDI consentono inoltre di specificare il percorso, il tipo di carattere e il formato. È possibile scegliere GDI o GDI+ per il rendering del testo; Tuttavia, GDI offre in genere prestazioni migliori e misurazioni del testo più accurate. Altre classi che contribuiscono al rendering del testo includono `FontFamily` ,, `Font` <xref:System.Drawing.StringFormat> e `TextFormatFlags` .  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: Creare tipi di carattere e famiglie di caratteri](how-to-construct-font-families-and-fonts.md)  
 Viene illustrato come creare `Font` `FontFamily` oggetti e.  
  
 [Procedura: Disegnare testo in una posizione specificata](how-to-draw-text-at-a-specified-location.md)  
 Viene descritto come creare testo in una determinata posizione utilizzando GDI+ e GDI.  
  
 [Procedura: Disegnare testo disposto su più righe in un rettangolo](how-to-draw-wrapped-text-in-a-rectangle.md)  
 Viene illustrato come creare testo in un rettangolo utilizzando GDI+ e GDI.  
  
 [Procedura: Disegnare testo con GDI](how-to-draw-text-with-gdi.md)  
 Viene illustrato come utilizzare GDI per il disegno di testo.  
  
 [Procedura: Allineare il testo disegnato](how-to-align-drawn-text.md)  
 Viene illustrato come formattare il testo GDI+ e il testo GDI.  
  
 [Procedura: Creare testo verticale](how-to-create-vertical-text.md)  
 Viene descritto come creare testo allineato verticalmente con GDI+.  
  
 [Procedura: Impostare tabulazioni nel testo disegnato](how-to-set-tab-stops-in-drawn-text.md)  
 Mostra come creare un testo con tabulazioni con GDI+.  
  
 [Procedura: Enumerare i tipi di carattere installati](how-to-enumerate-installed-fonts.md)  
 Viene illustrato come elencare i nomi dei tipi di carattere installati.  
  
 [Procedura: Creare una raccolta di tipi di carattere privata](how-to-create-a-private-font-collection.md)  
 Viene descritto come creare un <xref:System.Drawing.Text.PrivateFontCollection> oggetto.  
  
 [Procedura: Ottenere le misure dei tipi di carattere](how-to-obtain-font-metrics.md)  
 Viene illustrato come ottenere le metriche dei tipi di carattere, ad esempio l'ascesa e la discesa delle celle.  
  
 [Procedura: Usare l'antialiasing nel testo](how-to-use-antialiasing-with-text.md)  
 Viene illustrato come utilizzare l'anti-aliasing durante il disegno di testo.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.Drawing.Font>  
 Descrive questa classe e contiene i collegamenti a tutti i relativi membri.  
  
 <xref:System.Drawing.FontFamily>  
 Descrive questa classe e contiene i collegamenti a tutti i relativi membri.  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 Descrive questa classe e contiene i collegamenti a tutti i relativi membri.  
  
 <xref:System.Windows.Forms.TextRenderer>  
 Descrive questa classe e contiene i collegamenti a tutti i relativi membri.  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 Descrive questa classe e contiene i collegamenti a tutti i relativi membri.

---
title: Metafile in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
ms.openlocfilehash: df54289722cf12bad840722c6eafdaa43279a5dc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960661"
---
# <a name="metafiles-in-gdi"></a>Metafile in GDI+
GDI+ fornisce la <xref:System.Drawing.Imaging.Metafile> classe in modo che sia possibile registrare e visualizzare i metafile. Un metafile, detto anche immagine vettoriale, è un'immagine archiviata come sequenza di comandi e impostazioni di disegno. I comandi e le impostazioni registrati in un <xref:System.Drawing.Imaging.Metafile> oggetto possono essere archiviati in memoria o salvati in un file o in un flusso.  
  
## <a name="metafile-formats"></a>Formati di metafile  
 GDI+ consente di visualizzare i metafile archiviati nei formati seguenti:  
  
- Metafile di Windows (WMF)  
  
- Enhanced Metafile (EMF)  
  
- EMF +  
  
 GDI+ può registrare i metafile nei formati EMF e EMF +, ma non nel formato WMF.  
  
 EMF + è un'estensione di EMF che consente l'archiviazione di record GDI+. Sono disponibili due varianti nel formato EMF +, ovvero EMF + Only e EMF + Dual. EMF + solo i metafile contengono solo record GDI+. Tali metafile possono essere visualizzati da GDI+ ma non da GDI. I metafile EMF + Dual contengono i record GDI+ e GDI. Ogni record GDI+ in un metafile EMF + Dual è associato a un record GDI alternativo. Tali metafile possono essere visualizzati da GDI+ o da GDI.  
  
 Nell'esempio seguente viene visualizzato un metafile salvato in precedenza come file. Il metafile viene visualizzato con l'angolo superiore sinistro in (100, 100).  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>Vedere anche

- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)

---
title: Utilizzo di codificatori e decodificatori di immagini nel codice gestito GDI+
ms.date: 03/30/2017
helpviewer_keywords:
- image encoders [Windows Forms], using
- image decoders [Windows Forms], using
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
ms.openlocfilehash: 8cd66f3ce3da462867da9e23c38b3f6d877c058c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962383"
---
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a>Utilizzo di codificatori e decodificatori di immagini nel codice gestito GDI+
Lo <xref:System.Drawing> spazio dei nomi fornisce le <xref:System.Drawing.Image> <xref:System.Drawing.Bitmap> classi e per l'archiviazione e la manipolazione delle immagini. Utilizzando codificatori di immagini in GDI+, è possibile scrivere immagini dalla memoria su disco. Utilizzando i decodificatori di immagini in GDI+, è possibile caricare immagini dal disco in memoria. Un codificatore converte i dati in un <xref:System.Drawing.Image> oggetto o <xref:System.Drawing.Bitmap> in un formato di file su disco designato. Un decodificatore converte i dati in un file su disco nel formato richiesto dagli <xref:System.Drawing.Image> oggetti e <xref:System.Drawing.Bitmap> .  
  
 GDI+ include codificatori e decodificatori incorporati che supportano i tipi di file seguenti:  
  
- BMP  
  
- GIF  
  
- JPEG  
  
- PNG  
  
- TIFF  
  
 GDI+ dispone inoltre di decodificatori incorporati che supportano i tipi di file seguenti:  
  
- WMF  
  
- EMF  
  
- ICONA  
  
 Negli argomenti seguenti vengono illustrati in modo più dettagliato i codificatori e i decodificatori:  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: Elencare i codificatori installati](how-to-list-installed-encoders.md)  
 Viene descritto come elencare i codificatori disponibili in un computer.  
  
 [Procedura: Elencare i decodificatori installati](how-to-list-installed-decoders.md)  
 Viene descritto come elencare i decodificatori disponibili in un computer.  
  
 [Procedura: Determinare i parametri supportati da un codificatore](how-to-determine-the-parameters-supported-by-an-encoder.md)  
 Viene descritto come elencare l'oggetto <xref:System.Drawing.Imaging.EncoderParameters> supportato da un codificatore.  
  
 [Procedura: Convertire un'immagine BMP in un'immagine PNG](how-to-convert-a-bmp-image-to-a-png-image.md)  
 Viene descritto come salvare un'immagine in un formato di immagine diverso.  
  
 [Procedura: Impostare il livello di compressione JPEG](how-to-set-jpeg-compression-level.md)  
 Viene descritto come modificare il livello di qualità di un'immagine.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Informazioni sul codice gestito GDI+](about-gdi-managed-code.md)  
  
 [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)

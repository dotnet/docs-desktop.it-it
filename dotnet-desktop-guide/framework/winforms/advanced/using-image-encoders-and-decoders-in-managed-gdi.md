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
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a><span data-ttu-id="030aa-102">Utilizzo di codificatori e decodificatori di immagini nel codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="030aa-102">Using Image Encoders and Decoders in Managed GDI+</span></span>
<span data-ttu-id="030aa-103">Lo <xref:System.Drawing> spazio dei nomi fornisce le <xref:System.Drawing.Image> <xref:System.Drawing.Bitmap> classi e per l'archiviazione e la manipolazione delle immagini.</span><span class="sxs-lookup"><span data-stu-id="030aa-103">The <xref:System.Drawing> namespace provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <span data-ttu-id="030aa-104">Utilizzando codificatori di immagini in GDI+, è possibile scrivere immagini dalla memoria su disco.</span><span class="sxs-lookup"><span data-stu-id="030aa-104">By using image encoders in GDI+, you can write images from memory to disk.</span></span> <span data-ttu-id="030aa-105">Utilizzando i decodificatori di immagini in GDI+, è possibile caricare immagini dal disco in memoria.</span><span class="sxs-lookup"><span data-stu-id="030aa-105">By using image decoders in GDI+, you can load images from disk into memory.</span></span> <span data-ttu-id="030aa-106">Un codificatore converte i dati in un <xref:System.Drawing.Image> oggetto o <xref:System.Drawing.Bitmap> in un formato di file su disco designato.</span><span class="sxs-lookup"><span data-stu-id="030aa-106">An encoder translates the data in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object into a designated disk file format.</span></span> <span data-ttu-id="030aa-107">Un decodificatore converte i dati in un file su disco nel formato richiesto dagli <xref:System.Drawing.Image> oggetti e <xref:System.Drawing.Bitmap> .</span><span class="sxs-lookup"><span data-stu-id="030aa-107">A decoder translates the data in a disk file to the format required by the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> objects.</span></span>  
  
 <span data-ttu-id="030aa-108">GDI+ include codificatori e decodificatori incorporati che supportano i tipi di file seguenti:</span><span class="sxs-lookup"><span data-stu-id="030aa-108">GDI+ has built-in encoders and decoders that support the following file types:</span></span>  
  
- <span data-ttu-id="030aa-109">BMP</span><span class="sxs-lookup"><span data-stu-id="030aa-109">BMP</span></span>  
  
- <span data-ttu-id="030aa-110">GIF</span><span class="sxs-lookup"><span data-stu-id="030aa-110">GIF</span></span>  
  
- <span data-ttu-id="030aa-111">JPEG</span><span class="sxs-lookup"><span data-stu-id="030aa-111">JPEG</span></span>  
  
- <span data-ttu-id="030aa-112">PNG</span><span class="sxs-lookup"><span data-stu-id="030aa-112">PNG</span></span>  
  
- <span data-ttu-id="030aa-113">TIFF</span><span class="sxs-lookup"><span data-stu-id="030aa-113">TIFF</span></span>  
  
 <span data-ttu-id="030aa-114">GDI+ dispone inoltre di decodificatori incorporati che supportano i tipi di file seguenti:</span><span class="sxs-lookup"><span data-stu-id="030aa-114">GDI+ also has built-in decoders that support the following file types:</span></span>  
  
- <span data-ttu-id="030aa-115">WMF</span><span class="sxs-lookup"><span data-stu-id="030aa-115">WMF</span></span>  
  
- <span data-ttu-id="030aa-116">EMF</span><span class="sxs-lookup"><span data-stu-id="030aa-116">EMF</span></span>  
  
- <span data-ttu-id="030aa-117">ICONA</span><span class="sxs-lookup"><span data-stu-id="030aa-117">ICON</span></span>  
  
 <span data-ttu-id="030aa-118">Negli argomenti seguenti vengono illustrati in modo più dettagliato i codificatori e i decodificatori:</span><span class="sxs-lookup"><span data-stu-id="030aa-118">The following topics discuss encoders and decoders in more detail:</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="030aa-119">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="030aa-119">In This Section</span></span>  
 [<span data-ttu-id="030aa-120">Procedura: Elencare i codificatori installati</span><span class="sxs-lookup"><span data-stu-id="030aa-120">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)  
 <span data-ttu-id="030aa-121">Viene descritto come elencare i codificatori disponibili in un computer.</span><span class="sxs-lookup"><span data-stu-id="030aa-121">Describes how to list the encoders available on a computer.</span></span>  
  
 [<span data-ttu-id="030aa-122">Procedura: Elencare i decodificatori installati</span><span class="sxs-lookup"><span data-stu-id="030aa-122">How to: List Installed Decoders</span></span>](how-to-list-installed-decoders.md)  
 <span data-ttu-id="030aa-123">Viene descritto come elencare i decodificatori disponibili in un computer.</span><span class="sxs-lookup"><span data-stu-id="030aa-123">Describes how to list the decoders available on a computer.</span></span>  
  
 [<span data-ttu-id="030aa-124">Procedura: Determinare i parametri supportati da un codificatore</span><span class="sxs-lookup"><span data-stu-id="030aa-124">How to: Determine the Parameters Supported by an Encoder</span></span>](how-to-determine-the-parameters-supported-by-an-encoder.md)  
 <span data-ttu-id="030aa-125">Viene descritto come elencare l'oggetto <xref:System.Drawing.Imaging.EncoderParameters> supportato da un codificatore.</span><span class="sxs-lookup"><span data-stu-id="030aa-125">Describes how to list the <xref:System.Drawing.Imaging.EncoderParameters> supported by an encoder.</span></span>  
  
 [<span data-ttu-id="030aa-126">Procedura: Convertire un'immagine BMP in un'immagine PNG</span><span class="sxs-lookup"><span data-stu-id="030aa-126">How to: Convert a BMP image to a PNG image</span></span>](how-to-convert-a-bmp-image-to-a-png-image.md)  
 <span data-ttu-id="030aa-127">Viene descritto come salvare un'immagine in un formato di immagine diverso.</span><span class="sxs-lookup"><span data-stu-id="030aa-127">Describes how to save a image in a different image format.</span></span>  
  
 [<span data-ttu-id="030aa-128">Procedura: Impostare il livello di compressione JPEG</span><span class="sxs-lookup"><span data-stu-id="030aa-128">How to: Set JPEG Compression Level</span></span>](how-to-set-jpeg-compression-level.md)  
 <span data-ttu-id="030aa-129">Viene descritto come modificare il livello di qualità di un'immagine.</span><span class="sxs-lookup"><span data-stu-id="030aa-129">Describes how to change the quality level of an image.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="030aa-130">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="030aa-130">Reference</span></span>  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a><span data-ttu-id="030aa-131">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="030aa-131">Related Sections</span></span>  
 [<span data-ttu-id="030aa-132">Informazioni sul codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="030aa-132">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
  
 [<span data-ttu-id="030aa-133">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="030aa-133">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)

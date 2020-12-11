---
title: 'Procedura: Determinare i parametri supportati da un codificatore'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
ms.openlocfilehash: 3e5345180e0ff3321b9ef0b885b836d3e9456f28
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951455"
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a><span data-ttu-id="74159-102">Procedura: Determinare i parametri supportati da un codificatore</span><span class="sxs-lookup"><span data-stu-id="74159-102">How to: Determine the Parameters Supported by an Encoder</span></span>
<span data-ttu-id="74159-103">È possibile modificare i parametri dell'immagine, ad esempio la qualità e il livello di compressione, ma è necessario stabilire quali parametri sono supportati da un determinato codificatore di immagini.</span><span class="sxs-lookup"><span data-stu-id="74159-103">You can adjust image parameters, such as quality and compression level, but you must know which parameters are supported by a given image encoder.</span></span> <span data-ttu-id="74159-104">La <xref:System.Drawing.Image> classe fornisce il <xref:System.Drawing.Image.GetEncoderParameterList%2A> metodo in modo che sia possibile determinare quali parametri di immagine sono supportati per un determinato codificatore.</span><span class="sxs-lookup"><span data-stu-id="74159-104">The <xref:System.Drawing.Image> class provides the <xref:System.Drawing.Image.GetEncoderParameterList%2A> method so that you can determine which image parameters are supported for a particular encoder.</span></span> <span data-ttu-id="74159-105">Il codificatore viene specificato con un GUID.</span><span class="sxs-lookup"><span data-stu-id="74159-105">You specify the encoder with a GUID.</span></span> <span data-ttu-id="74159-106">Il <xref:System.Drawing.Image.GetEncoderParameterList%2A> metodo restituisce una matrice di <xref:System.Drawing.Imaging.EncoderParameter> oggetti.</span><span class="sxs-lookup"><span data-stu-id="74159-106">The <xref:System.Drawing.Image.GetEncoderParameterList%2A> method returns an array of <xref:System.Drawing.Imaging.EncoderParameter> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74159-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="74159-107">Example</span></span>  
 <span data-ttu-id="74159-108">Nel codice di esempio seguente vengono restituiti i parametri supportati per il codificatore JPEG.</span><span class="sxs-lookup"><span data-stu-id="74159-108">The following example code outputs the supported parameters for the JPEG encoder.</span></span> <span data-ttu-id="74159-109">Usare l'elenco di categorie di parametri e i GUID associati nella <xref:System.Drawing.Imaging.Encoder> Panoramica della classe per determinare la categoria per ogni parametro.</span><span class="sxs-lookup"><span data-stu-id="74159-109">Use the list of parameter categories and associated GUIDs in the <xref:System.Drawing.Imaging.Encoder> class overview to determine the category for each parameter.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#3](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="74159-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="74159-110">Compiling the Code</span></span>  
 <span data-ttu-id="74159-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="74159-111">This example requires:</span></span>  
  
- <span data-ttu-id="74159-112">Applicazione Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="74159-112">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="74159-113">Oggetto <xref:System.Windows.Forms.PaintEventArgs> , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .</span><span class="sxs-lookup"><span data-stu-id="74159-113">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74159-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74159-114">See also</span></span>

- [<span data-ttu-id="74159-115">Procedura: Elencare i codificatori installati</span><span class="sxs-lookup"><span data-stu-id="74159-115">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="74159-116">Tipi di bitmap</span><span class="sxs-lookup"><span data-stu-id="74159-116">Types of Bitmaps</span></span>](types-of-bitmaps.md)
- [<span data-ttu-id="74159-117">Utilizzo di codificatori e decodificatori di immagini nel codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="74159-117">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)

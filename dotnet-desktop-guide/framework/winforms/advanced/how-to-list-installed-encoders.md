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
# <a name="how-to-list-installed-encoders"></a><span data-ttu-id="1d985-102">Procedura: Elencare i codificatori installati</span><span class="sxs-lookup"><span data-stu-id="1d985-102">How to: List Installed Encoders</span></span>
<span data-ttu-id="1d985-103">Potrebbe essere necessario elencare i codificatori di immagini disponibili in un computer per determinare se l'applicazione può essere salvata in un formato di file di immagine specifico.</span><span class="sxs-lookup"><span data-stu-id="1d985-103">You may want to list the image encoders available on a computer, to determine whether your application can save to a particular image file format.</span></span> <span data-ttu-id="1d985-104">La <xref:System.Drawing.Imaging.ImageCodecInfo> classe fornisce i <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> metodi statici per poter determinare quali codificatori di immagini sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="1d985-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> static methods so that you can determine which image encoders are available.</span></span> <span data-ttu-id="1d985-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> Restituisce una matrice di <xref:System.Drawing.Imaging.ImageCodecInfo> oggetti.</span><span class="sxs-lookup"><span data-stu-id="1d985-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d985-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="1d985-106">Example</span></span>  
 <span data-ttu-id="1d985-107">Nell'esempio di codice seguente viene restituito l'elenco dei codificatori installati e i relativi valori delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="1d985-107">The following code example outputs the list of installed encoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#1](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1d985-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="1d985-108">Compiling the Code</span></span>  
 <span data-ttu-id="1d985-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d985-109">This example requires:</span></span>  
  
- <span data-ttu-id="1d985-110">Applicazione Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1d985-110">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="1d985-111">Oggetto <xref:System.Windows.Forms.PaintEventArgs> , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .</span><span class="sxs-lookup"><span data-stu-id="1d985-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d985-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d985-112">See also</span></span>

- [<span data-ttu-id="1d985-113">Procedura: Elencare i decodificatori installati</span><span class="sxs-lookup"><span data-stu-id="1d985-113">How to: List Installed Decoders</span></span>](how-to-list-installed-decoders.md)
- [<span data-ttu-id="1d985-114">Utilizzo di codificatori e decodificatori di immagini nel codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="1d985-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)

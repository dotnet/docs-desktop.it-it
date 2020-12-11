---
title: 'Procedura: Caricare in modo asincrono un suono in un Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SoundPlayer class [Windows Forms], loading sounds asynchronously
- sounds [Windows Forms], loading on separate threads
- threading [Windows Forms], sounds
ms.assetid: 3b6a9296-1d5e-4d52-a4ba-94366d6fe302
ms.openlocfilehash: 5f533d82fcca07a2b64bdbbfb160a7b2a23ce540
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964726"
---
# <a name="how-to-load-a-sound-asynchronously-within-a-windows-form"></a><span data-ttu-id="2e5ef-102">Procedura: Caricare in modo asincrono un suono in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="2e5ef-102">How to: Load a Sound Asynchronously within a Windows Form</span></span>
<span data-ttu-id="2e5ef-103">Nell'esempio di codice seguente viene caricato un suono in modo asincrono da un URL e quindi viene riprodotto in un nuovo thread.</span><span class="sxs-lookup"><span data-stu-id="2e5ef-103">The following code example asynchronously loads a sound from an URL and then plays it on a new thread.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e5ef-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="2e5ef-104">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.LoadAsync#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.LoadAsync#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2e5ef-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="2e5ef-105">Compiling the Code</span></span>  
 <span data-ttu-id="2e5ef-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2e5ef-106">This example requires:</span></span>  
  
- <span data-ttu-id="2e5ef-107">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="2e5ef-107">References to the System and System.Windows.Forms assemblies.</span></span>  
  
- <span data-ttu-id="2e5ef-108">Sostituzione del nome del file `"http://www.tailspintoys.com/sounds/stop.wav"` con un nome file valido.</span><span class="sxs-lookup"><span data-stu-id="2e5ef-108">That you replace the file name `"http://www.tailspintoys.com/sounds/stop.wav"` with a valid file name.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="2e5ef-109">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="2e5ef-109">Robust Programming</span></span>  
 <span data-ttu-id="2e5ef-110">Le operazioni sui file devono essere racchiuse tra blocchi di gestione delle eccezioni appropriati.</span><span class="sxs-lookup"><span data-stu-id="2e5ef-110">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="2e5ef-111">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="2e5ef-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="2e5ef-112">Il nome del percorso non è valido.</span><span class="sxs-lookup"><span data-stu-id="2e5ef-112">The path name is malformed.</span></span> <span data-ttu-id="2e5ef-113">Ad esempio, contiene caratteri non validi o solo uno spazio vuoto (classe <xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="2e5ef-113">For example, it contains characters that are not valid or is only white space (<xref:System.ArgumentException> class).</span></span>  
  
- <span data-ttu-id="2e5ef-114">Il percorso è di sola lettura (classe <xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="2e5ef-114">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
- <span data-ttu-id="2e5ef-115">Il nome del percorso è `Nothing` (classe <xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="2e5ef-115">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
- <span data-ttu-id="2e5ef-116">Il nome del percorso è troppo lungo (classe <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="2e5ef-116">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
- <span data-ttu-id="2e5ef-117">Il percorso non è valido (classe <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="2e5ef-117">The path is not valid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
- <span data-ttu-id="2e5ef-118">Il percorso contiene solo due punti ":" (classe <xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="2e5ef-118">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="2e5ef-119">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2e5ef-119">.NET Framework Security</span></span>  
 <span data-ttu-id="2e5ef-120">Non basarsi sul nome del file per prendere decisioni in merito al relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="2e5ef-120">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="2e5ef-121">È possibile ad esempio che il file `Form1.vb` non sia un file di origine di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2e5ef-121">For example, the file `Form1.vb` may not be a Visual Basic source file.</span></span> <span data-ttu-id="2e5ef-122">Prima di usare i dati nell'applicazione verificare tutti gli input.</span><span class="sxs-lookup"><span data-stu-id="2e5ef-122">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e5ef-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e5ef-123">See also</span></span>

- <xref:System.Media.SoundPlayer.LoadAsync%2A>
- <xref:System.Media.SoundPlayer.LoadCompleted>
- <xref:System.Media.SoundPlayer.Play%2A>
- [<span data-ttu-id="2e5ef-124">Procedura: Riprodurre un suono da un Windows Form</span><span class="sxs-lookup"><span data-stu-id="2e5ef-124">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)

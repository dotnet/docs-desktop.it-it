---
title: 'Procedura: Emettere un segnale acustico da un Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], beep
- Windows Forms, sounds
- sounds [Windows Forms], playing
- forms [Windows Forms], sounds
- examples [Windows Forms], sounds
ms.assetid: 7ea5cded-4888-4f35-8f28-5cab1a55c973
ms.openlocfilehash: 7fecc5d5b7259b743926713f87d9303596803582
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961726"
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a><span data-ttu-id="87957-102">Procedura: Emettere un segnale acustico da un Windows Form</span><span class="sxs-lookup"><span data-stu-id="87957-102">How to: Play a Beep from a Windows Form</span></span>
<span data-ttu-id="87957-103">In questo esempio viene riprodotto un segnale acustico in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="87957-103">This example plays a beep at run time.</span></span>

## <a name="example"></a><span data-ttu-id="87957-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="87957-104">Example</span></span>

```vb
Public Sub OnePing()
    Beep()
End Sub
```

```csharp
public void onePing()
{
    SystemSounds.Beep.Play();
}
```

> [!NOTE]
> <span data-ttu-id="87957-105">Il suono riprodotto nell'esempio di codice C# è determinato dall' <xref:System.Media.SystemSounds.Beep%2A> impostazione del suono del sistema.</span><span class="sxs-lookup"><span data-stu-id="87957-105">The sound played in the C# code sample is determined by the <xref:System.Media.SystemSounds.Beep%2A> system sound setting.</span></span> <span data-ttu-id="87957-106">Per altre informazioni, vedere <xref:System.Media.SystemSounds>.</span><span class="sxs-lookup"><span data-stu-id="87957-106">For more information, see <xref:System.Media.SystemSounds>.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="87957-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="87957-107">Compiling the Code</span></span>
 <span data-ttu-id="87957-108">Per C#, questo esempio richiede un riferimento allo <xref:System.Media?displayProperty=nameWithType> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="87957-108">For C#, this example requires  a reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="87957-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87957-109">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Beep%2A>
- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="87957-110">Procedura: Riprodurre un suono del sistema da un Windows Form</span><span class="sxs-lookup"><span data-stu-id="87957-110">How to: Play a System Sound from a Windows Form</span></span>](how-to-play-a-system-sound-from-a-windows-form.md)
- [<span data-ttu-id="87957-111">Procedura: Riprodurre un suono da un Windows Form</span><span class="sxs-lookup"><span data-stu-id="87957-111">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)

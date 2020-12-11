---
title: 'Procedura: Riprodurre un suono del sistema da un Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing for system events
- playing sounds [Windows Forms], Windows Forms
- system sounds [Windows Forms], playing from Windows Forms
- playing sounds [Windows Forms], system
- SoundPlayer class [Windows Forms], system sounds
- sounds [Windows Forms], playing
- examples [Windows Forms], sounds
ms.assetid: afb206ff-4824-4804-a8d4-185bf5ad8e7c
ms.openlocfilehash: 765021875767a754e62e3ec11e56487e4de91e93
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952068"
---
# <a name="how-to-play-a-system-sound-from-a-windows-form"></a><span data-ttu-id="668f7-102">Procedura: Riprodurre un suono del sistema da un Windows Form</span><span class="sxs-lookup"><span data-stu-id="668f7-102">How to: Play a System Sound from a Windows Form</span></span>
<span data-ttu-id="668f7-103">Nell'esempio di codice seguente viene riprodotto il suono del sistema `Exclamation` in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="668f7-103">The following code example plays the `Exclamation` system sound at run time.</span></span> <span data-ttu-id="668f7-104">Per ulteriori informazioni sui suoni di sistema, vedere <xref:System.Media.SystemSounds> .</span><span class="sxs-lookup"><span data-stu-id="668f7-104">For more information about system sounds, see <xref:System.Media.SystemSounds>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="668f7-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="668f7-105">Example</span></span>  
  
```vb  
Public Sub PlayExclamation()  
    SystemSounds.Exclamation.Play()  
End Sub  
```  
  
```csharp  
public void playExclamation()  
{  
    SystemSounds.Exclamation.Play();  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="668f7-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="668f7-106">Compiling the Code</span></span>  
 <span data-ttu-id="668f7-107">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="668f7-107">This example requires:</span></span>  
  
- <span data-ttu-id="668f7-108">Un riferimento allo spazio dei nomi <xref:System.Media?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="668f7-108">A reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="668f7-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="668f7-109">See also</span></span>

- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>
- [<span data-ttu-id="668f7-110">Procedura: Emettere un segnale acustico da un Windows Form</span><span class="sxs-lookup"><span data-stu-id="668f7-110">How to: Play a Beep from a Windows Form</span></span>](how-to-play-a-beep-from-a-windows-form.md)
- [<span data-ttu-id="668f7-111">Procedura: Riprodurre un suono da un Windows Form</span><span class="sxs-lookup"><span data-stu-id="668f7-111">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)

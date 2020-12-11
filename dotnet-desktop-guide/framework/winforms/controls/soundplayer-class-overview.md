---
title: Cenni preliminari sulla classe SoundPlayer
ms.date: 03/30/2017
helpviewer_keywords:
- playing sounds [Windows Forms], SoundPlayer class
- SoundPlayer class [Windows Forms], about SoundPlayer class
- sounds [Windows Forms], playing
ms.assetid: fcebb938-62b9-4677-9cbe-6465bc863e22
ms.openlocfilehash: 3ff23cbfa78b803d4526e7a7c389fd5d458a967c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966283"
---
# <a name="soundplayer-class-overview"></a><span data-ttu-id="38216-102">Cenni preliminari sulla classe SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="38216-102">SoundPlayer Class Overview</span></span>
<span data-ttu-id="38216-103">La classe <xref:System.Media.SoundPlayer> consente di includere facilmente suoni nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="38216-103">The <xref:System.Media.SoundPlayer> class enables you to easily include sounds in your applications.</span></span>  
  
 <span data-ttu-id="38216-104">La <xref:System.Media.SoundPlayer> classe può riprodurre file audio nel formato WAV, da una risorsa o da percorsi UNC o http.</span><span class="sxs-lookup"><span data-stu-id="38216-104">The <xref:System.Media.SoundPlayer> class can play sound files in the .wav format, either from a resource or from UNC or HTTP locations.</span></span> <span data-ttu-id="38216-105">La <xref:System.Media.SoundPlayer> classe consente inoltre di caricare o riprodurre suoni in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="38216-105">Additionally, the <xref:System.Media.SoundPlayer> class enables you to load or play sounds asynchronously.</span></span>  
  
 <span data-ttu-id="38216-106">È anche possibile usare la classe<xref:System.Media.SystemSounds> per riprodurre suoni del sistema comuni, compresi i segnali acustici.</span><span class="sxs-lookup"><span data-stu-id="38216-106">You can also use the <xref:System.Media.SystemSounds> class to play common system sounds, including a beep.</span></span>  
  
## <a name="commonly-used-properties-methods-and-events"></a><span data-ttu-id="38216-107">Proprietà, metodi ed eventi usati comunemente</span><span class="sxs-lookup"><span data-stu-id="38216-107">Commonly Used Properties, Methods, and Events</span></span>  
  
|<span data-ttu-id="38216-108">Name</span><span class="sxs-lookup"><span data-stu-id="38216-108">Name</span></span>|<span data-ttu-id="38216-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38216-109">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="38216-110">Proprietà<xref:System.Media.SoundPlayer.SoundLocation%2A></span><span class="sxs-lookup"><span data-stu-id="38216-110"><xref:System.Media.SoundPlayer.SoundLocation%2A> property</span></span>|<span data-ttu-id="38216-111">Percorso del file o l'indirizzo Web del suono.</span><span class="sxs-lookup"><span data-stu-id="38216-111">The file path or Web address of the sound.</span></span> <span data-ttu-id="38216-112">I valori accettabili sono UNC o HTTP.</span><span class="sxs-lookup"><span data-stu-id="38216-112">Acceptable values can be UNC or HTTP.</span></span>|  
|<span data-ttu-id="38216-113">Proprietà<xref:System.Media.SoundPlayer.LoadTimeout%2A></span><span class="sxs-lookup"><span data-stu-id="38216-113"><xref:System.Media.SoundPlayer.LoadTimeout%2A> property</span></span>|<span data-ttu-id="38216-114">Numero di millisecondi di attesa per caricare un suono prima genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="38216-114">The number of milliseconds your program will wait to load a sound before it throws an exception.</span></span> <span data-ttu-id="38216-115">Il valore predefinito è 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="38216-115">The default is 10 seconds.</span></span>|  
|<span data-ttu-id="38216-116">Proprietà<xref:System.Media.SoundPlayer.IsLoadCompleted%2A></span><span class="sxs-lookup"><span data-stu-id="38216-116"><xref:System.Media.SoundPlayer.IsLoadCompleted%2A> property</span></span>|<span data-ttu-id="38216-117">Valore booleano che indica se l'audio è stato caricato.</span><span class="sxs-lookup"><span data-stu-id="38216-117">A Boolean value indicating whether the sound has finished loading.</span></span>|  
|<span data-ttu-id="38216-118">Metodo <xref:System.Media.SoundPlayer.Load%2A></span><span class="sxs-lookup"><span data-stu-id="38216-118"><xref:System.Media.SoundPlayer.Load%2A> method</span></span>|<span data-ttu-id="38216-119">Carica un suono in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="38216-119">Loads a sound synchronously.</span></span>|  
|<span data-ttu-id="38216-120">Metodo <xref:System.Media.SoundPlayer.LoadAsync%2A></span><span class="sxs-lookup"><span data-stu-id="38216-120"><xref:System.Media.SoundPlayer.LoadAsync%2A> method</span></span>|<span data-ttu-id="38216-121">Inizia a caricare in modo asincrono un suono.</span><span class="sxs-lookup"><span data-stu-id="38216-121">Begins to load a sound asynchronously.</span></span> <span data-ttu-id="38216-122">Al termine del caricamento, viene generato l' <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> evento.</span><span class="sxs-lookup"><span data-stu-id="38216-122">When loading is complete, it raises the <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> event.</span></span>|  
|<span data-ttu-id="38216-123">Metodo <xref:System.Media.SoundPlayer.Play%2A></span><span class="sxs-lookup"><span data-stu-id="38216-123"><xref:System.Media.SoundPlayer.Play%2A> method</span></span>|<span data-ttu-id="38216-124">Riproduce il suono specificato nella <xref:System.Media.SoundPlayer.SoundLocation%2A> proprietà o <xref:System.Media.SoundPlayer.Stream%2A> in un nuovo thread.</span><span class="sxs-lookup"><span data-stu-id="38216-124">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in a new thread.</span></span>|  
|<span data-ttu-id="38216-125">Metodo <xref:System.Media.SoundPlayer.PlaySync%2A></span><span class="sxs-lookup"><span data-stu-id="38216-125"><xref:System.Media.SoundPlayer.PlaySync%2A> method</span></span>|<span data-ttu-id="38216-126">Riproduce il suono specificato nella <xref:System.Media.SoundPlayer.SoundLocation%2A> proprietà o <xref:System.Media.SoundPlayer.Stream%2A> nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="38216-126">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in the current thread.</span></span>|  
|<span data-ttu-id="38216-127">Metodo <xref:System.Media.SoundPlayer.Stop%2A></span><span class="sxs-lookup"><span data-stu-id="38216-127"><xref:System.Media.SoundPlayer.Stop%2A> method</span></span>|<span data-ttu-id="38216-128">Arresta un suono.</span><span class="sxs-lookup"><span data-stu-id="38216-128">Stops any sound currently playing.</span></span>|  
|<span data-ttu-id="38216-129">Evento<xref:System.Media.SoundPlayer.LoadCompleted></span><span class="sxs-lookup"><span data-stu-id="38216-129"><xref:System.Media.SoundPlayer.LoadCompleted> event</span></span>|<span data-ttu-id="38216-130">Generato dopo il tentativo di caricamento di un suono.</span><span class="sxs-lookup"><span data-stu-id="38216-130">Raised after the load of a sound is attempted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="38216-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38216-131">See also</span></span>

- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>

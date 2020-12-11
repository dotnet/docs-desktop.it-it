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
# <a name="soundplayer-class-overview"></a>Cenni preliminari sulla classe SoundPlayer
La classe <xref:System.Media.SoundPlayer> consente di includere facilmente suoni nelle applicazioni.  
  
 La <xref:System.Media.SoundPlayer> classe può riprodurre file audio nel formato WAV, da una risorsa o da percorsi UNC o http. La <xref:System.Media.SoundPlayer> classe consente inoltre di caricare o riprodurre suoni in modo asincrono.  
  
 È anche possibile usare la classe<xref:System.Media.SystemSounds> per riprodurre suoni del sistema comuni, compresi i segnali acustici.  
  
## <a name="commonly-used-properties-methods-and-events"></a>Proprietà, metodi ed eventi usati comunemente  
  
|Name|Descrizione|  
|----------|-----------------|  
|Proprietà<xref:System.Media.SoundPlayer.SoundLocation%2A>|Percorso del file o l'indirizzo Web del suono. I valori accettabili sono UNC o HTTP.|  
|Proprietà<xref:System.Media.SoundPlayer.LoadTimeout%2A>|Numero di millisecondi di attesa per caricare un suono prima genera un'eccezione. Il valore predefinito è 10 secondi.|  
|Proprietà<xref:System.Media.SoundPlayer.IsLoadCompleted%2A>|Valore booleano che indica se l'audio è stato caricato.|  
|Metodo <xref:System.Media.SoundPlayer.Load%2A>|Carica un suono in modo sincrono.|  
|Metodo <xref:System.Media.SoundPlayer.LoadAsync%2A>|Inizia a caricare in modo asincrono un suono. Al termine del caricamento, viene generato l' <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> evento.|  
|Metodo <xref:System.Media.SoundPlayer.Play%2A>|Riproduce il suono specificato nella <xref:System.Media.SoundPlayer.SoundLocation%2A> proprietà o <xref:System.Media.SoundPlayer.Stream%2A> in un nuovo thread.|  
|Metodo <xref:System.Media.SoundPlayer.PlaySync%2A>|Riproduce il suono specificato nella <xref:System.Media.SoundPlayer.SoundLocation%2A> proprietà o <xref:System.Media.SoundPlayer.Stream%2A> nel thread corrente.|  
|Metodo <xref:System.Media.SoundPlayer.Stop%2A>|Arresta un suono.|  
|Evento<xref:System.Media.SoundPlayer.LoadCompleted>|Generato dopo il tentativo di caricamento di un suono.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>

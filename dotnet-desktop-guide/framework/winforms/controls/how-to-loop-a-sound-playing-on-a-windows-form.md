---
title: 'Procedura: Riprodurre un suono ripetutamente in un Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sound loops
- SoundPlayer class [Windows Forms], play looping
- sounds [Windows Forms], looping
- playing sounds [Windows Forms], looping
ms.assetid: ea95dd46-10a3-46c0-8263-4b205f00df7f
ms.openlocfilehash: e14d9de2326234b86c1f24b227e86f822fbfdb71
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964933"
---
# <a name="how-to-loop-a-sound-playing-on-a-windows-form"></a>Procedura: Riprodurre un suono ripetutamente in un Windows Form
Nell'esempio di codice seguente un suono viene riprodotto ripetutamente. Quando viene eseguito il codice nel gestore dell'evento `stopPlayingButton_Click`, l'eventuale riproduzione corrente di un suono viene interrotta. Se non è in corso di riproduzione alcun suono, non accadrà nulla.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Media.SoundPlayer.PlayLooping#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.PlayLooping#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System e System.Windows.Forms.  
  
- Sostituzione del nome del file `"c:\Windows\Media\chimes.wav"` con un nome file valido.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le operazioni sui file devono essere racchiuse tra blocchi di gestione delle eccezioni appropriati.  
  
 Le seguenti condizioni possono generare un'eccezione:  
  
- Il nome del percorso non è valido. Ad esempio, contiene caratteri non validi o solo uno spazio vuoto (classe <xref:System.ArgumentException>).  
  
- Il percorso è di sola lettura (classe <xref:System.IO.IOException>).  
  
- Il nome del percorso è `Nothing` (classe <xref:System.ArgumentNullException>).  
  
- Il nome del percorso è troppo lungo (classe <xref:System.IO.PathTooLongException>).  
  
- Il percorso non è valido (classe <xref:System.IO.DirectoryNotFoundException>).  
  
- Il percorso contiene solo due punti ":" (classe <xref:System.NotSupportedException>).  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Non basarsi sul nome del file per prendere decisioni in merito al relativo contenuto. È possibile ad esempio che il file Form1.vb non sia un file di origine di Visual Basic. Prima di usare i dati nell'applicazione verificare tutti gli input.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Media.SoundPlayer.PlayLooping%2A>
- [Procedura: Riprodurre un suono da un Windows Form](how-to-play-a-sound-from-a-windows-form.md)
- [Cenni preliminari sulla classe SoundPlayer](soundplayer-class-overview.md)

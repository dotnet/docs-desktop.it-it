---
title: Controllo Etichetta
description: Informazioni sul controllo etichetta in Windows Forms per .NET. Le etichette vengono usate per identificare gli elementi visivi dell'utente.
ms.date: 10/26/2020
ms.topic: overview
f1_keywords:
- Label
helpviewer_keywords:
- images [Windows Forms], displaying in labels
- labels
- Label control [Windows Forms], about Label control
ms.openlocfilehash: 6f669b7aef1182c35e125ff8dd3ca5ccb299b898
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967312"
---
# <a name="label-control-overview-windows-forms-net"></a>Cenni preliminari sul controllo Label (Windows Forms .NET)

Windows Forms <xref:System.Windows.Forms.Label> controlli vengono utilizzati per visualizzare il testo che non può essere modificato dall'utente. Vengono usati per identificare gli oggetti in un form e per fornire una descrizione di un determinato controllo che rappresenta o fa. Ad esempio, è possibile usare le etichette per aggiungere didascalie descrittive a caselle di testo, caselle di riepilogo, caselle combinate e così via. È anche possibile scrivere codice che modifica il testo visualizzato da un'etichetta in risposta agli eventi in fase di esecuzione.

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="working-with-the-label-control"></a>Utilizzo del controllo Label  

Poiché il <xref:System.Windows.Forms.Label> controllo non può ricevere lo stato attivo, può essere usato per creare chiavi di accesso per altri controlli. Un tasto di scelta consente a un utente di concentrare il controllo successivo nell'ordine di tabulazione premendo il tasto <kbd>ALT</kbd> con il tasto di scelta scelto. Per altre informazioni, vedere [usare un'etichetta per concentrare un controllo](how-to-create-access-keys.md#use-a-label-to-focus-a-control).
  
La didascalia visualizzata nell'etichetta è contenuta nella <xref:System.Windows.Forms.Label.Text%2A> Proprietà. La <xref:System.Windows.Forms.Label.TextAlign%2A> proprietà consente di impostare l'allineamento del testo all'interno dell'etichetta. Per altre informazioni, vedere [procedura: impostare il testo visualizzato da un controllo Windows Forms](how-to-set-the-display-text.md).

## <a name="see-also"></a>Vedere anche

- [Usare un'etichetta per concentrare un controllo (Windows Forms .NET)](how-to-create-access-keys.md#use-a-label-to-focus-a-control)
- [Procedura: impostare il testo visualizzato da un controllo (Windows Forms .NET)](how-to-set-the-display-text.md)
- <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>
- <xref:System.Windows.Forms.Control.Scale%2A>
- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>

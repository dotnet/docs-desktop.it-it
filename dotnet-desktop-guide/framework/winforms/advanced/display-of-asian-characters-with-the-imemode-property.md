---
title: Visualizzazione di caratteri asiatici mediante la proprietà ImeMode
ms.date: 03/30/2017
helpviewer_keywords:
- Asian languages [Windows Forms], displaying with ImeMode
- Chinese characters [Windows Forms], displaying with ImeMode
- IME mode
- Japanese characters [Windows Forms], displaying with ImeMode
- international applications [Windows Forms], character display
- international characters
- Korean characters
- Asian languages
- Input Method Editor (IME), mode
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: c60ae399-0dab-4f07-9dea-6dbfb15ec0ae
ms.openlocfilehash: 25602e1a878443bd54411dfd6481581abebda5c7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951519"
---
# <a name="display-of-asian-characters-with-the-imemode-property"></a>Visualizzazione di caratteri asiatici mediante la proprietà ImeMode
La <xref:System.Windows.Forms.Control.ImeMode%2A> proprietà viene utilizzata da form e controlli per forzare una modalità specifica per un input Method Editor (IME). L'IME è un componente essenziale per la creazione di script in cinese, giapponese e coreano, perché questi sistemi di scrittura comprendono più caratteri che possono essere codificati per una normale tastiera. È possibile, ad esempio, consentire solo caratteri ASCII in una particolare casella di testo. In tal caso, è possibile impostare la <xref:System.Windows.Forms.Control.ImeMode%2A> proprietà su <xref:System.Windows.Forms.ImeMode> e gli utenti saranno in grado di immettere solo caratteri ASCII per la casella di testo specifica. Il valore predefinito della <xref:System.Windows.Forms.Control.ImeMode%2A> proprietà è <xref:System.Windows.Forms.ImeMode> , pertanto se si imposta la proprietà per un form, tutti i controlli del form erediteranno tale impostazione. Per ulteriori informazioni, vedere <xref:System.Windows.Forms.Control.ImeMode%2A> ) e <xref:System.Windows.Forms.ImeMode> .  
  
## <a name="see-also"></a>Vedere anche

- [Globalizzazione di applicazioni Windows Forms](globalizing-windows-forms.md)

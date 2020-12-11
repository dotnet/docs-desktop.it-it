---
title: "Procedura: Supportare l'interoperabilità COM visualizzando un Windows Form con il metodo ShowDialog"
ms.date: 03/30/2017
helpviewer_keywords:
- COM [Windows Forms]
- Windows Forms, unmanaged
- COM interop [Windows Forms], calling methods
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: 87aac8ad-3c04-43b3-9b0c-d0b00df9ee74
ms.openlocfilehash: a4b86616fab5603e08fe9efa1213edaa633deeb9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951538"
---
# <a name="how-to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>Procedura: Supportare l'interoperabilità COM visualizzando un Windows Form con il metodo ShowDialog

È possibile risolvere i problemi di interoperabilità di Component Object Model (COM) visualizzando il Windows Form in un ciclo di messaggi .NET Framework, creato usando il <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> metodo.  
  
 Per fare in modo che un form funzioni correttamente da un'applicazione client COM, è necessario eseguirlo in un ciclo di messaggi Windows Form. Per eseguire questa operazione, adottare uno degli approcci seguenti:  
  
- Usare il metodo <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> per visualizzare il Windows Form.  
  
- Visualizzare ogni Windows Form in un thread separato. Per altre informazioni, vedere [Procedura: supportare l'interoperabilità COM mediante la visualizzazione di ogni Windows Form nel relativo thread](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md).  
  
## <a name="procedure"></a>Procedura  

 L'utilizzo del <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> metodo può essere il modo più semplice per visualizzare un form in un ciclo di messaggi .NET Framework perché, di tutti gli approcci, è necessario che venga implementato il minor codice.  
  
 Il metodo <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> sospende il ciclo di messaggi dell'applicazione non gestita e visualizza il form come una finestra di dialogo. Poiché il ciclo di messaggi dell'applicazione host è stato sospeso, il <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> metodo crea un nuovo ciclo di messaggi .NET Framework per elaborare i messaggi del form.  
  
 Lo svantaggio dell'uso del metodo <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> consiste nel fatto che il form viene aperto come finestra di dialogo modale. Questo comportamento blocca eventuali interfacce utente (UI) nell'applicazione chiamante mentre il Windows Form è aperto. Quando l'utente esce dal form, il ciclo di messaggi .NET Framework si chiude e il ciclo di messaggi dell'applicazione precedente inizia a funzionare di nuovo.  
  
 È possibile creare una libreria di classi in Windows Form che dispone di un metodo per visualizzare il form e quindi compilare la libreria di classi per l'interoperabilità COM. È possibile usare questo file DLL da Visual Basic 6.0 o Microsoft Foundation Classes (MFC) e da uno dei due ambienti è possibile chiamare il metodo <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> per visualizzare il form.  
  
#### <a name="to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>Per supportare l'interoperabilità COM visualizzando un Windows Form con il metodo ShowDialog  
  
- Sostituire tutte le chiamate al <xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> metodo con chiamate al <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> metodo nel componente .NET Framework.  
  
## <a name="see-also"></a>Vedere anche

- [Esposizione di componenti .NET Framework a COM](/dotnet/framework/interop/exposing-dotnet-components-to-co)
- [Procedura: Supportare l'interoperabilità COM visualizzando ogni Windows Form nel proprio thread](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)
- [Windows Form e applicazioni non gestite](windows-forms-and-unmanaged-applications.md)

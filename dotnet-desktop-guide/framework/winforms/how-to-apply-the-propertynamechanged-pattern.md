---
title: 'Procedura: Applicare il modello PropertyNameChanged'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
ms.openlocfilehash: 01afa713e97206ea192ba55dc2affad20163f872
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951374"
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a>Procedura: Applicare il modello PropertyNameChanged
Nell'esempio di codice seguente viene illustrato come applicare il modello *PropertyName* changed a un controllo personalizzato. Applicare questo modello quando si implementano controlli personalizzati usati con il motore di data binding Windows Forms.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per compilare l'esempio di codice precedente:  
  
- Incollare il codice in un file di codice vuoto. È necessario utilizzare il controllo personalizzato in un Windows Form che contiene un `Main` metodo.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Implementare l'interfaccia INotifyPropertyChanged](how-to-implement-the-inotifypropertychanged-interface.md)
- [Notifica delle modifiche nell'associazione dati dei Windows Form](change-notification-in-windows-forms-data-binding.md)
- [Data binding di Windows Form](windows-forms-data-binding.md)

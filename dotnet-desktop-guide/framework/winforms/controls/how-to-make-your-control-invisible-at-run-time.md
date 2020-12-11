---
title: 'Procedura: Rendere invisibile il controllo in fase di esecuzione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], making invisible at run time
- invisible controls
- user controls [Windows Forms], invisible
- custom controls [Windows Forms], invisible
- run time [Windows Forms], making controls invisible
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
ms.openlocfilehash: e9af529541a40a951d6defea180dbbef04c8f3be
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952103"
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a>Procedura: Rendere invisibile il controllo in fase di esecuzione
In alcuni casi potrebbe essere necessario creare un controllo utente invisibile in fase di esecuzione. Ad esempio, un controllo che rappresenta una sveglia potrebbe essere invisibile, tranne quando l'allarme è stato emesso. Questa operazione viene eseguita facilmente impostando la <xref:System.Windows.Forms.Control.Visible%2A> Proprietà. Se la <xref:System.Windows.Forms.Control.Visible%2A> proprietà è `true` , il controllo verrà visualizzato come normale. Se `false` , il controllo sarà nascosto. Sebbene il codice nel controllo possa essere ancora eseguito mentre è invisibile, non sarà possibile interagire con il controllo tramite l'interfaccia utente. Se si desidera creare un controllo invisibile che ancora risponde all'input dell'utente, ad esempio clic del mouse, è necessario creare un controllo trasparente. Per ulteriori informazioni, vedere [assegnazione di uno sfondo trasparente al controllo](how-to-give-your-control-a-transparent-background.md).  
  
### <a name="to-make-your-control-invisible-at-run-time"></a>Per rendere invisibile il controllo in fase di esecuzione  
  
1. Impostare la proprietà <xref:System.Windows.Forms.Control.Visible%2A> su `false`.  
  
    ```vb  
    ' To set the Visible property from within your object's own code.  
    Me.Visible = False  
    ' To set the Visible property from another object.  
    myControl1.Visible = False  
    ```  
  
    ```csharp  
    // To set the Visible property from within your object's own code.  
    this.Visible = false;  
    // To set the Visible property from another object.  
    myControl1.Visible = false;  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.Visible%2A>
- [Sviluppo di controlli Windows Form personalizzati con .NET Framework](developing-custom-windows-forms-controls.md)
- [Procedura: Assegnare uno sfondo trasparente al controllo](how-to-give-your-control-a-transparent-background.md)

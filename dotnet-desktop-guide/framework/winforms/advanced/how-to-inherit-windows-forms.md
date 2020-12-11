---
title: Ereditarietà form
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
ms.openlocfilehash: d016eb52802a729ef3b41a1140cae3d64022d403
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962605"
---
# <a name="how-to-inherit-windows-forms"></a>Procedura: Ereditare Windows Form

La creazione di nuovi Windows Form mediante l'ereditarietà da form di base è un modo semplice di duplicare ciò che è stato creato senza ripetere ogni volta il medesimo processo di creazione di un form.

Per altre informazioni sull'ereditarietà di form in fase di progettazione tramite la finestra di dialogo **Selezione ereditarietà** e su come distinguere visivamente i livelli di sicurezza dei controlli ereditati, vedere [Procedura: Ereditare form tramite la finestra di dialogo Selezione ereditarietà](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).

> [!NOTE]
> Per ereditare da un form, il file o lo spazio dei nomi contenente tale form deve essere stato compilato in un file eseguibile o in una DLL. Per compilare il progetto, scegliere **Compila** dal menu **Compila**. È necessario aggiungere un riferimento allo spazio dei nomi anche alla classe che eredita il form.

## <a name="inherit-a-form-programmatically"></a>Ereditare un form a livello di codice

1. All'interno della classe aggiungere un riferimento allo spazio dei nomi che contiene il form da cui si vuole ereditare.

2. Nella definizione della classe aggiungere un riferimento al form da cui ereditare. Il riferimento deve includere lo spazio dei nomi che contiene il form, seguito da un punto, quindi il nome del form di base.

    ```vb
    Public Class Form2
        Inherits Namespace1.Form1
    ```

    ```csharp
    public class Form2 : Namespace1.Form1
    ```

 Quando si ereditano i form, tenere presente che possono insorgere problemi relativi alla doppia chiamata a gestori eventi, perché ogni evento viene gestito sia dalla classe di base che dalla classe ereditata. Per informazioni su come evitare questo problema, vedere [Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers).

## <a name="see-also"></a>Vedere anche

- [Inherits Statement](/dotnet/visual-basic/language-reference/statements/inherits-statement)
- [Istruzione Imports (tipo e spazio dei nomi .NET)](/dotnet/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type)
- [usando](/dotnet/csharp/language-reference/keywords/using)
- [Effetti della modifica dell'aspetto di un form di base](effects-of-modifying-base-form-appearance.md)
- [Ereditarietà visiva di Windows Form](windows-forms-visual-inheritance.md)

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
# <a name="how-to-inherit-windows-forms"></a><span data-ttu-id="49076-102">Procedura: Ereditare Windows Form</span><span class="sxs-lookup"><span data-stu-id="49076-102">How to: Inherit Windows Forms</span></span>

<span data-ttu-id="49076-103">La creazione di nuovi Windows Form mediante l'ereditarietà da form di base è un modo semplice di duplicare ciò che è stato creato senza ripetere ogni volta il medesimo processo di creazione di un form.</span><span class="sxs-lookup"><span data-stu-id="49076-103">Creating new Windows Forms by inheriting from base forms is a handy way to duplicate your best efforts without going through the process of entirely recreating a form every time you require it.</span></span>

<span data-ttu-id="49076-104">Per altre informazioni sull'ereditarietà di form in fase di progettazione tramite la finestra di dialogo **Selezione ereditarietà** e su come distinguere visivamente i livelli di sicurezza dei controlli ereditati, vedere [Procedura: Ereditare form tramite la finestra di dialogo Selezione ereditarietà](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="49076-104">For more information about inheriting forms at design time using the **Inheritance Picker** dialog box and how to visually distinguish between security levels of inherited controls, see [How to: Inherit Forms Using the Inheritance Picker Dialog Box](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).</span></span>

> [!NOTE]
> <span data-ttu-id="49076-105">Per ereditare da un form, il file o lo spazio dei nomi contenente tale form deve essere stato compilato in un file eseguibile o in una DLL.</span><span class="sxs-lookup"><span data-stu-id="49076-105">In order to inherit from a form, the file or namespace containing that form must have been built into an executable file or DLL.</span></span> <span data-ttu-id="49076-106">Per compilare il progetto, scegliere **Compila** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="49076-106">To build the project, choose **Build** from the **Build** menu.</span></span> <span data-ttu-id="49076-107">È necessario aggiungere un riferimento allo spazio dei nomi anche alla classe che eredita il form.</span><span class="sxs-lookup"><span data-stu-id="49076-107">Also, a reference to the namespace must be added to the class inheriting the form.</span></span>

## <a name="inherit-a-form-programmatically"></a><span data-ttu-id="49076-108">Ereditare un form a livello di codice</span><span class="sxs-lookup"><span data-stu-id="49076-108">Inherit a form programmatically</span></span>

1. <span data-ttu-id="49076-109">All'interno della classe aggiungere un riferimento allo spazio dei nomi che contiene il form da cui si vuole ereditare.</span><span class="sxs-lookup"><span data-stu-id="49076-109">In your class, add a reference to the namespace containing the form you wish to inherit from.</span></span>

2. <span data-ttu-id="49076-110">Nella definizione della classe aggiungere un riferimento al form da cui ereditare.</span><span class="sxs-lookup"><span data-stu-id="49076-110">In the class definition, add a reference to the form to inherit from.</span></span> <span data-ttu-id="49076-111">Il riferimento deve includere lo spazio dei nomi che contiene il form, seguito da un punto, quindi il nome del form di base.</span><span class="sxs-lookup"><span data-stu-id="49076-111">The reference should include the namespace that contains the form, followed by a period, then the name of the base form itself.</span></span>

    ```vb
    Public Class Form2
        Inherits Namespace1.Form1
    ```

    ```csharp
    public class Form2 : Namespace1.Form1
    ```

 <span data-ttu-id="49076-112">Quando si ereditano i form, tenere presente che possono insorgere problemi relativi alla doppia chiamata a gestori eventi, perché ogni evento viene gestito sia dalla classe di base che dalla classe ereditata.</span><span class="sxs-lookup"><span data-stu-id="49076-112">When inheriting forms, keep in mind that issues may arise with regard to event handlers being called twice, because each event is being handled by both the base class and the inherited class.</span></span> <span data-ttu-id="49076-113">Per informazioni su come evitare questo problema, vedere [Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers).</span><span class="sxs-lookup"><span data-stu-id="49076-113">For more information on how to avoid this problem, see [Troubleshooting Inherited Event Handlers in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers).</span></span>

## <a name="see-also"></a><span data-ttu-id="49076-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49076-114">See also</span></span>

- [<span data-ttu-id="49076-115">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="49076-115">Inherits Statement</span></span>](/dotnet/visual-basic/language-reference/statements/inherits-statement)
- [<span data-ttu-id="49076-116">Istruzione Imports (tipo e spazio dei nomi .NET)</span><span class="sxs-lookup"><span data-stu-id="49076-116">Imports Statement (.NET Namespace and Type)</span></span>](/dotnet/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type)
- [<span data-ttu-id="49076-117">usando</span><span class="sxs-lookup"><span data-stu-id="49076-117">using</span></span>](/dotnet/csharp/language-reference/keywords/using)
- [<span data-ttu-id="49076-118">Effetti della modifica dell'aspetto di un form di base</span><span class="sxs-lookup"><span data-stu-id="49076-118">Effects of Modifying a Base Form's Appearance</span></span>](effects-of-modifying-base-form-appearance.md)
- [<span data-ttu-id="49076-119">Ereditarietà visiva di Windows Form</span><span class="sxs-lookup"><span data-stu-id="49076-119">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)

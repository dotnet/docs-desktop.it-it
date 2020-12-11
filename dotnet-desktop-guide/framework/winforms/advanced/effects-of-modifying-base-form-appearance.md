---
title: Effetti della modifica dell'aspetto di un form di base
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms [Windows Forms]
- inherited forms [Windows Forms], modifications to base form
- Windows Forms, base form appearance
- base forms
- inheritance [Windows Forms], forms
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
ms.openlocfilehash: 1eda19f754d0b8d446ac9190b432ff0b6106847b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952457"
---
# <a name="effects-of-modifying-a-base-forms-appearance"></a><span data-ttu-id="a327a-102">Effetti della modifica dell'aspetto di un form di base</span><span class="sxs-lookup"><span data-stu-id="a327a-102">Effects of modifying a base form's appearance</span></span>

<span data-ttu-id="a327a-103">Durante lo sviluppo di applicazioni, spesso potrebbe essere necessario modificare l'aspetto del form di base da cui ereditano altri form nel progetto (o in altri progetti).</span><span class="sxs-lookup"><span data-stu-id="a327a-103">During application development, you may often need to change the appearance of the base form from which other forms in the project (or in other projects) are inheriting.</span></span>

<span data-ttu-id="a327a-104">In fase di progettazione, le modifiche all'aspetto del form di base, relative sia all'impostazione di proprietà o all'aggiunta e sottrazione dei controlli, vengono applicate ai form ereditati quando viene compilato il progetto contenente il form di base.</span><span class="sxs-lookup"><span data-stu-id="a327a-104">At design time, changes to the base form's appearance (be it the setting of properties or the addition and subtraction of controls) are reflected on inherited forms when the project containing the base form is built.</span></span> <span data-ttu-id="a327a-105">Non è sufficiente salvare le modifiche al form di base.</span><span class="sxs-lookup"><span data-stu-id="a327a-105">It is not sufficient for you to simply save the changes to the base form.</span></span> <span data-ttu-id="a327a-106">Per compilare un progetto, scegliere **Compila** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="a327a-106">To build a project, choose **Build** from the **Build** menu.</span></span>

<span data-ttu-id="a327a-107">Le modifiche apportate al form di base in fase di esecuzione non avranno alcun effetto sui form ereditati in cui è già stata creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="a327a-107">Modifications made to the base form at run time have no affect on inherited forms that are already instantiated.</span></span>

## <a name="see-also"></a><span data-ttu-id="a327a-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a327a-108">See also</span></span>

- [<span data-ttu-id="a327a-109">base</span><span class="sxs-lookup"><span data-stu-id="a327a-109">base</span></span>](/dotnet/csharp/language-reference/keywords/base)
- [<span data-ttu-id="a327a-110">Procedura: Ereditare Windows Form</span><span class="sxs-lookup"><span data-stu-id="a327a-110">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
- [<span data-ttu-id="a327a-111">Ereditarietà visiva di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a327a-111">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)

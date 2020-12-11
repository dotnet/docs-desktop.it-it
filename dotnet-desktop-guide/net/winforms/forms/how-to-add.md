---
title: Aggiungere un modulo a un progetto
description: Aggiungere un nuovo modulo a un progetto di Windows Forms .NET in Visual Studio
ms.date: 10/26/2020
helpviewer_keywords:
- Windows Forms, create add form
ms.openlocfilehash: fb35c1b62ca0b7a21581c350ddca7f21f45ec27f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967300"
---
# <a name="how-to-add-a-form-to-a-project-windows-forms-net"></a><span data-ttu-id="7ef0c-103">Come aggiungere un modulo a un progetto (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="7ef0c-103">How to add a form to a project (Windows Forms .NET)</span></span>

<span data-ttu-id="7ef0c-104">Aggiungere i moduli al progetto con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7ef0c-104">Add forms to your project with Visual Studio.</span></span> <span data-ttu-id="7ef0c-105">Quando l'app dispone di più moduli, è possibile scegliere quale sia il modulo di avvio per l'app ed è possibile visualizzare più forme nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="7ef0c-105">When your app has multiple forms, you can choose which is the startup form for your app, and you can display multiple forms at the same time.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="add-a-new-form"></a><span data-ttu-id="7ef0c-106">Aggiungi un nuovo modulo</span><span class="sxs-lookup"><span data-stu-id="7ef0c-106">Add a new form</span></span>

<span data-ttu-id="7ef0c-107">Aggiungere un nuovo modulo con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7ef0c-107">Add a new form with Visual Studio.</span></span>

01. <span data-ttu-id="7ef0c-108">In Visual Studio trovare il riquadro **Esplora progetti** .</span><span class="sxs-lookup"><span data-stu-id="7ef0c-108">In Visual Studio, find the **Project Explorer** pane.</span></span> <span data-ttu-id="7ef0c-109">Fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi**  >  **modulo (Windows Forms)**.</span><span class="sxs-lookup"><span data-stu-id="7ef0c-109">Right-click on the project and choose **Add** > **Form (Windows Forms)**.</span></span>

    :::image type="content" source="media/how-to-add/right-click.png" alt-text="Fare clic con il pulsante destro del mouse su Esplora soluzioni per aggiungere nuovo modulo al progetto Windows Form":::

01. <span data-ttu-id="7ef0c-111">Nella casella **nome** Digitare un nome per il form, ad esempio *MyNewForm*.</span><span class="sxs-lookup"><span data-stu-id="7ef0c-111">In the **Name** box, type a name for your form, such as *MyNewForm*.</span></span> <span data-ttu-id="7ef0c-112">Visual Studio fornirà un nome predefinito e univoco che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="7ef0c-112">Visual Studio will provide a default and unique name that you may use.</span></span>

    :::image type="content" source="media/how-to-add/new-form-dialog.png" alt-text="Finestra di dialogo Aggiungi elemento in Visual Studio per Windows Form":::

<span data-ttu-id="7ef0c-114">Una volta aggiunto il modulo, Visual Studio apre la finestra di progettazione del form per il form.</span><span class="sxs-lookup"><span data-stu-id="7ef0c-114">Once the form has been added, Visual Studio opens the form designer for the form.</span></span>

## <a name="add-a-project-reference-to-a-form"></a><span data-ttu-id="7ef0c-115">Aggiungere un riferimento di progetto a un modulo</span><span class="sxs-lookup"><span data-stu-id="7ef0c-115">Add a project reference to a form</span></span>

<span data-ttu-id="7ef0c-116">Se si dispone dei file di origine in un modulo, è possibile aggiungere il modulo al progetto copiando i file nella stessa cartella del progetto.</span><span class="sxs-lookup"><span data-stu-id="7ef0c-116">If you have the source files to a form, you can add the form to your project by copying the files into the same folder as your project.</span></span> <span data-ttu-id="7ef0c-117">Il progetto fa automaticamente riferimento a tutti i file di codice presenti nella stessa cartella o nella stessa cartella figlio del progetto.</span><span class="sxs-lookup"><span data-stu-id="7ef0c-117">The project automatically references any code files that are in the same folder or child folder of your project.</span></span>

<span data-ttu-id="7ef0c-118">I moduli sono costituiti da due file che condividono lo stesso nome: _Form2.cs_ (_Form2_ è un esempio di nome di file) e _Form2. Designer.cs_.</span><span class="sxs-lookup"><span data-stu-id="7ef0c-118">Forms are made up of two files that share the same name: _form2.cs_ (_form2_ being an example of a file name) and _form2.Designer.cs_.</span></span> <span data-ttu-id="7ef0c-119">Talvolta è presente un file di risorse, che condivide lo stesso nome, _Form2. resx_.</span><span class="sxs-lookup"><span data-stu-id="7ef0c-119">Sometimes a resource file exists, sharing the same name, _form2.resx_.</span></span> <span data-ttu-id="7ef0c-120">Nell'esempio precedente _Form2_ rappresenta il nome del file di base.</span><span class="sxs-lookup"><span data-stu-id="7ef0c-120">In in the previous example, _form2_ represents the base file name.</span></span> <span data-ttu-id="7ef0c-121">È possibile copiare tutti i file correlati nella cartella del progetto.</span><span class="sxs-lookup"><span data-stu-id="7ef0c-121">You'll want to copy all related files to your project folder.</span></span>

<span data-ttu-id="7ef0c-122">In alternativa, è possibile usare Visual Studio per importare un file nel progetto.</span><span class="sxs-lookup"><span data-stu-id="7ef0c-122">Alternatively, you can use Visual Studio to import a file into your project.</span></span> <span data-ttu-id="7ef0c-123">Quando si aggiunge un file esistente al progetto, il file viene copiato nella stessa cartella del progetto.</span><span class="sxs-lookup"><span data-stu-id="7ef0c-123">When you add an existing file to your project, the file is copied into the same folder as your project.</span></span>

01. <span data-ttu-id="7ef0c-124">In Visual Studio trovare il riquadro **Esplora progetti** .</span><span class="sxs-lookup"><span data-stu-id="7ef0c-124">In Visual Studio, find the **Project Explorer** pane.</span></span> <span data-ttu-id="7ef0c-125">Fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi**  >  **elemento esistente**.</span><span class="sxs-lookup"><span data-stu-id="7ef0c-125">Right-click on the project and choose **Add** > **Existing Item**.</span></span>

    :::image type="content" source="media/how-to-add/existing-right-click.png" alt-text="Fare clic con il pulsante destro del mouse su Esplora soluzioni per aggiungere il modulo esistente al progetto":::

02. <span data-ttu-id="7ef0c-127">Passare alla cartella contenente i file del modulo.</span><span class="sxs-lookup"><span data-stu-id="7ef0c-127">Navigate to the folder containing your form files.</span></span>

03. <span data-ttu-id="7ef0c-128">Selezionare il file _Form2.cs_ , dove _Form2_ è il nome del file di base dei file del modulo correlati.</span><span class="sxs-lookup"><span data-stu-id="7ef0c-128">Select the _form2.cs_ file, where _form2_ is the base file name of the related form files.</span></span> <span data-ttu-id="7ef0c-129">Non selezionare gli altri file, ad esempio _Form2. Designer.cs_.</span><span class="sxs-lookup"><span data-stu-id="7ef0c-129">Don't select the other files, such as _form2.Designer.cs_.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ef0c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ef0c-130">See also</span></span>

- [<span data-ttu-id="7ef0c-131">Come posizionare e ridimensionare un form (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="7ef0c-131">How to position and size a form (Windows Forms .NET)</span></span>](how-to-position-and-resize.md)
- [<span data-ttu-id="7ef0c-132">Cenni preliminari sugli eventi (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="7ef0c-132">Events overview (Windows Forms .NET)</span></span>](events.md)
- [<span data-ttu-id="7ef0c-133">Posizione e layout dei controlli (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="7ef0c-133">Position and layout of controls (Windows Forms .NET)</span></span>](../controls/layout.md)

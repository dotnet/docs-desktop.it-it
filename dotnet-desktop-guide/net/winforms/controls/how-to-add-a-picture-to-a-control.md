---
title: Visualizzare un'immagine in un controllo
description: Informazioni su come visualizzare un'immagine in un controllo Windows Form. Molti controlli, ad esempio PictureBox, possono visualizzare un'immagine.
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms contr ols
- examples [Windows Forms], controls
ms.openlocfilehash: a0b95d51f852df4c9ddc190903369faa41f7deae
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966022"
---
# <a name="how-to-display-an-image-on-a-control-windows-forms-net"></a><span data-ttu-id="e407e-104">Come visualizzare un'immagine in un controllo (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="e407e-104">How to display an image on a control (Windows Forms .NET)</span></span>

<span data-ttu-id="e407e-105">Diversi controlli Windows Forms possono visualizzare immagini.</span><span class="sxs-lookup"><span data-stu-id="e407e-105">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="e407e-106">Queste immagini possono essere icone che chiariscono lo scopo del controllo, ad esempio un'icona a forma di dischetto in un pulsante che indica il comando Salva.</span><span class="sxs-lookup"><span data-stu-id="e407e-106">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the Save command.</span></span> <span data-ttu-id="e407e-107">In alternativa, le icone possono essere immagini di sfondo per dare al controllo l'aspetto e il comportamento desiderati.</span><span class="sxs-lookup"><span data-stu-id="e407e-107">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="designer"></a><span data-ttu-id="e407e-108">Designer</span><span class="sxs-lookup"><span data-stu-id="e407e-108">Designer</span></span>

<span data-ttu-id="e407e-109">Nella finestra **Proprietà** di Visual Studio selezionare la proprietà **Image** o **BackgroundImage** del controllo, quindi selezionare i puntini di sospensione ( ![ pulsante con i puntini di sospensione in Visual Studio ](../media/visual-studio-ellipsis-button.png) ) per visualizzare la finestra di dialogo **Seleziona risorsa** , quindi selezionare l'immagine che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="e407e-109">In the **Properties** window of Visual Studio, select the **Image** or **BackgroundImage** property of the control, and then select the ellipsis (![Ellipsis button in Visual Studio](../media/visual-studio-ellipsis-button.png)) to display the **Select Resource** dialog box and then select the image you want to display.</span></span>

:::image type="content" source="media/how-to-add-a-picture-to-a-control/properties-image.png" alt-text="Finestra di dialogo Proprietà con proprietà immagine selezionata":::

## <a name="programmatic"></a><span data-ttu-id="e407e-111">Programmatica</span><span class="sxs-lookup"><span data-stu-id="e407e-111">Programmatic</span></span>

<span data-ttu-id="e407e-112">Impostare la `Image` proprietà o del controllo `BackgroundImage` su un oggetto di tipo <xref:System.Drawing.Image> .</span><span class="sxs-lookup"><span data-stu-id="e407e-112">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="e407e-113">In genere, è possibile caricare l'immagine da un file usando il <xref:System.Drawing.Image.FromFile%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="e407e-113">Generally, you'll be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>

<span data-ttu-id="e407e-114">Nell'esempio di codice seguente il percorso impostato per il percorso dell'immagine è la cartella **Immagini personali** .</span><span class="sxs-lookup"><span data-stu-id="e407e-114">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="e407e-115">La maggior parte dei computer che eseguono il sistema operativo Windows include questa directory.</span><span class="sxs-lookup"><span data-stu-id="e407e-115">Most computers running the Windows operating system include this directory.</span></span> <span data-ttu-id="e407e-116">Consente inoltre agli utenti con livelli di accesso di sistema minimi di eseguire l'applicazione in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="e407e-116">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="e407e-117">Nell'esempio di codice seguente è necessario avere già un modulo con un <xref:System.Windows.Forms.PictureBox> controllo aggiunto.</span><span class="sxs-lookup"><span data-stu-id="e407e-117">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>

```csharp
// Replace the image named below with your own icon.
// Note the escape character used (@) when specifying the path.
pictureBox1.Image = Image.FromFile
   (System.Environment.GetFolderPath
   (System.Environment.SpecialFolder.MyPictures)
   + @"\Image.gif");
```

```vb
' Replace the image named below with your own icon.
PictureBox1.Image = Image.FromFile _
   (System.Environment.GetFolderPath _
   (System.Environment.SpecialFolder.MyPictures) _
   & "\Image.gif")
```

## <a name="see-also"></a><span data-ttu-id="e407e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e407e-118">See also</span></span>

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>

---
title: Posizionare i controlli
description: Informazioni su come usare la Progettazione Windows Form in Visual Studio o la proprietà Location per posizionare i controlli.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e7b26d1741046ea242bd58a9216b8958697e1879
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952067"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="2b14d-103">Procedura: posizionare i controlli in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b14d-103">How to: Position controls on Windows Forms</span></span>

<span data-ttu-id="2b14d-104">Per posizionare i controlli, usare il Progettazione Windows Form in Visual Studio o specificare la <xref:System.Windows.Forms.Control.Location%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="2b14d-104">To position controls, use the Windows Forms Designer in Visual Studio or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="2b14d-105">Posizionare un controllo nell'area di progettazione dell'Progettazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="2b14d-105">Position a control on the design surface of the Windows Forms Designer</span></span>

<span data-ttu-id="2b14d-106">In Visual Studio trascinare il controllo nella posizione appropriata con il mouse.</span><span class="sxs-lookup"><span data-stu-id="2b14d-106">In Visual Studio, drag the control to the appropriate location with the mouse.</span></span>

> [!NOTE]
> <span data-ttu-id="2b14d-107">Selezionare il controllo e spostarlo con i tasti di direzione per posizionarlo più precisamente.</span><span class="sxs-lookup"><span data-stu-id="2b14d-107">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="2b14d-108">Inoltre, le guide di *allineamento* facilitano l'inserimento di controlli con precisione nel form.</span><span class="sxs-lookup"><span data-stu-id="2b14d-108">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="2b14d-109">Per ulteriori informazioni, vedere [procedura dettagliata: disposizione dei controlli su Windows Forms mediante guide di allineamento](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="2b14d-109">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

## <a name="position-a-control-using-the-properties-window"></a><span data-ttu-id="2b14d-110">Posizionare un controllo usando il Finestra Proprietà</span><span class="sxs-lookup"><span data-stu-id="2b14d-110">Position a control using the Properties window</span></span>

1. <span data-ttu-id="2b14d-111">In Visual Studio selezionare il controllo che si vuole posizionare.</span><span class="sxs-lookup"><span data-stu-id="2b14d-111">In Visual Studio, select the control you want to position.</span></span>

2. <span data-ttu-id="2b14d-112">Nella finestra **Proprietà** immettere i valori per la <xref:System.Windows.Forms.Control.Location%2A> proprietà, separati da una virgola, per posizionare il controllo all'interno del relativo contenitore.</span><span class="sxs-lookup"><span data-stu-id="2b14d-112">In the **Properties** window, enter values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>

   <span data-ttu-id="2b14d-113">Il primo numero (X) è la distanza dal bordo sinistro del contenitore; il secondo numero (Y) è la distanza dal bordo superiore dell'area del contenitore, misurata in pixel.</span><span class="sxs-lookup"><span data-stu-id="2b14d-113">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2b14d-114">È possibile espandere la <xref:System.Windows.Forms.Control.Location%2A> proprietà per digitare singolarmente i valori **X** e **Y** .</span><span class="sxs-lookup"><span data-stu-id="2b14d-114">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>

## <a name="position-a-control-programmatically"></a><span data-ttu-id="2b14d-115">Posizionare un controllo a livello di codice</span><span class="sxs-lookup"><span data-stu-id="2b14d-115">Position a control programmatically</span></span>

1. <span data-ttu-id="2b14d-116">Impostare la <xref:System.Windows.Forms.Control.Location%2A> proprietà del controllo su <xref:System.Drawing.Point> .</span><span class="sxs-lookup"><span data-stu-id="2b14d-116">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. <span data-ttu-id="2b14d-117">Modificare la coordinata X della posizione del controllo utilizzando la <xref:System.Windows.Forms.Control.Left%2A> sottoproprietà.</span><span class="sxs-lookup"><span data-stu-id="2b14d-117">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>

    ```vb
    Button1.Left = 300
    ```

    ```csharp
    button1.Left = 300;
    ```

    ```cpp
    button1->Left = 300;
    ```

## <a name="increment-a-controls-location-programmatically"></a><span data-ttu-id="2b14d-118">Incrementa la posizione di un controllo a livello di codice</span><span class="sxs-lookup"><span data-stu-id="2b14d-118">Increment a control's location programmatically</span></span>

<span data-ttu-id="2b14d-119">Impostare la <xref:System.Windows.Forms.Control.Left%2A> sottoproprietà per incrementare la coordinata X del controllo.</span><span class="sxs-lookup"><span data-stu-id="2b14d-119">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>

```vb
Button1.Left += 200
```

```csharp
button1.Left += 200;
```

```cpp
button1->Left += 200;
```

> [!NOTE]
> <span data-ttu-id="2b14d-120">Utilizzare la <xref:System.Windows.Forms.Control.Location%2A> proprietà per impostare le posizioni X e Y di un controllo simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="2b14d-120">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="2b14d-121">Per impostare una posizione singolarmente, utilizzare la <xref:System.Windows.Forms.Control.Left%2A> sottoproprietà del controllo (**X**) o <xref:System.Windows.Forms.Control.Top%2A> (**Y**).</span><span class="sxs-lookup"><span data-stu-id="2b14d-121">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="2b14d-122">Non tentare di impostare in modo implicito le coordinate X e Y della <xref:System.Drawing.Point> struttura che rappresenta la posizione del pulsante, perché questa struttura contiene una copia delle coordinate del pulsante.</span><span class="sxs-lookup"><span data-stu-id="2b14d-122">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b14d-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b14d-123">See also</span></span>

- [<span data-ttu-id="2b14d-124">Controlli di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b14d-124">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="2b14d-125">Procedura dettagliata: disposizione dei controlli in Windows Form utilizzando guide di allineamento</span><span class="sxs-lookup"><span data-stu-id="2b14d-125">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="2b14d-126">Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="2b14d-126">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="2b14d-127">Procedura dettagliata: Disposizione dei controlli in Windows Forms usando FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="2b14d-127">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="2b14d-128">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="2b14d-128">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="2b14d-129">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="2b14d-129">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="2b14d-130">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="2b14d-130">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="2b14d-131">[Procedura: impostare la posizione dello schermo di Windows Forms](/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2b14d-131">[How to: Set the Screen Location of Windows Forms](/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span></span>

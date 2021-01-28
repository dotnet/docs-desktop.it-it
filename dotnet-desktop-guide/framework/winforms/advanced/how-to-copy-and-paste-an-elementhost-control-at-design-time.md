---
title: 'Procedura: Copiare e incollare un controllo ElementHost in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
ms.openlocfilehash: 82312cdc2d5bf8d81b0eb53e3e8a3fdb3319a72f
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "98956915"
---
# <a name="how-to-copy-and-paste-an-elementhost-control"></a><span data-ttu-id="b0b24-102">Procedura: copiare e incollare un controllo ElementHost</span><span class="sxs-lookup"><span data-stu-id="b0b24-102">How to: Copy and paste an ElementHost control</span></span>

<span data-ttu-id="b0b24-103">Questa procedura illustra come copiare un controllo Windows Presentation Foundation (WPF) in un Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b0b24-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form in Visual Studio.</span></span>

1. <span data-ttu-id="b0b24-104">In Visual Studio aggiungere un nuovo WPF <xref:System.Windows.Controls.UserControl> a un progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="b0b24-104">In Visual Studio, add a new WPF <xref:System.Windows.Controls.UserControl> to a Windows Forms project.</span></span> <span data-ttu-id="b0b24-105">Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="b0b24-105">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="b0b24-106">Per ulteriori informazioni, vedere [procedura dettagliata: creazione di nuovi contenuti WPF in Windows Form in fase di progettazione](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="b0b24-106">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="b0b24-107">Nella finestra **Proprietà** impostare il valore delle <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> proprietà e di `UserControl1` su **200**.</span><span class="sxs-lookup"><span data-stu-id="b0b24-107">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to **200**.</span></span>

3. <span data-ttu-id="b0b24-108">Impostare il valore della <xref:System.Windows.Controls.Control.Background%2A> proprietà su **blu**.</span><span class="sxs-lookup"><span data-stu-id="b0b24-108">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to **Blue**.</span></span>

4. <span data-ttu-id="b0b24-109">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="b0b24-109">Build the project.</span></span>

5. <span data-ttu-id="b0b24-110">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="b0b24-110">Open `Form1` in the Windows Forms Designer.</span></span>

6. <span data-ttu-id="b0b24-111">Dalla **casella degli strumenti** trascinare un'istanza di `UserControl1` nel form.</span><span class="sxs-lookup"><span data-stu-id="b0b24-111">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>

   <span data-ttu-id="b0b24-112">L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="b0b24-112">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

7. <span data-ttu-id="b0b24-113">Con `elementHost1` selezionata, premere **CTRL** + **C** per copiarlo negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="b0b24-113">With `elementHost1` selected, press **Ctrl**+**C** to copy it to the clipboard.</span></span>

8. <span data-ttu-id="b0b24-114">Premere **CTRL** + **V** per incollare il controllo copiato nel form.</span><span class="sxs-lookup"><span data-stu-id="b0b24-114">Press **Ctrl**+**V** to paste the copied control onto the form.</span></span>

   <span data-ttu-id="b0b24-115"><xref:System.Windows.Forms.Integration.ElementHost> `elementHost2` Nel form viene creato un nuovo controllo denominato.</span><span class="sxs-lookup"><span data-stu-id="b0b24-115">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0b24-116">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="b0b24-116">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="b0b24-117">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="b0b24-117">Migration and Interoperability</span></span>](/dotnet/framework/wpf/advanced/migration-and-interoperability)
- [<span data-ttu-id="b0b24-118">Utilizzo di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="b0b24-118">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="b0b24-119">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b0b24-119">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)

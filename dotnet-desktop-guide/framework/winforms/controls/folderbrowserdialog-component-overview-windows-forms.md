---
title: Panoramica del componente FolderBrowserDialog
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: 8b017ba08ae4205e930ac00177c89a89fde17d3b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962899"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="b994d-102">Cenni preliminari sul componente FolderBrowserDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="b994d-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="b994d-103">Il <xref:System.Windows.Forms.FolderBrowserDialog> componente Windows Forms è una finestra di dialogo modale utilizzata per l'esplorazione e la selezione di cartelle.</span><span class="sxs-lookup"><span data-stu-id="b994d-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="b994d-104">È anche possibile creare nuove cartelle dall'interno del <xref:System.Windows.Forms.FolderBrowserDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="b994d-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>

> [!NOTE]
> <span data-ttu-id="b994d-105">Per selezionare i file, anziché le cartelle, utilizzare il componente [OpenFileDialog](openfiledialog-component-windows-forms.md) .</span><span class="sxs-lookup"><span data-stu-id="b994d-105">To select files, instead of folders, use the [OpenFileDialog](openfiledialog-component-windows-forms.md) component.</span></span>

<span data-ttu-id="b994d-106">Il <xref:System.Windows.Forms.FolderBrowserDialog> componente viene visualizzato in fase di esecuzione usando il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="b994d-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="b994d-107">Impostare la <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> proprietà per determinare la cartella più in alto e tutte le sottocartelle che verranno visualizzate nella visualizzazione albero della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b994d-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="b994d-108">Una volta visualizzata la finestra di dialogo, è possibile usare la <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> proprietà per ottenere il percorso della cartella selezionata.</span><span class="sxs-lookup"><span data-stu-id="b994d-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>

<span data-ttu-id="b994d-109">Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.FolderBrowserDialog> componente viene visualizzato nella barra delle applicazioni nella parte inferiore del progettazione Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b994d-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="b994d-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b994d-110">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="b994d-111">Procedura: Scegliere cartelle con il componente FolderBrowserDialog di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b994d-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [<span data-ttu-id="b994d-112">Componente FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="b994d-112">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)

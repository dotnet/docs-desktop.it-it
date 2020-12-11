---
title: Panoramica del componente OpenFileDialog
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: c519b373150a49ee41dbb0c503f7d5a4862477d5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965020"
---
# <a name="openfiledialog-component-overview-windows-forms"></a><span data-ttu-id="1b6e1-102">Cenni preliminari sul componente OpenFileDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="1b6e1-102">OpenFileDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="1b6e1-103">Il componente di Windows Form <xref:System.Windows.Forms.OpenFileDialog> è una finestra di dialogo preconfigurata.</span><span class="sxs-lookup"><span data-stu-id="1b6e1-103">The Windows Forms <xref:System.Windows.Forms.OpenFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="1b6e1-104">Si tratta della stessa finestra di dialogo **Apri file** esposta dal sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="1b6e1-104">It is the same **Open File** dialog box exposed by the Windows operating system.</span></span> <span data-ttu-id="1b6e1-105">Il componente eredita dalla classe <xref:System.Windows.Forms.CommonDialog>.</span><span class="sxs-lookup"><span data-stu-id="1b6e1-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="use-this-component"></a><span data-ttu-id="1b6e1-106">Usa questo componente</span><span class="sxs-lookup"><span data-stu-id="1b6e1-106">Use this component</span></span>

<span data-ttu-id="1b6e1-107">Usare questo componente nell'applicazione basata su Windows come soluzione semplice per la selezione dei file anziché configurare la propria finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="1b6e1-107">Use this component within your Windows-based application as a simple solution for file selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="1b6e1-108">Basandosi sulle finestre di dialogo standard di Windows è quindi possibile creare applicazioni le cui funzionalità di base sono immediatamente familiari agli utenti.</span><span class="sxs-lookup"><span data-stu-id="1b6e1-108">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="1b6e1-109">Tenere presente, tuttavia, che quando si usa il <xref:System.Windows.Forms.OpenFileDialog> componente, è necessario scrivere una logica di apertura dei file personalizzata.</span><span class="sxs-lookup"><span data-stu-id="1b6e1-109">Be aware, however, that when using the <xref:System.Windows.Forms.OpenFileDialog> component, you must write your own file-opening logic.</span></span>

<span data-ttu-id="1b6e1-110">Utilizzare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1b6e1-110">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="1b6e1-111">È possibile consentire agli utenti di selezionare più file da aprire con la <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="1b6e1-111">You can enable users to multi-select files to be opened with the <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> property.</span></span> <span data-ttu-id="1b6e1-112">Inoltre, è possibile utilizzare la <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> proprietà per determinare se nella finestra di dialogo viene visualizzata una casella di controllo di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="1b6e1-112">Additionally, you can use the <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> property to determine if a read-only check box appears in the dialog box.</span></span> <span data-ttu-id="1b6e1-113">La <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> proprietà indica se è selezionata la casella di controllo di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="1b6e1-113">The <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> property indicates whether the read-only check box is selected.</span></span> <span data-ttu-id="1b6e1-114">Infine, la <xref:System.Windows.Forms.FileDialog.Filter%2A> proprietà imposta la stringa di filtro del nome file corrente, che determina le scelte visualizzate nella casella "file di tipo" nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="1b6e1-114">Finally, the <xref:System.Windows.Forms.FileDialog.Filter%2A> property sets the current file name filter string, which determines the choices that appear in the "Files of type" box in the dialog box.</span></span>

<span data-ttu-id="1b6e1-115">Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.OpenFileDialog> componente viene visualizzato nella barra delle applicazioni nella parte inferiore del progettazione Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1b6e1-115">When it is added to a form, the <xref:System.Windows.Forms.OpenFileDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="1b6e1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b6e1-116">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="1b6e1-117">Componente OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="1b6e1-117">OpenFileDialog Component</span></span>](openfiledialog-component-windows-forms.md)

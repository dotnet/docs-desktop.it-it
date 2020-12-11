---
title: Panoramica del componente PrintDialog
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 0ed7f7a1f9770f71b75ae744a056b6943335c852
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961465"
---
# <a name="printdialog-component-overview-windows-forms"></a><span data-ttu-id="34e6c-102">Cenni preliminari sul componente PrintDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="34e6c-102">PrintDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="34e6c-103">Il Windows Forms componente [PrintDialog](printdialog-component-windows-forms.md) è una finestra di dialogo preconfigurata utilizzata per selezionare una stampante, scegliere le pagine da stampare e determinare altre impostazioni relative alla stampa nelle applicazioni basate su Windows.</span><span class="sxs-lookup"><span data-stu-id="34e6c-103">The Windows Forms [PrintDialog](printdialog-component-windows-forms.md) component is a pre-configured dialog box used to select a printer, choose the pages to print, and determine other print-related settings in Windows-based applications.</span></span> <span data-ttu-id="34e6c-104">Questo componente può essere usato come semplice soluzione per la selezione della stampante e delle impostazioni relative alla stampa anziché configurare una propria finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="34e6c-104">Use it as a simple solution for printer and print-related settings selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="34e6c-105">È possibile consentire agli utenti di stampare molte parti dei documenti: stampa tutto, stampa un intervallo di pagine selezionato o stampa una selezione.</span><span class="sxs-lookup"><span data-stu-id="34e6c-105">You can enable users to print many parts of their documents: print all, print a selected page range, or print a selection.</span></span> <span data-ttu-id="34e6c-106">Basandosi sulle finestre di dialogo standard di Windows è quindi possibile creare applicazioni le cui funzionalità di base sono immediatamente familiari agli utenti.</span><span class="sxs-lookup"><span data-stu-id="34e6c-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="34e6c-107">Il <xref:System.Windows.Forms.PrintDialog> componente eredita dalla <xref:System.Windows.Forms.CommonDialog> classe.</span><span class="sxs-lookup"><span data-stu-id="34e6c-107">The <xref:System.Windows.Forms.PrintDialog> component inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="working-with-the-component"></a><span data-ttu-id="34e6c-108">Utilizzo del componente</span><span class="sxs-lookup"><span data-stu-id="34e6c-108">Working with the Component</span></span>

<span data-ttu-id="34e6c-109">Utilizzare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="34e6c-109">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="34e6c-110">Questo componente dispone di proprietà correlate a un singolo processo di stampa ( <xref:System.Drawing.Printing.PrintDocument> classe) o alle impostazioni di una singola stampante ( <xref:System.Drawing.Printing.PrinterSettings> classe).</span><span class="sxs-lookup"><span data-stu-id="34e6c-110">This component has properties that relate to either a single print job (<xref:System.Drawing.Printing.PrintDocument> class) or the settings of an individual printer (<xref:System.Drawing.Printing.PrinterSettings> class).</span></span> <span data-ttu-id="34e6c-111">Uno di questi, a sua volta, può essere condiviso da più stampanti.</span><span class="sxs-lookup"><span data-stu-id="34e6c-111">Either of these, in turn, may be shared by multiple printers.</span></span>

<span data-ttu-id="34e6c-112">Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.PrintDialog> componente viene visualizzato nella barra delle applicazioni nella parte inferiore del progettazione Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="34e6c-112">When it is added to a form, the <xref:System.Windows.Forms.PrintDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="34e6c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34e6c-113">See also</span></span>

- <xref:System.Windows.Forms.PrintDialog>
- [<span data-ttu-id="34e6c-114">Componente PrintDialog</span><span class="sxs-lookup"><span data-stu-id="34e6c-114">PrintDialog Component</span></span>](printdialog-component-windows-forms.md)

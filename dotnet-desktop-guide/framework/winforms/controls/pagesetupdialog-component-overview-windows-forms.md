---
title: Panoramica del componente PageSetupDialog
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: a891cb8cc77007d7591d41461c94f61c077eb300
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964984"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a><span data-ttu-id="97f80-102">Cenni preliminari sul componente PageSetupDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="97f80-102">PageSetupDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="97f80-103">Il <xref:System.Windows.Forms.PageSetupDialog> componente Windows Forms è una finestra di dialogo preconfigurata utilizzata per impostare i dettagli della pagina per la stampa in applicazioni basate su Windows.</span><span class="sxs-lookup"><span data-stu-id="97f80-103">The Windows Forms <xref:System.Windows.Forms.PageSetupDialog> component is a pre-configured dialog box used to set page details for printing in Windows-based applications.</span></span> <span data-ttu-id="97f80-104">Utilizzarlo all'interno dell'applicazione basata su Windows come soluzione semplice per consentire agli utenti di impostare le preferenze di pagina anziché configurare la propria finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="97f80-104">Use it within your Windows-based application as a simple solution for users to set page preferences in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="97f80-105">È possibile consentire agli utenti di impostare le regolazioni del bordo e del margine, le intestazioni e i piè di pagina e l'orientamento verticale o orizzontale.</span><span class="sxs-lookup"><span data-stu-id="97f80-105">You can enable users to set border and margin adjustments, headers and footers, and portrait or landscape orientation.</span></span> <span data-ttu-id="97f80-106">Basandosi sulle finestre di dialogo standard di Windows è quindi possibile creare applicazioni le cui funzionalità di base sono immediatamente familiari agli utenti.</span><span class="sxs-lookup"><span data-stu-id="97f80-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span>

## <a name="key-properties-and-methods"></a><span data-ttu-id="97f80-107">Proprietà e metodi chiave</span><span class="sxs-lookup"><span data-stu-id="97f80-107">Key Properties and Methods</span></span>

<span data-ttu-id="97f80-108">Utilizzare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="97f80-108">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="97f80-109">Questo componente dispone di proprietà che è possibile impostare correlate a una singola pagina ( <xref:System.Drawing.Printing.PrintDocument> classe) o a qualsiasi documento ( <xref:System.Drawing.Printing.PageSettings> classe).</span><span class="sxs-lookup"><span data-stu-id="97f80-109">This component has properties you can set that relate to either a single page (<xref:System.Drawing.Printing.PrintDocument> class) or any document (<xref:System.Drawing.Printing.PageSettings> class).</span></span> <span data-ttu-id="97f80-110">Inoltre, il <xref:System.Windows.Forms.PageSetupDialog> componente può essere utilizzato per determinare impostazioni della stampante specifiche, che vengono archiviate nella <xref:System.Drawing.Printing.PrinterSettings> classe.</span><span class="sxs-lookup"><span data-stu-id="97f80-110">Additionally, the <xref:System.Windows.Forms.PageSetupDialog> component can be used to determine specific printer settings, which are stored in the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span>

<span data-ttu-id="97f80-111">Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.PageSetupDialog> componente viene visualizzato nella barra delle applicazioni nella parte inferiore del progettazione Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="97f80-111">When it is added to a form, the <xref:System.Windows.Forms.PageSetupDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="97f80-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97f80-112">See also</span></span>

- <xref:System.Windows.Forms.PageSetupDialog>
- [<span data-ttu-id="97f80-113">Componente PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="97f80-113">PageSetupDialog Component</span></span>](pagesetupdialog-component-windows-forms.md)

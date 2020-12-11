---
title: "Procedura: Rifiutare esplicitamente l'aggiornamento automatico della finestra di dialogo File"
ms.date: 03/30/2017
helpviewer_keywords:
- OpenFileDialog [Windows Forms], opt out of automatic upgrade
- file dialog box [Windows Forms], opt out of automatic upgrade
- Windows Vista file dialog box [Windows Forms], opt out of automatic upgrade
- SaveFileDialog [Windows Forms], opt out of automatic upgrade
- AutoUpgradeEnabled property
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
ms.openlocfilehash: 154953680426f98a9506feb0b8f4de25c873b795
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964921"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="3881a-102">Procedura: Rifiutare esplicitamente l'aggiornamento automatico della finestra di dialogo File</span><span class="sxs-lookup"><span data-stu-id="3881a-102">How To: Opt Out of File Dialog Box Automatic Upgrade</span></span>
<span data-ttu-id="3881a-103">Quando le <xref:System.Windows.Forms.OpenFileDialog> <xref:System.Windows.Forms.SaveFileDialog> classi e vengono usate in un'applicazione, l'aspetto e il comportamento dipendono dalla versione di Windows in cui è in esecuzione l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3881a-103">When the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes are used in an application, their appearance and behavior depend on the version of Windows the application is running on.</span></span> <span data-ttu-id="3881a-104">Quando un'applicazione creata in .NET Framework 2,0 o versioni precedenti viene visualizzata in Windows Vista <xref:System.Windows.Forms.OpenFileDialog> e viene <xref:System.Windows.Forms.SaveFileDialog> visualizzata automaticamente con l'aspetto e il comportamento di Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="3881a-104">When an application that was created on the .NET Framework 2.0 or earlier is displayed on Windows Vista, <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> are automatically displayed with the Windows Vista appearance and behavior.</span></span> <span data-ttu-id="3881a-105">A partire da .NET Framework 3,0, è possibile rifiutare esplicitamente l'aggiornamento automatico per visualizzare <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> con un aspetto e un comportamento di tipo Windows XP.</span><span class="sxs-lookup"><span data-stu-id="3881a-105">Starting in the .NET Framework 3.0, you can opt out of the automatic upgrade to display the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> with a Windows XP-style appearance and behavior.</span></span>  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="3881a-106">Per rifiutare esplicitamente l'aggiornamento automatico della finestra di dialogo File</span><span class="sxs-lookup"><span data-stu-id="3881a-106">To opt out of file dialog box automatic upgrade</span></span>  
  
1. <span data-ttu-id="3881a-107">Impostare la <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> proprietà di <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog> su `false` prima di visualizzare la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="3881a-107">Set the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property of <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> to `false` before you display the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3881a-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3881a-108">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>

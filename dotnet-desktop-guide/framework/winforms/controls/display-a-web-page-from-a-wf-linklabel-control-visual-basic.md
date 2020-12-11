---
title: Visualizza pagina Web dal controllo LinkLabel (Visual Basic)
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- LinkLabel1_LinkClicked
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Web pages [Windows Forms], displaying
- linking [Windows Forms], to Web pages from forms
- Windows Forms, linking to Web pages
- LinkLabel control [Windows Forms], examples
ms.assetid: 477a7398-5971-4de3-b24c-f49f32bdb28a
ms.openlocfilehash: 75373d55b7bc5ef11e39d5b9546996cb1c4f6f7c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96950958"
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a><span data-ttu-id="f2637-102">Procedura: Visualizzare una pagina Web da un controllo LinkLabel di Windows Forms (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2637-102">How to: Display a Web Page from a Windows Forms LinkLabel Control (Visual Basic)</span></span>
<span data-ttu-id="f2637-103">In questo esempio viene visualizzata una pagina Web nel browser predefinito quando un utente fa clic su un <xref:System.Windows.Forms.LinkLabel> controllo Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f2637-103">This example displays a Web page in the default browser when a user clicks a Windows Forms <xref:System.Windows.Forms.LinkLabel> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2637-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="f2637-104">Example</span></span>  
  
```vb  
Private Sub Form1_Load(ByVal sender As System.Object, ByVal e _  
As System.EventArgs) Handles MyBase.Load  
    LinkLabel1.Text = "Click here to get more info."  
    LinkLabel1.Links.Add(6, 4, "www.microsoft.com")  
End Sub  
Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, ByVal _  
e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) Handles _  
LinkLabel1.LinkClicked  
    System.Diagnostics.Process.Start(e.Link.LinkData.ToString())  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f2637-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="f2637-105">Compiling the Code</span></span>  
 <span data-ttu-id="f2637-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2637-106">This example requires:</span></span>  
  
- <span data-ttu-id="f2637-107">Windows Form denominato `Form1` .</span><span class="sxs-lookup"><span data-stu-id="f2637-107">A Windows Form named `Form1`.</span></span>  
  
- <span data-ttu-id="f2637-108">Un controllo <xref:System.Windows.Forms.LinkLabel> denominato `LinkLabel1`.</span><span class="sxs-lookup"><span data-stu-id="f2637-108">A <xref:System.Windows.Forms.LinkLabel> control named `LinkLabel1`.</span></span>  
  
- <span data-ttu-id="f2637-109">Una connessione Internet attiva.</span><span class="sxs-lookup"><span data-stu-id="f2637-109">An active Internet connection.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f2637-110">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f2637-110">.NET Framework Security</span></span>  
 <span data-ttu-id="f2637-111">La chiamata al <xref:System.Diagnostics.Process.Start%2A> metodo richiede l'attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="f2637-111">The call to the <xref:System.Diagnostics.Process.Start%2A> method requires full trust.</span></span> <span data-ttu-id="f2637-112">Per altre informazioni, vedere <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="f2637-112">For more information, see <xref:System.Security.SecurityException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2637-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2637-113">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel>
- [<span data-ttu-id="f2637-114">Controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="f2637-114">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)

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
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a>Procedura: Visualizzare una pagina Web da un controllo LinkLabel di Windows Forms (Visual Basic)
In questo esempio viene visualizzata una pagina Web nel browser predefinito quando un utente fa clic su un <xref:System.Windows.Forms.LinkLabel> controllo Windows Forms.  
  
## <a name="example"></a>Esempio  
  
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
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Windows Form denominato `Form1` .  
  
- Un controllo <xref:System.Windows.Forms.LinkLabel> denominato `LinkLabel1`.  
  
- Una connessione Internet attiva.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 La chiamata al <xref:System.Diagnostics.Process.Start%2A> metodo richiede l'attendibilità totale. Per altre informazioni, vedere <xref:System.Security.SecurityException>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.LinkLabel>
- [Controllo LinkLabel](linklabel-control-windows-forms.md)

---
title: "Procedura: Acquisire l'input dell'utente da un componente PrintDialog in fase di esecuzione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print options [Windows Forms], changing at run time
- printing [Windows Forms], options
- print options
- run time [Windows Forms], changing print options
ms.assetid: 438501d8-9a70-4fb3-aae6-e46579aba0c6
ms.openlocfilehash: 2aaf988f362baf9cd80eb16e4a08f7f65a5077bb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960973"
---
# <a name="how-to-capture-user-input-from-a-printdialog-at-run-time"></a>Procedura: Acquisire l'input dell'utente da un componente PrintDialog in fase di esecuzione
Sebbene sia possibile impostare opzioni correlate alla stampa in fase di progettazione, è talvolta necessario modificare queste opzioni in fase di esecuzione, probabilmente a causa delle scelte effettuate dall'utente. È possibile acquisire l'input dell'utente per la stampa di un documento usando i <xref:System.Windows.Forms.PrintDialog> <xref:System.Drawing.Printing.PrintDocument> componenti e.  
  
### <a name="to-change-print-options-programmatically"></a>Per modificare le opzioni di stampa a livello di codice  
  
1. Aggiungere un <xref:System.Windows.Forms.PrintDialog> e un <xref:System.Drawing.Printing.PrintDocument> componente al form.  
  
2. Impostare la <xref:System.Windows.Forms.PrintDialog.Document%2A> proprietà dell'oggetto sull' <xref:System.Windows.Forms.PrintDialog> oggetto <xref:System.Drawing.Printing.PrintDocument> aggiunto al form.  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3. Visualizzare il <xref:System.Windows.Forms.PrintDialog> componente utilizzando il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo.  
  
    ```vb  
    PrintDialog1.ShowDialog()  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4. Le scelte di stampa dell'utente dalla finestra di dialogo verranno copiate nella <xref:System.Drawing.Printing.PrinterSettings> proprietà del <xref:System.Drawing.Printing.PrintDocument> componente.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Stampare un file di testo con più pagine in Windows Form](how-to-print-a-multi-page-text-file-in-windows-forms.md)
- [Supporto per la stampa in Windows Form](windows-forms-print-support.md)

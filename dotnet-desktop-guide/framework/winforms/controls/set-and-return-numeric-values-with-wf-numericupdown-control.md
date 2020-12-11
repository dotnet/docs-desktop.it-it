---
title: Impostare e restituire valori numerici con il controllo NumericUpDown
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- numeric values [Windows Forms], Windows Forms
- Windows Forms, numeric values
- Windows Forms controls, NumericUpDown
- NumericUpDown control [Windows Forms], setting and returning values
ms.assetid: 5bd8f8cd-4c12-49ea-9cc3-2a647d064689
ms.openlocfilehash: a0b264fec9619b467c293bcb96278c4517775ac3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966067"
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a>Procedura: Impostare e restituire valori numerici con il controllo NumericUpDown di Windows Forms
Il valore numerico del controllo Windows Forms <xref:System.Windows.Forms.NumericUpDown> è determinato dalla relativa <xref:System.Windows.Forms.NumericUpDown.Value%2A> Proprietà. È possibile scrivere test condizionali per il valore del controllo esattamente come per qualsiasi altra proprietà. Una volta <xref:System.Windows.Forms.NumericUpDown.Value%2A> impostata la proprietà, è possibile modificarla direttamente scrivendo codice per eseguire operazioni su di esso oppure è possibile chiamare i <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> metodi e <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> .  
  
### <a name="to-set-the-numeric-value"></a>Per impostare il valore numerico  
  
1. Assegnare un valore alla <xref:System.Windows.Forms.NumericUpDown.Value%2A> proprietà nel codice o nel finestra Proprietà.  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     -oppure-  
  
2. Chiamare il <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> metodo o per aumentare o diminuire il valore in base alla quantità specificata nella <xref:System.Windows.Forms.NumericUpDown.Increment%2A> Proprietà.  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a>Per restituire il valore numerico  
  
- Accedere alla <xref:System.Windows.Forms.NumericUpDown.Value%2A> proprietà nel codice.  
  
    ```vb  
    If NumericUpDown1.Value >= 65 Then  
       MessageBox.Show("Age is: " & NumericUpDown1.Value.ToString)  
    Else  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.")  
    End If  
    ```  
  
    ```csharp  
    if(numericUpDown1.Value >= 65)  
    {  
       MessageBox.Show("Age is: " + numericUpDown1.Value.ToString());  
    }  
    else  
    {  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
    ```cpp  
    if(numericUpDown1->Value >= 65)  
    {  
       MessageBox::Show(String::Concat("Age is: ",  
          numericUpDown1->Value.ToString()));  
    }  
    else  
    {  
       MessageBox::Show  
          ("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.NumericUpDown>
- <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>
- [Controllo NumericUpDown](numericupdown-control-windows-forms.md)
- [Panoramica del controllo NumericUpDown](numericupdown-control-overview-windows-forms.md)

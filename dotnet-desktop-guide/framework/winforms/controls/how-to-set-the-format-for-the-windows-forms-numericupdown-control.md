---
title: Imposta il formato per il controllo NumericUpDown
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: 5ef1c801e96bef7b92e7e69dc36491144c456eeb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964912"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a>Procedura: Impostare il formato per il controllo NumericUpDown di Windows Forms
È possibile configurare la modalità di visualizzazione dei valori nel <xref:System.Windows.Forms.NumericUpDown> controllo Windows Forms. La <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> proprietà determina il numero di numeri visualizzati dopo il separatore decimale. il valore predefinito è 0. La <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> proprietà determina se un separatore verrà inserito tra tre cifre decimali. il valore predefinito è `false` . Il controllo può visualizzare i valori in formato esadecimale anziché decimale, se la <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> proprietà è impostata su `true` . il valore predefinito è `false` .  
  
### <a name="to-format-the-numeric-value"></a>Per formattare il valore numerico  
  
- Visualizzare un valore decimale impostando la <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> proprietà su un intero e impostando la <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> proprietà su `true` o `false` .  
  
    ```vb  
    NumericUpDown1.DecimalPlaces = 2  
    NumericUpDown1.ThousandsSeparator = True  
    ```  
  
    ```csharp  
    numericUpDown1.DecimalPlaces = 2;  
    numericUpDown1.ThousandsSeparator = true;  
    ```  
  
    ```cpp  
    numericUpDown1->DecimalPlaces = 2;  
    numericUpDown1->ThousandsSeparator = true;  
    ```  
  
     -oppure-  
  
- Per visualizzare un valore esadecimale, impostare la <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> proprietà su `true` .  
  
    ```vb  
    NumericUpDown1.Hexadecimal = True  
    ```  
  
    ```csharp  
    numericUpDown1.Hexadecimal = true;  
    ```  
  
    ```cpp  
    numericUpDown1->Hexadecimal = true;  
    ```  
  
    > [!NOTE]
    > Anche se il valore viene visualizzato nel formato esadecimale, i test eseguiti sulla proprietà ne verificheranno il <xref:System.Windows.Forms.NumericUpDown.Value%2A> valore decimale.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.NumericUpDown>
- [Controllo NumericUpDown](numericupdown-control-windows-forms.md)
- [Panoramica del controllo NumericUpDown](numericupdown-control-overview-windows-forms.md)

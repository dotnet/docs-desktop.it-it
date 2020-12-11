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
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a><span data-ttu-id="6b9d7-102">Procedura: Impostare il formato per il controllo NumericUpDown di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6b9d7-102">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="6b9d7-103">È possibile configurare la modalità di visualizzazione dei valori nel <xref:System.Windows.Forms.NumericUpDown> controllo Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6b9d7-103">You can configure how values are displayed in the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="6b9d7-104">La <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> proprietà determina il numero di numeri visualizzati dopo il separatore decimale. il valore predefinito è 0.</span><span class="sxs-lookup"><span data-stu-id="6b9d7-104">The <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property determines how many numbers appear after the decimal point; the default is 0.</span></span> <span data-ttu-id="6b9d7-105">La <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> proprietà determina se un separatore verrà inserito tra tre cifre decimali. il valore predefinito è `false` .</span><span class="sxs-lookup"><span data-stu-id="6b9d7-105">The <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property determines whether a separator will be inserted between every three decimal digits; the default is `false`.</span></span> <span data-ttu-id="6b9d7-106">Il controllo può visualizzare i valori in formato esadecimale anziché decimale, se la <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> proprietà è impostata su `true` . il valore predefinito è `false` .</span><span class="sxs-lookup"><span data-stu-id="6b9d7-106">The control can display values in hexadecimal instead of decimal format, if the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property is set to `true`; the default is `false`.</span></span>  
  
### <a name="to-format-the-numeric-value"></a><span data-ttu-id="6b9d7-107">Per formattare il valore numerico</span><span class="sxs-lookup"><span data-stu-id="6b9d7-107">To format the numeric value</span></span>  
  
- <span data-ttu-id="6b9d7-108">Visualizzare un valore decimale impostando la <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> proprietà su un intero e impostando la <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> proprietà su `true` o `false` .</span><span class="sxs-lookup"><span data-stu-id="6b9d7-108">Display a decimal value by setting the <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property to an integer and setting the <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property to `true` or `false`.</span></span>  
  
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
  
     <span data-ttu-id="6b9d7-109">-oppure-</span><span class="sxs-lookup"><span data-stu-id="6b9d7-109">-or-</span></span>  
  
- <span data-ttu-id="6b9d7-110">Per visualizzare un valore esadecimale, impostare la <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> proprietà su `true` .</span><span class="sxs-lookup"><span data-stu-id="6b9d7-110">Display a hexadecimal value by setting the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property to `true`.</span></span>  
  
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
    > <span data-ttu-id="6b9d7-111">Anche se il valore viene visualizzato nel formato esadecimale, i test eseguiti sulla proprietà ne verificheranno il <xref:System.Windows.Forms.NumericUpDown.Value%2A> valore decimale.</span><span class="sxs-lookup"><span data-stu-id="6b9d7-111">Even if the value is displayed on the form as hexadecimal, any tests you perform on the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property will be testing its decimal value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b9d7-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b9d7-112">See also</span></span>

- <xref:System.Windows.Forms.NumericUpDown>
- [<span data-ttu-id="6b9d7-113">Controllo NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="6b9d7-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="6b9d7-114">Panoramica del controllo NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="6b9d7-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)

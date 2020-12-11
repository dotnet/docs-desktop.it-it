---
title: 'Procedura: Condividere i dati associati tra moduli usando il componente BindingSource'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], BindingSource component
- data binding [Windows Forms], sharing data across forms
- BindingSource component [Windows Forms], examples
- BindingSource [Windows Forms], using with multiple forms
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
ms.openlocfilehash: aa497194fd4ac65f48773a45175333a1d862b453
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965176"
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a>Procedura: Condividere i dati associati tra moduli usando il componente BindingSource
È possibile condividere facilmente i dati tra i form con il componente <xref:System.Windows.Forms.BindingSource>. Ad esempio, è possibile visualizzare un form di sola lettura che riepiloga i dati dell'origine dati e un altro form modificabile che contiene informazioni dettagliate sull'elemento attualmente selezionato nell'origine dati. L'esempio illustra questo scenario.  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente illustra come condividere un oggetto <xref:System.Windows.Forms.BindingSource> e i dati associati tra i form. In questo esempio, l'oggetto <xref:System.Windows.Forms.BindingSource> condiviso viene passato al costruttore del form figlio. Il form figlio consente all'utente di modificare i dati per l'elemento attualmente selezionato nel form principale.  
  
> [!NOTE]
> Nell'esempio viene gestito l'evento <xref:System.Windows.Forms.BindingSource.BindingComplete> del componente <xref:System.Windows.Forms.BindingSource> per essere certi che i due form rimangano sincronizzati Per altre informazioni sul motivo per cui questa operazione viene eseguita, vedere [Procedura: Garantire la sincronizzazione di più controlli associati alla stessa origine dati](../multiple-controls-bound-to-data-source-synchronized.md).  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Windows.Forms, System.Drawing, System.Data e System.Xml.  
  
## <a name="see-also"></a>Vedere anche

- [Componente BindingSource](bindingsource-component.md)
- [Data binding di Windows Form](../windows-forms-data-binding.md)
- [Procedura: Gestire errori ed eccezioni relativi al data binding](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)

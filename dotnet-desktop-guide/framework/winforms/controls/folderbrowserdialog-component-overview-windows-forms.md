---
title: Panoramica del componente FolderBrowserDialog
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: 8b017ba08ae4205e930ac00177c89a89fde17d3b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962899"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a>Cenni preliminari sul componente FolderBrowserDialog (Windows Form)

Il <xref:System.Windows.Forms.FolderBrowserDialog> componente Windows Forms è una finestra di dialogo modale utilizzata per l'esplorazione e la selezione di cartelle. È anche possibile creare nuove cartelle dall'interno del <xref:System.Windows.Forms.FolderBrowserDialog> componente.

> [!NOTE]
> Per selezionare i file, anziché le cartelle, utilizzare il componente [OpenFileDialog](openfiledialog-component-windows-forms.md) .

Il <xref:System.Windows.Forms.FolderBrowserDialog> componente viene visualizzato in fase di esecuzione usando il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo. Impostare la <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> proprietà per determinare la cartella più in alto e tutte le sottocartelle che verranno visualizzate nella visualizzazione albero della finestra di dialogo. Una volta visualizzata la finestra di dialogo, è possibile usare la <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> proprietà per ottenere il percorso della cartella selezionata.

Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.FolderBrowserDialog> componente viene visualizzato nella barra delle applicazioni nella parte inferiore del progettazione Windows Form in Visual Studio.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [Procedura: Scegliere cartelle con il componente FolderBrowserDialog di Windows Forms](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [Componente FolderBrowserDialog](folderbrowserdialog-component-windows-forms.md)

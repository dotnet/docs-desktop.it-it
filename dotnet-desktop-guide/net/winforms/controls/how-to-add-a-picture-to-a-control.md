---
title: Visualizzare un'immagine in un controllo
description: Informazioni su come visualizzare un'immagine in un controllo Windows Form. Molti controlli, ad esempio PictureBox, possono visualizzare un'immagine.
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms contr ols
- examples [Windows Forms], controls
ms.openlocfilehash: a0b95d51f852df4c9ddc190903369faa41f7deae
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966022"
---
# <a name="how-to-display-an-image-on-a-control-windows-forms-net"></a>Come visualizzare un'immagine in un controllo (Windows Forms .NET)

Diversi controlli Windows Forms possono visualizzare immagini. Queste immagini possono essere icone che chiariscono lo scopo del controllo, ad esempio un'icona a forma di dischetto in un pulsante che indica il comando Salva. In alternativa, le icone possono essere immagini di sfondo per dare al controllo l'aspetto e il comportamento desiderati.

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="designer"></a>Designer

Nella finestra **Proprietà** di Visual Studio selezionare la proprietà **Image** o **BackgroundImage** del controllo, quindi selezionare i puntini di sospensione ( ![ pulsante con i puntini di sospensione in Visual Studio ](../media/visual-studio-ellipsis-button.png) ) per visualizzare la finestra di dialogo **Seleziona risorsa** , quindi selezionare l'immagine che si desidera visualizzare.

:::image type="content" source="media/how-to-add-a-picture-to-a-control/properties-image.png" alt-text="Finestra di dialogo Proprietà con proprietà immagine selezionata":::

## <a name="programmatic"></a>Programmatica

Impostare la `Image` proprietà o del controllo `BackgroundImage` su un oggetto di tipo <xref:System.Drawing.Image> . In genere, è possibile caricare l'immagine da un file usando il <xref:System.Drawing.Image.FromFile%2A> metodo.

Nell'esempio di codice seguente il percorso impostato per il percorso dell'immagine è la cartella **Immagini personali** . La maggior parte dei computer che eseguono il sistema operativo Windows include questa directory. Consente inoltre agli utenti con livelli di accesso di sistema minimi di eseguire l'applicazione in modo sicuro. Nell'esempio di codice seguente è necessario avere già un modulo con un <xref:System.Windows.Forms.PictureBox> controllo aggiunto.

```csharp
// Replace the image named below with your own icon.
// Note the escape character used (@) when specifying the path.
pictureBox1.Image = Image.FromFile
   (System.Environment.GetFolderPath
   (System.Environment.SpecialFolder.MyPictures)
   + @"\Image.gif");
```

```vb
' Replace the image named below with your own icon.
PictureBox1.Image = Image.FromFile _
   (System.Environment.GetFolderPath _
   (System.Environment.SpecialFolder.MyPictures) _
   & "\Image.gif")
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>

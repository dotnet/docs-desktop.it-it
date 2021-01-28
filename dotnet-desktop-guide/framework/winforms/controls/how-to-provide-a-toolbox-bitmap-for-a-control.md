---
title: 'Procedura: Specificare una bitmap nella casella degli strumenti per un controllo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
ms.openlocfilehash: ed4f40d5b25014e5f8222a7406ea3d7eb3f8a98b
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957656"
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a>Procedura: Specificare una bitmap nella casella degli strumenti per un controllo

Se si vuole che venga visualizzata un'icona speciale per il controllo nella **casella degli strumenti** di Visual Studio, è possibile specificare una particolare immagine usando <xref:System.Drawing.ToolboxBitmapAttribute> . Questa classe è un *attributo*, un tipo speciale di classe che è possibile allegare ad altre classi. Per altre informazioni sugli attributi, vedere [Cenni preliminari sugli attributi (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/attributes/index) per Visual Basic o [attributi (C#)](/dotnet/csharp/programming-guide/concepts/attributes/index) per c#.

Utilizzando la <xref:System.Drawing.ToolboxBitmapAttribute> , è possibile specificare una stringa che indica il percorso e il nome file per una bitmap di 16 per 16 pixel. Questa bitmap viene quindi visualizzata accanto al controllo quando è aggiunta alla **Casella degli strumenti**. È anche possibile specificare <xref:System.Type> , nel qual caso viene caricata la bitmap associata a tale tipo. Se si specificano sia un oggetto <xref:System.Type> che una stringa, il controllo Cerca una risorsa immagine con il nome specificato dal parametro stringa nell'assembly contenente il tipo specificato dal <xref:System.Type> parametro.

## <a name="to-specify-a-toolbox-bitmap-for-your-control"></a>Per specificare una bitmap della casella degli strumenti per il controllo

1. Aggiungere alla <xref:System.Drawing.ToolboxBitmapAttribute> dichiarazione di classe del controllo prima della `Class` parola chiave per Visual Basic e sopra la dichiarazione di classe per Visual C#.

    ```vb
    ' Specifies the bitmap associated with the Button type.
    <ToolboxBitmap(GetType(Button))> Class MyControl1
    ' Specifies a bitmap file.
    End Class
    <ToolboxBitmap("C:\Documents and Settings\Joe\MyPics\myImage.bmp")> _
       Class MyControl2
    End Class
    ' Specifies a type that indicates the assembly to search, and the name
    ' of an image resource to look for.
    <ToolboxBitmap(GetType(MyControl), "MyControlBitmap")> Class MyControl
    End Class
    ```

    ```csharp
    // Specifies the bitmap associated with the Button type.
    [ToolboxBitmap(typeof(Button))]
    class MyControl1 : UserControl
    {
    }
    // Specifies a bitmap file.
    [ToolboxBitmap(@"C:\Documents and Settings\Joe\MyPics\myImage.bmp")]
    class MyControl2 : UserControl
    {
    }
    // Specifies a type that indicates the assembly to search, and the name
    // of an image resource to look for.
    [ToolboxBitmap(typeof(MyControl), "MyControlBitmap")]
    class MyControl : UserControl
    {
    }
    ```

2. Ricompilare il progetto.

    > [!NOTE]
    > La bitmap non viene visualizzata nella casella degli strumenti per i controlli e i componenti generati automaticamente. Per visualizzare la bitmap, ricaricare il controllo usando la finestra di dialogo **Scegli elementi della casella degli strumenti**. Per altre informazioni, vedere [Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).

## <a name="see-also"></a>Vedi anche

- <xref:System.Drawing.ToolboxBitmapAttribute>
- [Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [Sviluppo di controlli Windows Form in fase di progettazione](developing-windows-forms-controls-at-design-time.md)
- [Panoramica degli attributi (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/attributes/index)
- [Attributi (C#)](/dotnet/csharp/programming-guide/concepts/attributes/index)

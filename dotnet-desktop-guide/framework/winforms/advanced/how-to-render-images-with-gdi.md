---
title: 'Procedura: Eseguire il rendering delle immagini con GDI+'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], creating
- GDI+, rendering existing images
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
ms.openlocfilehash: fffe1f1052d7323d234985b7e752866f2e89657d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963313"
---
# <a name="how-to-render-images-with-gdi"></a>Procedura: Eseguire il rendering delle immagini con GDI+
È possibile utilizzare GDI+ per eseguire il rendering di immagini presenti come file nelle applicazioni. A tale scopo, creare un nuovo oggetto di una <xref:System.Drawing.Image> classe, ad esempio <xref:System.Drawing.Bitmap> , creando un <xref:System.Drawing.Graphics> oggetto che fa riferimento alla superficie di disegno che si desidera utilizzare e chiamando il <xref:System.Drawing.Graphics.DrawImage%2A> metodo dell' <xref:System.Drawing.Graphics> oggetto. L'immagine verrà disegnata sulla superficie da disegno rappresentata dalla classe della grafica. È possibile utilizzare l'editor di immagini per creare e modificare i file di immagine in fase di progettazione ed eseguirne il rendering con GDI+ in fase di esecuzione. Per altre informazioni, vedere [Image Editor for Icons](/cpp/windows/image-editor-for-icons) (Editor di immagini per le icone).  
  
### <a name="to-render-an-image-with-gdi"></a>Per eseguire il rendering di un'immagine con GDI+  
  
1. Creare un oggetto che rappresenti l'immagine che si desidera visualizzare. Questo oggetto deve essere un membro di una classe che eredita da <xref:System.Drawing.Image> , ad esempio <xref:System.Drawing.Bitmap> o <xref:System.Drawing.Imaging.Metafile> . Esempio:  
  
    ```vb  
    ' Uses the System.Environment.GetFolderPath to get the path to the
    ' current user's MyPictures folder.  
    Dim myBitmap as New Bitmap _  
       (System.Environment.GetFolderPath _  
          (System.Environment.SpecialFolder.MyPictures))  
    ```  
  
    ```csharp  
    // Uses the System.Environment.GetFolderPath to get the path to the
    // current user's MyPictures folder.  
    Bitmap myBitmap = new Bitmap  
       (System.Environment.GetFolderPath  
          (System.Environment.SpecialFolder.MyPictures));  
    ```  
  
    ```cpp  
    // Uses the System.Environment.GetFolderPath to get the path to the
    // current user's MyPictures folder.  
    Bitmap^ myBitmap = gcnew Bitmap  
       (System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::MyPictures));  
    ```  
  
2. Creare un <xref:System.Drawing.Graphics> oggetto che rappresenti la superficie di disegno che si desidera utilizzare. Per altre informazioni, vedere [Procedura: Creare oggetti Graphics per disegnare](how-to-create-graphics-objects-for-drawing.md).  
  
    ```vb  
    ' Creates a Graphics object that represents the drawing surface of
    ' Button1.  
    Dim g as Graphics = Button1.CreateGraphics  
    ```  
  
    ```csharp  
    // Creates a Graphics object that represents the drawing surface of
    // Button1.  
    Graphics g = Button1.CreateGraphics();  
    ```  
  
    ```cpp  
    // Creates a Graphics object that represents the drawing surface of
    // Button1.  
    Graphics^ g = button1->CreateGraphics();  
    ```  
  
3. Chiamare il <xref:System.Drawing.Graphics.DrawImage%2A> dell'oggetto Graphics per eseguire il rendering dell'immagine. È necessario specificare l'immagine da disegnare e le coordinate in cui deve essere disegnata.  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Guida introduttiva alla programmazione grafica](getting-started-with-graphics-programming.md)
- [Procedura: Creare oggetti Graphics per disegnare](how-to-create-graphics-objects-for-drawing.md)
- [Penne, linee e rettangoli in GDI+](pens-lines-and-rectangles-in-gdi.md)
- [Procedura: Disegnare testo in un Windows Form](how-to-draw-text-on-a-windows-form.md)
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Disegno di linee o figure chiuse](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)
- [Editor di immagini per le icone](/cpp/windows/image-editor-for-icons)

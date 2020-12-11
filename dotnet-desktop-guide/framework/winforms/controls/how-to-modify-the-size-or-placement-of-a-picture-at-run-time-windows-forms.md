---
title: "Procedura: Modificare le dimensioni o la posizione di un'immagine in fase di esecuzione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], controlling placement in PictureBox control [Windows Forms]
- examples [Windows Forms], PictureBox control
- PictureBox control [Windows Forms], picture size and alignment
- pictures [Windows Forms], controlling placement in PictureBox control [Windows Forms]
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
ms.openlocfilehash: fea813d7b9fe585e35b729b8b64e3a5f414ef76d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961738"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>Procedura: modificare le dimensioni o la posizione di un'immagine in fase di esecuzione (Windows Form)
Se si usa il <xref:System.Windows.Forms.PictureBox> controllo Windows Forms in un form, è possibile impostare la <xref:System.Windows.Forms.PictureBox.SizeMode%2A> proprietà su:  
  
- Allinea l'angolo superiore sinistro dell'immagine all'angolo superiore sinistro del controllo  
  
- Centrare l'immagine all'interno del controllo  
  
- Regolare le dimensioni del controllo in modo da adattarle all'immagine visualizzata  
  
- Estendi tutte le immagini visualizzate per adattarle al controllo  
  
 L'estensione di un'immagine, in particolare un formato bitmap, può causare una perdita di qualità dell'immagine. I metafile, che sono elenchi di istruzioni grafiche per il disegno di immagini in fase di esecuzione, sono più adatti per l'estensione delle bitmap.  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>Per impostare la proprietà SizeMode in fase di esecuzione  
  
1. Impostare <xref:System.Windows.Forms.PictureBox.SizeMode%2A> su <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (valore predefinito), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> , <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> o <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> . <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> indica che l'immagine viene posizionata nell'angolo superiore sinistro del controllo; Se l'immagine è più grande del controllo, i bordi inferiore e destro vengono ritagliati. <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> indica che l'immagine è centrata all'interno del controllo; Se l'immagine è più grande del controllo, i bordi esterni dell'immagine vengono ritagliati. <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> indica che le dimensioni del controllo vengono modificate fino alla dimensione dell'immagine. <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> è il contrario e indica che le dimensioni dell'immagine vengono modificate in modo da determinare le dimensioni del controllo.  
  
     Nell'esempio seguente, il percorso impostato per il percorso dell'immagine è la cartella documenti. Questa operazione viene eseguita perché è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows includa questa directory. Ciò consente inoltre agli utenti del sistema con livelli di accesso minimo di eseguire l'applicazione senza problemi. Nell'esempio seguente si presuppone che un modulo con un <xref:System.Windows.Forms.PictureBox> controllo sia già stato aggiunto.  
  
    ```vb  
    Private Sub StretchPic()  
       ' Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage  
       ' Load the picture into the control.  
       ' You should replace the bold image
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void StretchPic(){  
       // Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage;  
       // Load the picture into the control.  
       // You should replace the bold image
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Image.gif")  
    }  
    ```  
  
    ```cpp  
    private:  
       void StretchPic()  
       {  
          // Stretch the picture to fit the control.  
          pictureBox1->SizeMode = PictureBoxSizeMode::StretchImage;  
          // Load the picture into the control.  
          // You should replace the bold image
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.PictureBox>
- [Procedura: Caricare un'immagine usando la finestra di progettazione](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Panoramica del controllo PictureBox](picturebox-control-overview-windows-forms.md)
- [Procedura: Impostare le immagini in fase di esecuzione](how-to-set-pictures-at-run-time-windows-forms.md)
- [Controllo PictureBox](picturebox-control-windows-forms.md)

---
title: "Procedura: Modificare l'input da tastiera in un controllo standard"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboard input [Windows Forms], modifying
- modifying keyboard input
- Windows Forms, modifying keyboard input
- keyboards [Windows Forms], keyboard input
ms.assetid: 626d3712-d866-4988-bcda-a2d5b36ec0ba
ms.openlocfilehash: 1aa22501eb3d15b30be4ea4918473cf5a48cfe94
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965425"
---
# <a name="how-to-modify-keyboard-input-to-a-standard-control"></a>Procedura: Modificare l'input da tastiera in un controllo standard
Windows Forms permette di usare e modificare l'input da tastiera. L'utilizzo di una chiave fa riferimento alla gestione di una chiave entro un metodo o un gestore eventi, in modo che altri metodi ed eventi successivi nella coda di messaggi non ricevano il valore della chiave. Per modifica di una chiave si intente la modifica del valore di una chiave, in modo che i metodi e i gestori eventi successivi nella coda di messaggi ricevano un valore di chiave diverso. Questo argomento illustra come completare queste attività.  
  
### <a name="to-consume-a-key"></a>Per usare una chiave  
  
- In un gestore eventi <xref:System.Windows.Forms.Control.KeyPress> impostare la proprietà <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> della classe <xref:System.Windows.Forms.KeyPressEventArgs> su `true`.  
  
     -oppure-  
  
     In un gestore eventi <xref:System.Windows.Forms.Control.KeyDown> impostare la proprietà <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> della classe <xref:System.Windows.Forms.KeyEventArgs> su `true`.  
  
    > [!NOTE]
    > L'impostazione della proprietà <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> nel gestore eventi <xref:System.Windows.Forms.Control.KeyDown> non impedisce la generazione degli eventi <xref:System.Windows.Forms.Control.KeyPress> e <xref:System.Windows.Forms.Control.KeyUp> per la sequenza di tasti attuale. Usare la proprietà <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> per questo scopo.  
  
     L'esempio seguente è tratto da un'istruzione `switch` che esamina la proprietà <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> dell'oggetto <xref:System.Windows.Forms.KeyPressEventArgs> ricevuto da un gestore eventi <xref:System.Windows.Forms.Control.KeyPress>. Questo codice usa i tasti corrispondenti ai caratteri 'A' e 'a'.  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#6)]  
  
### <a name="to-modify-a-standard-character-key"></a>Per modificare un tasto carattere standard  
  
- In un gestore eventi <xref:System.Windows.Forms.Control.KeyPress> impostare la proprietà <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> della classe <xref:System.Windows.Forms.KeyPressEventArgs> sul valore del nuovo tasto carattere.  
  
     L'esempio seguente è tratto da un'istruzione `switch` che modifica 'B' in 'A' e 'b' in 'a'. Si noti che la proprietà <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> del parametro <xref:System.Windows.Forms.KeyPressEventArgs> è impostata su `false`, in modo che il nuovo valore del tasto venga propagato ad altri metodi ed eventi nella coda dei messaggi.  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#7)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#7)]  
  
### <a name="to-modify-a-noncharacter-key"></a>Per modificare un tasto non corrispondente a un carattere  
  
- Eseguire l'override di un metodo <xref:System.Windows.Forms.Control> che elabora messaggi di Windows, individuare il messaggio WM_KEYDOWN o WM_SYSKEYDOWN e impostare la proprietà <xref:System.Windows.Forms.Message.WParam%2A> del parametro <xref:System.Windows.Forms.Message> sul valore <xref:System.Windows.Forms.Keys> che rappresenta il nuovo tasto non corrispondente a un carattere.  
  
     L'esempio di codice seguente illustra come eseguire l'override del metodo <xref:System.Windows.Forms.Control.PreProcessMessage%2A> di un controllo per individuare i tasti da F1 a F9 e modificare la funzione del tasto F3 in quella del tasto F1. Per altre informazioni sui <xref:System.Windows.Forms.Control> metodi di cui è possibile eseguire l'override per intercettare i messaggi della tastiera, vedere [input dell'utente in un'applicazione Windows Forms](user-input-in-a-windows-forms-application.md) e funzionamento dell' [input da tastiera](how-keyboard-input-works.md).  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#12)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#12)]  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente è l'applicazione completa degli esempi di codice delle sezioni precedenti. L'applicazione usa un controllo personalizzato derivato dalla classe <xref:System.Windows.Forms.TextBox> per usare e modificare gli input da tastiera.  
  
 [!code-csharp[System.Windows.Forms.KeyBoardInput#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInput#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- [Input da tastiera in un'applicazione Windows Form](keyboard-input-in-a-windows-forms-application.md)
- [Input dell'utente in un'applicazione Windows Form](user-input-in-a-windows-forms-application.md)
- [Funzionamento dell'input da tastiera](how-keyboard-input-works.md)

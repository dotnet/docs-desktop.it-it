---
title: Panoramica del componente ErrorProvider
ms.date: 03/30/2017
f1_keywords:
- ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
ms.openlocfilehash: b66e97d97d0d8c2ea4e9bdba29f8ff35e486e1f6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962206"
---
# <a name="errorprovider-component-overview-windows-forms"></a>Cenni preliminari sul componente ErrorProvider (Windows Form)
Il componente Windows Forms [ErrorProvider](errorprovider-component-windows-forms.md) viene usato per convalidare l'input dell'utente in un form o un controllo. Viene in genere usato in combinazione con la convalida dell'input dell'utente in un form o la visualizzazione di errori all'interno di un set di dati. Un provider di errori è un'alternativa migliore rispetto alla visualizzazione di un messaggio di errore in una finestra di messaggio, perché quando una finestra di messaggio viene rilasciata, il messaggio di errore non è più visibile. Il <xref:System.Windows.Forms.ErrorProvider> componente Visualizza un'icona di errore ( ![ un punto esclamativo bianco all'interno di un cerchio rosso ](./media/errorprovider-component-overview-windows-forms/vb-error-provider-icon.gif) ) accanto al controllo pertinente, ad esempio una casella di testo. quando l'utente posiziona il puntatore del mouse sull'icona di errore, viene visualizzata una descrizione comando che mostra la stringa del messaggio di errore.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Le <xref:System.Windows.Forms.ErrorProvider> proprietà chiave del componente sono <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> , <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> e <xref:System.Windows.Forms.ErrorProvider.Icon%2A> . Quando si usa <xref:System.Windows.Forms.ErrorProvider> un componente con controlli associati a dati, la <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> proprietà deve essere impostata sul contenitore appropriato (in genere il Windows Form) affinché il componente visualizzi un'icona di errore nel form. Quando il componente viene aggiunto nella finestra di progettazione, la <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> proprietà viene impostata sul form che lo contiene; se si aggiunge il controllo nel codice, è necessario impostarlo manualmente.  
  
 La <xref:System.Windows.Forms.ErrorProvider.Icon%2A> proprietà può essere impostata su un'icona di errore personalizzata anziché sul valore predefinito. Quando <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> viene impostata la proprietà, il <xref:System.Windows.Forms.ErrorProvider> componente può visualizzare i messaggi di errore per un set di dati. Il metodo principale del <xref:System.Windows.Forms.ErrorProvider> componente è il <xref:System.Windows.Forms.ErrorProvider.SetError%2A> metodo, che specifica la stringa del messaggio di errore e il punto in cui deve essere visualizzata l'icona di errore.  
  
> [!NOTE]
> Il <xref:System.Windows.Forms.ErrorProvider> componente non fornisce supporto incorporato per i client di accessibilità. Per rendere l'applicazione accessibile quando si utilizza questo componente, è necessario fornire un meccanismo aggiuntivo di feedback accessibile.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ErrorProvider>
- [Procedura: Visualizzare gli errori all'interno di un set di dati con il componente ErrorProvider di Windows Forms](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
- [Procedura: Visualizzare le icone di errore per la convalida dei moduli con il componente ErrorProvider di Windows Forms](display-error-icons-for-form-validation-with-wf-errorprovider.md)

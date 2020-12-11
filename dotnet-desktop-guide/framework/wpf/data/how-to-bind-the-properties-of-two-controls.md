---
title: "Procedura: eseguire l'associazione delle proprietà di due controlli"
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 28b5f65a57fc210f3d405020daa0d75c28b934c8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951639"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a>Procedura: eseguire l'associazione delle proprietà di due controlli

Questo esempio illustra come associare la proprietà di un controllo di cui è stata creata un'istanza a quella di un altro usando la <xref:System.Windows.Data.Binding.ElementName%2A> Proprietà.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come associare la <xref:System.Windows.Controls.Panel.Background%2A> proprietà di un oggetto <xref:System.Windows.Controls.Canvas> alla proprietà [SelectedItem. Content](xref:System.Windows.Controls.ContentControl.Content%2A) di un oggetto <xref:System.Windows.Controls.ComboBox> :

[!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]

Dopo il rendering questo esempio avrà l'aspetto seguente:

![Screenshot che mostra una casella combinata con il valore verde selezionato e un quadrato verde.](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> La proprietà di destinazione del binding, in questo esempio la <xref:System.Windows.Controls.Panel.Background%2A> proprietà, deve essere una proprietà di dipendenza. Per altre informazioni, vedere [Cenni preliminari sul data binding](/dotnet/desktop-wpf/data/data-binding-overview).

## <a name="see-also"></a>Vedere anche

- [Specificare l'origine del binding](how-to-specify-the-binding-source.md)
- [Procedure](data-binding-how-to-topics.md)

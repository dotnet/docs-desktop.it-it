---
title: Tipo XAML intrinseco x:XData
ms.date: 03/30/2017
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
ms.openlocfilehash: 89bdae68608db235b76d6a9b210c77f97bcebe00
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961045"
---
# <a name="xxdata-intrinsic-xaml-type"></a>Tipo XAML intrinseco x:XData
Consente di posizionare le isole di dati XML all'interno di una produzione XAML. Gli elementi XML all'interno di `x:XData` non devono essere considerati da processori XAML come se facessero parte dello spazio dei nomi XAML predefinito di azione o di qualsiasi altro spazio dei nomi XAML. `x:XData` può contenere XML ben formato arbitrario.

## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto

```xaml
<x:XData>
  <elementDataRoot>
    [elementData]
  </elementDataRoot>
</x:XData>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|`elementDataRoot`|Singolo elemento radice dell'isola di dati racchiusi. Per la maggior parte degli utenti finali, il codice XML che non dispone di una singola radice viene considerato non valido. In particolare, è necessaria una singola radice se `x:XData` è destinato a un'origine dati XML per WPF o a molte altre tecnologie che utilizzano origini XML per data binding.|
|`[elementData]`|facoltativo. XML che rappresenta i dati XML. Un numero qualsiasi di elementi può essere contenuto come dati di elemento e gli elementi annidati possono essere contenuti in altri elementi; Tuttavia, vengono applicate le regole generali di XML.|

## <a name="remarks"></a>Osservazioni

Gli elementi XML all'interno `x:XData` di un oggetto possono dichiarare nuovamente tutti gli spazi dei nomi e i prefissi della classe che lo contiene XMLDOM all'interno dei dati.

L'accesso a livello di codice ai dati XML e al `x:XData` tipo XAML intrinseco è possibile nei servizi XAML .NET tramite la <xref:System.Windows.Markup.XData> classe.

## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF

L' `x:XData` oggetto viene principalmente usato come oggetto figlio di un oggetto <xref:System.Windows.Data.XmlDataProvider> o, in alternativa, come oggetto figlio della <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> Proprietà (in XAML, questo viene in genere espresso nella sintassi dell'elemento Property).

I dati in genere ridefiniscono lo spazio dei nomi XML di base all'interno dell'isola di dati in modo che sia un nuovo spazio dei nomi XML predefinito (impostato su una stringa vuota). Questa operazione è più semplice per le isole dati semplici perché le <xref:System.Windows.Data.Binding.XPath%2A> espressioni usate per fare riferimento ai dati e associarle possono evitare di includere i prefissi. Le isole dati più complesse potrebbero definire più prefissi per i dati e usare un prefisso specifico per lo spazio dei nomi XML nella radice. In questo caso, tutti <xref:System.Windows.Data.Binding.XPath%2A> i riferimenti all'espressione devono includere il prefisso mappato allo spazio dei nomi appropriato. Per altre informazioni, vedere [Cenni preliminari sul data binding](../net/wpf/data/data-binding-overview.md).

Tecnicamente, `x:XData` può essere usato come contenuto di qualsiasi proprietà di tipo <xref:System.Xml.Serialization.IXmlSerializable> . Tuttavia, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> è l'unica implementazione prominente.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.XmlDataProvider>
- [Panoramica sul data binding](../net/wpf/data/data-binding-overview.md)
- [Estensione di markup Binding](../framework/wpf/advanced/binding-markup-extension.md)

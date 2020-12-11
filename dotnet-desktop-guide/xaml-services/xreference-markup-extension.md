---
title: estensione di markup x:Reference
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: f06e259893111a436e5afe2df754c3edee326d54
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960985"
---
# <a name="xreference-markup-extension"></a>estensione di markup x:Reference

Fa riferimento a un'istanza di dichiarata in un'altra posizione nel markup XAML. Il riferimento si riferisce a un elemento `x:Name` .

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object property="{x:Reference instancexName}" .../>
```

## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto

```xaml
<object>
  <object.property>
    <x:Reference Name="instancexName"/>
  </object.property>
</object>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|`instancexName`|`x:Name`Valore (o valore della <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> proprietà identificata dall'oggetto) dell'istanza a cui si fa riferimento.|

## <a name="remarks"></a>Osservazioni

`x:Reference` fornisce supporto a livello di linguaggio XAML per un concetto di riferimento a un elemento che è stato altrimenti implementato in Framework specifici, ad esempio WPF.

## <a name="xreference-and-wpf"></a>x:Reference e WPF

In WPF e XAML 2006, i riferimenti agli elementi vengono risolti dalla funzionalità a livello di Framework dell' <xref:System.Windows.Data.Binding.ElementName%2A> associazione. Per la maggior parte delle applicazioni e degli scenari WPF, <xref:System.Windows.Data.Binding.ElementName%2A> è comunque necessario utilizzare l'associazione. Le eccezioni a questo materiale sussidiario generale potrebbero includere casi in cui è presente un contesto dei dati o altre considerazioni sull'ambito che rendono data binding impraticabile e in cui la compilazione del markup non è implicata.

`x:Reference` è un costrutto definito in XAML 2009. In WPF è possibile usare le funzionalità di XAML 2009, ma solo per il codice XAML non compilato dal markup WPF. Il codice XAML compilato dal markup e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.

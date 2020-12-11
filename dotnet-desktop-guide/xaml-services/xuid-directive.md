---
title: Direttiva x:Uid
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: 7508d4917750d108b8843c6926938327b671ac06
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969226"
---
# <a name="xuid-directive"></a>Direttiva x:Uid

Fornisce un identificatore univoco per gli elementi di markup. In molti scenari, questo identificatore univoco viene usato dai processi e dagli strumenti di localizzazione XAML.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object x:Uid="identifier"... />
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|`identifier`|Stringa creata manualmente o generata automaticamente che deve essere univoca in un file quando viene interpretata da un `x:Uid` consumer.|

## <a name="remarks"></a>Osservazioni

In [MS-XAML], `x:Uid` viene definito come direttiva. Per ulteriori informazioni, vedere la [ \[ sezione MS-XAML \] 5.3.6](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

`x:Uid` è discreto da `x:Name` entrambi a causa dello scenario di localizzazione XAML dichiarato e, pertanto, gli identificatori utilizzati per la localizzazione non hanno dipendenze dalle implicazioni del modello di programmazione di `x:Name` . Inoltre, `x:Name` è governato dall'ambito dei nomi XAML. Tuttavia, `x:Uid` non è regolato da alcun concetto di imposizione di univocità definito dal linguaggio XAML. I processori XAML in senso ampio (i processori che non fanno parte del processo di localizzazione) non sono previsti per applicare l'univocità dei `x:Uid` valori. Questa responsabilità è concettualmente sul creatore dei valori. L'aspettativa di univocità dei `x:Uid` valori all'interno di una singola origine XAML è ragionevole per i consumer dei valori, ad esempio i processi o gli strumenti di globalizzazione dedicati. Il modello di univocità tipico è che `x:Uid` i valori sono univoci all'interno di un file con codifica XML che rappresenta XAML.

Gli strumenti con una conoscenza significativa di uno schema XAML specifico possono scegliere di applicare `x:Uid` solo le stringhe localizzabili vere, anziché per tutti i casi in cui viene rilevato un valore stringa di testo nel markup.

I Framework possono specificare una particolare proprietà nel modello a oggetti in modo che sia un alias per `x:Uid` applicando l'attributo <xref:System.Windows.Markup.UidPropertyAttribute> al tipo di definizione. Se un Framework specifica una particolare proprietà, non è possibile specificare sia `x:Uid` che il membro con alias nello stesso oggetto. Se `x:Uid` vengono specificati entrambi e il membro con alias, l'API dei servizi XAML .NET in genere genera un'eccezione <xref:System.Xaml.XamlDuplicateMemberException> per questo caso.

## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF

Per ulteriori informazioni sul ruolo di `x:Uid` nel processo di localizzazione WPF e nella forma BAML di XAML, vedere [globalizzazione per WPF](../framework/wpf/advanced/globalization-for-wpf.md) o <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>
- <xref:Microsoft.Build.Tasks.Windows.UidManager>
- [Globalizzazione per WPF](../framework/wpf/advanced/globalization-for-wpf.md)

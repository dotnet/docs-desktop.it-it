---
title: Direttiva x:FieldModifier
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 3c27ffb6ba190c694926ea45a44ab4fb35564e90
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961039"
---
# <a name="xfieldmodifier-directive"></a>Direttiva x:FieldModifier
Modifica il comportamento di compilazione XAML in modo che i campi per i riferimenti a oggetti denominati siano definiti con <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> Access anziché con il <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> comportamento predefinito.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object x:FieldModifier="Public".../>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|*Pubblica*|La stringa esatta passata per specificare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> anziché <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varia a seconda del linguaggio di programmazione code-behind usato. Vedere la sezione Osservazioni.|

## <a name="dependencies"></a>Dependencies

 Se in un ambiente di produzione XAML viene utilizzato `x:FieldModifier` Anywhere, l'elemento radice di tale produzione XAML deve dichiarare una [direttiva x:Class](xclass-directive.md).

## <a name="remarks"></a>Osservazioni

`x:FieldModifier` non è pertinente per dichiarare il livello di accesso generale di una classe o dei relativi membri. È pertinente solo per il comportamento di elaborazione XAML quando un particolare oggetto XAML che fa parte di un ambiente di produzione XAML viene elaborato e diventa un oggetto potenzialmente accessibile nell'oggetto grafico di un'applicazione. Per impostazione predefinita, il riferimento al campo per un oggetto di questo tipo viene mantenuto privato, impedendo ai consumer di controlli di modificare direttamente l'oggetto grafico. Al contrario, gli utenti del controllo dovrebbero modificare l'oggetto grafico utilizzando modelli standard abilitati dai modelli di programmazione, ad esempio ottenendo la radice del layout, le raccolte di elementi figlio, le proprietà pubbliche dedicate e così via.

Il valore dell' `x:FieldModifier` attributo varia in base al linguaggio di programmazione e il suo scopo può variare in Framework specifici. La stringa da usare dipende dal modo in cui ogni linguaggio implementa i <xref:System.CodeDom.Compiler.CodeDomProvider> convertitori di tipi che restituisce per definire i significati per <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> e <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> e se tale lingua fa distinzione tra maiuscole e minuscole.

- Per C#, la stringa da passare a designare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> è `public` .

- Per Microsoft Visual Basic .NET, la stringa da passare a designare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> è `Public` .

- Per C++/CLI, attualmente non esiste alcuna destinazione per XAML. Pertanto, la stringa da passare non è definita.

È anche possibile specificare <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ( `internal` in C#, `Friend` in Visual Basic) ma specificare <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> è insolito perché `NotPublic` il comportamento è già quello predefinito.

<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> è il comportamento predefinito perché non è frequente che il codice esterno all'assembly in cui è stato compilato il codice XAML debba accedere a un elemento creato da XAML. L'architettura della sicurezza WPF con il comportamento di compilazione XAML non dichiarerà i campi che archiviano le istanze dell'elemento come Public, a meno che non si imposti specificamente `x:FieldModifier` per consentire l'accesso pubblico.

`x:FieldModifier` è pertinente solo per gli elementi con [direttiva x:Name](xname-directive.md) perché tale nome viene utilizzato per fare riferimento al campo dopo che è pubblico.

Per impostazione predefinita, la classe parziale per l'elemento radice è Public; Tuttavia, è possibile renderlo non pubblico usando la [direttiva x:ClassModifier](xclassmodifier-directive.md). La [direttiva x:ClassModifier](xclassmodifier-directive.md) influisca anche sul livello di accesso dell'istanza della classe dell'elemento radice. È possibile inserire sia sia nell' `x:Name` `x:FieldModifier` elemento radice, ma si tratta solo di una copia di campo pubblica dell'elemento radice, con il livello di accesso della classe di elementi radice true ancora controllato dalla [direttiva x:ClassModifier](xclassmodifier-directive.md).

## <a name="see-also"></a>Vedere anche

- [Classi XAML e personalizzate per WPF](../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [Code-behind e XAML in WPF](../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Direttiva x:Name](xname-directive.md)
- [Compilazione di un'applicazione WPF (WPF)](../framework/wpf/app-development/building-a-wpf-application-wpf.md)
- [Direttiva x:ClassModifier](xclassmodifier-directive.md)

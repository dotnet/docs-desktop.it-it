---
title: Direttiva x:ClassModifier
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: 2d795ad1caa766d21ea98e5a97c98304067cbef1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961078"
---
# <a name="xclassmodifier-directive"></a>Direttiva x:ClassModifier

Modifica il comportamento di compilazione XAML quando `x:Class` viene fornito anche. In particolare, anziché creare un oggetto parziale `class` `Public` con livello di accesso (impostazione predefinita), l'oggetto fornito `x:Class` viene creato con un `NotPublic` livello di accesso. Questo comportamento influiscono sul livello di accesso per la classe negli assembly generati.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|*NotPublic*|La stringa esatta da passare per specificare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> e varia a seconda del linguaggio di programmazione code-behind usato. Vedere la sezione Osservazioni.|

## <a name="dependencies"></a>Dependencies

è necessario fornire anche [x:Class](xclass-directive.md) sullo stesso elemento e tale elemento deve essere l'elemento radice in una pagina. Per ulteriori informazioni, vedere la [ \[ sezione MS-XAML \] 4.3.1.8](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="remarks"></a>Osservazioni

Il valore di `x:ClassModifier` nell'utilizzo dei servizi XAML .NET varia in base al linguaggio di programmazione. La stringa da usare dipende dal modo in cui ogni linguaggio implementa i <xref:System.CodeDom.Compiler.CodeDomProvider> convertitori di tipi che restituisce per definire i significati per <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> e <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> e se tale lingua fa distinzione tra maiuscole e minuscole.

- Per C#, la stringa da passare a designare <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> è `internal` .

- Per Microsoft Visual Basic .NET, la stringa da passare a designare <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> è `Friend` .

- Per C++/CLI, non esistono destinazioni che supportano la compilazione di XAML. Pertanto, il valore da passare non è specificato.

È anche possibile specificare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ( `public` in C#, `Public` in Visual Basic). Tuttavia, l'impostazione di <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> viene eseguita raramente perché <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> è già il comportamento predefinito.

Altri valori con restrizioni a livello di accesso del codice utente equivalente, ad esempio `private` in C#, non sono rilevanti per `x:ClassModifier` perché i riferimenti a classi annidate non sono supportati in XAML e pertanto il <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modificatore ha lo stesso effetto.

## <a name="security-notes"></a>Note sulla sicurezza

Il livello di accesso dichiarato in `x:ClassModifier` è ancora soggetto all'interpretazione da parte di framework specifici e alle relative funzionalità. WPF include funzionalità per caricare e creare istanze di tipi in cui `x:ClassModifier` è `internal` , se a tale classe viene fatto riferimento da una risorsa WPF tramite un riferimento URI di tipo pack. Come conseguenza di questo caso e potenzialmente altri come implementati da altri Framework, non si basano esclusivamente su `x:ClassModifier` per bloccare tutti i possibili tentativi di creazione di istanze.

## <a name="see-also"></a>Vedere anche

- [Direttiva x:Class](xclass-directive.md)
- [Code-behind e XAML in WPF](../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Direttiva x:FieldModifier](xfieldmodifier-directive.md)
- [Sicurezza (WPF)](../framework/wpf/security-wpf.md)
- [Tipi migrati da WPF a System.Xaml](../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)

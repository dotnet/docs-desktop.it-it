---
title: Direttiva x:Subclass
ms.date: 03/30/2017
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
ms.openlocfilehash: 5da3634ac05b4f6a3825dae87e361003518b0830
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969589"
---
# <a name="xsubclass-directive"></a>Direttiva x:Subclass

Modifica il comportamento di compilazione del markup XAML quando `x:Class` viene fornito anche. Anziché creare una classe parziale basata su `x:Class` , l'oggetto fornito `x:Class` viene creato come classe intermedia, quindi la classe derivata fornita dovrebbe essere basata su `x:Class` .

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">
   ...
</object>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|`namespace`|facoltativo. Specifica uno spazio dei nomi CLR che contiene `classname` . Se `namespace` si specifica, un punto (.) separa `namespace` e `classname` .|
|`classname`|Obbligatorio. Specifica il nome CLR della classe parziale che connette il codice XAML caricato e il code-behind per il codice XAML. Vedere la sezione Osservazioni.|
|`subclassNamespace`|facoltativo. Può essere diverso da `namespace` se ogni spazio dei nomi può risolvere l'altro. Specifica uno spazio dei nomi CLR che contiene `subclassName` . Se `subclassName` si specifica, un punto (.) separa `subclassNamespace` e `subclassName` .|
|`subclassName`|Obbligatorio. Specifica il nome CLR della sottoclasse.|

## <a name="dependencies"></a>Dependencies

è necessario fornire anche la [direttiva x:Class](xclass-directive.md) sullo stesso oggetto e tale oggetto deve essere l'elemento radice dell'ambiente di produzione XAML.

## <a name="remarks"></a>Osservazioni

`x:Subclass` l'utilizzo è destinato principalmente a linguaggi che non supportano dichiarazioni di classe parziali.

La classe utilizzata come `x:Subclass` non può essere una classe annidata e `x:Subclass` deve fare riferimento all'oggetto radice come illustrato nella sezione "dipendenze".

In caso contrario, il significato concettuale di non `x:Subclass` è definito da un'implementazione dei servizi XAML .NET. Questo perché il comportamento dei servizi XAML .NET non specifica il modello di programmazione generale in base al quale sono connessi il markup XAML e il codice di supporto. Le implementazioni di altri concetti correlati a `x:Class` e `x:Subclass` vengono eseguite da framework specifici che usano modelli di programmazione o modelli di applicazione per definire come connettere markup XAML, markup compilato e code-behind basato su CLR. Ogni Framework potrebbe disporre di proprie azioni di compilazione che abilitano parte del comportamento o componenti specifici che devono essere inclusi nell'ambiente di compilazione. All'interno di un Framework, le azioni di compilazione possono variare anche in base al linguaggio CLR specifico usato per il code-behind.

## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF

`x:Subclass` può trovarsi in una radice della pagina o nella <xref:System.Windows.Application> radice nella definizione dell'applicazione, che ha già `x:Class` . La Dichiarazione `x:Subclass` di qualsiasi elemento diverso dalla radice di una pagina o di un'applicazione o di specificarla laddove non `x:Class` esiste, causa un errore in fase di compilazione.

La creazione di classi derivate che funzionano correttamente per lo `x:Subclass` scenario è piuttosto complessa. Potrebbe essere necessario esaminare i file intermedi, ovvero i file. g prodotti nella cartella obj del progetto tramite il markup Compile, con i nomi che incorporano i nomi di file con estensione XAML. Questi file intermedi consentono di determinare l'origine di determinati costrutti di programmazione nelle classi parziali unite in join nell'applicazione compilata.

I gestori eventi nella classe derivata devono essere `internal override` ( `Friend Overrides` in Microsoft Visual Basic) per eseguire l'override degli stub per i gestori creati nella classe intermedia durante la compilazione. In caso contrario, le implementazioni della classe derivata nascondono (ombreggiatura) l'implementazione della classe intermedia e i gestori della classe intermedia non vengono richiamati.

Quando si definiscono sia `x:Class` che `x:Subclass` , non è necessario fornire alcuna implementazione per la classe a cui fa riferimento `x:Class` . È sufficiente assegnare un nome tramite l' `x:Class` attributo, in modo che il compilatore abbia alcune linee guida per la classe creata nei file intermedi. in questo caso il compilatore non seleziona un nome predefinito. È possibile assegnare alla `x:Class` classe un'implementazione. Tuttavia, questo non è lo scenario tipico per l'utilizzo di `x:Class` e `x:Subclass` .

## <a name="see-also"></a>Vedere anche

- [Direttiva x:Class](xclass-directive.md)
- [Classi XAML e personalizzate per WPF](../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)

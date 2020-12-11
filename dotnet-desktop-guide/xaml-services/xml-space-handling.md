---
title: Gestione di xml:space in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: b05fb396850316c76721c72276ebb97f7e805ed3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961021"
---
# <a name="xmlspace-handling-in-xaml"></a>Gestione di xml:space in XAML

L' `xml:space` attributo è un attributo definito da XML che dichiara il comportamento di elaborazione degli spazi vuoti significativo all'interno di un elemento oggetto. Questo comportamento è pertinente per tutto il contenuto (testo interno) contenuto all'interno dell'elemento in cui `xml:space` è dichiarato e anche gli ambiti degli elementi figlio.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object xml:space="preserve" />
```

 \- - oppure -

```xaml
<object xml:space="default" />
```

## <a name="remarks"></a>Osservazioni

La definizione per l' `xml:space` attributo in XAML, inclusi i due valori possibili, deriva da `xml:space` come definito come "attributo speciale" dalle specifiche W3C per XML.

Il valore predefinito dell' `xml:space` attributo è il valore letterale `"default"` . Per il valore `"default"` , o se `xml:space` non è indicato, il comportamento di analisi dello spazio vuoto significative è la gestione predefinita, come definito nell'argomento [elaborazione di spazi vuoti in XAML](white-space-processing.md).

Per mantenere lo spazio vuoto all'interno del contenuto dell'elemento oggetto, specificare `xml:space="preserve"` su tale elemento oggetto.

Nella maggior parte delle interpretazioni gli `xml:space` effetti degli attributi e il valore dell'attributo hanno come ambito gli elementi figlio.

Per una descrizione completa dell'elaborazione di spazi vuoti in XAML, vedere [elaborazione di spazi vuoti in XAML](white-space-processing.md).

## <a name="see-also"></a>Vedere anche

- [Elaborazione degli spazi vuoti in XAML](white-space-processing.md)
- [Panoramica di XAML (WPF)](../net/wpf/fundamentals/xaml.md)

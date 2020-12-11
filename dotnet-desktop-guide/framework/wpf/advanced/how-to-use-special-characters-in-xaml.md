---
title: 'Procedura: Usare caratteri speciali in XAML'
description: Informazioni sulla sintassi per la codifica di caratteri speciali in formato di file UTF-8 Unicode in Visual Studio per l'uso nei file XAML in Windows Presentation Foundation.
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: b627f7ee1d6ab80d5d1cd14de0339a1afad3ec62
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968698"
---
# <a name="how-to-use-special-characters-in-xaml"></a>Procedura: Usare caratteri speciali in XAML
I file di markup creati in Visual Studio vengono salvati automaticamente nel formato di file UTF-8 Unicode, il che significa che la maggior parte dei caratteri speciali, ad esempio i contrassegni accentati, sono codificati correttamente. Tuttavia, esiste un set di caratteri speciali di uso comune che viene gestito diversamente. Questi caratteri speciali seguono lo [standard XML W3C (World Wide Web Consortium) per la codifica](https://www.w3resource.com/xml/reserved-markup-characters.php).

La tabella seguente illustra la sintassi per la codifica di questo set di caratteri speciali:

| Carattere | Sintassi   | Descrizione          |
|-----------|----------|----------------------|
| `<`       | `&lt;`   | Simbolo minore di.    |
| `>`       | `&gt;`   | Simbolo maggiore di.   |
| `&`       | `&amp;`  | Simbolo e commerciale.    |
| `"`       | `&quot;` | Simbolo virgoletta doppia. |
| `'`       | `&apos;` | Simbolo virgoletta singola. |

> [!NOTE]
> Se si crea un file di markup usando un editor di testo, ad esempio Blocco note di Windows, è necessario salvare il file nel formato di file UTF-8 Unicode per mantenere i caratteri speciali codificati.

L'esempio riportato di seguito mostra come usare i caratteri speciali nel testo durante la creazione del markup.

## <a name="example"></a>Esempio

[!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]

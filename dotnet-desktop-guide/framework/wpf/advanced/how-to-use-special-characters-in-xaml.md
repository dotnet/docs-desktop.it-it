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
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="37183-103">Procedura: Usare caratteri speciali in XAML</span><span class="sxs-lookup"><span data-stu-id="37183-103">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="37183-104">I file di markup creati in Visual Studio vengono salvati automaticamente nel formato di file UTF-8 Unicode, il che significa che la maggior parte dei caratteri speciali, ad esempio i contrassegni accentati, sono codificati correttamente.</span><span class="sxs-lookup"><span data-stu-id="37183-104">Markup files that are created in Visual Studio are automatically saved in the Unicode UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="37183-105">Tuttavia, esiste un set di caratteri speciali di uso comune che viene gestito diversamente.</span><span class="sxs-lookup"><span data-stu-id="37183-105">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="37183-106">Questi caratteri speciali seguono lo [standard XML W3C (World Wide Web Consortium) per la codifica](https://www.w3resource.com/xml/reserved-markup-characters.php).</span><span class="sxs-lookup"><span data-stu-id="37183-106">These special characters follow the World [Wide Web Consortium (W3C) XML standard for encoding](https://www.w3resource.com/xml/reserved-markup-characters.php).</span></span>

<span data-ttu-id="37183-107">La tabella seguente illustra la sintassi per la codifica di questo set di caratteri speciali:</span><span class="sxs-lookup"><span data-stu-id="37183-107">The following table shows the syntax for encoding this set of special characters:</span></span>

| <span data-ttu-id="37183-108">Carattere</span><span class="sxs-lookup"><span data-stu-id="37183-108">Character</span></span> | <span data-ttu-id="37183-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="37183-109">Syntax</span></span>   | <span data-ttu-id="37183-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37183-110">Description</span></span>          |
|-----------|----------|----------------------|
| `<`       | `&lt;`   | <span data-ttu-id="37183-111">Simbolo minore di.</span><span class="sxs-lookup"><span data-stu-id="37183-111">Less than symbol.</span></span>    |
| `>`       | `&gt;`   | <span data-ttu-id="37183-112">Simbolo maggiore di.</span><span class="sxs-lookup"><span data-stu-id="37183-112">Greater than sign.</span></span>   |
| `&`       | `&amp;`  | <span data-ttu-id="37183-113">Simbolo e commerciale.</span><span class="sxs-lookup"><span data-stu-id="37183-113">Ampersand symbol.</span></span>    |
| `"`       | `&quot;` | <span data-ttu-id="37183-114">Simbolo virgoletta doppia.</span><span class="sxs-lookup"><span data-stu-id="37183-114">Double quote symbol.</span></span> |
| `'`       | `&apos;` | <span data-ttu-id="37183-115">Simbolo virgoletta singola.</span><span class="sxs-lookup"><span data-stu-id="37183-115">Single quote symbol.</span></span> |

> [!NOTE]
> <span data-ttu-id="37183-116">Se si crea un file di markup usando un editor di testo, ad esempio Blocco note di Windows, è necessario salvare il file nel formato di file UTF-8 Unicode per mantenere i caratteri speciali codificati.</span><span class="sxs-lookup"><span data-stu-id="37183-116">If you create a markup file using a text editor, such as Windows Notepad, you must save the file in the Unicode UTF-8 file format in order to preserve any encoded special characters.</span></span>

<span data-ttu-id="37183-117">L'esempio riportato di seguito mostra come usare i caratteri speciali nel testo durante la creazione del markup.</span><span class="sxs-lookup"><span data-stu-id="37183-117">The following example shows how you can use special characters in text when creating markup.</span></span>

## <a name="example"></a><span data-ttu-id="37183-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="37183-118">Example</span></span>

[!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]

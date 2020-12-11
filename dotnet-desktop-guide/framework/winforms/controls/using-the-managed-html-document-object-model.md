---
title: Utilizzare il Document Object Model HTML gestito
ms.date: 03/30/2017
helpviewer_keywords:
- managed HTML DOM
ms.assetid: a017dd5c-cd7b-47e4-952c-f4f54cb48409
ms.openlocfilehash: fe84cabfaabdc14c7dec6cb69653d41b4c6f6416
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966691"
---
# <a name="using-the-managed-html-document-object-model"></a><span data-ttu-id="18e63-102">Utilizzare il Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="18e63-102">Using the Managed HTML Document Object Model</span></span>
<span data-ttu-id="18e63-103">Il DOM (Document Object Model) HTML gestito fornisce un wrapper basato sul .NET Framework per le classi HTML esposte da Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="18e63-103">The managed HTML document object model (DOM) provides a wrapper based on the .NET Framework for the HTML classes exposed by Internet Explorer.</span></span> <span data-ttu-id="18e63-104">Usare queste classi per modificare le pagine HTML ospitate nel <xref:System.Windows.Forms.WebBrowser> controllo o per creare nuove pagine dall'inizio.</span><span class="sxs-lookup"><span data-stu-id="18e63-104">Use these classes to manipulate HTML pages hosted in the <xref:System.Windows.Forms.WebBrowser> control, or to build new pages from the beginning.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="18e63-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="18e63-105">In This Section</span></span>  
 [<span data-ttu-id="18e63-106">Procedura: Accedere al Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="18e63-106">How to: Access the Managed HTML Document Object Model</span></span>](how-to-access-the-managed-html-document-object-model.md)  
 <span data-ttu-id="18e63-107">Viene descritto come ottenere un'istanza valida di <xref:System.Windows.Forms.HtmlDocument> da un Windows Forms Application o da un <xref:System.Windows.Forms.UserControl> ospitato in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="18e63-107">Describes how to obtain a valid instance of <xref:System.Windows.Forms.HtmlDocument> from either a Windows Forms application or a <xref:System.Windows.Forms.UserControl> hosted in Internet Explorer.</span></span>  
  
 [<span data-ttu-id="18e63-108">Procedura: Accedere all'origine HTML nel Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="18e63-108">How to: Access the HTML Source in the Managed HTML Document Object Model</span></span>](how-to-access-the-html-source-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="18e63-109">Viene descritto come ottenere l'origine HTML originale, non modificata e come ottenere l'origine "attiva" che riflette lo stato corrente del DOM.</span><span class="sxs-lookup"><span data-stu-id="18e63-109">Describes how to obtain the original, unmodified HTML source, and how to obtain the "live" source that reflects the current state of the DOM.</span></span>  
  
 [<span data-ttu-id="18e63-110">Procedura: Modificare gli stili di un elemento nel Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="18e63-110">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>](how-to-change-styles-on-an-element-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="18e63-111">Viene descritto come modificare gli stili, che vengono usati per controllare la visualizzazione degli elementi visivi.</span><span class="sxs-lookup"><span data-stu-id="18e63-111">Describes how to manipulate styles, which are used to control the visual display of elements.</span></span>  
  
 [<span data-ttu-id="18e63-112">Accesso a frame nel Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="18e63-112">Accessing Frames in the Managed HTML Document Object Model</span></span>](accessing-frames-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="18e63-113">Descrive quali frame e frame sono e come accedere al DOM di un frame.</span><span class="sxs-lookup"><span data-stu-id="18e63-113">Describes what frames and framesets are, and how to access the DOM of a frame.</span></span>  
  
 [<span data-ttu-id="18e63-114">Accesso ai membri non esposti del Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="18e63-114">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>](accessing-unexposed-members-on-the-managed-html-document-object-model.md)  
 <span data-ttu-id="18e63-115">Viene descritto come accedere ai membri del DOM sottostante che non dispongono di un equivalente gestito.</span><span class="sxs-lookup"><span data-stu-id="18e63-115">Describes how to access members of the underlying DOM that do not have a managed equivalent.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="18e63-116">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="18e63-116">Reference</span></span>  
 <xref:System.Windows.Forms.HtmlDocument>  
  
 <xref:System.Windows.Forms.HtmlElement>  
  
 <xref:System.Windows.Forms.HtmlWindow>  
  
## <a name="related-sections"></a><span data-ttu-id="18e63-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="18e63-117">Related Sections</span></span>  
 [<span data-ttu-id="18e63-118">Controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="18e63-118">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)  

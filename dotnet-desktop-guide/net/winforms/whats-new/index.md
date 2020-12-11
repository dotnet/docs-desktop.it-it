---
title: Novità di Windows Forms
description: Informazioni sulle novità di Windows Forms per .NET. Windows Forms. .NET fornisce nuove funzionalità e miglioramenti rispetto a .NET Framework.
ms.date: 11/05/2020
ms.topic: conceptual
ms.openlocfilehash: 5c22fdd2df68cd59b7bc0b93c6aa7223bdf06ec0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966007"
---
# <a name="whats-new-windows-forms-net"></a><span data-ttu-id="b6936-105">Novità (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="b6936-105">What's new (Windows Forms .NET)</span></span>

<span data-ttu-id="b6936-106">Windows Forms per .NET 5,0 aggiunge le funzionalità e i miglioramenti seguenti rispetto a .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b6936-106">Windows Forms for .NET 5.0 adds the following features and enhancements over .NET Framework.</span></span>

<span data-ttu-id="b6936-107">Quando si esegue la migrazione da .NET Framework a .NET 5,0, è necessario tenere presenti alcune modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="b6936-107">There are a few breaking changes you should be aware of when migrating from .NET Framework to .NET 5.0.</span></span> <span data-ttu-id="b6936-108">Per ulteriori informazioni, vedere [modifiche di rilievo nelle Windows Forms](/dotnet/core/compatibility/winforms).</span><span class="sxs-lookup"><span data-stu-id="b6936-108">For more information, see [Breaking changes in Windows Forms](/dotnet/core/compatibility/winforms).</span></span>

## <a name="enhanced-features"></a><span data-ttu-id="b6936-109">Funzionalità avanzate</span><span class="sxs-lookup"><span data-stu-id="b6936-109">Enhanced features</span></span>

- <span data-ttu-id="b6936-110">I modelli di automazione interfaccia utente Microsoft funzionano meglio con strumenti di accessibilità come assistente vocale e Jaws.</span><span class="sxs-lookup"><span data-stu-id="b6936-110">Microsoft UI Automation patterns work better with accessibility tools like Narrator and Jaws.</span></span>
- <span data-ttu-id="b6936-111">Prestazioni migliorate.</span><span class="sxs-lookup"><span data-stu-id="b6936-111">Improved performance.</span></span>
- <span data-ttu-id="b6936-112">Il modello di progetto VB.NET per impostazione predefinita è DPI impostazioni SystemAware per risoluzioni DPI elevate, ad esempio i monitoraggi 4K.</span><span class="sxs-lookup"><span data-stu-id="b6936-112">The VB.NET project template defaults to DPI SystemAware settings for high DPI resolutions such as 4k monitors.</span></span>
- <span data-ttu-id="b6936-113">Il tipo di carattere predefinito corrisponde alle indicazioni di progettazione di Windows correnti.</span><span class="sxs-lookup"><span data-stu-id="b6936-113">The default font matches the current Windows design recommendations.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="b6936-114">Questo può influisca sul layout delle app migrate da .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b6936-114">This may impact the layout of apps migrated from .NET Framework.</span></span>

## <a name="new-controls"></a><span data-ttu-id="b6936-115">Nuovi controlli</span><span class="sxs-lookup"><span data-stu-id="b6936-115">New controls</span></span>

<span data-ttu-id="b6936-116">Sono stati aggiunti i controlli seguenti poiché Windows Forms stato trasferito a .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b6936-116">The following controls have been added since Windows Forms was ported to .NET Framework:</span></span>

- <xref:System.Windows.Forms.TaskDialog?displayProperty=fullName>
  
  <span data-ttu-id="b6936-117">Una finestra di dialogo attività è una finestra di dialogo che può essere usata per visualizzare le informazioni e ricevere input semplice dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b6936-117">A task dialog is a dialog box that can be used to display information and receive simple input from the user.</span></span> <span data-ttu-id="b6936-118">Analogamente a una finestra di messaggio, viene formattata dal sistema operativo in base ai parametri impostati.</span><span class="sxs-lookup"><span data-stu-id="b6936-118">Like a message box, it's formatted by the operating system according to parameters you set.</span></span> <span data-ttu-id="b6936-119">La finestra di dialogo attività dispone di più funzionalità rispetto a una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="b6936-119">Task dialog has more features than a message box.</span></span> <span data-ttu-id="b6936-120">Per ulteriori informazioni, vedere l' [esempio di finestra di dialogo attività](https://github.com/dotnet/samples/tree/master/windowsforms/TaskDialogDemo).</span><span class="sxs-lookup"><span data-stu-id="b6936-120">For more information, see the [Task dialog sample](https://github.com/dotnet/samples/tree/master/windowsforms/TaskDialogDemo).</span></span>

- <xref:Microsoft.Web.WebView2.WinForms.WebView2?displayProperty=fullName>

  <span data-ttu-id="b6936-121">Un nuovo controllo Web browser con supporto Web moderno.</span><span class="sxs-lookup"><span data-stu-id="b6936-121">A new web browser control with modern web support.</span></span> <span data-ttu-id="b6936-122">Basato su Edge (cromo).</span><span class="sxs-lookup"><span data-stu-id="b6936-122">Based on Edge (Chromium).</span></span> <span data-ttu-id="b6936-123">Per altre informazioni, vedere [Introduzione a WebView2 in Windows Forms](/microsoft-edge/webview2/gettingstarted/winforms).</span><span class="sxs-lookup"><span data-stu-id="b6936-123">For more information, see [Getting started with WebView2 in Windows Forms](/microsoft-edge/webview2/gettingstarted/winforms).</span></span>

## <a name="enhanced-controls"></a><span data-ttu-id="b6936-124">Controlli avanzati</span><span class="sxs-lookup"><span data-stu-id="b6936-124">Enhanced controls</span></span>

- <xref:System.Windows.Forms.ListView?displayProperty=fullName>

  - <span data-ttu-id="b6936-125">Supporta gruppi comprimibili</span><span class="sxs-lookup"><span data-stu-id="b6936-125">Supports collapsible groups</span></span>
  - <span data-ttu-id="b6936-126">Piè</span><span class="sxs-lookup"><span data-stu-id="b6936-126">Footers</span></span>
  - <span data-ttu-id="b6936-127">Immagini di sottotitolo, attività e titolo del gruppo</span><span class="sxs-lookup"><span data-stu-id="b6936-127">Group subtitle, task, and title images</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog?displayProperty=fullName>

  <span data-ttu-id="b6936-128">Questa finestra di dialogo è stata aggiornata in modo da usare l'esperienza Windows moderna anziché quella precedente di Windows 7.</span><span class="sxs-lookup"><span data-stu-id="b6936-128">This dialog has been upgraded to use the modern Windows experience instead of the old Windows 7 experience.</span></span>

- <xref:System.Windows.Forms.FileDialog?displayProperty=fullName>

  - <span data-ttu-id="b6936-129">Aggiunta del supporto per <xref:System.Windows.Forms.FileDialog.ClientGuid> .</span><span class="sxs-lookup"><span data-stu-id="b6936-129">Added support for <xref:System.Windows.Forms.FileDialog.ClientGuid>.</span></span>

    <span data-ttu-id="b6936-130">`ClientGuid` consente a un'applicazione chiamante di associare un GUID a uno stato permanente della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b6936-130">`ClientGuid` enables a calling application to associate a GUID with a dialog's persisted state.</span></span> <span data-ttu-id="b6936-131">Lo stato di una finestra di dialogo può includere fattori quali l'ultima cartella visitata e la posizione e le dimensioni della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b6936-131">A dialog's state can include factors such as the last visited folder and the position and size of the dialog.</span></span> <span data-ttu-id="b6936-132">In genere, questo stato viene reso permanente in base al nome del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="b6936-132">Typically, this state is persisted based on the name of the executable file.</span></span> <span data-ttu-id="b6936-133">Con `ClientGuid` , un'applicazione può salvare in modo permanente diversi Stati della finestra di dialogo all'interno della stessa applicazione.</span><span class="sxs-lookup"><span data-stu-id="b6936-133">With `ClientGuid`, an application can persist  different states of the dialog within the same application.</span></span>

- <xref:System.Windows.Forms.TextRenderer?displayProperty=fullName>

  <span data-ttu-id="b6936-134">Aggiunto il supporto per per <xref:System.ReadOnlySpan%601> migliorare le prestazioni di rendering del testo.</span><span class="sxs-lookup"><span data-stu-id="b6936-134">Support added for <xref:System.ReadOnlySpan%601> to enhance performance of rendering text.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6936-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6936-135">See also</span></span>

- [<span data-ttu-id="b6936-136">Modifiche di rilievo in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b6936-136">Breaking changes in Windows Forms</span></span>](/dotnet/core/compatibility/winforms)
- [<span data-ttu-id="b6936-137">Esercitazione: creare una nuova app WinForms (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="b6936-137">Tutorial: Create a new WinForms app (Windows Forms .NET)</span></span>](../get-started/create-app-visual-studio.md)
- [<span data-ttu-id="b6936-138">Come eseguire la migrazione di un'app desktop Windows Forms a .NET 5</span><span class="sxs-lookup"><span data-stu-id="b6936-138">How to migrate a Windows Forms desktop app to .NET 5</span></span>](../migration/index.md)

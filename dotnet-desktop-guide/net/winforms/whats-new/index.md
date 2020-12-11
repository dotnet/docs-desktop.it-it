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
# <a name="whats-new-windows-forms-net"></a>Novità (Windows Forms .NET)

Windows Forms per .NET 5,0 aggiunge le funzionalità e i miglioramenti seguenti rispetto a .NET Framework.

Quando si esegue la migrazione da .NET Framework a .NET 5,0, è necessario tenere presenti alcune modifiche di rilievo. Per ulteriori informazioni, vedere [modifiche di rilievo nelle Windows Forms](/dotnet/core/compatibility/winforms).

## <a name="enhanced-features"></a>Funzionalità avanzate

- I modelli di automazione interfaccia utente Microsoft funzionano meglio con strumenti di accessibilità come assistente vocale e Jaws.
- Prestazioni migliorate.
- Il modello di progetto VB.NET per impostazione predefinita è DPI impostazioni SystemAware per risoluzioni DPI elevate, ad esempio i monitoraggi 4K.
- Il tipo di carattere predefinito corrisponde alle indicazioni di progettazione di Windows correnti.

  > [!CAUTION]
  > Questo può influisca sul layout delle app migrate da .NET Framework.

## <a name="new-controls"></a>Nuovi controlli

Sono stati aggiunti i controlli seguenti poiché Windows Forms stato trasferito a .NET Framework:

- <xref:System.Windows.Forms.TaskDialog?displayProperty=fullName>
  
  Una finestra di dialogo attività è una finestra di dialogo che può essere usata per visualizzare le informazioni e ricevere input semplice dall'utente. Analogamente a una finestra di messaggio, viene formattata dal sistema operativo in base ai parametri impostati. La finestra di dialogo attività dispone di più funzionalità rispetto a una finestra di messaggio. Per ulteriori informazioni, vedere l' [esempio di finestra di dialogo attività](https://github.com/dotnet/samples/tree/master/windowsforms/TaskDialogDemo).

- <xref:Microsoft.Web.WebView2.WinForms.WebView2?displayProperty=fullName>

  Un nuovo controllo Web browser con supporto Web moderno. Basato su Edge (cromo). Per altre informazioni, vedere [Introduzione a WebView2 in Windows Forms](/microsoft-edge/webview2/gettingstarted/winforms).

## <a name="enhanced-controls"></a>Controlli avanzati

- <xref:System.Windows.Forms.ListView?displayProperty=fullName>

  - Supporta gruppi comprimibili
  - Piè
  - Immagini di sottotitolo, attività e titolo del gruppo

- <xref:System.Windows.Forms.FolderBrowserDialog?displayProperty=fullName>

  Questa finestra di dialogo è stata aggiornata in modo da usare l'esperienza Windows moderna anziché quella precedente di Windows 7.

- <xref:System.Windows.Forms.FileDialog?displayProperty=fullName>

  - Aggiunta del supporto per <xref:System.Windows.Forms.FileDialog.ClientGuid> .

    `ClientGuid` consente a un'applicazione chiamante di associare un GUID a uno stato permanente della finestra di dialogo. Lo stato di una finestra di dialogo può includere fattori quali l'ultima cartella visitata e la posizione e le dimensioni della finestra di dialogo. In genere, questo stato viene reso permanente in base al nome del file eseguibile. Con `ClientGuid` , un'applicazione può salvare in modo permanente diversi Stati della finestra di dialogo all'interno della stessa applicazione.

- <xref:System.Windows.Forms.TextRenderer?displayProperty=fullName>

  Aggiunto il supporto per per <xref:System.ReadOnlySpan%601> migliorare le prestazioni di rendering del testo.

## <a name="see-also"></a>Vedere anche

- [Modifiche di rilievo in Windows Forms](/dotnet/core/compatibility/winforms)
- [Esercitazione: creare una nuova app WinForms (Windows Forms .NET)](../get-started/create-app-visual-studio.md)
- [Come eseguire la migrazione di un'app desktop Windows Forms a .NET 5](../migration/index.md)

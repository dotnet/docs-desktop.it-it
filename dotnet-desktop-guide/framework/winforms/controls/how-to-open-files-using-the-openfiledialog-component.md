---
title: 'Procedura: aprire file con il componente OpenFileDialog'
ms.date: 02/11/2019
description: Informazioni su come utilizzare il componente OpenFileDialog per aprire la finestra di dialogo Windows per l'esplorazione e la selezione dei file.
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: 7021aacf09d7d927322abf1c9aa883bbb29507a8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952080"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a><span data-ttu-id="704b1-103">Procedura: aprire file con OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="704b1-103">How to: Open files with the OpenFileDialog</span></span>

<span data-ttu-id="704b1-104">Il <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> componente apre la finestra di dialogo di Windows per l'esplorazione e la selezione dei file.</span><span class="sxs-lookup"><span data-stu-id="704b1-104">The <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> component opens the Windows dialog box for browsing and selecting files.</span></span> <span data-ttu-id="704b1-105">Per aprire e leggere i file selezionati, è possibile usare il <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> metodo o creare un'istanza della <xref:System.IO.StreamReader?displayProperty=nameWithType> classe.</span><span class="sxs-lookup"><span data-stu-id="704b1-105">To open and read the selected files, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> method, or create an instance of the <xref:System.IO.StreamReader?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="704b1-106">Negli esempi seguenti vengono illustrati entrambi gli approcci.</span><span class="sxs-lookup"><span data-stu-id="704b1-106">The following examples show both approaches.</span></span>

<span data-ttu-id="704b1-107">In .NET Framework per ottenere o impostare la <xref:System.Windows.Forms.FileDialog.FileName%2A> proprietà è necessario un livello di privilegio concesso dalla <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> classe.</span><span class="sxs-lookup"><span data-stu-id="704b1-107">In .NET Framework, to get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="704b1-108">Gli esempi eseguono un <xref:System.Security.Permissions.FileIOPermission> controllo delle autorizzazioni e possono generare un'eccezione a causa di privilegi insufficienti se vengono eseguiti in un contesto parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="704b1-108">The examples run a <xref:System.Security.Permissions.FileIOPermission> permission check, and can throw an exception due to insufficient privileges if run in a partial-trust context.</span></span> <span data-ttu-id="704b1-109">Per altre informazioni, vedere [nozioni di base sulla sicurezza dall'accesso di codice](/dotnet/framework/misc/code-access-security-basics).</span><span class="sxs-lookup"><span data-stu-id="704b1-109">For more information, see [Code access security basics](/dotnet/framework/misc/code-access-security-basics).</span></span>

<span data-ttu-id="704b1-110">È possibile compilare ed eseguire questi esempi come app .NET Framework dalla riga di comando C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="704b1-110">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="704b1-111">Per ulteriori informazioni, vedere compilazione dalla [riga di comando con csc.exe](/dotnet/csharp/language-reference/compiler-options/command-line-building-with-csc-exe) o [compilazione dalla riga di comando](/dotnet/visual-basic/reference/command-line-compiler/building-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="704b1-111">For more information, see [Command-line building with csc.exe](/dotnet/csharp/language-reference/compiler-options/command-line-building-with-csc-exe) or [Build from the command line](/dotnet/visual-basic/reference/command-line-compiler/building-from-the-command-line).</span></span>

<span data-ttu-id="704b1-112">A partire da .NET Core 3,0, è anche possibile compilare ed eseguire gli esempi come app di Windows .NET Core da una cartella che contiene un file di progetto .NET Core Windows Forms *\<folder name> . csproj* .</span><span class="sxs-lookup"><span data-stu-id="704b1-112">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span>

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a><span data-ttu-id="704b1-113">Esempio: leggere un file come flusso con StreamReader</span><span class="sxs-lookup"><span data-stu-id="704b1-113">Example: Read a file as a stream with StreamReader</span></span>  
  
<span data-ttu-id="704b1-114">Nell'esempio seguente viene usato il <xref:System.Windows.Forms.Button> gestore eventi del controllo Windows Forms <xref:System.Windows.Forms.Control.Click> per aprire <xref:System.Windows.Forms.OpenFileDialog> con il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="704b1-114">The following example uses the Windows Forms <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="704b1-115">Quando l'utente sceglie un file e seleziona **OK**, un'istanza della <xref:System.IO.StreamReader> classe legge il file e ne Visualizza il contenuto nella casella di testo del modulo.</span><span class="sxs-lookup"><span data-stu-id="704b1-115">After the user chooses a file and selects **OK**, an instance of the <xref:System.IO.StreamReader> class reads the file and displays its contents in the form's text box.</span></span> <span data-ttu-id="704b1-116">Per ulteriori informazioni sulla lettura da flussi di file, vedere <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> e <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="704b1-116">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> and <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.</span></span>  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a><span data-ttu-id="704b1-117">Esempio: aprire un file da una selezione filtrata con OpenFile</span><span class="sxs-lookup"><span data-stu-id="704b1-117">Example: Open a file from a filtered selection with OpenFile</span></span>

<span data-ttu-id="704b1-118">Nell'esempio seguente viene usato il <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Click> gestore eventi del controllo per aprire l'oggetto <xref:System.Windows.Forms.OpenFileDialog> con un filtro che mostra solo file di testo.</span><span class="sxs-lookup"><span data-stu-id="704b1-118">The following example uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with a filter that shows only text files.</span></span> <span data-ttu-id="704b1-119">Quando l'utente sceglie un file di testo e seleziona **OK**, <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> viene usato il metodo per aprire il file nel blocco note.</span><span class="sxs-lookup"><span data-stu-id="704b1-119">After the user chooses a text file and selects **OK**, the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is used to open the file in Notepad.</span></span>

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="704b1-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="704b1-120">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="704b1-121">Componente OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="704b1-121">OpenFileDialog component</span></span>](openfiledialog-component-windows-forms.md)

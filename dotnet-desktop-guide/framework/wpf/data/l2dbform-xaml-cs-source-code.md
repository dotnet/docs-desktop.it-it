---
title: Codice sorgente di L2DBForm.xaml.cs
ms.date: 10/22/2019
ms.topic: sample
ms.openlocfilehash: 882699a76eab3c291cd92c298287bc5d28fb08e1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964543"
---
# <a name="l2dbformxamlcs-source-code"></a><span data-ttu-id="3c112-102">Codice sorgente di L2DBForm.xaml.cs</span><span class="sxs-lookup"><span data-stu-id="3c112-102">L2DBForm.xaml.cs source code</span></span>

<span data-ttu-id="3c112-103">Questa pagina contiene il contenuto e la descrizione del codice sorgente C# nel file *L2DBForm.XAML.cs*.</span><span class="sxs-lookup"><span data-stu-id="3c112-103">This page contains the contents and description of the C# source code in the file *L2DBForm.xaml.cs*.</span></span> <span data-ttu-id="3c112-104">La classe parziale L2XDBForm contenuta in questo file può essere divisa in tre sezioni logiche: membri di dati e gestori degli eventi Click `OnRemove` e `OnAddBook`.</span><span class="sxs-lookup"><span data-stu-id="3c112-104">The L2XDBForm partial class contained in this file can be divided into three logical sections: data members and the `OnRemove` and `OnAddBook` button click event handlers.</span></span>

## <a name="data-members"></a><span data-ttu-id="3c112-105">Membri dati</span><span class="sxs-lookup"><span data-stu-id="3c112-105">Data members</span></span>

<span data-ttu-id="3c112-106">Per associare questa classe alle risorse della finestra usate in *L2DBForm. XAML*, vengono usati due membri di dati privati.</span><span class="sxs-lookup"><span data-stu-id="3c112-106">Two private data members are used to associate this class to the window resources used in *L2DBForm.xaml*.</span></span>

- <span data-ttu-id="3c112-107">La variabile dello spazio dei nomi `myBooks` viene inizializzata in `"http://www.mybooks.com"`.</span><span class="sxs-lookup"><span data-stu-id="3c112-107">The namespace variable `myBooks` is initialized to `"http://www.mybooks.com"`.</span></span>

- <span data-ttu-id="3c112-108">Il membro `bookList` viene inizializzato nel costruttore nella stringa CDATA in *L2DBForm. XAML* con la riga seguente:</span><span class="sxs-lookup"><span data-stu-id="3c112-108">The member `bookList` is initialized in the constructor to the CDATA string in *L2DBForm.xaml* with the following line:</span></span>

    ```csharp
    bookList = (XElement)((ObjectDataProvider)Resources["LoadedBooks"]).Data;
    ```

## <a name="onaddbook-event-handler"></a><span data-ttu-id="3c112-109">Gestore dell'evento OnAddBook</span><span class="sxs-lookup"><span data-stu-id="3c112-109">OnAddBook event handler</span></span>

<span data-ttu-id="3c112-110">Questo metodo contiene le tre istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c112-110">This method contains the following three statements:</span></span>

- <span data-ttu-id="3c112-111">La prima istruzione condizionale viene usata per la convalida dell'input.</span><span class="sxs-lookup"><span data-stu-id="3c112-111">The first conditional statement is used for input validation.</span></span>

- <span data-ttu-id="3c112-112">La seconda istruzione crea un nuovo oggetto <xref:System.Xml.Linq.XElement> dai valori stringa immessi dall'utente nella sezione **Add New Book** (Aggiungi nuovo libro) dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="3c112-112">The second statement creates a new <xref:System.Xml.Linq.XElement> from the string values the user entered in the **Add New Book** user interface (UI) section.</span></span>

- <span data-ttu-id="3c112-113">L'ultima istruzione aggiunge questo nuovo elemento libro al provider di dati in *L2DBForm. XAML*.</span><span class="sxs-lookup"><span data-stu-id="3c112-113">The last statement adds this new book element to the data provider in *L2DBForm.xaml*.</span></span> <span data-ttu-id="3c112-114">Di conseguenza, l'associazione dati dinamica aggiornerà automaticamente l'interfaccia utente con questo nuovo elemento. Non è necessario altro codice specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="3c112-114">Consequently, dynamic data binding will automatically update the UI with this new item; no extra user-supplied code is required.</span></span>

## <a name="onremove-event-handler"></a><span data-ttu-id="3c112-115">Gestore dell'evento OnRemove</span><span class="sxs-lookup"><span data-stu-id="3c112-115">OnRemove event handler</span></span>

<span data-ttu-id="3c112-116">Il gestore dell'evento `OnRemove` è più complicato del gestore dell'evento `OnAddBook`, per due motivi.</span><span class="sxs-lookup"><span data-stu-id="3c112-116">The `OnRemove` handler is more complicated than the `OnAddBook` handler for two reasons.</span></span> <span data-ttu-id="3c112-117">Innanzitutto, poiché l'XML non elaborato contiene lo spazio vuoto conservato, è necessario anche rimuovere le nuove righe corrispondente con la voce del libro.</span><span class="sxs-lookup"><span data-stu-id="3c112-117">First, because the raw XML contains preserved white space, matching newlines must also be removed with the book entry.</span></span> <span data-ttu-id="3c112-118">In secondo luogo, per comodità, la selezione applicata sull'elemento eliminato è stata reimpostata sull'elemento precedente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3c112-118">Second, as a convenience, the selection, which was on the deleted item, is reset to the previous one in the list.</span></span>

<span data-ttu-id="3c112-119">Tuttavia l'operazione principale di rimozione dell'elemento libro selezionato viene effettuata con due sole istruzioni:</span><span class="sxs-lookup"><span data-stu-id="3c112-119">However, the core work of removing the selected book item is accomplished by only two statements:</span></span>

- <span data-ttu-id="3c112-120">Innanzitutto viene recuperato l'elemento libro associato all'elemento attualmente selezionato nella casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="3c112-120">First, the book element associated with the currently selected item in the list box is retrieved:</span></span>

    ```csharp
    XElement selBook = (XElement)lbBooks.SelectedItem;
    ```

- <span data-ttu-id="3c112-121">Quindi questo elemento viene eliminato dal provider di dati.</span><span class="sxs-lookup"><span data-stu-id="3c112-121">Then, this element is deleted from the data provider:</span></span>

    ```csharp
    selBook.Remove();
    ```

<span data-ttu-id="3c112-122">Ancora una volta, l'associazione dati dinamica assicura l'aggiornamento automatico dell'interfaccia utente del programma.</span><span class="sxs-lookup"><span data-stu-id="3c112-122">Again, dynamic data binding assures that the program's UI is automatically updated.</span></span>

## <a name="example"></a><span data-ttu-id="3c112-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="3c112-123">Example</span></span>

### <a name="code"></a><span data-ttu-id="3c112-124">Codice</span><span class="sxs-lookup"><span data-stu-id="3c112-124">Code</span></span>

```csharp
using System;
using System.Linq;
using System.Collections;
using System.Collections.Generic;
using System.Diagnostics;
using System.Text;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Input;
using System.Xml;
using System.Xml.Linq;

namespace LinqToXmlDataBinding {
    /// <summary>
    /// Interaction logic for L2XDBForm.xaml
    /// </summary>

    public partial class L2XDBForm : System.Windows.Window
    {
        XNamespace mybooks = "http://www.mybooks.com";
        XElement bookList;

        public L2XDBForm()
        {
            InitializeComponent();
            bookList = (XElement)((ObjectDataProvider)Resources["LoadedBooks"]).Data;
        }

        void OnRemoveBook(object sender, EventArgs e)
        {
            int index = lbBooks.SelectedIndex;
            if (index < 0) return;

            XElement selBook = (XElement)lbBooks.SelectedItem;
            //Get next node before removing element.
            XNode nextNode = selBook.NextNode;
            selBook.Remove();

            //Remove any matching newline node.
            if (nextNode != null && nextNode.ToString().Trim().Equals(""))
            { nextNode.Remove(); }

            //Set selected item.
            if (lbBooks.Items.Count > 0)
            {  lbBooks.SelectedItem = lbBooks.Items[index > 0 ? index - 1 : 0]; }
        }

        void OnAddBook(object sender, EventArgs e)
        {
            if (String.IsNullOrEmpty(tbAddID.Text) ||
                String.IsNullOrEmpty(tbAddValue.Text))
            {
                MessageBox.Show("Please supply both a Book ID and a Value!", "Entry Error!");
                return;
            }
            XElement newBook = new XElement(
                                mybooks + "book",
                                new XAttribute("id", tbAddID.Text),
                                tbAddValue.Text);
            bookList.Add("  ", newBook, "\r\n");
        }
    }
}
```

### <a name="comments"></a><span data-ttu-id="3c112-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="3c112-125">Comments</span></span>

<span data-ttu-id="3c112-126">Per l'origine XAML associata per questi gestori, vedere [codice sorgente L2DBForm. XAML](l2dbform-xaml-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="3c112-126">For the associated XAML source for these handlers, see [L2DBForm.xaml source code](l2dbform-xaml-source-code.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3c112-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c112-127">See also</span></span>

- [<span data-ttu-id="3c112-128">Procedura dettagliata: Esempio LinqToXmlDataBinding</span><span class="sxs-lookup"><span data-stu-id="3c112-128">Walkthrough: LinqToXmlDataBinding example</span></span>](linq-to-xml-data-binding-sample.md)
- [<span data-ttu-id="3c112-129">Codice sorgente di L2DBForm.xaml</span><span class="sxs-lookup"><span data-stu-id="3c112-129">L2DBForm.xaml source code</span></span>](l2dbform-xaml-source-code.md)

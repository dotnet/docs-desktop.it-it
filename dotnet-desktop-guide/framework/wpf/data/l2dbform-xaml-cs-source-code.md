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
# <a name="l2dbformxamlcs-source-code"></a>Codice sorgente di L2DBForm.xaml.cs

Questa pagina contiene il contenuto e la descrizione del codice sorgente C# nel file *L2DBForm.XAML.cs*. La classe parziale L2XDBForm contenuta in questo file può essere divisa in tre sezioni logiche: membri di dati e gestori degli eventi Click `OnRemove` e `OnAddBook`.

## <a name="data-members"></a>Membri dati

Per associare questa classe alle risorse della finestra usate in *L2DBForm. XAML*, vengono usati due membri di dati privati.

- La variabile dello spazio dei nomi `myBooks` viene inizializzata in `"http://www.mybooks.com"`.

- Il membro `bookList` viene inizializzato nel costruttore nella stringa CDATA in *L2DBForm. XAML* con la riga seguente:

    ```csharp
    bookList = (XElement)((ObjectDataProvider)Resources["LoadedBooks"]).Data;
    ```

## <a name="onaddbook-event-handler"></a>Gestore dell'evento OnAddBook

Questo metodo contiene le tre istruzioni seguenti:

- La prima istruzione condizionale viene usata per la convalida dell'input.

- La seconda istruzione crea un nuovo oggetto <xref:System.Xml.Linq.XElement> dai valori stringa immessi dall'utente nella sezione **Add New Book** (Aggiungi nuovo libro) dell'interfaccia utente.

- L'ultima istruzione aggiunge questo nuovo elemento libro al provider di dati in *L2DBForm. XAML*. Di conseguenza, l'associazione dati dinamica aggiornerà automaticamente l'interfaccia utente con questo nuovo elemento. Non è necessario altro codice specificato dall'utente.

## <a name="onremove-event-handler"></a>Gestore dell'evento OnRemove

Il gestore dell'evento `OnRemove` è più complicato del gestore dell'evento `OnAddBook`, per due motivi. Innanzitutto, poiché l'XML non elaborato contiene lo spazio vuoto conservato, è necessario anche rimuovere le nuove righe corrispondente con la voce del libro. In secondo luogo, per comodità, la selezione applicata sull'elemento eliminato è stata reimpostata sull'elemento precedente nell'elenco.

Tuttavia l'operazione principale di rimozione dell'elemento libro selezionato viene effettuata con due sole istruzioni:

- Innanzitutto viene recuperato l'elemento libro associato all'elemento attualmente selezionato nella casella di riepilogo.

    ```csharp
    XElement selBook = (XElement)lbBooks.SelectedItem;
    ```

- Quindi questo elemento viene eliminato dal provider di dati.

    ```csharp
    selBook.Remove();
    ```

Ancora una volta, l'associazione dati dinamica assicura l'aggiornamento automatico dell'interfaccia utente del programma.

## <a name="example"></a>Esempio

### <a name="code"></a>Codice

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

### <a name="comments"></a>Commenti

Per l'origine XAML associata per questi gestori, vedere [codice sorgente L2DBForm. XAML](l2dbform-xaml-source-code.md).

## <a name="see-also"></a>Vedere anche

- [Procedura dettagliata: Esempio LinqToXmlDataBinding](linq-to-xml-data-binding-sample.md)
- [Codice sorgente di L2DBForm.xaml](l2dbform-xaml-source-code.md)

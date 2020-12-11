---
title: Implementare la modalità virtuale con caricamento dati JIT nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], just-in-time data loading
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- just-in-time data loading
- DataGridView control [Windows Forms], large data sets
- virtual mode [Windows Forms], just-in-time data loading
ms.assetid: 33825f92-7a22-40ee-86d9-9a2ed1ead7b7
ms.openlocfilehash: 7b7990ceacba9e5f479149c934db1914e8dd0bef
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966841"
---
# <a name="how-to-implement-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a>Procedura: Implementare la modalità virtuale con caricamento dati JIT nel controllo DataGridView di Windows Forms

Il seguente esempio di codice mostra come usare la modalità virtuale nel controllo <xref:System.Windows.Forms.DataGridView> con una cache dei dati che carica i dati da un server solo quando è necessario. Questo esempio è descritto in dettaglio in [implementazione della modalità virtuale con caricamento dati JIT nel controllo Windows Forms DataGridView](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).  
  
## <a name="example"></a>Esempio  

 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#000)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  

 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Data, System.Xml e System.Windows.Forms.  
  
- Accesso a un server in cui sia installato il database SQL Server di esempio Northwind.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  

 L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [Protezione delle informazioni di connessione](/dotnet/framework/data/adonet/protecting-connection-information).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- [Implementazione del modo virtuale con caricamento dati JIT nel controllo DataGridView di Windows Form](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [Ottimizzazione delle prestazioni nel controllo DataGridView Windows Form](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Modo virtuale nel controllo DataGridView di Windows Form](virtual-mode-in-the-windows-forms-datagridview-control.md)

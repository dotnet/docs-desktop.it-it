---
title: Considerazioni aggiuntive sulla sicurezza
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, secure calls to Windows API
- security [Windows Forms]
- security [Windows Forms], calling APIs
- Clipboard [Windows Forms], securing access
ms.assetid: 15abda8b-0527-47c7-aedb-77ab595f2bf1
ms.openlocfilehash: 5b9cc25cef8a0fabb4e01fa56c38add6c2048f33
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952265"
---
# <a name="additional-security-considerations-in-windows-forms"></a>Considerazioni aggiuntive sulla sicurezza in Windows Form

.NET Framework impostazioni di sicurezza potrebbero far sì che l'applicazione venga eseguita in modo diverso in un ambiente con attendibilità parziale rispetto al computer locale. Il .NET Framework limita l'accesso a queste risorse locali critiche come file system, rete e API non gestite, tra le altre cose. Le impostazioni di sicurezza influiscono sulla possibilità di chiamare l'API di Microsoft Windows o altre API che non possono essere verificate dal sistema di sicurezza. La sicurezza influisce inoltre su altri aspetti dell'applicazione, inclusi l'accesso ai file e ai dati e la stampa. Per altre informazioni sull'accesso a file e dati in un ambiente ad attendibilità parziale, vedere [More Secure File and Data Access in Windows Forms](more-secure-file-and-data-access-in-windows-forms.md) (Accesso più sicuro a file e dati in Windows Form). Per altre informazioni sulla stampa in un ambiente ad attendibilità parziale, vedere [More Secure Printing in Windows Forms](more-secure-printing-in-windows-forms.md) (Stampa più sicura in Windows Form).  
  
 Le sezioni seguenti illustrano come usare gli appunti, eseguire la manipolazione delle finestre e chiamare l'API Windows dalle applicazioni in esecuzione in un ambiente parzialmente attendibile.  
  
## <a name="clipboard-access"></a>Accesso agli Appunti  

 La <xref:System.Security.Permissions.UIPermission> classe controlla l'accesso agli Appunti e il <xref:System.Security.Permissions.UIPermissionClipboard> valore di enumerazione associato indica il livello di accesso. Nella tabella seguente sono elencati i livelli di autorizzazione possibili.  
  
|Valore UIPermissionClipboard|Descrizione|  
|---------------------------------|-----------------|  
|<xref:System.Security.Permissions.UIPermissionClipboard.AllClipboard>|È possibile usare gli Appunti senza restrizioni.|  
|<xref:System.Security.Permissions.UIPermissionClipboard.OwnClipboard>|È possibile usare gli Appunti con alcune restrizioni. Possibilità di inserire dati negli Appunti (operazioni dei comandi Copia o Taglia) senza restrizioni. I controlli intrinseci che accettano operazioni Incolla, ad esempio una casella di testo, possono accettare i dati negli Appunti, ma i controlli utente non possono leggere a livello di codice dagli Appunti.|  
|<xref:System.Security.Permissions.UIPermissionClipboard.NoClipboard>|Impossibile usare gli Appunti.|  
  
 Per impostazione predefinita, l'area Intranet locale riceve l' <xref:System.Security.Permissions.UIPermissionClipboard.AllClipboard> accesso e l'area Internet riceve l' <xref:System.Security.Permissions.UIPermissionClipboard.OwnClipboard> accesso. Ciò significa che l'applicazione può copiare dati negli Appunti, ma non può incollare negli Appunti o leggere dagli Appunti a livello di codice. Queste restrizioni impediscono ai programmi senza attendibilità totale di leggere il contenuto copiati negli Appunti da un'altra applicazione. Se l'applicazione richiede l'accesso completo agli Appunti ma non disporre delle autorizzazioni, sarà necessario elevarne le autorizzazioni. Per altre informazioni sull'elevazione delle autorizzazioni, vedere [General Security Policy Administration](/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100)) (Amministrazione generale dei criteri di sicurezza).  
  
## <a name="window-manipulation"></a>Modifica delle finestre  

 La <xref:System.Security.Permissions.UIPermission> classe controlla anche l'autorizzazione per eseguire la manipolazione delle finestre e altre azioni correlate all'interfaccia utente e il <xref:System.Security.Permissions.UIPermissionWindow> valore di enumerazione associato indica il livello di accesso. Nella tabella seguente sono elencati i livelli di autorizzazione possibili.  
  
 Per impostazione predefinita, l'area Intranet locale riceve l' <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> accesso e l'area Internet riceve l' <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> accesso. Ciò significa che, nell'area Internet, l'applicazione può eseguire la maggior parte delle azioni legate a finestre e interfaccia utente, con conseguente modifica dell'aspetto della finestra. La finestra modificata visualizza una notifica alla prima esecuzione, contiene testo modificato nella barra del titolo e richiede un pulsante di chiusura nella medesima barra. La notifica e la barra del titolo indicano all'utente dell'applicazione che quest'ultima è in esecuzione ad attendibilità parziale.  
  
|Valore UIPermissionWindow|Descrizione|  
|------------------------------|-----------------|  
|<xref:System.Security.Permissions.UIPermissionWindow.AllWindows>|Gli utenti possono usare tutte le finestre e tutti gli eventi input utente senza restrizioni.|  
|<xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows>|Gli utenti possono usare solo le più sicure finestre principali e secondarie per il disegno e possono usare solo gli eventi input utente dell'interfaccia all'interno di tali finestre. Queste finestre sicure sono contrassegnate in modo chiaro e dispongono di restrizioni per la dimensione minima e massima. Le restrizioni impediscono attacchi di spoofing potenzialmente dannosi, ad esempio imitando le schermate di accesso al sistema o il desktop di sistema, e limitano l'accesso a livello di codice alle finestre padre, alle API correlate allo stato attivo e all'uso del <xref:System.Windows.Forms.ToolTip> controllo.|  
|<xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows>|Gli utenti possono usare solo le più sicure finestre secondarie per il disegno e possono usare solo gli eventi input utente dell'interfaccia all'interno di tali finestre. Un controllo visualizzato all'interno di un browser è un esempio di finestra secondaria sicura.|  
|<xref:System.Security.Permissions.UIPermissionWindow.NoWindows>|Gli utenti non possono usare finestre o eventi dell'interfaccia utente. Non è possibile usare l'interfaccia utente.|  
  
 Ogni livello di autorizzazione identificato dall' <xref:System.Security.Permissions.UIPermissionWindow> enumerazione consente un minor numero di azioni rispetto al livello superiore. Le tabelle seguenti indicano le azioni che sono limitate dai <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> valori e <xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows> . Per le autorizzazioni esattamente necessarie per ogni membro, vedere il riferimento per tale membro nella documentazione della libreria di classi .NET Framework.  
  
 <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> l'autorizzazione limita le azioni elencate nella tabella seguente.  
  
|Componente|Azioni limitate|  
|---------------|------------------------|  
|<xref:System.Windows.Forms.Application>|-   Impostazione della proprietà <xref:System.Windows.Forms.Application.SafeTopLevelCaptionFormat%2A>.|  
|<xref:System.Windows.Forms.Control>|-Recupero della <xref:System.Windows.Forms.Control.Parent%2A> Proprietà.<br />-   Impostazione della proprietà `Region`.<br />-Chiamata del <xref:System.Windows.Forms.Control.FindForm%2A> <xref:System.Windows.Forms.Control.Focus%2A> metodo,, <xref:System.Windows.Forms.Control.FromChildHandle%2A> e <xref:System.Windows.Forms.Control.FromHandle%2A> , <xref:System.Windows.Forms.Control.PreProcessMessage%2A> , <xref:System.Windows.Forms.Control.ReflectMessage%2A> o <xref:System.Windows.Forms.Control.SetTopLevel%2A> .<br />-Chiamata del <xref:System.Windows.Forms.Control.GetChildAtPoint%2A> metodo se il controllo restituito non è un elemento figlio del controllo chiamante.<br />-   Modifica del focus del controllo all'interno di un controllo contenitore.|  
|<xref:System.Windows.Forms.Cursor>|-   Impostazione della proprietà <xref:System.Windows.Forms.Cursor.Clip%2A>.<br />-Chiamata del <xref:System.Windows.Forms.Control.Hide%2A> metodo.|  
|<xref:System.Windows.Forms.DataGrid>|-Chiamata del <xref:System.Windows.Forms.ContainerControl.ProcessTabKey%2A> metodo.|  
|<xref:System.Windows.Forms.Form>|-Recupero della <xref:System.Windows.Forms.Form.ActiveForm%2A> <xref:System.Windows.Forms.Form.MdiParent%2A> proprietà o.<br />-Impostazione della <xref:System.Windows.Forms.Form.ControlBox%2A> <xref:System.Windows.Forms.Form.ShowInTaskbar%2A> proprietà, o <xref:System.Windows.Forms.Form.TopMost%2A> .<br />-Impostazione della <xref:System.Windows.Forms.Form.Opacity%2A> proprietà al di sotto del 50%.<br />-Impostazione della <xref:System.Windows.Forms.Form.WindowState%2A> proprietà su a <xref:System.Windows.Forms.FormWindowState.Minimized> livello di codice.<br />-Chiamata del <xref:System.Windows.Forms.Form.Activate%2A> metodo.<br />-Uso dei <xref:System.Windows.Forms.FormBorderStyle.None> <xref:System.Windows.Forms.FormBorderStyle.FixedToolWindow> valori di enumerazione, e <xref:System.Windows.Forms.FormBorderStyle.SizableToolWindow> <xref:System.Windows.Forms.FormBorderStyle> .|  
|<xref:System.Windows.Forms.NotifyIcon>|-L'uso del <xref:System.Windows.Forms.NotifyIcon> componente è completamente limitato.|  
  
 Il <xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows> valore limita le azioni elencate nella tabella seguente, oltre alle restrizioni inserite dal <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> valore.  
  
|Componente|Azioni limitate|  
|---------------|------------------------|  
|<xref:System.Windows.Forms.CommonDialog>|-Visualizzazione di una finestra di dialogo derivata dalla <xref:System.Windows.Forms.CommonDialog> classe.|  
|<xref:System.Windows.Forms.Control>|-Chiamata del <xref:System.Windows.Forms.Control.CreateGraphics%2A> metodo.<br />-   Impostazione della proprietà <xref:System.Windows.Forms.Control.Cursor%2A>.|  
|<xref:System.Windows.Forms.Control.Cursor%2A>|-   Impostazione della proprietà <xref:System.Windows.Forms.Cursor.Current%2A>.|  
|<xref:System.Windows.Forms.MessageBox>|-Chiamata del <xref:System.Windows.Forms.Form.Show%2A> metodo.|  
  
### <a name="hosting-third-party-controls"></a>Hosting di controlli di terze parti  

 Se i moduli ospitano controlli di terze parti, può verificarsi un altro tipo di modifica delle finestre. Un controllo di terze parti è un qualsiasi personalizzato <xref:System.Windows.Forms.UserControl> che non è stato sviluppato e compilato autonomamente. Sebbene lo scenario di hosting sia difficile da sfruttare, un controllo di terze parti può almeno in teoria espandere la propria superficie di rendering per coprire l'intera area del modulo. Il controllo potrebbe quindi imitare una finestra di dialogo critica e richiedere informazioni come combinazioni di nome utente e password o numeri di conti corrente degli utenti.  
  
 Per limitare questo rischio, usare solo controlli di terze parti considerati attendibili. Se si usano controlli di terze parti scaricati da origini non verificabili, si consiglia di esaminarne il codice sorgente alla ricerca di exploit potenziali. Dopo aver verificato che l'origine non è dannosa, compilare l'assembly da sé per assicurarsi che l'origine corrisponda.  
  
## <a name="windows-api-calls"></a>Chiamate API Windows  

 Se la progettazione dell'applicazione richiede la chiamata di una funzione dall'API Windows, si accede a codice non gestito. In questo caso non è possibile determinare le azioni del codice per la finestra o il sistema operativo quando si utilizzano chiamate o valori API Windows. La <xref:System.Security.Permissions.SecurityPermission> classe e il <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> valore dell' <xref:System.Security.Permissions.SecurityPermissionFlag> enumerazione controllano l'accesso al codice non gestito. Un'applicazione può accedere al codice non gestito solo quando viene concessa l' <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> autorizzazione. Per impostazione predefinita, solo le applicazioni in esecuzione in locale possono chiamare codice non gestito.  
  
 Alcuni Windows Forms membri forniscono accesso non gestito che richiede l' <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> autorizzazione. Nella tabella seguente sono elencati i membri dello <xref:System.Windows.Forms> spazio dei nomi che richiedono l'autorizzazione. Per altre informazioni sulle autorizzazioni necessarie per un membro, vedere la documentazione della libreria di classi .NET Framework.  
  
|Componente|Membro|  
|---------------|------------|  
|<xref:System.Windows.Forms.Application>|-    Metodo <xref:System.Windows.Forms.Application.AddMessageFilter%2A><br />-   <xref:System.Windows.Forms.Application.CurrentInputLanguage%2A> Proprietà<br />-    Metodo `Exit`<br />-    Metodo <xref:System.Windows.Forms.Application.ExitThread%2A><br />-   <xref:System.Windows.Forms.Application.ThreadException> evento|  
|<xref:System.Windows.Forms.CommonDialog>|-    Metodo <xref:System.Windows.Forms.CommonDialog.HookProc%2A><br />-   <xref:System.Windows.Forms.CommonDialog.OwnerWndProc%2A>\ (metodo)<br />-    Metodo <xref:System.Windows.Forms.CommonDialog.Reset%2A><br />-    Metodo <xref:System.Windows.Forms.CommonDialog.RunDialog%2A>|  
|<xref:System.Windows.Forms.Control>|-    Metodo <xref:System.Windows.Forms.Control.CreateParams%2A><br />-    Metodo <xref:System.Windows.Forms.Control.DefWndProc%2A><br />-    Metodo <xref:System.Windows.Forms.Control.DestroyHandle%2A><br />-    Metodo <xref:System.Windows.Forms.Control.WndProc%2A>|  
|<xref:System.Windows.Forms.Help>|-   <xref:System.Windows.Forms.Help.ShowHelp%2A> Metodi<br />-    Metodo <xref:System.Windows.Forms.Help.ShowHelpIndex%2A>|  
|<xref:System.Windows.Forms.NativeWindow>|-   <xref:System.Windows.Forms.NativeWindow> classe|  
|<xref:System.Windows.Forms.Screen>|-    Metodo <xref:System.Windows.Forms.Screen.FromHandle%2A>|  
|<xref:System.Windows.Forms.SendKeys>|-    Metodo <xref:System.Windows.Forms.SendKeys.Send%2A><br />-    Metodo <xref:System.Windows.Forms.SendKeys.SendWait%2A>|  
  
 Se l'applicazione non è autorizzata a chiamare codice non gestito, l'applicazione deve richiedere l' <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> autorizzazione oppure è necessario prendere in considerazione modi alternativi per implementare le funzionalità. in molti casi Windows Forms fornisce un'alternativa gestita alle funzioni dell'API Windows. Se non esistono metodi alternativi e l'applicazione deve accedere a codice non gestito, sarà necessario elevare le autorizzazioni per l'applicazione.  
  
 L'autorizzazione a chiamare codice non gestito consente a un'applicazione di eseguire praticamente qualsiasi operazione. Fornire pertanto tale autorizzazione solo alle applicazioni provenienti da fonti attendibili. In alternativa, a seconda dell'applicazione, la caratteristica che esegue la chiamata al codice non gestite potrebbe essere facoltativa oppure abilitata solo in un ambiente ad attendibilità totale. Per altre informazioni sulle autorizzazioni pericolose, vedere [Autorizzazioni pericolose e amministrazione dei criteri](/dotnet/framework/misc/dangerous-permissions-and-policy-administration). Per altre informazioni sull'elevazione delle autorizzazioni, vedere [General Security Policy Administration](/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100)) (Amministrazione generale dei criteri di sicurezza).  
  
## <a name="see-also"></a>Vedere anche

- [File e accesso ai dati più protetti in Windows Form](more-secure-file-and-data-access-in-windows-forms.md)
- [Stampa più protetta in Windows Form](more-secure-printing-in-windows-forms.md)
- [Cenni preliminari sulla sicurezza in Windows Form](security-in-windows-forms-overview.md)
- [Sicurezza di Windows Form](windows-forms-security.md)
- [Protezione di applicazioni ClickOnce](/visualstudio/deployment/securing-clickonce-applications)

---
title: 'Procedura: Disabilitare le schede'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
ms.openlocfilehash: 9074aedb81a485267dc4faff92e0fe8d0d3b467f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963832"
---
# <a name="how-to-disable-tab-pages"></a><span data-ttu-id="8bf02-102">Procedura: Disabilitare le schede</span><span class="sxs-lookup"><span data-stu-id="8bf02-102">How to: Disable Tab Pages</span></span>
<span data-ttu-id="8bf02-103">In alcuni casi, è possibile limitare l'accesso ai dati disponibili all'interno del Windows Forms Application.</span><span class="sxs-lookup"><span data-stu-id="8bf02-103">On some occasions, you will want to restrict access to data that is available within your Windows Forms application.</span></span> <span data-ttu-id="8bf02-104">Un esempio potrebbe essere quando i dati vengono visualizzati nelle schede di un controllo struttura a schede; gli amministratori possono disporre di informazioni su una scheda che si desidera limitare dagli utenti guest o di livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="8bf02-104">One example of this might be when you have data displayed in the tab pages of a tab control; administrators could have information on a tab page that you would want to restrict from guest or lower-level users.</span></span>  
  
### <a name="to-disable-tab-pages-programmatically"></a><span data-ttu-id="8bf02-105">Per disabilitare le schede a livello di codice</span><span class="sxs-lookup"><span data-stu-id="8bf02-105">To disable tab pages programmatically</span></span>  
  
1. <span data-ttu-id="8bf02-106">Scrivere il codice per gestire l'evento del controllo Tab <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> .</span><span class="sxs-lookup"><span data-stu-id="8bf02-106">Write code to handle the tab control's <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event.</span></span> <span data-ttu-id="8bf02-107">Si tratta dell'evento generato quando l'utente passa da una scheda a quella successiva.</span><span class="sxs-lookup"><span data-stu-id="8bf02-107">This is the event that is raised when the user switches from one tab to the next.</span></span>  
  
2. <span data-ttu-id="8bf02-108">Verificare le credenziali.</span><span class="sxs-lookup"><span data-stu-id="8bf02-108">Check credentials.</span></span> <span data-ttu-id="8bf02-109">A seconda delle informazioni presentate, potrebbe essere necessario controllare il nome utente con cui l'utente ha eseguito l'accesso o altre forme di credenziali prima di consentire all'utente di visualizzare la scheda.</span><span class="sxs-lookup"><span data-stu-id="8bf02-109">Depending upon the information presented, you may want to check the user name the user has logged in with or some other form of credentials before allowing the user to view the tab.</span></span>  
  
3. <span data-ttu-id="8bf02-110">Se l'utente dispone delle credenziali appropriate, visualizzare la scheda su cui è stato fatto clic.</span><span class="sxs-lookup"><span data-stu-id="8bf02-110">If the user has appropriate credentials, display the tab that was clicked.</span></span> <span data-ttu-id="8bf02-111">Se l'utente non dispone delle credenziali appropriate, Visualizza una finestra di messaggio o un'altra interfaccia utente che indica che non è possibile accedervi e tornare alla scheda iniziale.</span><span class="sxs-lookup"><span data-stu-id="8bf02-111">If the user does not have appropriate credentials, display a message box or some other user interface indicating that they do not have access, and return to the initial tab.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8bf02-112">Quando si implementa questa funzionalità nelle applicazioni di produzione, è possibile eseguire questo controllo delle credenziali durante l'evento del modulo <xref:System.Windows.Forms.Form.Load> .</span><span class="sxs-lookup"><span data-stu-id="8bf02-112">When you implement this functionality in your production applications, you can perform this credential check during the form's <xref:System.Windows.Forms.Form.Load> event.</span></span> <span data-ttu-id="8bf02-113">In questo modo sarà possibile nascondere la scheda prima di visualizzare un'interfaccia utente, un approccio molto più semplice alla programmazione.</span><span class="sxs-lookup"><span data-stu-id="8bf02-113">This will allow you to hide the tab before any user interface is shown, which is a much cleaner approach to programming.</span></span> <span data-ttu-id="8bf02-114">La metodologia utilizzata di seguito (controllando le credenziali e disabilitando la scheda durante l' <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> evento) è a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="8bf02-114">The methodology used below (checking credentials and disabling the tab during the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event) is for illustrative purposes.</span></span>  
  
4. <span data-ttu-id="8bf02-115">Facoltativamente, se si dispone di più di due schede, visualizzare una scheda diversa dall'originale.</span><span class="sxs-lookup"><span data-stu-id="8bf02-115">Optionally, if you have more than two tab pages, display a tab page different from the original.</span></span>  
  
     <span data-ttu-id="8bf02-116">Nell'esempio seguente <xref:System.Windows.Forms.CheckBox> viene usato un controllo anziché controllare le credenziali, in quanto i criteri per l'accesso alla scheda variano in base all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8bf02-116">In the example below, a <xref:System.Windows.Forms.CheckBox> control is used in lieu of checking the credentials, as the criteria for access to the tab will vary by application.</span></span> <span data-ttu-id="8bf02-117">Quando <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> viene generato l'evento, se il controllo delle credenziali è true (ovvero la casella di controllo è selezionata) e la scheda selezionata è `TabPage2` (la scheda con le informazioni riservate, in questo esempio), `TabPage2` viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="8bf02-117">When the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event is raised, if the credential check is true (that is, the check box is checked) and the selected tab is `TabPage2` (the tab with the confidential information, in this example), then `TabPage2` is displayed.</span></span> <span data-ttu-id="8bf02-118">In caso contrario, `TabPage3` viene visualizzato e viene visualizzata una finestra di messaggio all'utente che indica che non dispone dei privilegi di accesso appropriati.</span><span class="sxs-lookup"><span data-stu-id="8bf02-118">Otherwise, `TabPage3` is displayed and a message box is shown to the user, indicating they did not have appropriate access privileges.</span></span> <span data-ttu-id="8bf02-119">Il codice riportato di seguito presuppone un form con un <xref:System.Windows.Forms.CheckBox> controllo ( `CredentialCheck` ) e un <xref:System.Windows.Forms.TabControl> controllo con tre schede.</span><span class="sxs-lookup"><span data-stu-id="8bf02-119">The code below assumes a form with a <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) and a <xref:System.Windows.Forms.TabControl> control with three tab pages.</span></span>  
  
    ```vb  
    Private Sub TabControl1_SelectedIndexChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles TabControl1.SelectedIndexChanged  
       ' Check Credentials Here  
  
       If CredentialCheck.Checked = True And _
       TabControl1.SelectedTab Is TabPage2 Then  
          TabControl1.SelectedTab = TabPage2  
       ElseIf CredentialCheck.Checked = False _
       And TabControl1.SelectedTab Is TabPage2 Then  
          MessageBox.Show _
         ("Unable to load tab. You have insufficient access privileges.")  
          TabControl1.SelectedTab = TabPage3  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void tabControl1_SelectedIndexChanged(object sender, System.EventArgs e)  
    {  
        // Check Credentials Here  
  
        if ((CredentialCheck.Checked == true) && (tabControl1.SelectedTab == tabPage2))
        {  
            tabControl1.SelectedTab = tabPage2;  
        }  
        else if ((CredentialCheck.Checked == false) && (tabControl1.SelectedTab == tabPage2))  
        {  
            MessageBox.Show("Unable to load tab. You have insufficient access privileges.");  
            tabControl1.SelectedTab = tabPage3;  
        }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void tabControl1_SelectedIndexChanged(  
          System::Object ^ sender,  
          System::EventArgs ^  e)  
       {  
          // Check Credentials Here  
          if ((CredentialCheck->Checked == true) &&  
              (tabControl1->SelectedTab == tabPage2))  
          {  
             tabControl1->SelectedTab = tabPage2;  
          }  
          else if ((CredentialCheck->Checked == false) &&  
                   (tabControl1->SelectedTab == tabPage2))  
          {  
             MessageBox::Show(String::Concat("Unable to load tab. ",  
                "You have insufficient access privileges."));  
             tabControl1->SelectedTab = tabPage3;  
          }  
       }  
    ```  
  
     <span data-ttu-id="8bf02-120">(Visual C#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="8bf02-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8bf02-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8bf02-121">See also</span></span>

- [<span data-ttu-id="8bf02-122">Panoramica del controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="8bf02-122">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="8bf02-123">Procedura: Aggiungere un controllo a una scheda</span><span class="sxs-lookup"><span data-stu-id="8bf02-123">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="8bf02-124">Procedura: Aggiungere e rimuovere schede con TabControl di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8bf02-124">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="8bf02-125">Procedura: Modificare l'aspetto di TabControl di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8bf02-125">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)

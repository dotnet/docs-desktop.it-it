---
title: 'Procedura: Creare impostazioni applicazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], Windows Forms
- application settings [Windows Forms], creating
ms.assetid: 1e7aa347-af75-41e5-89ca-f53cab704f72
ms.openlocfilehash: 1c7bcb5b9166cf8fcb01f11d701ea4ebca713ee7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952139"
---
# <a name="how-to-create-application-settings"></a><span data-ttu-id="cdafe-102">Procedura: Creare impostazioni applicazione</span><span class="sxs-lookup"><span data-stu-id="cdafe-102">How to: Create Application Settings</span></span>

<span data-ttu-id="cdafe-103">Usando il codice gestito, è possibile creare nuove impostazioni dell'applicazione e associarle alle proprietà nel form o nei controlli del form, in modo che queste impostazioni vengano caricate e salvate automaticamente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cdafe-103">Using managed code, you can create new application settings and bind them to properties on your form or your form's controls, so that these settings are loaded and saved automatically at run time.</span></span>  
  
 <span data-ttu-id="cdafe-104">Nella routine seguente, viene creata manualmente una classe wrapper che deriva da <xref:System.Configuration.ApplicationSettingsBase>.</span><span class="sxs-lookup"><span data-stu-id="cdafe-104">In the following procedure, you manually create a wrapper class that derives from <xref:System.Configuration.ApplicationSettingsBase>.</span></span> <span data-ttu-id="cdafe-105">A questa classe è possibile aggiungere una proprietà accessibile pubblicamente per ogni impostazione dell'applicazione da esporre.</span><span class="sxs-lookup"><span data-stu-id="cdafe-105">To this class you add a publicly accessible property for each application setting that you want to expose.</span></span>  
  
 <span data-ttu-id="cdafe-106">È anche possibile eseguire questa routine usando la quantità minima di codice nella finestra di progettazione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cdafe-106">You can also perform this procedure using minimal code in the Visual Studio designer.</span></span>  <span data-ttu-id="cdafe-107">Vedere anche [procedura: creare le impostazioni dell'applicazione usando la finestra di progettazione](/previous-versions/visualstudio/visual-studio-2010/wabtadw6(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="cdafe-107">Also see [How to: Create Application Settings Using the Designer](/previous-versions/visualstudio/visual-studio-2010/wabtadw6(v=vs.100)).</span></span>  
  
### <a name="to-create-new-application-settings-programmatically"></a><span data-ttu-id="cdafe-108">Per creare nuove impostazioni dell'applicazione a livello di codice</span><span class="sxs-lookup"><span data-stu-id="cdafe-108">To create new Application Settings programmatically</span></span>  
  
1. <span data-ttu-id="cdafe-109">Aggiungere una nuova classe al progetto e rinominarlo.</span><span class="sxs-lookup"><span data-stu-id="cdafe-109">Add a new class to your project, and rename it.</span></span> <span data-ttu-id="cdafe-110">Per questa procedura verrà chiamata questa classe `MyUserSettings` .</span><span class="sxs-lookup"><span data-stu-id="cdafe-110">For this procedure, we will call this class `MyUserSettings`.</span></span> <span data-ttu-id="cdafe-111">Modificare la definizione della classe in modo che la classe derivi da <xref:System.Configuration.ApplicationSettingsBase>.</span><span class="sxs-lookup"><span data-stu-id="cdafe-111">Change the class definition so that the class derives from <xref:System.Configuration.ApplicationSettingsBase>.</span></span>  
  
2. <span data-ttu-id="cdafe-112">Definire una proprietà in questa classe wrapper per ogni impostazione dell'applicazione richiesta e applicare la proprietà con <xref:System.Configuration.ApplicationScopedSettingAttribute> o <xref:System.Configuration.UserScopedSettingAttribute>, in base all'ambito dell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="cdafe-112">Define a property on this wrapper class for each application setting you require, and apply that property with either the <xref:System.Configuration.ApplicationScopedSettingAttribute> or <xref:System.Configuration.UserScopedSettingAttribute>, depending on the scope of the setting.</span></span> <span data-ttu-id="cdafe-113">Per ulteriori informazioni sull'ambito delle impostazioni, vedere [Cenni preliminari sulle impostazioni delle applicazioni](application-settings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cdafe-113">For more information about settings scope, see [Application Settings Overview](application-settings-overview.md).</span></span> <span data-ttu-id="cdafe-114">A questo punto, il codice dovrebbe risultare simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="cdafe-114">By now, your code should look like this:</span></span>  
  
     [!code-csharp[ApplicationSettings.Create#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
     [!code-vb[ApplicationSettings.Create#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]  
  
3. <span data-ttu-id="cdafe-115">Creare un'istanza della classe wrapper nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cdafe-115">Create an instance of this wrapper class in your application.</span></span> <span data-ttu-id="cdafe-116">Generalmente è un membro privato del form principale.</span><span class="sxs-lookup"><span data-stu-id="cdafe-116">It will commonly be a private member of the main form.</span></span> <span data-ttu-id="cdafe-117">Dopo aver definito la classe, è necessario associarla a una proprietà. In questo caso, la proprietà <xref:System.Windows.Forms.Form.BackColor%2A> del form.</span><span class="sxs-lookup"><span data-stu-id="cdafe-117">Now that you have defined your class, you need to bind it to a property; in this case, the <xref:System.Windows.Forms.Form.BackColor%2A> property of your form.</span></span> <span data-ttu-id="cdafe-118">È possibile eseguire questa operazione nel `Load` gestore eventi del form.</span><span class="sxs-lookup"><span data-stu-id="cdafe-118">You can accomplish this in your form's `Load` event handler.</span></span>  
  
     [!code-csharp[ApplicationSettings.Create#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#2)]
     [!code-vb[ApplicationSettings.Create#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#2)]  
  
4. <span data-ttu-id="cdafe-119">Se si fornisce un modo per modificare le impostazioni in fase di esecuzione, sarà necessario salvare le impostazioni correnti dell'utente su disco quando il form viene chiuso altrimenti le modifiche andranno perse.</span><span class="sxs-lookup"><span data-stu-id="cdafe-119">If you provide a way to change settings at run time, you will need to save the user's current settings to disk when your form closes, or else these changes will be lost.</span></span>  
  
     [!code-csharp[ApplicationSettings.Create#3](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#3)]
     [!code-vb[ApplicationSettings.Create#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#3)]  
  
     <span data-ttu-id="cdafe-120">È stata creata una nuova impostazione dell’applicazione, che è stata associata correttamente alla proprietà specificata.</span><span class="sxs-lookup"><span data-stu-id="cdafe-120">You have now successfully created a new application setting and bound it to the specified property.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="cdafe-121">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cdafe-121">.NET Framework Security</span></span>  

 <span data-ttu-id="cdafe-122">Il provider di impostazioni predefinito, <xref:System.Configuration.LocalFileSettingsProvider>, memorizza le informazioni nei file di configurazione come testo normale.</span><span class="sxs-lookup"><span data-stu-id="cdafe-122">The default settings provider, <xref:System.Configuration.LocalFileSettingsProvider>, persists information to configuration files as plain text.</span></span> <span data-ttu-id="cdafe-123">Questo riduce la protezione dell'accesso ai file fornito dal sistema operativo per l'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="cdafe-123">This limits security to the file access security provided by the operating system for the current user.</span></span> <span data-ttu-id="cdafe-124">Per questo motivo, è necessario prestare attenzione alle informazioni archiviate nei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="cdafe-124">Because of this, care must be taken with the information stored in configuration files.</span></span> <span data-ttu-id="cdafe-125">Ad esempio, un utilizzo comune per le impostazioni dell'applicazione consiste nell'archiviare le stringhe di connessione che puntano all'archivio dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cdafe-125">For example, one common use for application settings is to store connection strings that point to the application's data store.</span></span> <span data-ttu-id="cdafe-126">Tuttavia, per motivi di sicurezza, queste stringhe non devono includere le password.</span><span class="sxs-lookup"><span data-stu-id="cdafe-126">However, because of security concerns, such strings should not include passwords.</span></span> <span data-ttu-id="cdafe-127">Per altre informazioni sulle stringhe di connessione, vedere <xref:System.Configuration.SpecialSetting>.</span><span class="sxs-lookup"><span data-stu-id="cdafe-127">For more information about connection strings, see <xref:System.Configuration.SpecialSetting>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdafe-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cdafe-128">See also</span></span>

- <xref:System.Configuration.SpecialSettingAttribute>
- <xref:System.Configuration.LocalFileSettingsProvider>
- [<span data-ttu-id="cdafe-129">Cenni preliminari sulle impostazioni delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="cdafe-129">Application Settings Overview</span></span>](application-settings-overview.md)
- [<span data-ttu-id="cdafe-130">Procedura: Convalidare le impostazioni applicazione</span><span class="sxs-lookup"><span data-stu-id="cdafe-130">How to: Validate Application Settings</span></span>](how-to-validate-application-settings.md)

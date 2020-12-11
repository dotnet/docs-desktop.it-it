---
title: Eseguire la migrazione di un'app Windows Forms a .NET 5
description: Informazioni su come trasferire un .NET Framework Windows Forms Application a .NET 5.
ms.date: 11/02/2020
ms.topic: how-to
ms.openlocfilehash: 105c209fc567d2cce70b01267f793152d8140cb8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966013"
---
# <a name="how-to-migrate-a-windows-forms-desktop-app-to-net-5"></a><span data-ttu-id="b13be-103">Come eseguire la migrazione di un'app desktop Windows Forms a .NET 5</span><span class="sxs-lookup"><span data-stu-id="b13be-103">How to migrate a Windows Forms desktop app to .NET 5</span></span>

<span data-ttu-id="b13be-104">Questo articolo descrive come eseguire la migrazione di un'app desktop Windows Forms da .NET Framework a .NET 5 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="b13be-104">This article describes how to migrate a Windows Forms desktop app from .NET Framework to .NET 5 or later.</span></span> <span data-ttu-id="b13be-105">.NET SDK include il supporto per applicazioni Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b13be-105">The .NET SDK includes support for Windows Forms applications.</span></span> <span data-ttu-id="b13be-106">Windows Forms è ancora un framework solo per Windows e supporta l'esecuzione solo in Windows.</span><span class="sxs-lookup"><span data-stu-id="b13be-106">Windows Forms is still a Windows-only framework and only runs on Windows.</span></span>

<span data-ttu-id="b13be-107">La migrazione dell'app da .NET Framework a .NET 5 richiede in genere un nuovo file di progetto.</span><span class="sxs-lookup"><span data-stu-id="b13be-107">Migrating your app from .NET Framework to .NET 5 generally requires a new project file.</span></span> <span data-ttu-id="b13be-108">.NET 5 USA i file di progetto in stile SDK mentre .NET Framework in genere usa il file di progetto di Visual Studio meno recente.</span><span class="sxs-lookup"><span data-stu-id="b13be-108">.NET 5 uses SDK-style project files while .NET Framework typically uses the older Visual Studio project file.</span></span> <span data-ttu-id="b13be-109">Se si è mai aperto un file di progetto di Visual Studio in un editor di testo, è possibile verificare il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="b13be-109">If you've ever opened a Visual Studio project file in a text editor, you know how verbose it is.</span></span> <span data-ttu-id="b13be-110">I progetti in stile SDK sono più piccoli e non richiedono il numero di voci del formato di file di progetto precedente.</span><span class="sxs-lookup"><span data-stu-id="b13be-110">SDK-style projects are smaller and don't require as many entries as the older project file format does.</span></span>

<span data-ttu-id="b13be-111">Per altre informazioni su .NET 5, vedere [Introduzione a .NET](/dotnet/core/introduction).</span><span class="sxs-lookup"><span data-stu-id="b13be-111">To learn more about .NET 5, see [Introduction to .NET](/dotnet/core/introduction).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b13be-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b13be-112">Prerequisites</span></span>

- [<span data-ttu-id="b13be-113">Visual Studio 2019 versione 16,8 Preview</span><span class="sxs-lookup"><span data-stu-id="b13be-113">Visual Studio 2019 version 16.8 Preview</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+winforms)

  - <span data-ttu-id="b13be-114">Selezionare il [carico di lavoro desktop di Visual Studio](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads).</span><span class="sxs-lookup"><span data-stu-id="b13be-114">Select the [Visual Studio Desktop workload](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads).</span></span>

  - <span data-ttu-id="b13be-115">Selezionare il [singolo componente .NET 5](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components).</span><span class="sxs-lookup"><span data-stu-id="b13be-115">Select the [.NET 5 individual component](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components).</span></span>

- <span data-ttu-id="b13be-116">Anteprima di progettazione Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b13be-116">Preview WinForms designer in Visual Studio.</span></span>

  <span data-ttu-id="b13be-117">Per abilitare la finestra di progettazione, passare a **strumenti**  >  **Opzioni**  >  **ambiente**  >  **Anteprima funzionalità** e selezionare l'opzione **usare l'anteprima Windows Forms finestra di progettazione per le app .NET Core** .</span><span class="sxs-lookup"><span data-stu-id="b13be-117">To enable the designer, go to **Tools** > **Options** > **Environment** > **Preview Features** and select the **Use the preview Windows Forms designer for .NET Core apps** option.</span></span>

- <span data-ttu-id="b13be-118">Questo articolo usa l'app di esempio del [gioco corrispondente](https://github.com/dotnet/samples/tree/master/windowsforms/matching-game/net45/) .</span><span class="sxs-lookup"><span data-stu-id="b13be-118">This article uses the [Matching game](https://github.com/dotnet/samples/tree/master/windowsforms/matching-game/net45/) sample app.</span></span> <span data-ttu-id="b13be-119">Se si vuole seguire la procedura, scaricare e aprire l'applicazione in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b13be-119">If you want to follow along, download and open the application in Visual Studio.</span></span> <span data-ttu-id="b13be-120">In caso contrario, usare la propria app.</span><span class="sxs-lookup"><span data-stu-id="b13be-120">Otherwise, use your own app.</span></span>

### <a name="consider"></a><span data-ttu-id="b13be-121">Consider</span><span class="sxs-lookup"><span data-stu-id="b13be-121">Consider</span></span>

<span data-ttu-id="b13be-122">Quando si esegue la migrazione di un .NET Framework Windows Forms Application, è necessario prendere in considerazione alcuni aspetti.</span><span class="sxs-lookup"><span data-stu-id="b13be-122">When migrating a .NET Framework Windows Forms application, there are a few things you must consider.</span></span>

01. <span data-ttu-id="b13be-123">Controllare che l'applicazione sia un buon candidato per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="b13be-123">Check that your application is a good candidate for migration.</span></span>

    <span data-ttu-id="b13be-124">Usare [.NET Portability Analyzer](/dotnet/standard/analyzers/portability-analyzer) per determinare se il progetto verrà migrato a .NET 5.</span><span class="sxs-lookup"><span data-stu-id="b13be-124">Use the [.NET Portability Analyzer](/dotnet/standard/analyzers/portability-analyzer) to determine if your project will migrate to .NET 5.</span></span> <span data-ttu-id="b13be-125">Se nel progetto si verificano problemi con .NET 5, l'analizzatore consente di identificare tali problemi.</span><span class="sxs-lookup"><span data-stu-id="b13be-125">If your project has issues with .NET 5, the analyzer helps you identify those problems.</span></span> <span data-ttu-id="b13be-126">Lo strumento .NET Portability Analyzer può essere installato come estensione di Visual Studio o usato dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b13be-126">The .NET Portability Analyzer tool can be installed as a Visual Studio extension or used from the command line.</span></span> <span data-ttu-id="b13be-127">Per altre informazioni, vedere [.NET Portability Analyzer](/dotnet/standard/analyzers/portability-analyzer).</span><span class="sxs-lookup"><span data-stu-id="b13be-127">For more information, see [.NET Portability Analyzer](/dotnet/standard/analyzers/portability-analyzer).</span></span>

01. <span data-ttu-id="b13be-128">Si usa una versione diversa di Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b13be-128">You're using a different version of Windows Forms.</span></span>

    <span data-ttu-id="b13be-129">Quando è stato rilasciato .NET Core 3,0, Windows Forms è [disponibile in GitHub](https://github.com/dotnet/winforms).</span><span class="sxs-lookup"><span data-stu-id="b13be-129">When .NET Core 3.0 was released, Windows Forms went [open source on GitHub](https://github.com/dotnet/winforms).</span></span> <span data-ttu-id="b13be-130">Il codice per Windows Forms per .NET 5 è un fork della .NET Framework Windows Forms codebase.</span><span class="sxs-lookup"><span data-stu-id="b13be-130">The code for Windows Forms for .NET 5 is a fork of the .NET Framework Windows Forms codebase.</span></span> <span data-ttu-id="b13be-131">È possibile che esistano alcune differenze e che l'app sarà difficile da migrare.</span><span class="sxs-lookup"><span data-stu-id="b13be-131">It's possible some differences exist and your app will be difficult to migrate.</span></span>

01. <span data-ttu-id="b13be-132">[Windows Compatibility Pack][compat-pack] può essere utile per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="b13be-132">The [Windows Compatibility Pack][compat-pack] may help you migrate.</span></span>

    <span data-ttu-id="b13be-133">Alcune API disponibili in .NET Framework non sono disponibili in .NET 5.</span><span class="sxs-lookup"><span data-stu-id="b13be-133">Some APIs that are available in .NET Framework aren't available in .NET 5.</span></span> <span data-ttu-id="b13be-134">[Windows Compatibility Pack][compat-pack] aggiunge molte di queste API e può aiutare l'app Windows Forms a diventare compatibile con .NET 5.</span><span class="sxs-lookup"><span data-stu-id="b13be-134">The [Windows Compatibility Pack][compat-pack] adds many of these APIs and may help your Windows Forms app become compatible with .NET 5.</span></span>

01. <span data-ttu-id="b13be-135">Aggiornare i pacchetti NuGet usati dal progetto.</span><span class="sxs-lookup"><span data-stu-id="b13be-135">Update the NuGet packages used by your project.</span></span>

    <span data-ttu-id="b13be-136">È sempre consigliabile usare le versioni più recenti dei pacchetti NuGet prima di qualsiasi migrazione.</span><span class="sxs-lookup"><span data-stu-id="b13be-136">It's always a good practice to use the latest versions of NuGet packages before any migration.</span></span> <span data-ttu-id="b13be-137">Se l'applicazione fa riferimento a pacchetti NuGet, aggiornarli alla versione più recente.</span><span class="sxs-lookup"><span data-stu-id="b13be-137">If your application is referencing any NuGet packages, update them to the latest version.</span></span> <span data-ttu-id="b13be-138">Verificare che l'applicazione venga compilata correttamente.</span><span class="sxs-lookup"><span data-stu-id="b13be-138">Ensure your application builds successfully.</span></span> <span data-ttu-id="b13be-139">Dopo l'aggiornamento, se sono presenti errori di pacchetto, effettuare il downgrade del pacchetto alla versione più recente che non causa problemi al codice.</span><span class="sxs-lookup"><span data-stu-id="b13be-139">After upgrading, if there are any package errors, downgrade the package to the latest version that doesn't break your code.</span></span>

## <a name="back-up-your-projects"></a><span data-ttu-id="b13be-140">Eseguire il backup dei progetti</span><span class="sxs-lookup"><span data-stu-id="b13be-140">Back up your projects</span></span>

<span data-ttu-id="b13be-141">Il primo passaggio per eseguire la migrazione di un progetto consiste nel eseguire il backup del progetto.</span><span class="sxs-lookup"><span data-stu-id="b13be-141">The first step to migrating a project is to back up your project!</span></span> <span data-ttu-id="b13be-142">Se si verifica un problema, è possibile ripristinare lo stato originale del codice ripristinando il backup.</span><span class="sxs-lookup"><span data-stu-id="b13be-142">If something goes wrong, you can restore your code to its original state by restoring your backup.</span></span> <span data-ttu-id="b13be-143">Non fare affidamento su strumenti come .NET Portability Analyzer per eseguire il backup del progetto, anche se sembrano.</span><span class="sxs-lookup"><span data-stu-id="b13be-143">Don't rely on tools such as the .NET Portability Analyzer to back up your project, even if they seem to.</span></span> <span data-ttu-id="b13be-144">È consigliabile creare personalmente una copia del progetto originale.</span><span class="sxs-lookup"><span data-stu-id="b13be-144">It's best to personally create a copy of the original project.</span></span>

## <a name="nuget-packages"></a><span data-ttu-id="b13be-145">Pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="b13be-145">NuGet packages</span></span>

<span data-ttu-id="b13be-146">Se il progetto fa riferimento a pacchetti NuGet, è probabile che si disponga di un **packages.config** file nella cartella del progetto.</span><span class="sxs-lookup"><span data-stu-id="b13be-146">If your project is referencing NuGet packages, you probably have a **packages.config** file in your project folder.</span></span> <span data-ttu-id="b13be-147">Con i progetti in stile SDK, i riferimenti ai pacchetti NuGet sono configurati nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="b13be-147">With SDK-style projects, NuGet package references are configured in the project file.</span></span> <span data-ttu-id="b13be-148">I file di progetto di Visual Studio possono facoltativamente definire anche i pacchetti NuGet nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="b13be-148">Visual Studio project files can optionally define NuGet packages in the project file too.</span></span> <span data-ttu-id="b13be-149">.NET 5 non usa **packages.config** per i pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="b13be-149">.NET 5 doesn't use **packages.config** for NuGet packages.</span></span> <span data-ttu-id="b13be-150">È necessario eseguire la migrazione dei riferimenti ai pacchetti NuGet nel file di progetto prima della migrazione.</span><span class="sxs-lookup"><span data-stu-id="b13be-150">NuGet package references must be migrated into the project file before migration.</span></span>

<span data-ttu-id="b13be-151">Per eseguire la migrazione del file di **packages.config** , attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="b13be-151">To migrate the **packages.config** file, do the following steps:</span></span>

01. <span data-ttu-id="b13be-152">In **Esplora soluzioni** trovare il progetto di cui si sta eseguendo la migrazione.</span><span class="sxs-lookup"><span data-stu-id="b13be-152">In **Solution explorer**, find the project you're migrating.</span></span>
02. <span data-ttu-id="b13be-153">Fare clic con il pulsante destro del mouse su **packages.config**  >  **migrare packages.config a PackageReference**.</span><span class="sxs-lookup"><span data-stu-id="b13be-153">Right-click on **packages.config** > **Migrate packages.config to PackageReference**.</span></span>
03. <span data-ttu-id="b13be-154">Selezionare tutti i pacchetti di primo livello.</span><span class="sxs-lookup"><span data-stu-id="b13be-154">Select all of the top-level packages.</span></span>

<span data-ttu-id="b13be-155">Viene generato un report di compilazione che consente di individuare eventuali problemi di migrazione dei pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="b13be-155">A build report is generated to let you know of any issues migrating the NuGet packages.</span></span>

## <a name="project-file"></a><span data-ttu-id="b13be-156">File di progetto</span><span class="sxs-lookup"><span data-stu-id="b13be-156">Project file</span></span>

<span data-ttu-id="b13be-157">Il passaggio successivo per la migrazione dell'app consiste nel convertire il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="b13be-157">The next step in migrating your app is converting the project file.</span></span> <span data-ttu-id="b13be-158">Come indicato in precedenza, .NET 5 USA i file di progetto in stile SDK e non carica i file di progetto di Visual Studio utilizzati .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b13be-158">As previously stated, .NET 5 uses SDK-style project files and won't load the Visual Studio project files that .NET Framework uses.</span></span> <span data-ttu-id="b13be-159">Tuttavia, è possibile che si stiano già usando progetti in stile SDK.</span><span class="sxs-lookup"><span data-stu-id="b13be-159">However, there's the possibility that you're already using SDK-style projects.</span></span> <span data-ttu-id="b13be-160">È possibile individuare facilmente la differenza in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b13be-160">You can easily spot the difference in Visual Studio.</span></span> <span data-ttu-id="b13be-161">Fare clic con il pulsante destro del mouse sul file di progetto in **Esplora soluzioni** e cercare l'opzione di menu **modifica file di progetto** .</span><span class="sxs-lookup"><span data-stu-id="b13be-161">Right-click on the project file in **Solution explorer** and look for the **Edit Project File** menu option.</span></span> <span data-ttu-id="b13be-162">Se questa voce di menu non è presente, si sta usando il vecchio formato di progetto di Visual Studio ed è necessario eseguire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="b13be-162">If this menu item is missing, you're using the old Visual Studio project format and need to upgrade.</span></span>

<span data-ttu-id="b13be-163">Convertire ogni progetto nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="b13be-163">Convert each project in your solution.</span></span> <span data-ttu-id="b13be-164">Se si usa l'app di esempio a cui si fa riferimento in precedenza, i progetti **digitare MatchingGame** e **digitare MatchingGame. Logic** verranno convertiti.</span><span class="sxs-lookup"><span data-stu-id="b13be-164">If you're using the sample app previously referenced, both the **MatchingGame** and **MatchingGame.Logic** projects would be converted.</span></span>

<span data-ttu-id="b13be-165">Per convertire un progetto, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="b13be-165">To convert a project, do the following steps:</span></span>

01. <span data-ttu-id="b13be-166">In **Esplora soluzioni** trovare il progetto di cui si sta eseguendo la migrazione.</span><span class="sxs-lookup"><span data-stu-id="b13be-166">In **Solution explorer**, find the project you're migrating.</span></span>
01. <span data-ttu-id="b13be-167">Fare clic con il pulsante destro del mouse sul progetto e scegliere **Scarica progetto**.</span><span class="sxs-lookup"><span data-stu-id="b13be-167">Right-click on the project and select **Unload Project**.</span></span>
01. <span data-ttu-id="b13be-168">Fare clic con il pulsante destro del mouse sul progetto e scegliere **modifica file di progetto**.</span><span class="sxs-lookup"><span data-stu-id="b13be-168">Right-click on the project and select **Edit Project File**.</span></span>
01. <span data-ttu-id="b13be-169">Copiare e incollare il codice XML del progetto in un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="b13be-169">Copy-and-paste the project XML into a text editor.</span></span> <span data-ttu-id="b13be-170">È necessario disporre di una copia per facilitare lo spostamento del contenuto nel nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="b13be-170">You'll want a copy so that it's easy to move content into the new project.</span></span>
01. <span data-ttu-id="b13be-171">Cancellare il contenuto del file e incollare il codice XML seguente:</span><span class="sxs-lookup"><span data-stu-id="b13be-171">Erase the content of the file and paste the following XML:</span></span>

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">

      <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>net5.0-windows</TargetFramework>
        <UseWindowsForms>true</UseWindowsForms>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
      </PropertyGroup>

    </Project>
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="b13be-172">Le librerie non devono definire un' `<OutputType>` impostazione.</span><span class="sxs-lookup"><span data-stu-id="b13be-172">Libraries don't need to define an `<OutputType>` setting.</span></span> <span data-ttu-id="b13be-173">Rimuovere la voce se si sta aggiornando un progetto di libreria.</span><span class="sxs-lookup"><span data-stu-id="b13be-173">Remove that entry if you're upgrading a library project.</span></span>

<span data-ttu-id="b13be-174">Questo codice XML fornisce la struttura di base del progetto.</span><span class="sxs-lookup"><span data-stu-id="b13be-174">This XML gives you the basic structure of the project.</span></span> <span data-ttu-id="b13be-175">Tuttavia, non contiene alcuna impostazione del vecchio file di progetto.</span><span class="sxs-lookup"><span data-stu-id="b13be-175">However, it doesn't contain any of the settings from the old project file.</span></span> <span data-ttu-id="b13be-176">Utilizzando le informazioni del progetto precedenti copiate in precedenza in un editor di testo, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="b13be-176">Using the old project information you previously copied to a text editor, do the following steps:</span></span>

01. <span data-ttu-id="b13be-177">Copiare gli elementi seguenti dal file di progetto precedente nell' `<PropertyGroup>` elemento nel nuovo file di progetto:</span><span class="sxs-lookup"><span data-stu-id="b13be-177">Copy the following elements from the old project file into the `<PropertyGroup>` element in the new project file:</span></span>

    - `<RootNamespace>`
    - `<AssemblyName>`

    <span data-ttu-id="b13be-178">Il file di progetto dovrebbe avere un aspetto simile al codice XML seguente:</span><span class="sxs-lookup"><span data-stu-id="b13be-178">Your project file should look similar to the following XML:</span></span>

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">

      <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>net5.0-windows</TargetFramework>
        <UseWindowsForms>true</UseWindowsForms>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>

        <RootNamespace>MatchingGame</RootNamespace>
        <AssemblyName>MatchingGame</AssemblyName>
      </PropertyGroup>

    </Project>
    ```

01. <span data-ttu-id="b13be-179">Copiare gli `<ItemGroup>` elementi del vecchio file di progetto che contiene `<ProjectReference>` o `<PackageReference>` nel nuovo file dopo il `</PropertyGroup>` tag di chiusura.</span><span class="sxs-lookup"><span data-stu-id="b13be-179">Copy the `<ItemGroup>` elements from the old project file that contain `<ProjectReference>` or `<PackageReference>` into the new file after the `</PropertyGroup>` closing tag.</span></span>

    <span data-ttu-id="b13be-180">Il file di progetto dovrebbe avere un aspetto simile al codice XML seguente:</span><span class="sxs-lookup"><span data-stu-id="b13be-180">Your project file should look similar to the following XML:</span></span>

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">

      <PropertyGroup>
        (contains settings previously described)
      </PropertyGroup>

      <ItemGroup>
        <ProjectReference Include="..\MatchingGame.Logic\MatchingGame.Logic.csproj">
          <Project>{36b3e6e2-a9ae-4924-89ae-7f0120ce08bd}</Project>
          <Name>MatchingGame.Logic</Name>
        </ProjectReference>
      </ItemGroup>
      <ItemGroup>
        <PackageReference Include="MetroFramework">
          <Version>1.2.0.3</Version>
        </PackageReference>
      </ItemGroup>

    </Project>
    ```

    <span data-ttu-id="b13be-181">`<ProjectReference>`Per gli elementi non sono necessari gli elementi `<Project>` `<Name>` figlio e, pertanto è possibile rimuovere le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b13be-181">The `<ProjectReference>` elements don't need the `<Project>` and `<Name>` children, so you can remove those settings:</span></span>

    ```xml
    <ItemGroup>
      <ProjectReference Include="..\MatchingGame.Logic\MatchingGame.Logic.csproj" />
    </ItemGroup>
    ```

### <a name="resources-and-settings"></a><span data-ttu-id="b13be-182">Risorse e impostazioni</span><span class="sxs-lookup"><span data-stu-id="b13be-182">Resources and settings</span></span>

<span data-ttu-id="b13be-183">I progetti Windows Forms per .NET Framework includono in genere altri file, ad esempio *Proprietà/impostazioni. Settings* e *Properties/resources. resx*.</span><span class="sxs-lookup"><span data-stu-id="b13be-183">Windows Forms projects for .NET Framework typically include other files such as *Properties/Settings.settings* and *Properties/Resources.resx*.</span></span> <span data-ttu-id="b13be-184">È necessario eseguire la migrazione di questi file e di qualsiasi file *resx* creato per l'app oltre ai file *resx* di form.</span><span class="sxs-lookup"><span data-stu-id="b13be-184">These files, and any *resx* file created for your app besides form *resx* files, would need to be migrated.</span></span>

<span data-ttu-id="b13be-185">Copiare le voci dal file di progetto precedente in un `<ItemGroup>` elemento del nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="b13be-185">Copy those entries from the old project file into an `<ItemGroup>` element in the new project.</span></span> <span data-ttu-id="b13be-186">Dopo aver copiato le voci, modificare qualsiasi `<Compile Include="value">` `<EmbeddedResource Include="value">` elemento o in modo da usare invece `Update` di `Include` .</span><span class="sxs-lookup"><span data-stu-id="b13be-186">After you copy the entries, change any `<Compile Include="value">` or `<EmbeddedResource Include="value">` elements to instead use `Update` instead of `Include`.</span></span>

- <span data-ttu-id="b13be-187">Importare la configurazione per il file *Settings. Settings* .</span><span class="sxs-lookup"><span data-stu-id="b13be-187">Import the configuration for the *Settings.settings* file.</span></span> <span data-ttu-id="b13be-188">Si noti che `Include` è stato modificato in nell' `Update` `<Compile>` elemento:</span><span class="sxs-lookup"><span data-stu-id="b13be-188">Notice that the `Include` was changed to `Update` on the `<Compile>` element:</span></span>

  ```xml
  <ItemGroup>
    <None Include="Properties\Settings.settings">
      <Generator>SettingsSingleFileGenerator</Generator>
      <LastGenOutput>Settings.Designer.cs</LastGenOutput>
    </None>
    <Compile Update="Properties\Settings.Designer.cs">
      <AutoGen>True</AutoGen>
      <DependentUpon>Settings.settings</DependentUpon>
      <DesignTimeSharedInput>True</DesignTimeSharedInput>
    </Compile>
  </ItemGroup>
  ```

  > [!IMPORTANT]
  > <span data-ttu-id="b13be-189">I progetti **Visual Basic** usano in genere la cartella *My Project* mentre i progetti C# usano in genere le *proprietà* della cartella per il file di impostazioni del progetto predefinito.</span><span class="sxs-lookup"><span data-stu-id="b13be-189">**Visual Basic** projects typically use the folder *My Project* while C# projects typically use the folder *Properties* for the default project settings file.</span></span>
  
- <span data-ttu-id="b13be-190">Importare la configurazione per qualsiasi file *resx* , ad esempio il file *Properties/resources. resx* .</span><span class="sxs-lookup"><span data-stu-id="b13be-190">Import the configuration for any *resx* file, such as the *properties/Resources.resx* file.</span></span> <span data-ttu-id="b13be-191">Si noti che `Include` è stato modificato in `Update` in entrambi `<Compile>` gli `<EmbeddedResource>` elementi e ed `<SubType>` è stato rimosso da `<EmbeddedResource>` :</span><span class="sxs-lookup"><span data-stu-id="b13be-191">Notice that the `Include` was changed to `Update` on both the `<Compile>` and `<EmbeddedResource>` elements, and `<SubType>` was removed from `<EmbeddedResource>`:</span></span>

  ```xml
  <ItemGroup>
    <EmbeddedResource Update="Properties\Resources.resx">
      <Generator>ResXFileCodeGenerator</Generator>
      <LastGenOutput>Resources.Designer.cs</LastGenOutput>
    </EmbeddedResource>
    <Compile Update="Properties\Resources.Designer.cs">
      <AutoGen>True</AutoGen>
      <DependentUpon>Resources.resx</DependentUpon>
      <DesignTime>True</DesignTime>
    </Compile>
  </ItemGroup>
  ```

  > [!IMPORTANT]
  > <span data-ttu-id="b13be-192">I progetti **Visual Basic** usano in genere la cartella *My Project* mentre i progetti C# usano in genere le *proprietà* della cartella per il file di risorse del progetto predefinito.</span><span class="sxs-lookup"><span data-stu-id="b13be-192">**Visual Basic** projects typically use the folder *My Project* while C# projects typically use the folder *Properties* for the default project resource file.</span></span>

### <a name="visual-basic"></a><span data-ttu-id="b13be-193">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b13be-193">Visual Basic</span></span>

<span data-ttu-id="b13be-194">I progetti di linguaggio Visual Basic richiedono una configurazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="b13be-194">Visual Basic language projects require extra configuration.</span></span>

01. <span data-ttu-id="b13be-195">Importare il file di configurazione *Project\Application.myapp* l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="b13be-195">Import the configuration file *My Project\Application.myapp* setting.</span></span> <span data-ttu-id="b13be-196">Si noti che `<None>` gli `<Compile>` elementi e utilizzano l' `Update` attributo anziché l' `Include` attributo.</span><span class="sxs-lookup"><span data-stu-id="b13be-196">Notice that the `<None>` and `<Compile>` elements use the `Update` attribute instead of the `Include` attribute.</span></span>

    ```xml
    <ItemGroup>
      <None Update="My Project\Application.myapp">
        <Generator>MyApplicationCodeGenerator</Generator>
        <LastGenOutput>Application.Designer.vb</LastGenOutput>
      </None>
      <Compile Update="My Project\Application.Designer.vb">
        <AutoGen>True</AutoGen>
        <DependentUpon>Application.myapp</DependentUpon>
        <DesignTime>True</DesignTime>
      </Compile>
    </ItemGroup>
    ```

01. <span data-ttu-id="b13be-197">Aggiungere l' `<MyType>WindowsForms</MyType>` impostazione all' `<PropertyGroup>` elemento:</span><span class="sxs-lookup"><span data-stu-id="b13be-197">Add the `<MyType>WindowsForms</MyType>` setting to the `<PropertyGroup>` element:</span></span>

    ```xml
    <PropertyGroup>
      (contains settings previously described)

      <MyType>WindowsForms</MyType>
    </PropertyGroup>
    ```

    <span data-ttu-id="b13be-198">Questa impostazione importa i `My` membri dello spazio dei nomi Visual Basic i programmatori hanno familiarità con.</span><span class="sxs-lookup"><span data-stu-id="b13be-198">This setting imports the `My` namespace members Visual Basic programmers are familiar with.</span></span>

01. <span data-ttu-id="b13be-199">Importare gli spazi dei nomi definiti dal progetto.</span><span class="sxs-lookup"><span data-stu-id="b13be-199">Import the namespaces defined by your project.</span></span>

    <span data-ttu-id="b13be-200">Visual Basic progetti possono importare automaticamente spazi dei nomi in ogni file di codice.</span><span class="sxs-lookup"><span data-stu-id="b13be-200">Visual Basic projects can automatically import namespaces into every code file.</span></span> <span data-ttu-id="b13be-201">Copiare gli `<ItemGroup>` elementi del vecchio file di progetto che contengono `<Import>` nel nuovo file dopo il `</PropertyGroup>` tag di chiusura.</span><span class="sxs-lookup"><span data-stu-id="b13be-201">Copy the `<ItemGroup>` elements from the old project file that contain `<Import>` into the new file after the `</PropertyGroup>` closing tag.</span></span>

    ```xml
    <ItemGroup>
      <Import Include="Microsoft.VisualBasic" />
      <Import Include="System" />
      <Import Include="System.Collections" />
      <Import Include="System.Collections.Generic" />
      <Import Include="System.Data" />
      <Import Include="System.Drawing" />
      <Import Include="System.Diagnostics" />
      <Import Include="System.Windows.Forms" />
      <Import Include="System.Linq" />
      <Import Include="System.Xml.Linq" />
      <Import Include="System.Threading.Tasks" />
    </ItemGroup>
    ```

    <span data-ttu-id="b13be-202">Se non si riesce `<Import>` a trovare istruzioni o se il progetto non viene compilato, assicurarsi di avere almeno le seguenti `<Import>` istruzioni definite nel progetto:</span><span class="sxs-lookup"><span data-stu-id="b13be-202">If you can't find any `<Import>` statements, or your project fails to compile, make sure you at least have the following `<Import>` statements defined in your project:</span></span>

    ```xml
    <ItemGroup>
      <Import Include="System.Data" />
      <Import Include="System.Drawing" />
      <Import Include="System.Windows.Forms" />
    </ItemGroup>
    ```

01. <span data-ttu-id="b13be-203">Dal progetto originale, copiare le `<Option*>` Impostazioni e nell' `<StartupObject>` `<PropertyGroup>` elemento:</span><span class="sxs-lookup"><span data-stu-id="b13be-203">From the original project, copy the `<Option*>` and `<StartupObject>` settings to the `<PropertyGroup>` element:</span></span>

    ```xml
    <PropertyGroup>
      (contains settings previously described)

      <OptionExplicit>On</OptionExplicit>
      <OptionCompare>Binary</OptionCompare>
      <OptionStrict>Off</OptionStrict>
      <OptionInfer>On</OptionInfer>
      <StartupObject>MatchingGame.My.MyApplication</StartupObject>
    </PropertyGroup>
    ```

### <a name="reload-the-project"></a><span data-ttu-id="b13be-204">Ricarica il progetto</span><span class="sxs-lookup"><span data-stu-id="b13be-204">Reload the project</span></span>

<span data-ttu-id="b13be-205">Dopo aver convertito un progetto nel nuovo formato di tipo SDK, ricaricare il progetto in Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="b13be-205">After you convert a project to the new SDK-style format, reload the project in Visual Studio:</span></span>

01. <span data-ttu-id="b13be-206">In **Esplora soluzioni** individuare il progetto che è stato convertito.</span><span class="sxs-lookup"><span data-stu-id="b13be-206">In **Solution Explorer**, find the project you converted.</span></span>
01. <span data-ttu-id="b13be-207">Fare clic con il pulsante destro del mouse sul progetto e selezionare **Ricarica progetto**.</span><span class="sxs-lookup"><span data-stu-id="b13be-207">Right-click on the project and select **Reload Project**.</span></span>

    <span data-ttu-id="b13be-208">Se il caricamento del progetto non riesce, è possibile che sia stato introdotto un errore nel codice XML del progetto.</span><span class="sxs-lookup"><span data-stu-id="b13be-208">If the project fails to load, you may have introduced a mistake in the XML of the project.</span></span> <span data-ttu-id="b13be-209">Aprire il file di progetto per la modifica e provare a identificare e correggere l'errore.</span><span class="sxs-lookup"><span data-stu-id="b13be-209">Open the project file for editing and try to identify and fix the mistake.</span></span> <span data-ttu-id="b13be-210">Se non si riesce a trovare un errore, provare a ricominciare.</span><span class="sxs-lookup"><span data-stu-id="b13be-210">If you can't find a mistake, try starting over.</span></span>

## <a name="edit-appconfig"></a><span data-ttu-id="b13be-211">Modifica App.config</span><span class="sxs-lookup"><span data-stu-id="b13be-211">Edit App.config</span></span>

<span data-ttu-id="b13be-212">Se l'app contiene un file di *App.config* , rimuovere l' `<supportedRuntime>` elemento:</span><span class="sxs-lookup"><span data-stu-id="b13be-212">If your app has an *App.config* file, remove the `<supportedRuntime>` element:</span></span>

```xml
<supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
```

<span data-ttu-id="b13be-213">È necessario considerare alcune considerazioni con il file di *App.config* .</span><span class="sxs-lookup"><span data-stu-id="b13be-213">There are some things you should consider with the *App.config* file.</span></span> <span data-ttu-id="b13be-214">Il file di *App.config* in .NET Framework è stato usato non solo per configurare l'app, ma per configurare le impostazioni e il comportamento di runtime, ad esempio la registrazione.</span><span class="sxs-lookup"><span data-stu-id="b13be-214">The *App.config* file in .NET Framework was used not only to configure the app, but to configure runtime settings and behavior, such as logging.</span></span> <span data-ttu-id="b13be-215">Il file di *App.config* in .NET 5 + (e .NET Core) non viene più usato per la configurazione del runtime.</span><span class="sxs-lookup"><span data-stu-id="b13be-215">The *App.config* file in .NET 5+ (and .NET Core) is no longer used for runtime configuration.</span></span> <span data-ttu-id="b13be-216">Se il file di *App.config* contiene queste sezioni, non verranno rispettate.</span><span class="sxs-lookup"><span data-stu-id="b13be-216">If your *App.config* file has these sections, they won't be respected.</span></span>

## <a name="add-the-compatibility-package"></a><span data-ttu-id="b13be-217">Aggiungere il pacchetto di compatibilità</span><span class="sxs-lookup"><span data-stu-id="b13be-217">Add the compatibility package</span></span>

<span data-ttu-id="b13be-218">Se il file di progetto viene caricato correttamente, ma la compilazione ha esito negativo per il progetto e vengono visualizzati errori simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="b13be-218">If your project file is loading correctly, but compilation fails for your project and you receive errors similar to the following:</span></span>

- <span data-ttu-id="b13be-219">**Il tipo o lo spazio dei nomi \<some name> non è stato trovato**</span><span class="sxs-lookup"><span data-stu-id="b13be-219">**The type or namespace \<some name> could not be found**</span></span>
- <span data-ttu-id="b13be-220">**Il nome non \<some name> esiste nel contesto corrente**</span><span class="sxs-lookup"><span data-stu-id="b13be-220">**The name \<some name> does not exist in the current context**</span></span>

<span data-ttu-id="b13be-221">Potrebbe essere necessario aggiungere il [`Microsoft.Windows.Compatibility`](https://www.nuget.org/packages/Microsoft.Windows.Compatibility/) pacchetto all'app.</span><span class="sxs-lookup"><span data-stu-id="b13be-221">You may need to add the [`Microsoft.Windows.Compatibility`](https://www.nuget.org/packages/Microsoft.Windows.Compatibility/) package to your app.</span></span> <span data-ttu-id="b13be-222">Questo pacchetto aggiunge le API .NET di ~ 21.000 da .NET Framework, ad esempio la `System.Configuration.ConfigurationManager` classe e le API per interagire con il registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="b13be-222">This package adds ~21,000 .NET APIs from .NET Framework, such as the `System.Configuration.ConfigurationManager` class and APIs for interacting with the Windows Registry.</span></span> <span data-ttu-id="b13be-223">Aggiungere il pacchetto `Microsoft.Windows.Compatibility`.</span><span class="sxs-lookup"><span data-stu-id="b13be-223">Add the `Microsoft.Windows.Compatibility` package.</span></span>

<span data-ttu-id="b13be-224">Modificare il file di progetto e aggiungere l' `<ItemGroup>` elemento seguente:</span><span class="sxs-lookup"><span data-stu-id="b13be-224">Edit your project file and add the following `<ItemGroup>` element:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.Windows.Compatibility" Version="5.0.0" />
</ItemGroup>
```

## <a name="test-your-app"></a><span data-ttu-id="b13be-225">Test dell'app</span><span class="sxs-lookup"><span data-stu-id="b13be-225">Test your app</span></span>

<span data-ttu-id="b13be-226">Al termine della migrazione dell'app, eseguirne il test.</span><span class="sxs-lookup"><span data-stu-id="b13be-226">After you've finished migrating your app, test it!</span></span>

## <a name="next-steps"></a><span data-ttu-id="b13be-227">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b13be-227">Next steps</span></span>

- <span data-ttu-id="b13be-228">Informazioni sulle [modifiche di rilievo in Windows Forms](/dotnet/core/compatibility/winforms).</span><span class="sxs-lookup"><span data-stu-id="b13be-228">Learn about [breaking changes in Windows Forms](/dotnet/core/compatibility/winforms).</span></span>
- <span data-ttu-id="b13be-229">Vedere altre informazioni su [Windows Compatibility Pack][compat-pack].</span><span class="sxs-lookup"><span data-stu-id="b13be-229">Read more about the [Windows Compatibility Pack][compat-pack].</span></span>

[compat-pack]: /dotnet/core/porting/windows-compat-pack

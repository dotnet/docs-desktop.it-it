---
title: Eseguire la migrazione di un'app Windows Form a .NET 5
description: Informazioni su come trasferire un .NET Framework Windows Forms Application a .NET 5.
ms.date: 11/02/2020
ms.topic: how-to
ms.openlocfilehash: adf87df169217a5d190338bf9c4beaec873f0b69
ms.sourcegitcommit: d7d89e96c827b6e20d9353d34c0aa329fdae0144
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506711"
---
# <a name="how-to-migrate-a-windows-forms-desktop-app-to-net-5"></a><span data-ttu-id="b90a5-103">Come eseguire la migrazione di un'app desktop Windows Form a .NET 5</span><span class="sxs-lookup"><span data-stu-id="b90a5-103">How to migrate a Windows Forms desktop app to .NET 5</span></span>

<span data-ttu-id="b90a5-104">Questo articolo descrive come eseguire la migrazione di un'app desktop Windows Form da .NET Framework a .NET 5 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="b90a5-104">This article describes how to migrate a Windows Forms desktop app from .NET Framework to .NET 5 or later.</span></span> <span data-ttu-id="b90a5-105">.NET SDK include il supporto per applicazioni Windows Form.</span><span class="sxs-lookup"><span data-stu-id="b90a5-105">The .NET SDK includes support for Windows Forms applications.</span></span> <span data-ttu-id="b90a5-106">Windows Forms è ancora un framework solo per Windows e supporta l'esecuzione solo in Windows.</span><span class="sxs-lookup"><span data-stu-id="b90a5-106">Windows Forms is still a Windows-only framework and only runs on Windows.</span></span>

<span data-ttu-id="b90a5-107">La migrazione dell'app da .NET Framework a .NET 5 richiede in genere un nuovo file di progetto.</span><span class="sxs-lookup"><span data-stu-id="b90a5-107">Migrating your app from .NET Framework to .NET 5 generally requires a new project file.</span></span> <span data-ttu-id="b90a5-108">.NET 5 USA i file di progetto in stile SDK mentre .NET Framework in genere usa il file di progetto di Visual Studio meno recente.</span><span class="sxs-lookup"><span data-stu-id="b90a5-108">.NET 5 uses SDK-style project files while .NET Framework typically uses the older Visual Studio project file.</span></span> <span data-ttu-id="b90a5-109">Se si è mai aperto un file di progetto di Visual Studio in un editor di testo, è possibile verificare il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="b90a5-109">If you've ever opened a Visual Studio project file in a text editor, you know how verbose it is.</span></span> <span data-ttu-id="b90a5-110">I progetti in stile SDK sono più piccoli e non richiedono il numero di voci del formato di file di progetto precedente.</span><span class="sxs-lookup"><span data-stu-id="b90a5-110">SDK-style projects are smaller and don't require as many entries as the older project file format does.</span></span>

<span data-ttu-id="b90a5-111">Per altre informazioni su .NET 5, vedere [Introduzione a .NET](/dotnet/core/introduction).</span><span class="sxs-lookup"><span data-stu-id="b90a5-111">To learn more about .NET 5, see [Introduction to .NET](/dotnet/core/introduction).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b90a5-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b90a5-112">Prerequisites</span></span>

- [<span data-ttu-id="b90a5-113">Visual Studio 2019 versione 16,8 Preview</span><span class="sxs-lookup"><span data-stu-id="b90a5-113">Visual Studio 2019 version 16.8 Preview</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+winforms)

  - <span data-ttu-id="b90a5-114">Selezionare il [carico di lavoro desktop di Visual Studio](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads).</span><span class="sxs-lookup"><span data-stu-id="b90a5-114">Select the [Visual Studio Desktop workload](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads).</span></span>

  - <span data-ttu-id="b90a5-115">Selezionare il [singolo componente .NET 5](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components).</span><span class="sxs-lookup"><span data-stu-id="b90a5-115">Select the [.NET 5 individual component](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components).</span></span>

- <span data-ttu-id="b90a5-116">Anteprima di progettazione Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b90a5-116">Preview WinForms designer in Visual Studio.</span></span>

  <span data-ttu-id="b90a5-117">Per abilitare la finestra di progettazione, passare a **strumenti**  >  **Opzioni**  >  **ambiente**  >  **Anteprima funzionalità** e selezionare l'opzione **usare l'anteprima Windows form finestra di progettazione per le app .NET Core** .</span><span class="sxs-lookup"><span data-stu-id="b90a5-117">To enable the designer, go to **Tools** > **Options** > **Environment** > **Preview Features** and select the **Use the preview Windows Forms designer for .NET Core apps** option.</span></span>

- <span data-ttu-id="b90a5-118">Questo articolo usa l'app di esempio del [gioco corrispondente](https://github.com/dotnet/samples/tree/master/windowsforms/matching-game/net45/) .</span><span class="sxs-lookup"><span data-stu-id="b90a5-118">This article uses the [Matching game](https://github.com/dotnet/samples/tree/master/windowsforms/matching-game/net45/) sample app.</span></span> <span data-ttu-id="b90a5-119">Se si vuole seguire la procedura, scaricare e aprire l'applicazione in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b90a5-119">If you want to follow along, download and open the application in Visual Studio.</span></span> <span data-ttu-id="b90a5-120">In caso contrario, usare la propria app.</span><span class="sxs-lookup"><span data-stu-id="b90a5-120">Otherwise, use your own app.</span></span>

### <a name="consider"></a><span data-ttu-id="b90a5-121">Consider</span><span class="sxs-lookup"><span data-stu-id="b90a5-121">Consider</span></span>

<span data-ttu-id="b90a5-122">Quando si esegue la migrazione di un .NET Framework Windows Forms Application, è necessario prendere in considerazione alcuni aspetti.</span><span class="sxs-lookup"><span data-stu-id="b90a5-122">When migrating a .NET Framework Windows Forms application, there are a few things you must consider.</span></span>

01. <span data-ttu-id="b90a5-123">Controllare che l'applicazione sia un buon candidato per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="b90a5-123">Check that your application is a good candidate for migration.</span></span>

    <span data-ttu-id="b90a5-124">Usare [.NET Portability Analyzer](/dotnet/standard/analyzers/portability-analyzer) per determinare se il progetto verrà migrato a .NET 5.</span><span class="sxs-lookup"><span data-stu-id="b90a5-124">Use the [.NET Portability Analyzer](/dotnet/standard/analyzers/portability-analyzer) to determine if your project will migrate to .NET 5.</span></span> <span data-ttu-id="b90a5-125">Se nel progetto si verificano problemi con .NET 5, l'analizzatore consente di identificare tali problemi.</span><span class="sxs-lookup"><span data-stu-id="b90a5-125">If your project has issues with .NET 5, the analyzer helps you identify those problems.</span></span> <span data-ttu-id="b90a5-126">Lo strumento .NET Portability Analyzer può essere installato come estensione di Visual Studio o usato dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b90a5-126">The .NET Portability Analyzer tool can be installed as a Visual Studio extension or used from the command line.</span></span> <span data-ttu-id="b90a5-127">Per altre informazioni, vedere [.NET Portability Analyzer](/dotnet/standard/analyzers/portability-analyzer).</span><span class="sxs-lookup"><span data-stu-id="b90a5-127">For more information, see [.NET Portability Analyzer](/dotnet/standard/analyzers/portability-analyzer).</span></span>

01. <span data-ttu-id="b90a5-128">Si usa una versione diversa di Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b90a5-128">You're using a different version of Windows Forms.</span></span>

    <span data-ttu-id="b90a5-129">Quando è stato rilasciato .NET Core 3,0, Windows Form è [disponibile in GitHub](https://github.com/dotnet/winforms).</span><span class="sxs-lookup"><span data-stu-id="b90a5-129">When .NET Core 3.0 was released, Windows Forms went [open source on GitHub](https://github.com/dotnet/winforms).</span></span> <span data-ttu-id="b90a5-130">Il codice per Windows Form per .NET 5 è un fork della .NET Framework Windows Form codebase.</span><span class="sxs-lookup"><span data-stu-id="b90a5-130">The code for Windows Forms for .NET 5 is a fork of the .NET Framework Windows Forms codebase.</span></span> <span data-ttu-id="b90a5-131">È possibile che esistano alcune differenze e che l'app sarà difficile da migrare.</span><span class="sxs-lookup"><span data-stu-id="b90a5-131">It's possible some differences exist and your app will be difficult to migrate.</span></span>

01. <span data-ttu-id="b90a5-132">[Windows Compatibility Pack][compat-pack] può essere utile per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="b90a5-132">The [Windows Compatibility Pack][compat-pack] may help you migrate.</span></span>

    <span data-ttu-id="b90a5-133">Alcune API disponibili in .NET Framework non sono disponibili in .NET 5.</span><span class="sxs-lookup"><span data-stu-id="b90a5-133">Some APIs that are available in .NET Framework aren't available in .NET 5.</span></span> <span data-ttu-id="b90a5-134">[Windows Compatibility Pack][compat-pack] aggiunge molte di queste API e può aiutare l'app Windows Form a diventare compatibile con .NET 5.</span><span class="sxs-lookup"><span data-stu-id="b90a5-134">The [Windows Compatibility Pack][compat-pack] adds many of these APIs and may help your Windows Forms app become compatible with .NET 5.</span></span>

01. <span data-ttu-id="b90a5-135">Aggiornare i pacchetti NuGet usati dal progetto.</span><span class="sxs-lookup"><span data-stu-id="b90a5-135">Update the NuGet packages used by your project.</span></span>

    <span data-ttu-id="b90a5-136">È sempre consigliabile usare le versioni più recenti dei pacchetti NuGet prima di qualsiasi migrazione.</span><span class="sxs-lookup"><span data-stu-id="b90a5-136">It's always a good practice to use the latest versions of NuGet packages before any migration.</span></span> <span data-ttu-id="b90a5-137">Se l'applicazione fa riferimento a pacchetti NuGet, aggiornarli alla versione più recente.</span><span class="sxs-lookup"><span data-stu-id="b90a5-137">If your application is referencing any NuGet packages, update them to the latest version.</span></span> <span data-ttu-id="b90a5-138">Verificare che l'applicazione venga compilata correttamente.</span><span class="sxs-lookup"><span data-stu-id="b90a5-138">Ensure your application builds successfully.</span></span> <span data-ttu-id="b90a5-139">Dopo l'aggiornamento, se sono presenti errori di pacchetto, effettuare il downgrade del pacchetto alla versione più recente che non causa problemi al codice.</span><span class="sxs-lookup"><span data-stu-id="b90a5-139">After upgrading, if there are any package errors, downgrade the package to the latest version that doesn't break your code.</span></span>

## <a name="back-up-your-projects"></a><span data-ttu-id="b90a5-140">Eseguire il backup dei progetti</span><span class="sxs-lookup"><span data-stu-id="b90a5-140">Back up your projects</span></span>

<span data-ttu-id="b90a5-141">Il primo passaggio per eseguire la migrazione di un progetto consiste nel eseguire il backup del progetto.</span><span class="sxs-lookup"><span data-stu-id="b90a5-141">The first step to migrating a project is to back up your project!</span></span> <span data-ttu-id="b90a5-142">Se si verifica un problema, è possibile ripristinare lo stato originale del codice ripristinando il backup.</span><span class="sxs-lookup"><span data-stu-id="b90a5-142">If something goes wrong, you can restore your code to its original state by restoring your backup.</span></span> <span data-ttu-id="b90a5-143">Non fare affidamento su strumenti come .NET Portability Analyzer per eseguire il backup del progetto, anche se sembrano.</span><span class="sxs-lookup"><span data-stu-id="b90a5-143">Don't rely on tools such as the .NET Portability Analyzer to back up your project, even if they seem to.</span></span> <span data-ttu-id="b90a5-144">È consigliabile creare personalmente una copia del progetto originale.</span><span class="sxs-lookup"><span data-stu-id="b90a5-144">It's best to personally create a copy of the original project.</span></span>

## <a name="nuget-packages"></a><span data-ttu-id="b90a5-145">Pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="b90a5-145">NuGet packages</span></span>

<span data-ttu-id="b90a5-146">Se il progetto fa riferimento a pacchetti NuGet, è probabile che si disponga di un **packages.config** file nella cartella del progetto.</span><span class="sxs-lookup"><span data-stu-id="b90a5-146">If your project is referencing NuGet packages, you probably have a **packages.config** file in your project folder.</span></span> <span data-ttu-id="b90a5-147">Con i progetti in stile SDK, i riferimenti ai pacchetti NuGet sono configurati nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="b90a5-147">With SDK-style projects, NuGet package references are configured in the project file.</span></span> <span data-ttu-id="b90a5-148">I file di progetto di Visual Studio possono facoltativamente definire anche i pacchetti NuGet nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="b90a5-148">Visual Studio project files can optionally define NuGet packages in the project file too.</span></span> <span data-ttu-id="b90a5-149">.NET 5 non usa **packages.config** per i pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="b90a5-149">.NET 5 doesn't use **packages.config** for NuGet packages.</span></span> <span data-ttu-id="b90a5-150">È necessario eseguire la migrazione dei riferimenti ai pacchetti NuGet nel file di progetto prima della migrazione.</span><span class="sxs-lookup"><span data-stu-id="b90a5-150">NuGet package references must be migrated into the project file before migration.</span></span>

<span data-ttu-id="b90a5-151">Per eseguire la migrazione del file di **packages.config** , attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="b90a5-151">To migrate the **packages.config** file, do the following steps:</span></span>

01. <span data-ttu-id="b90a5-152">In **Esplora soluzioni** trovare il progetto di cui si sta eseguendo la migrazione.</span><span class="sxs-lookup"><span data-stu-id="b90a5-152">In **Solution explorer**, find the project you're migrating.</span></span>
02. <span data-ttu-id="b90a5-153">Fare clic con il pulsante destro del mouse su **packages.config**  >  **migrare packages.config a PackageReference**.</span><span class="sxs-lookup"><span data-stu-id="b90a5-153">Right-click on **packages.config** > **Migrate packages.config to PackageReference**.</span></span>
03. <span data-ttu-id="b90a5-154">Selezionare tutti i pacchetti di primo livello.</span><span class="sxs-lookup"><span data-stu-id="b90a5-154">Select all of the top-level packages.</span></span>

<span data-ttu-id="b90a5-155">Viene generato un report di compilazione che consente di individuare eventuali problemi di migrazione dei pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="b90a5-155">A build report is generated to let you know of any issues migrating the NuGet packages.</span></span>

## <a name="project-file"></a><span data-ttu-id="b90a5-156">File di progetto</span><span class="sxs-lookup"><span data-stu-id="b90a5-156">Project file</span></span>

<span data-ttu-id="b90a5-157">Il passaggio successivo per la migrazione dell'app consiste nel convertire il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="b90a5-157">The next step in migrating your app is converting the project file.</span></span> <span data-ttu-id="b90a5-158">Come indicato in precedenza, .NET 5 USA i file di progetto in stile SDK e non carica i file di progetto di Visual Studio utilizzati .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b90a5-158">As previously stated, .NET 5 uses SDK-style project files and won't load the Visual Studio project files that .NET Framework uses.</span></span> <span data-ttu-id="b90a5-159">Tuttavia, è possibile che si stiano già usando progetti in stile SDK.</span><span class="sxs-lookup"><span data-stu-id="b90a5-159">However, there's the possibility that you're already using SDK-style projects.</span></span> <span data-ttu-id="b90a5-160">È possibile individuare facilmente la differenza in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b90a5-160">You can easily spot the difference in Visual Studio.</span></span> <span data-ttu-id="b90a5-161">Fare clic con il pulsante destro del mouse sul file di progetto in **Esplora soluzioni** e cercare l'opzione di menu **modifica file di progetto** .</span><span class="sxs-lookup"><span data-stu-id="b90a5-161">Right-click on the project file in **Solution explorer** and look for the **Edit Project File** menu option.</span></span> <span data-ttu-id="b90a5-162">Se questa voce di menu non è presente, si sta usando il vecchio formato di progetto di Visual Studio ed è necessario eseguire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="b90a5-162">If this menu item is missing, you're using the old Visual Studio project format and need to upgrade.</span></span>

<span data-ttu-id="b90a5-163">Convertire ogni progetto nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="b90a5-163">Convert each project in your solution.</span></span> <span data-ttu-id="b90a5-164">Se si usa l'app di esempio a cui si fa riferimento in precedenza, i progetti **digitare MatchingGame** e **digitare MatchingGame. Logic** verranno convertiti.</span><span class="sxs-lookup"><span data-stu-id="b90a5-164">If you're using the sample app previously referenced, both the **MatchingGame** and **MatchingGame.Logic** projects would be converted.</span></span>

<span data-ttu-id="b90a5-165">Per convertire un progetto, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="b90a5-165">To convert a project, do the following steps:</span></span>

01. <span data-ttu-id="b90a5-166">In **Esplora soluzioni** trovare il progetto di cui si sta eseguendo la migrazione.</span><span class="sxs-lookup"><span data-stu-id="b90a5-166">In **Solution explorer**, find the project you're migrating.</span></span>
01. <span data-ttu-id="b90a5-167">Fare clic con il pulsante destro del mouse sul progetto e scegliere **Scarica progetto**.</span><span class="sxs-lookup"><span data-stu-id="b90a5-167">Right-click on the project and select **Unload Project**.</span></span>
01. <span data-ttu-id="b90a5-168">Fare clic con il pulsante destro del mouse sul progetto e scegliere **modifica file di progetto**.</span><span class="sxs-lookup"><span data-stu-id="b90a5-168">Right-click on the project and select **Edit Project File**.</span></span>
01. <span data-ttu-id="b90a5-169">Copiare e incollare il codice XML del progetto in un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="b90a5-169">Copy-and-paste the project XML into a text editor.</span></span> <span data-ttu-id="b90a5-170">È necessario disporre di una copia per facilitare lo spostamento del contenuto nel nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="b90a5-170">You'll want a copy so that it's easy to move content into the new project.</span></span>
01. <span data-ttu-id="b90a5-171">Cancellare il contenuto del file e incollare il codice XML seguente:</span><span class="sxs-lookup"><span data-stu-id="b90a5-171">Erase the content of the file and paste the following XML:</span></span>

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
    > <span data-ttu-id="b90a5-172">Le librerie non devono definire un' `<OutputType>` impostazione.</span><span class="sxs-lookup"><span data-stu-id="b90a5-172">Libraries don't need to define an `<OutputType>` setting.</span></span> <span data-ttu-id="b90a5-173">Rimuovere la voce se si sta aggiornando un progetto di libreria.</span><span class="sxs-lookup"><span data-stu-id="b90a5-173">Remove that entry if you're upgrading a library project.</span></span>

<span data-ttu-id="b90a5-174">Questo codice XML fornisce la struttura di base del progetto.</span><span class="sxs-lookup"><span data-stu-id="b90a5-174">This XML gives you the basic structure of the project.</span></span> <span data-ttu-id="b90a5-175">Tuttavia, non contiene alcuna impostazione del vecchio file di progetto.</span><span class="sxs-lookup"><span data-stu-id="b90a5-175">However, it doesn't contain any of the settings from the old project file.</span></span> <span data-ttu-id="b90a5-176">Utilizzando le informazioni del progetto precedenti copiate in precedenza in un editor di testo, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="b90a5-176">Using the old project information you previously copied to a text editor, do the following steps:</span></span>

01. <span data-ttu-id="b90a5-177">Copiare gli elementi seguenti dal file di progetto precedente nell' `<PropertyGroup>` elemento nel nuovo file di progetto:</span><span class="sxs-lookup"><span data-stu-id="b90a5-177">Copy the following elements from the old project file into the `<PropertyGroup>` element in the new project file:</span></span>

    - `<RootNamespace>`
    - `<AssemblyName>`

    <span data-ttu-id="b90a5-178">Il file di progetto dovrebbe avere un aspetto simile al codice XML seguente:</span><span class="sxs-lookup"><span data-stu-id="b90a5-178">Your project file should look similar to the following XML:</span></span>

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

01. <span data-ttu-id="b90a5-179">Copiare gli `<ItemGroup>` elementi del vecchio file di progetto che contiene `<ProjectReference>` o `<PackageReference>` nel nuovo file dopo il `</PropertyGroup>` tag di chiusura.</span><span class="sxs-lookup"><span data-stu-id="b90a5-179">Copy the `<ItemGroup>` elements from the old project file that contain `<ProjectReference>` or `<PackageReference>` into the new file after the `</PropertyGroup>` closing tag.</span></span>

    <span data-ttu-id="b90a5-180">Il file di progetto dovrebbe avere un aspetto simile al codice XML seguente:</span><span class="sxs-lookup"><span data-stu-id="b90a5-180">Your project file should look similar to the following XML:</span></span>

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

    <span data-ttu-id="b90a5-181">`<ProjectReference>`Per gli elementi non sono necessari gli elementi `<Project>` `<Name>` figlio e, pertanto è possibile rimuovere le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b90a5-181">The `<ProjectReference>` elements don't need the `<Project>` and `<Name>` children, so you can remove those settings:</span></span>

    ```xml
    <ItemGroup>
      <ProjectReference Include="..\MatchingGame.Logic\MatchingGame.Logic.csproj" />
    </ItemGroup>
    ```

### <a name="resources-and-settings"></a><span data-ttu-id="b90a5-182">Risorse e impostazioni</span><span class="sxs-lookup"><span data-stu-id="b90a5-182">Resources and settings</span></span>

<span data-ttu-id="b90a5-183">Una cosa da notare sulla differenza tra i progetti .NET Framework e i progetti in stile SDK usati da .NET 5 è che i progetti .NET Framework usano un modello di consenso esplicito per i file di codice.</span><span class="sxs-lookup"><span data-stu-id="b90a5-183">One thing to note about the difference between .NET Framework projects and the SDK-style projects used by .NET 5 is that .NET Framework projects use an opt-in model for code files.</span></span> <span data-ttu-id="b90a5-184">Tutti i file di codice che si desidera compilare devono essere definiti in modo esplicito nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="b90a5-184">Any code file you want to compile needs to be explicitly defined in your project file.</span></span> <span data-ttu-id="b90a5-185">I progetti in stile SDK sono inversi. per impostazione predefinita, il comportamento non è esplicito: tutti i file di codice che iniziano dalla directory del progetto e di seguito vengono automaticamente inclusi nel progetto.</span><span class="sxs-lookup"><span data-stu-id="b90a5-185">SDK-style projects are reverse, they default to opt-out behavior: All code files starting from the project's directory and below are automatically included in your project.</span></span> <span data-ttu-id="b90a5-186">Non è necessario eseguire la migrazione di queste voci se sono semplici e senza impostazioni.</span><span class="sxs-lookup"><span data-stu-id="b90a5-186">You don't need to migrate these entries if they are simple and without settings.</span></span> <span data-ttu-id="b90a5-187">Questo è lo stesso per altri file comuni, ad esempio _resx_.</span><span class="sxs-lookup"><span data-stu-id="b90a5-187">This is the same for other common files such as _resx_.</span></span>

<span data-ttu-id="b90a5-188">I progetti Windows Form includono anche file specifici del progetto Windows Form, ad esempio _properties/Settings. Settings_ e _Properties/resources. resx_.</span><span class="sxs-lookup"><span data-stu-id="b90a5-188">Windows Forms projects also include Windows Form project specific files, such as _Properties/Settings.settings_ and _Properties/Resources.resx_.</span></span> <span data-ttu-id="b90a5-189">Potrebbe essere necessario eseguire la migrazione di questi file, che vengono dichiarati nel progetto originale.</span><span class="sxs-lookup"><span data-stu-id="b90a5-189">These files may need to be migrated they are declared in your original project.</span></span>

<span data-ttu-id="b90a5-190">Copiare le voci dal file di progetto precedente in un `<ItemGroup>` elemento del nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="b90a5-190">Copy those entries from the old project file into an `<ItemGroup>` element in the new project.</span></span> <span data-ttu-id="b90a5-191">Dopo aver copiato le voci, modificare tutti `<Compile Include="value">` gli elementi in modo da usare invece l' `Update` attributo anziché `Include` .</span><span class="sxs-lookup"><span data-stu-id="b90a5-191">After you copy the entries, change all `<Compile Include="value">` elements to instead use the `Update` attribute instead of `Include`.</span></span>

- <span data-ttu-id="b90a5-192">Importare la configurazione per il file _Settings. Settings_ .</span><span class="sxs-lookup"><span data-stu-id="b90a5-192">Import the configuration for the _Settings.settings_ file.</span></span>

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

  <span data-ttu-id="b90a5-193">Si noti che la voce _Properties\Settings.Settings_ è rimasta `Include` .</span><span class="sxs-lookup"><span data-stu-id="b90a5-193">Notice that the _Properties\Settings.settings_ entry remained `Include`.</span></span> <span data-ttu-id="b90a5-194">Il progetto non include automaticamente i file di _Impostazioni_ .</span><span class="sxs-lookup"><span data-stu-id="b90a5-194">The project doesn't automatically include _settings_ files.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="b90a5-195">I progetti **Visual Basic** usano in genere la cartella _My Project_ mentre i progetti C# usano in genere le _proprietà_ della cartella per il file di impostazioni del progetto predefinito.</span><span class="sxs-lookup"><span data-stu-id="b90a5-195">**Visual Basic** projects typically use the folder _My Project_ while C# projects typically use the folder _Properties_ for the default project settings file.</span></span>
  
- <span data-ttu-id="b90a5-196">Importare la configurazione per qualsiasi file _resx_ , ad esempio il file _Properties/resources. resx_ .</span><span class="sxs-lookup"><span data-stu-id="b90a5-196">Import the configuration for any _resx_ file, such as the _properties/Resources.resx_ file.</span></span> <span data-ttu-id="b90a5-197">Si noti che l' `Include` attributo è stato modificato in nell' `Update` `<Compile>` elemento ed `<SubType>` è stato rimosso da `<EmbeddedResource>` :</span><span class="sxs-lookup"><span data-stu-id="b90a5-197">Notice that the `Include` attribute was changed to `Update` on the `<Compile>` element, and `<SubType>` was removed from `<EmbeddedResource>`:</span></span>

  ```xml
  <ItemGroup>
    <EmbeddedResource Include="Properties\Resources.resx">
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
  > <span data-ttu-id="b90a5-198">I progetti **Visual Basic** usano in genere la cartella _My Project_ mentre i progetti C# usano in genere le _proprietà_ della cartella per il file di risorse del progetto predefinito.</span><span class="sxs-lookup"><span data-stu-id="b90a5-198">**Visual Basic** projects typically use the folder _My Project_ while C# projects typically use the folder _Properties_ for the default project resource file.</span></span>

### <a name="visual-basic"></a><span data-ttu-id="b90a5-199">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b90a5-199">Visual Basic</span></span>

<span data-ttu-id="b90a5-200">I progetti di linguaggio Visual Basic richiedono una configurazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="b90a5-200">Visual Basic language projects require extra configuration.</span></span>

01. <span data-ttu-id="b90a5-201">Importare il file di configurazione _Project\Application.myapp_ l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="b90a5-201">Import the configuration file _My Project\Application.myapp_ setting.</span></span> <span data-ttu-id="b90a5-202">Si noti che l' `<Compile>` elemento utilizza l' `Update` attributo anziché l' `Include` attributo.</span><span class="sxs-lookup"><span data-stu-id="b90a5-202">Notice that the `<Compile>` element uses the `Update` attribute instead of the `Include` attribute.</span></span>

    ```xml
    <ItemGroup>
      <None Include="My Project\Application.myapp">
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

01. <span data-ttu-id="b90a5-203">Aggiungere l' `<MyType>WindowsForms</MyType>` impostazione all' `<PropertyGroup>` elemento:</span><span class="sxs-lookup"><span data-stu-id="b90a5-203">Add the `<MyType>WindowsForms</MyType>` setting to the `<PropertyGroup>` element:</span></span>

    ```xml
    <PropertyGroup>
      (contains settings previously described)

      <MyType>WindowsForms</MyType>
    </PropertyGroup>
    ```

    <span data-ttu-id="b90a5-204">Questa impostazione importa i `My` membri dello spazio dei nomi Visual Basic i programmatori hanno familiarità con.</span><span class="sxs-lookup"><span data-stu-id="b90a5-204">This setting imports the `My` namespace members Visual Basic programmers are familiar with.</span></span>

01. <span data-ttu-id="b90a5-205">Importare gli spazi dei nomi definiti dal progetto.</span><span class="sxs-lookup"><span data-stu-id="b90a5-205">Import the namespaces defined by your project.</span></span>

    <span data-ttu-id="b90a5-206">Visual Basic progetti possono importare automaticamente spazi dei nomi in ogni file di codice.</span><span class="sxs-lookup"><span data-stu-id="b90a5-206">Visual Basic projects can automatically import namespaces into every code file.</span></span> <span data-ttu-id="b90a5-207">Copiare gli `<ItemGroup>` elementi del vecchio file di progetto che contengono `<Import>` nel nuovo file dopo il `</PropertyGroup>` tag di chiusura.</span><span class="sxs-lookup"><span data-stu-id="b90a5-207">Copy the `<ItemGroup>` elements from the old project file that contain `<Import>` into the new file after the `</PropertyGroup>` closing tag.</span></span>

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

    <span data-ttu-id="b90a5-208">Se non si riesce `<Import>` a trovare istruzioni o se il progetto non viene compilato, assicurarsi di avere almeno le seguenti `<Import>` istruzioni definite nel progetto:</span><span class="sxs-lookup"><span data-stu-id="b90a5-208">If you can't find any `<Import>` statements, or your project fails to compile, make sure you at least have the following `<Import>` statements defined in your project:</span></span>

    ```xml
    <ItemGroup>
      <Import Include="System.Data" />
      <Import Include="System.Drawing" />
      <Import Include="System.Windows.Forms" />
    </ItemGroup>
    ```

01. <span data-ttu-id="b90a5-209">Dal progetto originale, copiare le `<Option*>` Impostazioni e nell' `<StartupObject>` `<PropertyGroup>` elemento:</span><span class="sxs-lookup"><span data-stu-id="b90a5-209">From the original project, copy the `<Option*>` and `<StartupObject>` settings to the `<PropertyGroup>` element:</span></span>

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

### <a name="reload-the-project"></a><span data-ttu-id="b90a5-210">Ricarica il progetto</span><span class="sxs-lookup"><span data-stu-id="b90a5-210">Reload the project</span></span>

<span data-ttu-id="b90a5-211">Dopo aver convertito un progetto nel nuovo formato di tipo SDK, ricaricare il progetto in Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="b90a5-211">After you convert a project to the new SDK-style format, reload the project in Visual Studio:</span></span>

01. <span data-ttu-id="b90a5-212">In **Esplora soluzioni** individuare il progetto che è stato convertito.</span><span class="sxs-lookup"><span data-stu-id="b90a5-212">In **Solution Explorer**, find the project you converted.</span></span>
01. <span data-ttu-id="b90a5-213">Fare clic con il pulsante destro del mouse sul progetto e selezionare **Ricarica progetto**.</span><span class="sxs-lookup"><span data-stu-id="b90a5-213">Right-click on the project and select **Reload Project**.</span></span>

    <span data-ttu-id="b90a5-214">Se il caricamento del progetto non riesce, è possibile che sia stato introdotto un errore nel codice XML del progetto.</span><span class="sxs-lookup"><span data-stu-id="b90a5-214">If the project fails to load, you may have introduced a mistake in the XML of the project.</span></span> <span data-ttu-id="b90a5-215">Aprire il file di progetto per la modifica e provare a identificare e correggere l'errore.</span><span class="sxs-lookup"><span data-stu-id="b90a5-215">Open the project file for editing and try to identify and fix the mistake.</span></span> <span data-ttu-id="b90a5-216">Se non si riesce a trovare un errore, provare a ricominciare.</span><span class="sxs-lookup"><span data-stu-id="b90a5-216">If you can't find a mistake, try starting over.</span></span>

## <a name="edit-appconfig"></a><span data-ttu-id="b90a5-217">Modifica App.config</span><span class="sxs-lookup"><span data-stu-id="b90a5-217">Edit App.config</span></span>

<span data-ttu-id="b90a5-218">Se l'app contiene un file di _App.config_ , rimuovere l' `<supportedRuntime>` elemento:</span><span class="sxs-lookup"><span data-stu-id="b90a5-218">If your app has an _App.config_ file, remove the `<supportedRuntime>` element:</span></span>

```xml
<supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
```

<span data-ttu-id="b90a5-219">È necessario considerare alcune considerazioni con il file di *App.config* .</span><span class="sxs-lookup"><span data-stu-id="b90a5-219">There are some things you should consider with the *App.config* file.</span></span> <span data-ttu-id="b90a5-220">Il file di *App.config* in .NET Framework è stato usato non solo per configurare l'app, ma per configurare le impostazioni e il comportamento di runtime, ad esempio la registrazione.</span><span class="sxs-lookup"><span data-stu-id="b90a5-220">The *App.config* file in .NET Framework was used not only to configure the app, but to configure runtime settings and behavior, such as logging.</span></span> <span data-ttu-id="b90a5-221">Il file di *App.config* in .NET 5 + (e .NET Core) non viene più usato per la configurazione del runtime.</span><span class="sxs-lookup"><span data-stu-id="b90a5-221">The *App.config* file in .NET 5+ (and .NET Core) is no longer used for runtime configuration.</span></span> <span data-ttu-id="b90a5-222">Se il file di *App.config* contiene queste sezioni, non verranno rispettate.</span><span class="sxs-lookup"><span data-stu-id="b90a5-222">If your *App.config* file has these sections, they won't be respected.</span></span>

## <a name="add-the-compatibility-package"></a><span data-ttu-id="b90a5-223">Aggiungere il pacchetto di compatibilità</span><span class="sxs-lookup"><span data-stu-id="b90a5-223">Add the compatibility package</span></span>

<span data-ttu-id="b90a5-224">Se il file di progetto viene caricato correttamente, ma la compilazione ha esito negativo per il progetto e vengono visualizzati errori simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="b90a5-224">If your project file is loading correctly, but compilation fails for your project and you receive errors similar to the following:</span></span>

- <span data-ttu-id="b90a5-225">**Il tipo o lo spazio dei nomi \<some name> non è stato trovato**</span><span class="sxs-lookup"><span data-stu-id="b90a5-225">**The type or namespace \<some name> could not be found**</span></span>
- <span data-ttu-id="b90a5-226">**Il nome non \<some name> esiste nel contesto corrente**</span><span class="sxs-lookup"><span data-stu-id="b90a5-226">**The name \<some name> does not exist in the current context**</span></span>

<span data-ttu-id="b90a5-227">Potrebbe essere necessario aggiungere il [`Microsoft.Windows.Compatibility`](https://www.nuget.org/packages/Microsoft.Windows.Compatibility/) pacchetto all'app.</span><span class="sxs-lookup"><span data-stu-id="b90a5-227">You may need to add the [`Microsoft.Windows.Compatibility`](https://www.nuget.org/packages/Microsoft.Windows.Compatibility/) package to your app.</span></span> <span data-ttu-id="b90a5-228">Questo pacchetto aggiunge le API .NET di ~ 21.000 da .NET Framework, ad esempio la `System.Configuration.ConfigurationManager` classe e le API per interagire con il registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="b90a5-228">This package adds ~21,000 .NET APIs from .NET Framework, such as the `System.Configuration.ConfigurationManager` class and APIs for interacting with the Windows Registry.</span></span> <span data-ttu-id="b90a5-229">Aggiungere il pacchetto `Microsoft.Windows.Compatibility`.</span><span class="sxs-lookup"><span data-stu-id="b90a5-229">Add the `Microsoft.Windows.Compatibility` package.</span></span>

<span data-ttu-id="b90a5-230">Modificare il file di progetto e aggiungere l' `<ItemGroup>` elemento seguente:</span><span class="sxs-lookup"><span data-stu-id="b90a5-230">Edit your project file and add the following `<ItemGroup>` element:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.Windows.Compatibility" Version="5.0.0" />
</ItemGroup>
```

## <a name="test-your-app"></a><span data-ttu-id="b90a5-231">Test dell'app</span><span class="sxs-lookup"><span data-stu-id="b90a5-231">Test your app</span></span>

<span data-ttu-id="b90a5-232">Al termine della migrazione dell'app, eseguirne il test.</span><span class="sxs-lookup"><span data-stu-id="b90a5-232">After you've finished migrating your app, test it!</span></span>

## <a name="next-steps"></a><span data-ttu-id="b90a5-233">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b90a5-233">Next steps</span></span>

- <span data-ttu-id="b90a5-234">Informazioni sulle [modifiche di rilievo in Windows Form](/dotnet/core/compatibility/winforms).</span><span class="sxs-lookup"><span data-stu-id="b90a5-234">Learn about [breaking changes in Windows Forms](/dotnet/core/compatibility/winforms).</span></span>
- <span data-ttu-id="b90a5-235">Vedere altre informazioni su [Windows Compatibility Pack][compat-pack].</span><span class="sxs-lookup"><span data-stu-id="b90a5-235">Read more about the [Windows Compatibility Pack][compat-pack].</span></span>

[compat-pack]: /dotnet/core/porting/windows-compat-pack

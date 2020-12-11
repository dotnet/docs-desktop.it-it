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
# <a name="how-to-migrate-a-windows-forms-desktop-app-to-net-5"></a>Come eseguire la migrazione di un'app desktop Windows Forms a .NET 5

Questo articolo descrive come eseguire la migrazione di un'app desktop Windows Forms da .NET Framework a .NET 5 o versione successiva. .NET SDK include il supporto per applicazioni Windows Forms. Windows Forms è ancora un framework solo per Windows e supporta l'esecuzione solo in Windows.

La migrazione dell'app da .NET Framework a .NET 5 richiede in genere un nuovo file di progetto. .NET 5 USA i file di progetto in stile SDK mentre .NET Framework in genere usa il file di progetto di Visual Studio meno recente. Se si è mai aperto un file di progetto di Visual Studio in un editor di testo, è possibile verificare il livello di dettaglio. I progetti in stile SDK sono più piccoli e non richiedono il numero di voci del formato di file di progetto precedente.

Per altre informazioni su .NET 5, vedere [Introduzione a .NET](/dotnet/core/introduction).

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2019 versione 16,8 Preview](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+winforms)

  - Selezionare il [carico di lavoro desktop di Visual Studio](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads).

  - Selezionare il [singolo componente .NET 5](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components).

- Anteprima di progettazione Windows Form in Visual Studio.

  Per abilitare la finestra di progettazione, passare a **strumenti**  >  **Opzioni**  >  **ambiente**  >  **Anteprima funzionalità** e selezionare l'opzione **usare l'anteprima Windows Forms finestra di progettazione per le app .NET Core** .

- Questo articolo usa l'app di esempio del [gioco corrispondente](https://github.com/dotnet/samples/tree/master/windowsforms/matching-game/net45/) . Se si vuole seguire la procedura, scaricare e aprire l'applicazione in Visual Studio. In caso contrario, usare la propria app.

### <a name="consider"></a>Consider

Quando si esegue la migrazione di un .NET Framework Windows Forms Application, è necessario prendere in considerazione alcuni aspetti.

01. Controllare che l'applicazione sia un buon candidato per la migrazione.

    Usare [.NET Portability Analyzer](/dotnet/standard/analyzers/portability-analyzer) per determinare se il progetto verrà migrato a .NET 5. Se nel progetto si verificano problemi con .NET 5, l'analizzatore consente di identificare tali problemi. Lo strumento .NET Portability Analyzer può essere installato come estensione di Visual Studio o usato dalla riga di comando. Per altre informazioni, vedere [.NET Portability Analyzer](/dotnet/standard/analyzers/portability-analyzer).

01. Si usa una versione diversa di Windows Forms.

    Quando è stato rilasciato .NET Core 3,0, Windows Forms è [disponibile in GitHub](https://github.com/dotnet/winforms). Il codice per Windows Forms per .NET 5 è un fork della .NET Framework Windows Forms codebase. È possibile che esistano alcune differenze e che l'app sarà difficile da migrare.

01. [Windows Compatibility Pack][compat-pack] può essere utile per la migrazione.

    Alcune API disponibili in .NET Framework non sono disponibili in .NET 5. [Windows Compatibility Pack][compat-pack] aggiunge molte di queste API e può aiutare l'app Windows Forms a diventare compatibile con .NET 5.

01. Aggiornare i pacchetti NuGet usati dal progetto.

    È sempre consigliabile usare le versioni più recenti dei pacchetti NuGet prima di qualsiasi migrazione. Se l'applicazione fa riferimento a pacchetti NuGet, aggiornarli alla versione più recente. Verificare che l'applicazione venga compilata correttamente. Dopo l'aggiornamento, se sono presenti errori di pacchetto, effettuare il downgrade del pacchetto alla versione più recente che non causa problemi al codice.

## <a name="back-up-your-projects"></a>Eseguire il backup dei progetti

Il primo passaggio per eseguire la migrazione di un progetto consiste nel eseguire il backup del progetto. Se si verifica un problema, è possibile ripristinare lo stato originale del codice ripristinando il backup. Non fare affidamento su strumenti come .NET Portability Analyzer per eseguire il backup del progetto, anche se sembrano. È consigliabile creare personalmente una copia del progetto originale.

## <a name="nuget-packages"></a>Pacchetti NuGet

Se il progetto fa riferimento a pacchetti NuGet, è probabile che si disponga di un **packages.config** file nella cartella del progetto. Con i progetti in stile SDK, i riferimenti ai pacchetti NuGet sono configurati nel file di progetto. I file di progetto di Visual Studio possono facoltativamente definire anche i pacchetti NuGet nel file di progetto. .NET 5 non usa **packages.config** per i pacchetti NuGet. È necessario eseguire la migrazione dei riferimenti ai pacchetti NuGet nel file di progetto prima della migrazione.

Per eseguire la migrazione del file di **packages.config** , attenersi alla procedura seguente:

01. In **Esplora soluzioni** trovare il progetto di cui si sta eseguendo la migrazione.
02. Fare clic con il pulsante destro del mouse su **packages.config**  >  **migrare packages.config a PackageReference**.
03. Selezionare tutti i pacchetti di primo livello.

Viene generato un report di compilazione che consente di individuare eventuali problemi di migrazione dei pacchetti NuGet.

## <a name="project-file"></a>File di progetto

Il passaggio successivo per la migrazione dell'app consiste nel convertire il file di progetto. Come indicato in precedenza, .NET 5 USA i file di progetto in stile SDK e non carica i file di progetto di Visual Studio utilizzati .NET Framework. Tuttavia, è possibile che si stiano già usando progetti in stile SDK. È possibile individuare facilmente la differenza in Visual Studio. Fare clic con il pulsante destro del mouse sul file di progetto in **Esplora soluzioni** e cercare l'opzione di menu **modifica file di progetto** . Se questa voce di menu non è presente, si sta usando il vecchio formato di progetto di Visual Studio ed è necessario eseguire l'aggiornamento.

Convertire ogni progetto nella soluzione. Se si usa l'app di esempio a cui si fa riferimento in precedenza, i progetti **digitare MatchingGame** e **digitare MatchingGame. Logic** verranno convertiti.

Per convertire un progetto, attenersi alla procedura seguente:

01. In **Esplora soluzioni** trovare il progetto di cui si sta eseguendo la migrazione.
01. Fare clic con il pulsante destro del mouse sul progetto e scegliere **Scarica progetto**.
01. Fare clic con il pulsante destro del mouse sul progetto e scegliere **modifica file di progetto**.
01. Copiare e incollare il codice XML del progetto in un editor di testo. È necessario disporre di una copia per facilitare lo spostamento del contenuto nel nuovo progetto.
01. Cancellare il contenuto del file e incollare il codice XML seguente:

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
    > Le librerie non devono definire un' `<OutputType>` impostazione. Rimuovere la voce se si sta aggiornando un progetto di libreria.

Questo codice XML fornisce la struttura di base del progetto. Tuttavia, non contiene alcuna impostazione del vecchio file di progetto. Utilizzando le informazioni del progetto precedenti copiate in precedenza in un editor di testo, attenersi alla procedura seguente:

01. Copiare gli elementi seguenti dal file di progetto precedente nell' `<PropertyGroup>` elemento nel nuovo file di progetto:

    - `<RootNamespace>`
    - `<AssemblyName>`

    Il file di progetto dovrebbe avere un aspetto simile al codice XML seguente:

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

01. Copiare gli `<ItemGroup>` elementi del vecchio file di progetto che contiene `<ProjectReference>` o `<PackageReference>` nel nuovo file dopo il `</PropertyGroup>` tag di chiusura.

    Il file di progetto dovrebbe avere un aspetto simile al codice XML seguente:

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

    `<ProjectReference>`Per gli elementi non sono necessari gli elementi `<Project>` `<Name>` figlio e, pertanto è possibile rimuovere le impostazioni seguenti:

    ```xml
    <ItemGroup>
      <ProjectReference Include="..\MatchingGame.Logic\MatchingGame.Logic.csproj" />
    </ItemGroup>
    ```

### <a name="resources-and-settings"></a>Risorse e impostazioni

I progetti Windows Forms per .NET Framework includono in genere altri file, ad esempio *Proprietà/impostazioni. Settings* e *Properties/resources. resx*. È necessario eseguire la migrazione di questi file e di qualsiasi file *resx* creato per l'app oltre ai file *resx* di form.

Copiare le voci dal file di progetto precedente in un `<ItemGroup>` elemento del nuovo progetto. Dopo aver copiato le voci, modificare qualsiasi `<Compile Include="value">` `<EmbeddedResource Include="value">` elemento o in modo da usare invece `Update` di `Include` .

- Importare la configurazione per il file *Settings. Settings* . Si noti che `Include` è stato modificato in nell' `Update` `<Compile>` elemento:

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
  > I progetti **Visual Basic** usano in genere la cartella *My Project* mentre i progetti C# usano in genere le *proprietà* della cartella per il file di impostazioni del progetto predefinito.
  
- Importare la configurazione per qualsiasi file *resx* , ad esempio il file *Properties/resources. resx* . Si noti che `Include` è stato modificato in `Update` in entrambi `<Compile>` gli `<EmbeddedResource>` elementi e ed `<SubType>` è stato rimosso da `<EmbeddedResource>` :

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
  > I progetti **Visual Basic** usano in genere la cartella *My Project* mentre i progetti C# usano in genere le *proprietà* della cartella per il file di risorse del progetto predefinito.

### <a name="visual-basic"></a>Visual Basic

I progetti di linguaggio Visual Basic richiedono una configurazione aggiuntiva.

01. Importare il file di configurazione *Project\Application.myapp* l'impostazione. Si noti che `<None>` gli `<Compile>` elementi e utilizzano l' `Update` attributo anziché l' `Include` attributo.

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

01. Aggiungere l' `<MyType>WindowsForms</MyType>` impostazione all' `<PropertyGroup>` elemento:

    ```xml
    <PropertyGroup>
      (contains settings previously described)

      <MyType>WindowsForms</MyType>
    </PropertyGroup>
    ```

    Questa impostazione importa i `My` membri dello spazio dei nomi Visual Basic i programmatori hanno familiarità con.

01. Importare gli spazi dei nomi definiti dal progetto.

    Visual Basic progetti possono importare automaticamente spazi dei nomi in ogni file di codice. Copiare gli `<ItemGroup>` elementi del vecchio file di progetto che contengono `<Import>` nel nuovo file dopo il `</PropertyGroup>` tag di chiusura.

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

    Se non si riesce `<Import>` a trovare istruzioni o se il progetto non viene compilato, assicurarsi di avere almeno le seguenti `<Import>` istruzioni definite nel progetto:

    ```xml
    <ItemGroup>
      <Import Include="System.Data" />
      <Import Include="System.Drawing" />
      <Import Include="System.Windows.Forms" />
    </ItemGroup>
    ```

01. Dal progetto originale, copiare le `<Option*>` Impostazioni e nell' `<StartupObject>` `<PropertyGroup>` elemento:

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

### <a name="reload-the-project"></a>Ricarica il progetto

Dopo aver convertito un progetto nel nuovo formato di tipo SDK, ricaricare il progetto in Visual Studio:

01. In **Esplora soluzioni** individuare il progetto che è stato convertito.
01. Fare clic con il pulsante destro del mouse sul progetto e selezionare **Ricarica progetto**.

    Se il caricamento del progetto non riesce, è possibile che sia stato introdotto un errore nel codice XML del progetto. Aprire il file di progetto per la modifica e provare a identificare e correggere l'errore. Se non si riesce a trovare un errore, provare a ricominciare.

## <a name="edit-appconfig"></a>Modifica App.config

Se l'app contiene un file di *App.config* , rimuovere l' `<supportedRuntime>` elemento:

```xml
<supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
```

È necessario considerare alcune considerazioni con il file di *App.config* . Il file di *App.config* in .NET Framework è stato usato non solo per configurare l'app, ma per configurare le impostazioni e il comportamento di runtime, ad esempio la registrazione. Il file di *App.config* in .NET 5 + (e .NET Core) non viene più usato per la configurazione del runtime. Se il file di *App.config* contiene queste sezioni, non verranno rispettate.

## <a name="add-the-compatibility-package"></a>Aggiungere il pacchetto di compatibilità

Se il file di progetto viene caricato correttamente, ma la compilazione ha esito negativo per il progetto e vengono visualizzati errori simili ai seguenti:

- **Il tipo o lo spazio dei nomi \<some name> non è stato trovato**
- **Il nome non \<some name> esiste nel contesto corrente**

Potrebbe essere necessario aggiungere il [`Microsoft.Windows.Compatibility`](https://www.nuget.org/packages/Microsoft.Windows.Compatibility/) pacchetto all'app. Questo pacchetto aggiunge le API .NET di ~ 21.000 da .NET Framework, ad esempio la `System.Configuration.ConfigurationManager` classe e le API per interagire con il registro di sistema di Windows. Aggiungere il pacchetto `Microsoft.Windows.Compatibility`.

Modificare il file di progetto e aggiungere l' `<ItemGroup>` elemento seguente:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.Windows.Compatibility" Version="5.0.0" />
</ItemGroup>
```

## <a name="test-your-app"></a>Test dell'app

Al termine della migrazione dell'app, eseguirne il test.

## <a name="next-steps"></a>Passaggi successivi

- Informazioni sulle [modifiche di rilievo in Windows Forms](/dotnet/core/compatibility/winforms).
- Vedere altre informazioni su [Windows Compatibility Pack][compat-pack].

[compat-pack]: /dotnet/core/porting/windows-compat-pack

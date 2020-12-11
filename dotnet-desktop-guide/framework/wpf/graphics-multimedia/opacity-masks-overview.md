---
title: Cenni preliminari sulle maschere di opacità
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [WPF], opacity masks
- masks [WPF], opacity
- opacity [WPF], masks
ms.assetid: 22367fab-5f59-4583-abfd-db2bf86eaef7
ms.openlocfilehash: fc3c0057416449bed56c69d1caa823a93e66037e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960754"
---
# <a name="opacity-masks-overview"></a>Cenni preliminari sulle maschere di opacità
Le maschere di opacità consentono di rendere trasparenti o parzialmente trasparenti parti di un elemento o di un oggetto visivo. Per creare una maschera di opacità, applicare un oggetto <xref:System.Windows.Media.Brush> alla <xref:System.Windows.UIElement.OpacityMask%2A> proprietà di un elemento o <xref:System.Windows.Media.Visual> .  Viene eseguito il mapping del pennello all'elemento o oggetto visivo e il valore di opacità di ogni pixel del pennello viene usato per determinare l'opacità risultante di ogni pixel corrispondente dell'elemento o dell'oggetto visivo.  
  
<a name="prereqs"></a>
## <a name="prerequisites"></a>Prerequisiti  
 In questa panoramica si presuppone che l'utente abbia familiarità con <xref:System.Windows.Media.Brush> gli oggetti. Per un'introduzione all'uso dei pennelli, vedere [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md). Per informazioni su <xref:System.Windows.Media.ImageBrush> e <xref:System.Windows.Media.DrawingBrush> , vedere [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).  
  
<a name="opacitymasks"></a>
## <a name="creating-visual-effects-with-opacity-masks"></a>Creazione di effetti visivi con maschere di opacità  
 Il funzionamento delle maschere di opacità è basato sul mapping del suo contenuto all'elemento o oggetto visivo. Il canale alfa di ogni pixel del pennello viene usato per determinare l'opacità risultante dei pixel corrispondenti dell'elemento o oggetto visivo. Il colore effettivo del pennello viene ignorato. Se una parte del pennello è trasparente, la parte corrispondente dell'elemento o oggetto visivo diventa trasparente. Se una parte del pennello è opaca, l'opacità della parte corrispondente dell'elemento o oggetto visivo rimane inalterata. L'opacità specificata dalla maschera di opacità viene combinata a qualsiasi impostazione di opacità dell'elemento o oggetto visivo. Se ad esempio un elemento è opaco al 25 percento e viene applicata una maschera di opacità che crea una transizione da opacità totale a trasparenza totale, il risultato è un elemento che passa dal 25 percento di opacità a una trasparenza totale.  
  
> [!NOTE]
> Sebbene gli esempi in questa panoramica dimostrino l'uso di maschere di opacità sugli elementi immagine, una maschera di opacità può essere applicata a qualsiasi elemento o <xref:System.Windows.Media.Visual> , inclusi i pannelli e i controlli.  
  
 Le maschere di opacità vengono usate per creare effetti visivi interessanti, ad esempio dissolvenze per immagini o pulsanti, aggiunta di trame agli elementi o combinazione di sfumature per ottenere il cosiddetto effetto cristallo. La figura seguente illustra l'uso di una maschera di opacità. Per visualizzare le parti trasparenti della maschera viene usato uno sfondo a scacchi.  
  
 ![Oggetto con maschera di opacità LinearGradientBrush](./media/wcpsdk-graphicsmm-opacitymask-imageexample.png "wcpsdk_graphicsmm_opacitymask_imageexample")  
Esempio di maschera di opacità  
  
<a name="creatingopacitymasks"></a>
## <a name="creating-an-opacity-mask"></a>Creazione di una maschera di opacità  
 Per creare una maschera di opacità, creare un oggetto <xref:System.Windows.Media.Brush> e applicarlo alla <xref:System.Windows.UIElement.OpacityMask%2A> proprietà di un elemento o di un oggetto visivo. È possibile utilizzare qualsiasi tipo di <xref:System.Windows.Media.Brush> come maschera di opacità.  
  
- <xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush> : Utilizzato per rendere un elemento o una dissolvenza visiva dalla visualizzazione.  
  
     Nell'immagine seguente viene illustrato un oggetto <xref:System.Windows.Media.LinearGradientBrush> utilizzato come maschera di opacità.  
  
     ![Oggetto con maschera di opacità LinearGradientBrush](./media/wcpsdk-graphicsmm-brushes-lineagradientopacitymasksingle.jpg "wcpsdk_graphicsmm_brushes_lineagradientopacitymasksingle")  
Esempio di maschera di opacità LinearGradientBrush  
  
- <xref:System.Windows.Media.ImageBrush>: Usato per creare gli effetti di trama e contorno.  
  
     Nell'immagine seguente viene illustrato un oggetto <xref:System.Windows.Media.ImageBrush> utilizzato come maschera di opacità.  
  
     ![Oggetto con maschera di opacità ImageBrush](./media/wcpsdk-graphicsmm-brushes-imageasopacitymasksingle.jpg "wcpsdk_graphicsmm_brushes_imageasopacitymasksingle")  
Esempio di maschera di opacità LinearGradientBrush  
  
- <xref:System.Windows.Media.DrawingBrush>: Usato per creare maschere di opacità complesse da modelli di forme, immagini e sfumature.  
  
     Nell'immagine seguente viene illustrato un oggetto <xref:System.Windows.Media.DrawingBrush> utilizzato come maschera di opacità.  
  
     ![Oggetto con maschera di opacità DrawingBrush](./media/wcpsdk-drawingbrushasopacitymask-single.jpg "wcpsdk_drawingbrushasopacitymask_single")  
Esempio di maschera di opacità DrawingBrush  
  
 I pennelli sfumatura ( <xref:System.Windows.Media.LinearGradientBrush> e <xref:System.Windows.Media.RadialGradientBrush> ) sono particolarmente adatti per essere utilizzati come maschera di opacità. Poiché un oggetto <xref:System.Windows.Media.SolidColorBrush> riempie un'area con un colore uniforme, rendono le maschere di opacità insufficienti. l'utilizzo di un oggetto <xref:System.Windows.Media.SolidColorBrush> equivale a impostare la proprietà dell'elemento o dell'oggetto visivo <xref:System.Windows.UIElement.OpacityMask%2A> .  
  
<a name="creatingopacitymaskswithgradients"></a>
## <a name="using-a-gradient-as-an-opacity-mask"></a>Uso di una sfumatura come maschera di opacità  
 Per creare un riempimento sfumato, specificare due o più cursori sfumatura. Ogni cursore sfumatura descrive un colore e una posizione. Per altre informazioni sulla creazione e l'uso di sfumature, vedere [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md). Il processo equivale a quello relativo all'uso di una sfumatura come maschera di opacità, ma, anziché miscelare i colori, la maschera di opacità miscela i valori del canale alfa. Pertanto, ciò che è importante non è il colore effettivo del contenuto della sfumatura, bensì il canale alfa, o opacità, di ogni colore. Di seguito è riportato un esempio.  
  
 [!code-xaml[OpacityMasksSnippet#LinearGradientOpacityMaskonImage](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/GradientBrushExample.xaml#lineargradientopacitymaskonimage)]  
  
<a name="specifyinggradientcolors"></a>
## <a name="specifying-gradient-stops-for-an-opacity-mask"></a>Definizione di cursori sfumatura per una maschera di opacità  
 Nell'esempio precedente, il colore definito dal sistema <xref:System.Windows.Media.Colors.Black%2A> viene utilizzato come colore iniziale della sfumatura. Poiché tutti i colori della <xref:System.Windows.Media.Colors> classe, ad eccezione di <xref:System.Windows.Media.Colors.Transparent%2A> , sono completamente opachi, possono essere usati per definire semplicemente un colore iniziale per una maschera di opacità della sfumatura.  
  
 Per un controllo aggiuntivo sui valori alfa durante la definizione di una maschera di opacità, è possibile specificare il canale alfa dei colori usando la notazione esadecimale ARGB nel markup o usando il <xref:System.Windows.Media.Color.FromScRgb%2A?displayProperty=nameWithType> metodo.  
  
<a name="argbsyntax"></a>
### <a name="specifying-color-opacity-in-xaml"></a>Specifica dell'opacità di colore in "XAML"  
 In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] è possibile usare la notazione esadecimale ARGB per specificare l'opacità dei singoli colori. La notazione esadecimale ARGB usa la sintassi seguente:  
  
 `#` **aa** *rrggbb*  
  
 *aa* nella riga precedente rappresenta un valore esadecimale a due cifre usato per specificare l'opacità del colore. *rr*, *gg* e *bb* rappresentano un valore esadecimale a due cifre usato per specificare la quantità di rosso, verde e blu nel colore. Ogni cifra esadecimale può avere un valore compreso tra 0 e 9 o tra A e F. 0 è il valore più basso, mentre F è il più elevato. Un valore alfa pari a 00 indica un colore completamente trasparente, mentre un valore alfa pari a FF indica un colore completamente opaco.  Nell'esempio seguente viene usata la notazione ARGB esadecimale per specificare due colori. Il primo è completamente opaco, mentre il secondo è completamente trasparente.  
  
 [!code-xaml[OpacityMasksSnippet#AARRGGBBValueonOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/GradientBrushExample.xaml#aarrggbbvalueonopacitymask)]  
  
<a name="usingimageasopacitymask"></a>
## <a name="using-an-image-as-an-opacity-mask"></a>Uso di un'immagine come maschera di opacità  
 È anche possibile usare le immagini come maschere di opacità. La figura seguente mostra un esempio. Per visualizzare le parti trasparenti della maschera viene usato uno sfondo a scacchi.  
  
 ![Oggetto con maschera di opacità ImageBrush](./media/wcpsdk-graphicsmm-imageasopacitymask.png "wcpsdk_graphicsmm_imageasopacitymask")  
Esempio di maschera di opacità  
  
 Per usare un'immagine come maschera di opacità, usare un oggetto <xref:System.Windows.Media.ImageBrush> per contenere l'immagine. Quando si crea un'immagine da usare come maschera di opacità, salvare l'immagine in un formato che supporta più livelli di trasparenza, ad esempio Portable Network Graphics (PNG). L'esempio seguente illustra il codice usato per creare la precedente illustrazione.  
  
 [!code-xaml[OpacityMasksSnippet#UIElementOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/ImageBrushExample.xaml#uielementopacitymask)]  
  
<a name="tilingimageopacitymask"></a>
### <a name="using-a-tiled-image-as-an-opacity-mask"></a>Uso di un'immagine affiancata come maschera di opacità  
 Nell'esempio seguente, la stessa immagine viene usata con un'altra <xref:System.Windows.Media.ImageBrush> , ma le funzionalità di affiancamento del pennello vengono usate per produrre riquadri del quadrato immagine 50 pixel.  
  
 [!code-xaml[OpacityMasksSnippet#TiledImageasOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/ImageBrushExample.xaml#tiledimageasopacitymask)]  
  
<a name="drawingbrushasopacitymask"></a>
## <a name="creating-an-opacity-mask-from-a-drawing"></a>Creazione di una maschera di opacità da un disegno  
 È possibile usare i disegni per creare maschere di opacità. Le forme contenute nel disegno possono essere riempite con sfumature, tinte unite, immagini o anche gli altri disegni. L'immagine seguente illustra un esempio di disegno usato come maschera di opacità. Per visualizzare le parti trasparenti della maschera viene usato uno sfondo a scacchi.  
  
 ![Oggetto con maschera di opacità DrawingBrush](./media/wcpsdk-drawingbrushasopacitymask.png "wcpsdk_drawingbrushasopacitymask")  
Esempio di maschera di opacità DrawingBrush  
  
 Per usare un disegno come maschera di opacità, usare un oggetto <xref:System.Windows.Media.DrawingBrush> per contenere il disegno. L'esempio seguente illustra il codice usato per creare la precedente illustrazione:  
  
 [!code-xaml[OpacityMasksSnippet#OpacityMaskfromDrawing](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/DrawingBrushExample.xaml#opacitymaskfromdrawing)]  
  
<a name="tileddrawingbrush"></a>
### <a name="using-a-tiled-drawing-as-an-opacity-mask"></a>Uso di un disegno affiancato come maschera di opacità  
 Analogamente <xref:System.Windows.Media.ImageBrush> a, <xref:System.Windows.Media.DrawingBrush> è possibile fare in modo che il relativo disegno venga affiancato. Nell'esempio seguente viene usato un pennello da disegno per creare una maschera di opacità affiancata.  
  
 [!code-xaml[OpacityMasksSnippet#TiledDrawingasOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/DrawingBrushExample.xaml#tileddrawingasopacitymask)]  
  
## <a name="see-also"></a>Vedere anche

- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
- [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md)

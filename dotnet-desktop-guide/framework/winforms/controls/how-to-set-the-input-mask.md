---
title: 'Procedura: Impostare la maschera di input'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: 06dee48765653ac7a659246cc3dfe865c795ca21
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964909"
---
# <a name="how-to-set-the-input-mask"></a><span data-ttu-id="24c03-102">Procedura: Impostare la maschera di input</span><span class="sxs-lookup"><span data-stu-id="24c03-102">How to: Set the Input Mask</span></span>
<span data-ttu-id="24c03-103">Il controllo casella di testo mascherato è un controllo casella di testo avanzato che supporta una sintassi dichiarativa per accettare o rifiutare l'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="24c03-103">The masked text box control is an enhanced text box control that supports a declarative syntax for accepting or rejecting user input.</span></span> <span data-ttu-id="24c03-104">Impostando la proprietà Mask, è possibile specificare l'input dell'utente consentito senza scrivere alcuna logica di convalida personalizzata nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="24c03-104">By setting the Mask property, you can specify the allowable user input without writing any custom validation logic in your application.</span></span> <span data-ttu-id="24c03-105">Per ulteriori informazioni, vedere la sezione Osservazioni della <xref:System.Windows.Forms.MaskedTextBox> classe.</span><span class="sxs-lookup"><span data-stu-id="24c03-105">For more information, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox> class.</span></span>  
  
## <a name="setting-the-mask-property-manually"></a><span data-ttu-id="24c03-106">Impostazione manuale della proprietà Mask</span><span class="sxs-lookup"><span data-stu-id="24c03-106">Setting the Mask Property Manually</span></span>  
 <span data-ttu-id="24c03-107">Se si ha familiarità con i caratteri supportati dalla proprietà Mask, è possibile immetterla manualmente.</span><span class="sxs-lookup"><span data-stu-id="24c03-107">If you are familiar with the characters that the Mask property supports, you can enter it manually.</span></span> <span data-ttu-id="24c03-108">Per un riepilogo dei caratteri supportati dalla proprietà Mask, vedere la sezione Osservazioni della <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="24c03-108">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
### <a name="to-set-the-mask-property-manually"></a><span data-ttu-id="24c03-109">Per impostare manualmente la proprietà Mask</span><span class="sxs-lookup"><span data-stu-id="24c03-109">To set the Mask property manually</span></span>  
  
1. <span data-ttu-id="24c03-110">In visualizzazione **progettazione** selezionare un <xref:System.Windows.Forms.MaskedTextBox> .</span><span class="sxs-lookup"><span data-stu-id="24c03-110">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
2. <span data-ttu-id="24c03-111">Nella finestra **Proprietà** individuare la <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="24c03-111">In the **Properties** window, locate the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
3. <span data-ttu-id="24c03-112">Digitare la maschera desiderata.</span><span class="sxs-lookup"><span data-stu-id="24c03-112">Type the mask that you want.</span></span> <span data-ttu-id="24c03-113">Ad esempio digitare `###`.</span><span class="sxs-lookup"><span data-stu-id="24c03-113">For example, type `###`.</span></span>  
  
## <a name="using-the-input-mask-dialog-box"></a><span data-ttu-id="24c03-114">Uso della finestra di dialogo Maschera di input</span><span class="sxs-lookup"><span data-stu-id="24c03-114">Using the Input Mask Dialog Box</span></span>  
 <span data-ttu-id="24c03-115">La finestra di dialogo Maschera di input fornisce alcune maschere di input predefinite.</span><span class="sxs-lookup"><span data-stu-id="24c03-115">The Input Mask dialog box provides some predefined input masks.</span></span> <span data-ttu-id="24c03-116">È anche possibile modificare le maschere predefinite o immettere manualmente la propria maschera.</span><span class="sxs-lookup"><span data-stu-id="24c03-116">You can also change the predefined masks or enter your own mask manually.</span></span>  
  
### <a name="to-open-the-input-mask-dialog-box"></a><span data-ttu-id="24c03-117">Per aprire la finestra di dialogo Maschera di input</span><span class="sxs-lookup"><span data-stu-id="24c03-117">To open the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="24c03-118">In visualizzazione **progettazione** selezionare un <xref:System.Windows.Forms.MaskedTextBox> .</span><span class="sxs-lookup"><span data-stu-id="24c03-118">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
    1. <span data-ttu-id="24c03-119">Fare clic sullo smart tag per aprire il pannello **attività di MaskedTextBox** .</span><span class="sxs-lookup"><span data-stu-id="24c03-119">Click the smart tag to open the **MaskedTextBox Tasks** panel.</span></span>  
  
    2. <span data-ttu-id="24c03-120">Fare clic su **Imposta maschera**.</span><span class="sxs-lookup"><span data-stu-id="24c03-120">Click **Set Mask**.</span></span>  
  
     <span data-ttu-id="24c03-121">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="24c03-121">\- or -</span></span>  
  
    1. <span data-ttu-id="24c03-122">Nella finestra **Proprietà** selezionare la <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="24c03-122">In the **Properties** window, select the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
    2. <span data-ttu-id="24c03-123">Fare clic sul pulsante con i puntini di sospensione nella colonna valore proprietà.</span><span class="sxs-lookup"><span data-stu-id="24c03-123">Click the ellipsis button in the property value column.</span></span>  
  
     <span data-ttu-id="24c03-124">Verrà visualizzata la finestra di dialogo **maschera di input** .</span><span class="sxs-lookup"><span data-stu-id="24c03-124">The **Input Mask** dialog box appears.</span></span>  
  
### <a name="to-use-the-input-mask-dialog-box"></a><span data-ttu-id="24c03-125">Per utilizzare la finestra di dialogo Maschera di input</span><span class="sxs-lookup"><span data-stu-id="24c03-125">To use the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="24c03-126">Opzionale Fare clic su una delle maschere predefinite nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="24c03-126">(Optional) Click one of the predefined masks in the list.</span></span>  
  
2. <span data-ttu-id="24c03-127">Opzionale Modificare la maschera predefinita nella casella **maschera** .</span><span class="sxs-lookup"><span data-stu-id="24c03-127">(Optional) Edit the predefined mask in the **Mask** box.</span></span>  
  
3. <span data-ttu-id="24c03-128">Opzionale Digitare una nuova maschera nella casella **maschera** .</span><span class="sxs-lookup"><span data-stu-id="24c03-128">(Optional) Type a new mask in the **Mask** box.</span></span> <span data-ttu-id="24c03-129">Ovvero, non è necessario utilizzare una delle maschere predefinite.</span><span class="sxs-lookup"><span data-stu-id="24c03-129">That is, you do not have to use one of the predefined masks.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="24c03-130">Nella casella Anteprima vengono visualizzati i caratteri visualizzati dall'utente in <xref:System.Windows.Forms.MaskedTextBox> .</span><span class="sxs-lookup"><span data-stu-id="24c03-130">The Preview box displays the characters that the user sees in the <xref:System.Windows.Forms.MaskedTextBox>.</span></span> <span data-ttu-id="24c03-131">Questi caratteri sono una guida che consente all'utente di immettere correttamente i dati.</span><span class="sxs-lookup"><span data-stu-id="24c03-131">These characters are a guide to help the user enter the data correctly.</span></span>  
  
4. <span data-ttu-id="24c03-132">Selezionare o deselezionare la casella di controllo **USA ValidatingType** .</span><span class="sxs-lookup"><span data-stu-id="24c03-132">Select or clear the **Use ValidatingType** check box.</span></span> <span data-ttu-id="24c03-133">La casella di controllo **use ValidatingType** specifica se un tipo di dati viene utilizzato per verificare l'input dei dati da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="24c03-133">The **Use ValidatingType** check box specifies whether a data type is used to verify the data input by the user.</span></span> <span data-ttu-id="24c03-134">Per altre informazioni, vedere la proprietà <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>.</span><span class="sxs-lookup"><span data-stu-id="24c03-134">For more information, see the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property.</span></span>  
  
5. <span data-ttu-id="24c03-135">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="24c03-135">Click **OK**.</span></span>  
  
     <span data-ttu-id="24c03-136">La maschera viene immessa nella proprietà **mask** nella finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="24c03-136">The mask is entered in the **Mask** property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24c03-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24c03-137">See also</span></span>

- [<span data-ttu-id="24c03-138">Procedura dettagliata: Uso del controllo MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="24c03-138">Walkthrough: Working with the MaskedTextBox Control</span></span>](walkthrough-working-with-the-maskedtextbox-control.md)

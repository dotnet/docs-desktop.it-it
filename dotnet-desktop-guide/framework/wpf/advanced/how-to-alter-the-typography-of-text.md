---
title: 'Procedura: modificare le opzioni tipografiche del testo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting Typography attributes [WPF]
- Typography attribute [WPF], setting
ms.assetid: 19a3b49b-60a2-4c11-a786-e26b4c965588
ms.openlocfilehash: 4c027424632f8671ba8d7cae1c899ef3a53edc26
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964090"
---
# <a name="how-to-alter-the-typography-of-text"></a>Procedura: modificare le opzioni tipografiche del testo
Nell'esempio seguente viene illustrato come impostare l' <xref:System.Windows.Documents.TextElement.Typography%2A> attributo utilizzando <xref:System.Windows.Documents.Paragraph> come elemento di esempio.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 La figura seguente illustra il rendering di questo esempio.  
  
 ![Schermata: testo con tipografia modificata](./media/textelement-typog.png "TextElement_Typog")  
  
 La figura seguente mostra invece il rendering dello stesso esempio con le proprietà tipografiche predefinite.  
  
 ![Schermata: testo con tipografia modificata](./media/textelement-typog-default.png "TextElement_Typog_Default")  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come impostare la <xref:System.Windows.Controls.TextBox.Typography%2A> proprietà a livello di codice.  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sui documenti dinamici](flow-document-overview.md)

---
title: Applicare gli attributi nei controlli
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: f12b430d787b4b974e12902b2c17d3a35a09e468
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962059"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a>Procedura: Applicare attributi nei controlli Windows Forms

Per sviluppare componenti e controlli che interagiscono correttamente con l'ambiente di progettazione e vengono eseguiti correttamente in fase di esecuzione, è necessario applicare correttamente gli attributi a classi e membri.  
  
## <a name="example"></a>Esempio  

 Nell'esempio di codice riportato di seguito viene illustrato come utilizzare diversi attributi in un controllo personalizzato. Il controllo illustra una semplice funzionalità di registrazione. Quando il controllo è associato a un'origine dati, Visualizza i valori inviati dall'origine dati in un <xref:System.Windows.Forms.DataGridView> controllo. Se un valore supera il valore specificato dalla `Threshold` proprietà, `ThresholdExceeded` viene generato un evento.  
  
 `AttributesDemoControl`Registra i valori con una `LogEntry` classe. La `LogEntry` classe è una classe modello, che significa che è parametrizzata sul tipo che registra. Se, ad esempio, l'oggetto `AttributesDemoControl` sta registrando valori di tipo `float` , ogni `LogEntry` istanza viene dichiarata e utilizzata come indicato di seguito.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> Poiché `LogEntry` è parametrizzato da un tipo arbitrario, deve utilizzare la reflection per operare sul tipo di parametro. Per il funzionamento della funzionalità di soglia, il tipo di parametro `T` deve implementare l' <xref:System.IComparable> interfaccia.  
  
 Il form che ospita le `AttributesDemoControl` query di un contatore delle prestazioni periodicamente. Ogni valore è incluso in un oggetto `LogEntry` del tipo appropriato e viene aggiunto al form <xref:System.Windows.Forms.BindingSource> . `AttributesDemoControl`Riceve il valore tramite la relativa data binding e visualizza il valore in un <xref:System.Windows.Forms.DataGridView> controllo.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 Il primo esempio di codice è l' `AttributesDemoControl` implementazione di. Nel secondo esempio di codice viene illustrato un form che utilizza `AttributesDemoControl` .  
  
## <a name="class-level-attributes"></a>Attributi a livello di classe  

 Alcuni attributi vengono applicati a livello di classe. Nell'esempio di codice riportato di seguito vengono illustrati gli attributi comunemente applicati a un controllo Windows Forms.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a>TypeConverter (attributo)  

 <xref:System.ComponentModel.TypeConverterAttribute> è un altro attributo a livello di classe comunemente utilizzato. Nell'esempio di codice riportato di seguito viene illustrato l'utilizzo della `LogEntry` classe. In questo esempio viene inoltre illustrata un'implementazione di <xref:System.ComponentModel.TypeConverter> per il `LogEntry` tipo, denominato `LogEntryTypeConverter` .  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a>Attributi a livello di membro  

 Alcuni attributi vengono applicati a livello di membro. Negli esempi di codice riportati di seguito vengono illustrati alcuni attributi che vengono comunemente applicati alle proprietà dei controlli Windows Forms.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a>Attributo AmbientValue  

 Nell'esempio seguente viene illustrato il <xref:System.ComponentModel.AmbientValueAttribute> e viene mostrato il codice che supporta l'interazione con l'ambiente di progettazione. Questa interazione è detta *ambiente*.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a>Attributi DataBinding  

 Negli esempi seguenti viene illustrata un'implementazione di data binding complesse. Il livello di classe <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> , illustrato in precedenza, specifica `DataSource` le `DataMember` proprietà e da utilizzare per data binding. <xref:System.ComponentModel.AttributeProviderAttribute>Specifica il tipo a cui la `DataSource` proprietà eseguirà l'associazione.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
- Il form che ospita l'oggetto `AttributesDemoControl` richiede un riferimento all' `AttributesDemoControl` assembly per la compilazione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [Sviluppo di controlli Windows Form personalizzati con .NET Framework](developing-custom-windows-forms-controls.md)
- [Attributi nei controlli Windows Form](attributes-in-windows-forms-controls.md)
- [Procedura: serializzare raccolte di tipi standard mediante DesignerSerializationVisibilityAttribute](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))

# [XML 文件和資料](index.md)
## [XML 處理選項](xml-processing-options.md)
## [處理記憶體中的 XML 資料](processing-xml-data-in-memory.md)
### [使用 DOM 模型處理 XML 資料](process-xml-data-using-the-dom-model.md)
#### [XML 文件物件模型 (DOM)](xml-document-object-model-dom.md)
#### [類型的 XML 節點](types-of-xml-nodes.md)
#### [XML 文件物件模型 (DOM) 階層架構](xml-document-object-model-dom-hierarchy.md)
#### [將物件階層架構對應至 XML 資料](mapping-the-object-hierarchy-to-xml-data.md)
#### [建立 XML 文件](xml-document-creation.md)
#### [XML 文件讀入 DOM](reading-an-xml-document-into-the-dom.md)
##### [內嵌在文件的樣式表指示詞](style-sheet-directives-embedded-in-a-document.md)
##### [從讀取器載入資料](load-data-from-a-reader.md)
##### [泛空白字元和顯著泛空白字元處理載入 DOM 時](white-space-and-significant-white-space-handling-when-loading-the-dom.md)
##### [存取 DOM 中的屬性](accessing-attributes-in-the-dom.md)
##### [實體宣告和實體參考讀入 DOM](reading-entity-declarations-and-entity-references-into-the-dom.md)
##### [保留實體參考](entity-references-are-preserved.md)
##### [實體參考已擴充且沒有保留](entity-references-are-expanded-and-not-preserved.md)
#### [將節點插入 XML 文件](inserting-nodes-into-an-xml-document.md)
##### [在 DOM 中建立新的節點](create-new-nodes-in-the-dom.md)
###### [DOM 中的項目建立新屬性](creating-new-attributes-for-elements-in-the-dom.md)
###### [XML 項目和屬性名稱的驗證時，建立新的節點](xml-element-and-attribute-name-verification-when-creating-new-nodes.md)
###### [建立新的實體參考](creating-new-entity-references.md)
###### [命名空間包含的元素和屬性的新節點的實體參考擴充的影響](namespace-affect-on-entity-ref-expansion-for-new-nodes.md)
##### [複製現有節點](copy-existing-nodes.md)
##### [現有的節點複製到另一份文件](copying-existing-nodes-from-one-document-to-another.md)
##### [複製文件片段](copying-document-fragments.md)
#### [從 XML 文件移除節點、 內容和值](removing-nodes-content-and-values-from-an-xml-document.md)
##### [從 DOM 移除節點](removing-nodes-from-the-dom.md)
##### [移除 DOM 中項目節點屬性](removing-attributes-from-an-element-node-in-the-dom.md)
##### [移除 DOM 中的節點內容](removing-node-content-in-the-dom.md)
#### [修改節點、 內容和 XML 文件中的值](modifying-nodes-content-and-values-in-an-xml-document.md)
#### [驗證 DOM 中的 XML 文件](validating-an-xml-document-in-the-dom.md)
#### [儲存與寫入文件](saving-and-writing-a-document.md)
#### [使用 XPath 巡覽選取節點](select-nodes-using-xpath-navigation.md)
#### [解析外部資源](resolving-external-resources.md)
#### [使用 xmlnametable 進行物件比較](object-comparison-using-xmlnametable.md)
#### [Namednodemap 和 Nodelist 中的節點集合](node-collections-in-namednodemaps-and-nodelists.md)
##### [根據名稱或索引擷取的未排序的節點](unordered-node-retrieval-by-name-or-index.md)
##### [排序根據索引擷取節點](ordered-node-retrieval-by-index.md)
#### [動態更新 Nodelist 和 Namednodemap](dynamic-updates-to-nodelists-and-namednodemaps.md)
#### [在 DOM 中的命名空間支援](namespace-support-in-the-dom.md)
##### [命名空間和 Dtd DOM 中](namespaces-and-dtds-in-the-dom.md)
##### [變更 XML 文件中的命名空間宣告](changing-namespace-declarations-in-an-xml-document.md)
##### [變更命名空間前置詞屬性](changing-namespace-prefix-properties.md)
#### [使用 xmlnodechangedeventargs 之 XML 文件中的事件處理](event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md)
#### [擴充 DOM](extending-the-dom.md)
### [使用 XPath 資料模型處理 XML 資料](process-xml-data-using-the-xpath-data-model.md)
#### [使用 XPathDocument 及 XmlDocument 讀取 XML 資料](reading-xml-data-using-xpathdocument-and-xmldocument.md)
#### [選取、 評估及使用 XPathNavigator 比對 XML 資料](selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)
##### [使用 XPathNavigator 選取 XML 資料](select-xml-data-using-xpathnavigator.md)
##### [使用 XPathNavigator 評估 XPath 運算式](evaluate-xpath-expressions-using-xpathnavigator.md)
##### [使用 XPathNavigator 比對節點](matching-nodes-using-xpathnavigator.md)
##### [XPath 查詢中辨識的節點型別](node-types-recognized-with-xpath-queries.md)
##### [XPath 查詢及命名空間](xpath-queries-and-namespaces.md)
##### [編譯的 XPath 運算式](compiled-xpath-expressions.md)
##### [XPath 命名空間巡覽](xpath-namespace-navigation.md)
#### [使用 XPathNavigator 存取 XML 資料](accessing-xml-data-using-xpathnavigator.md)
##### [使用 XPathNavigator 巡覽節點集](node-set-navigation-using-xpathnavigator.md)
##### [巡覽屬性及命名空間節點使用 XPathNavigator](attribute-and-namespace-node-navigation-using-xpathnavigator.md)
##### [使用 XPathNavigator 擷取 XML 資料](extract-xml-data-using-xpathnavigator.md)
##### [存取強型別使用 XPathNavigator XML 資料](accessing-strongly-typed-xml-data-using-xpathnavigator.md)
##### [使用者定義函式和變數](user-defined-functions-and-variables.md)
#### [使用 XPathNavigator 編輯 XML 資料](editing-xml-data-using-xpathnavigator.md)
##### [使用 XPathNavigator 插入 XML 資料](insert-xml-data-using-xpathnavigator.md)
##### [使用 XPathNavigator 修改 XML 資料](modify-xml-data-using-xpathnavigator.md)
##### [使用 XPathNavigator 移除 XML 資料](remove-xml-data-using-xpathnavigator.md)
#### [使用 xpathnavigator 進行結構描述驗證](schema-validation-using-xpathnavigator.md)
### [使用 LINQ to XML 處理 XML 資料](process-xml-data-using-linq-to-xml.md)
## [XSLT 轉換](xslt-transformations.md)
### [使用 XslCompiledTransform 類別](using-the-xslcompiledtransform-class.md)
#### [XslCompiledTransform 類別的輸入](inputs-to-the-xslcompiledtransform-class.md)
#### [XslCompiledTransform 類別上的輸出選項](output-options-on-the-xslcompiledtransform-class.md)
#### [在 XSLT 處理期間解析外部資源](resolving-external-resources-during-xslt-processing.md)
#### [延伸 XSLT 樣式表](extending-xslt-style-sheets.md)
##### [XSLT 擴充物件](xslt-extension-objects.md)
##### [XSLT 參數](xslt-parameters.md)
##### [指令碼區塊使用 msxsl: script](script-blocks-using-msxsl-script.md)
#### [可復原的 XSLT 錯誤](recoverable-xslt-errors.md)
#### [如何： 轉換節點片段](how-to-transform-a-node-fragment.md)
### [從 XslTransform 類別移轉](migrating-from-the-xsltransform-class.md)
#### [如何： 移轉 XslTransform 程式碼](how-to-migrate-your-xsltransform-code.md)
### [XSLT 安全性考量](xslt-security-considerations.md)
### [XSLT 編譯器 (xsltc.exe)](xslt-compiler-xsltc-exe.md)
#### [如何： 使用組件執行 XSLT 轉換](how-to-perform-an-xslt-transformation-by-using-an-assembly.md)
### [使用 XslTransform 類別進行 XSLT 轉換](xslt-transformations-with-the-xsltransform-class.md)
#### [XslTransform 類別中的 Discretionary 行為的實作](implementation-of-discretionary-behaviors-in-the-xsltransform-class.md)
#### [XslTransform 類別實作 XSLT 處理器](xsltransform-class-implements-the-xslt-processor.md)
##### [XslTransform 的輸出](outputs-from-an-xsltransform.md)
##### [不同的存放區上的 XSLT 轉換](xslt-transformations-over-different-stores.md)
##### [解析外部的 XSLT 樣式表和文件](resolving-external-xslt-style-sheets-and-documents.md)
##### [樣式表參數和擴充物件的 XsltArgumentList](xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md)
##### [XSLT 樣式表指令碼使用 < msxsl: script >](xslt-stylesheet-scripting-using-msxsl-script.md)
##### [支援 msxsl:node-set() 函式](support-for-the-msxsl-node-set-function.md)
##### [轉換中的節點集](node-sets-in-transformations.md)
##### [轉換中的結果樹狀片段](result-tree-fragment-in-transformations.md)
#### [轉換中的 XPathNavigator](xpathnavigator-in-transformations.md)
#### [轉換中的 XPathNodeIterator](xpathnodeiterator-in-transformations.md)
#### [XslTransform 的 XPathDocument 輸入](xpathdocument-input-to-xsltransform.md)
#### [XslTransform 的 XmlDataDocument 輸入](xmldatadocument-input-to-xsltransform.md)
#### [XslTransform 的 XmlDocument 輸入](xmldocument-input-to-xsltransform.md)
## [使用 XML 結構描述](working-with-xml-schemas.md)
### [XML 結構描述物件模型 (SOM)](xml-schema-object-model-som.md)
#### [XML 結構描述物件模型概觀](xml-schema-object-model-overview.md)
#### [讀取和寫入 XML 結構描述](reading-and-writing-xml-schemas.md)
#### [建置 XML 結構描述](building-xml-schemas.md)
#### [周遊 XML 結構描述](traversing-xml-schemas.md)
#### [編輯 XML 結構描述](editing-xml-schemas.md)
#### [併入或匯入 XML 結構描述](including-or-importing-xml-schemas.md)
### [結構描述編譯的 XmlSchemaSet](xmlschemaset-for-schema-compilation.md)
#### [後結構描述編譯資訊集](post-schema-compilation-infoset.md)
#### [使用 XmlSchemaSet 驗證 XML 結構描述 (XSD)](xml-schema-xsd-validation-with-xmlschemaset.md)
#### [XmlSchemaCollection 結構描述編譯](xmlschemacollection-schema-compilation.md)
##### [使用 XmlSchemaCollection 的 XDR 驗證](xdr-validation-with-xmlschemacollection.md)
##### [使用 xmlschemacollection 進行 XML 結構描述 (XSD) 驗證](xml-schema-xsd-validation-with-xmlschemacollection.md)
### [XmlSchemaValidator 推入型驗證](xmlschemavalidator-push-based-validation.md)
### [推斷 XML 結構描述](inferring-an-xml-schema.md)
#### [從 XML 文件推斷結構描述](inferring-schemas-from-xml-documents.md)
#### [推斷結構描述節點型別與結構的規則](rules-for-inferring-schema-node-types-and-structure.md)
#### [推斷簡單型別的規則](rules-for-inferring-simple-types.md)
## [XML 與關聯式資料和 ADO.NET 互相整合](xml-integration-with-relational-data-and-adonet.md)
## [管理 XML 文件中的命名空間](managing-namespaces-in-an-xml-document.md)
## [System.Xml 類別中的類型支援](type-support-in-the-system-xml-classes.md)
### [XML 資料類型對應至 CLR 型別](mapping-xml-data-types-to-clr-types.md)
### [XML 型別支援實作注意事項](xml-type-support-implementation-notes.md)
### [XML 資料型別轉換](conversion-of-xml-data-types.md)
#### [將字串轉換為.NET Framework 資料型別](converting-strings-to-dotnet-data-types.md)
#### [將.NET Framework 型別轉換為字串](converting-dotnet-types-to-strings.md)

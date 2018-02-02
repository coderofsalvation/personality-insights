---

copyright:
  years: 2015, 2017
lastupdated: "2017-08-13"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:javascript: .ph data-hd-programlang='javascript'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}

# 用法指引
{: #guidance}

使用者將 {{site.data.keyword.personalityinsightsshort}} 服務套用在愈來愈多的使用案例上。他們套用此服務，以透過店內的多媒體資訊站，提供個人化的產品推薦給客戶。他們從美國歷屆總統的國情咨文 (State of the Union Addresses) 推斷，探索並分析每位總統的性格差異。另外，他們將此服務與 {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}} 組合中的另一項產品 {{site.data.keyword.watson}} Explorer 整合，示範投資顧問如何根據投資者的性格側寫，提供適合的選項。（如需相關資訊，請參閱[使用案例](/docs/services/personality-insights/usecases.html)。）
{: shortdesc}

在這些和其他未來使用案例的整個開發過程中，{{site.data.keyword.IBM_notm}} 已經與銀行、醫療機構事業、客戶體驗管理公司和聯邦政府機構進行交流。這些交流通常會產生適用之使用實務的相關問題。其中部分問題及其解答的鏈結會以 FAQ（常見問題）形式提供。{{site.data.keyword.IBM_notm}} 對一些其他問題的觀點如下：

-   哪種文字類型最適合用來推斷個人的性格？這些文字是否必須具有反映的本質？如果是，會如何反映，以及要如何測量反映？請參閱[哪種文字類型最適合用來推斷性格？](#optimal)
-   要如何解譯某個人針對另一個人撰寫的文字？是否可以從作者虛構的作品來推斷作者的性格？是否可以結合多人撰寫的文字來取得性格側寫？請參閱[從不同的文字類型解譯結果](#interpreting)。
-   是否可以從轉錄或翻譯服務所產生的文字推斷性格側寫？請參閱[從所產生的文字推斷性格](#inferring)。
-   是否可以將性格側寫套用至應用程式，例如個人配對、監視及預測心理衛生，以及透過社交媒體來監視激進和犯罪元素？請參閱[將性格側寫運用在特定應用程式](#applying)。
-   個人的性格是否會隨著年齡的增長而演變？請參閱[個人的性格是否會隨著時間而改變？](#evolve)

## 哪種文字類型最適合用來推斷性格？
{: #optimal}

哪種文字類型最適合用來推斷性格？文字是否需要為反映、自我反映、正式或非正式？如何測量日常生活中使用的字詞？這類字詞是否具有反映的本質？這些問題的答案可協助您選取最適當的輸入文字，以最有效的方式套用服務。

{{site.data.keyword.IBM_notm}} 在設計 {{site.data.keyword.personalityinsightsshort}} 服務時的基本前提是，個人日常使用的字詞會顯示一個人的性格（[Pennebaker 等人 (2001)](/docs/services/personality-insights/references.html#pennebaker2001)，以及 [Pennebaker 等人 (2007)](/docs/services/personality-insights/references.html#pennebaker2007)）。此服務可以分析個人針對自己或任何主題所撰寫的字詞，但是那個人必須選擇及撰寫那些字詞，此服務才能產生精確的性格側寫。

{{site.data.keyword.IBM_notm}} 認為，用來推斷個人性格的文字最好具有反映性。反映性書寫會顯露作者的個人經驗和回應；這需要作者將一定數量的想法轉化為所選擇的字詞。例如，文字中可以包括撰寫者對某人或某事的看法、態度、觀感和觀察，或是可以表達出撰寫者的好惡，但必須能反映撰寫者選用的字詞。

關於用來推斷性格的文字中是否需要具有反映性，{{site.data.keyword.IBM_notm}} 在心理語言學文獻中並沒有找到明確的參考資料。不過，{{site.data.keyword.IBM_notm}} 確實注意到某些研究會在實驗室設定中，要求個人針對特定主題撰寫短文，然後使用所收集文字中的字詞。這類書寫會隱約要求一定的反映量。其他研究則是使用自然樣本中的文字，例如各種主題的部落格、Twitter 上的推文、電子郵件，甚至是從*魔獸世界* 遊戲中擷取的通訊。這些研究全都是假設日常生活中所使用的字詞會顯露性格，因為這些字詞傾向於反映出撰寫者的思維。

其他研究顯示，情緒書寫、控管書寫、部落格和語音記錄都非常適合用來推斷性格。反之，科學文章只是稍微適用於推斷性格。此外，文獻指出，具有下列情況的文字會使獲得精確的性格測量更加複雜

-   缺乏真實性，如諷刺、嘲弄、密集的編輯或有多位作者
-   包括拼寫錯誤、技術詞彙、字詞有替代含義、否定，以及片語詞組，而非單一字詞
-   包括不適當的比較組，例如專業與個人，以及技術與情感寫作

## 從不同的文字類型解譯結果
{: #interpreting}

所要分析的文字類型，對 {{site.data.keyword.personalityinsightsshort}} 服務結果的品質有重大影響。下列各節討論如何解譯從不同來源取得的結果：

-   [從撰寫關於他人的文字解譯結果](#writingaboutothers)
-   [從虛構的作品解譯結果](#fictionalworks)
-   [從多人撰寫的文字解譯結果](#multipleindividuals)

### 從撰寫關於他人的文字解譯結果
{: #writingaboutothers}

若要確實推斷個人的性格，這些文字必須*由* 本人撰寫，還是可以由他人撰寫*關於* 該人的事項？當一個人撰寫關於另一個人的事項時，會從文字中推斷出哪個人的性格？

{{site.data.keyword.IBM_notm}} 的直覺是，不論主題為何，書寫內容一律會反映作者的性格。例如，如果個人 A 撰寫關於個人 B 的文字，該文字的分析會推斷個人 A 的性格。雖然個人 A 是撰寫關於個人 B 的文字，但選擇字詞來表達個人 B 相關事物的是個人 A。不過，{{site.data.keyword.IBM_notm}} 並沒有進行研究來明確地測試此情境。

### 從虛構的作品解譯結果
{: #fictionalworks}

{{site.data.keyword.IBM_notm}} 不建議從其虛構的作品推斷作者的性格。作者在撰寫小說時，會刻意為每個人物塑造不同的形象，他們會編造對話來反映人物的性格，並且會在心中預先定義每個人物的性格。

使用刻意反映人格化虛構人物性格的文字來推斷該人物創造者的性格，這個方式是有疑慮的。雖然每位作者都有獨特的風格，但那些人物還是刻意預先設定好的。不過，還是可以從作者的非小說類散文、訪談記錄或其他作品（例如簡介、序言、謝辭或獻辭）來推斷作者的性格。

### 從多人撰寫的文字解譯結果
{: #multipleindividuals}

{{site.data.keyword.personalityinsightsshort}} 服務常見的使用案例是分析品牌或公司的追蹤者。追蹤者的定義為在 Twitter 或 Facebook 公開粉絲專頁上追蹤某公司的人。在此實務範例中，目標是衍生公司追蹤者的整體性格。首選方法是收集足夠的群組成員撰寫文字，以計算每個個別成員的性格，然後將這些性格聚集在不同的群組中。這些群組代表追蹤該公司之具有不同性格特質的角色。

如果群組成員的可用文字不足，可將由眾多成員撰寫的文字合併並分析，以產生整個群組的平均或複合性格側寫。這種方式可以得到群組主要品質的指示，但此方法的精確度會隨著母體的多樣性而降低。在解譯聚集多人的文字而取得的側寫時，請謹慎操作。{{site.data.keyword.IBM_notm}} 在此領域的成果仍在起始階段；{{site.data.keyword.IBM_notm}} 會在找出令人信服的結果時，報告其發現內容。

## 從所產生的文字推斷性格
{: #inferring}

分析從轉錄或翻譯服務所產生的文字，會影響 {{site.data.keyword.personalityinsightsshort}} 服務結果的可靠性。下列各節討論從所產生文字推斷性格的影響：

-   [從語音記錄推斷性格](#transcription)
-   [從翻譯的文字推斷性格](#translation)

### 從語音記錄推斷性格
{: #transcription}

語音轉錄引擎（例如 {{site.data.keyword.IBM_notm}}{{site.data.keyword.speechtotextshort}} 服務）會從口語字詞產生撰寫的文字。因為不同的語音轉錄引擎有不同的精確度範圍，所以將語音轉為文字來輸入 {{site.data.keyword.personalityinsightsshort}} 服務的客戶必須注意，結果會因引擎的效能而有很大的差異。具體而言，{{site.data.keyword.IBM_notm}} 建議客戶和事業夥伴針對兩種錯誤類型來判斷轉錄的品質：

-   *掉字：* 轉錄中遺漏了某個口語字詞。
-   *替代字：* 口語字詞轉譯不正確。

替代字可能是更嚴重的問題，因為它可能會導入未說出的字詞，但是該符合字詞會被用來判斷性格。在使用轉譯的文字之前，請考慮手動更正測試主體的文字，並計算您找到的錯誤。然後，比較自動產生的文字與手動更正版本的結果，以判斷因為轉譯錯誤而導致的結果變異。

### 從翻譯的文字推斷性格
{: #translation}

語言翻譯服務會將以某種語言撰寫的文字翻譯成另一種語言。如同語音轉錄，翻譯後的文字是否可以用來作為 {{site.data.keyword.personalityinsightsshort}} 服務的輸入會是個問題。{{site.data.keyword.IBM_notm}} 不建議您使用從翻譯服務取得的文字作為 {{site.data.keyword.personalityinsightsshort}} 服務的輸入。依翻譯服務的不同，翻譯和性格推斷的結果都會有很大的不同。字詞及其語感和文字文化感受性往往會在翻譯中流失，而產生無效的結果。

{{site.data.keyword.IBM_notm}} 建議您只使用以啟用 {{site.data.keyword.personalityinsightsshort}} 服務之語言所撰寫的文字作為輸入。已啟用語言功能的服務版本會以輸入文字的國家語言進行剖析、使用國家語言字典來識別性格特質，並使用針對國家語言校準的模型來產生統計結果。如果您必須分析翻譯的文字，則 {{site.data.keyword.IBM_notm}} 建議您先使用人類語言專家的服務，手動翻譯一些文字樣本。然後，您可以比較 {{site.data.keyword.personalityinsightsshort}} 服務從手動和自動翻譯文字取得的結果，以瞭解結果中的變異。

{{site.data.keyword.IBM_notm}} 將會隨著商業需求增加，繼續新增更多語言。{{site.data.keyword.IBM_notm}} 瞭解，{{site.data.keyword.personalityinsightsshort}} 服務支援您國家語言的速度可能來不及供您使用。{{site.data.keyword.IBM_notm}} 正在進行測試，以比較從國家語言啟用取得的結果與取自語言翻譯服務的結果，並即時報告所發現的結果。

## 將性格側寫運用在特定應用程式
{: #applying}

{{site.data.keyword.personalityinsightsshort}} 服務可以套用至不可列舉的使用案例。下列各節說明將性格側寫用於一些特定目的的情況：

-   [個人配對](#matching)
-   [監視及預測心理衛生](#mentalhealth)
-   [透過社交媒體來監視激進和犯罪元素](#monitoring)

### 個人配對
{: #matching}

做好人際之間的配對可以增進關係中的互動和結果。公司內部的團隊建立，以及各種產業與客戶的互動也是如此。在一項醫生與病患配對的研究中，研究人員發現，病患會比較喜歡與自己相似的醫生。有效的醫生與病患配對可以建立信任並鼓勵溝通，進而增進病患聽從指示的意願，讓治療更成功 ([Godager, 2012](/docs/services/personality-insights/references.html#godager2012))。

性格也會影響專業人員與客戶之間的互動偏好。例如，具有高度責任感和開放性的病患會比較積極參與決定自己的療程。高度隨和或神經質的病患會比較偏好由醫生主導重要的醫療決策 ([Flynn &amp; Smith, 2007](/docs/services/personality-insights/references.html#flynn2007))。

### 監視及預測心理衛生
{: #mentalhealth}

{{site.data.keyword.IBM_notm}} 認為疾病診斷最好是由訓練有素的醫療專業人員來執行。從一個人的用字或許可以察覺出其心理狀態的一些徵兆。但是 {{site.data.keyword.IBM_notm}} 尚未在這個領域中從事研究來進行基準調查，或探索針對這類工作建立科學基準的可能性。

歡迎有興趣使用 {{site.data.keyword.personalityinsightsshort}} 服務來進行心理衛生診斷的客戶和事業夥伴，針對這類使用案例來設計及進行基準實驗。在這個領域中，目前正在進行並持續中的研究，包括將性格與醫療成果建立關聯的工作（[Israel 等人 (2014)](/docs/services/personality-insights/references.html#israel2014)），以及旨在從社交媒體預測產後憂鬱症和其他形式憂鬱症的工作（[De Choudhury 等人 (2013a)](/docs/services/personality-insights/references.html#dechoudhury2013a) 和 [De Choudhury 等人 (2013b)](/docs/services/personality-insights/references.html#dechoudhury2013b)）。

### 透過社交媒體來監視激進和犯罪元素
{: #monitoring}

全世界的政府機關都不斷地在尋找方法，以透過社交媒體管道來偵測個人或個人群組激進化的早期訊號。從個人的書寫內容推斷性格是 {{site.data.keyword.personalityinsightsshort}} 服務的傳統應用方式。因此，想當然耳，使用此服務透過社交媒體來推斷激進和犯罪元素是可行的使用案例。可靠的推斷不僅需要性格特質，還需要許多其他屬性，例如性別、年齡和地理位置。{{site.data.keyword.IBM_notm}} 尚未進行任何研究來驗證這個使用案例有效或無效。歡迎客戶和事業夥伴進行研究，以根據他們的特定目標和需求來探索這個使用案例。

## 個人的性格是否會隨著時間而改變？
{: #evolve}

個人的性格是否會隨著時間而演變？如果會，應該多久使用一次 {{site.data.keyword.personalityinsightsshort}} 服務來推斷一個人的性格？對於「一個人的性格會在成年後逐漸穩定」的理論，不同的研究提出了正反不同的證明。哈佛心理學教授 William James 在他 1890 年出版的關於測量性格穩定性的重要著作 *The Principles of Psychology*（心理學原理）中指出，「我們大部分的人，到三十歲的時候，性格就像石膏一樣，永遠不會再軟化了」。但最近的研究報告顯示，性格的確會隨著時間不斷演變：

-   [Helson 等人 (2002)](/docs/services/personality-insights/references.html#helson2002) 的報告表示，「性格變化在 30 歲以前最為明顯，之後就會穩定下來的這個想法並沒有依據」。作者對兩組人進行長達 40 年的縱貫性研究。他們指出，生命週期和社會氛圍是性格在成人時期改變的重要因素。他們表示，「『支配』和『獨立』的評分在兩組人的中年時期都達到高峰，而『責任』的評分在個人主義文化達到高峰的那幾年最低」。
-   [Scollon 和 Diener (2006)](/docs/services/personality-insights/references.html#scollon2006) 著手調查個人在外向、神經質，以及工作和關係滿意度隨著時間變化的差異。作者指出，工作和關係滿意度的增加，與隨著時間變化的神經質降低和外向提高相關聯。
-   [Roberts 和 Mroczek (2008)](/docs/services/personality-insights/references.html#roberts2008) 評論，有證據可證明「性格特質的平均變化，以及一生變化的個人差異」。作者指出，隨著年齡增長，人們所表現的自信、溫暖、自我控制和情緒穩定度都會增加。這些改變主導著青年時期（20 到 40 歲）。此外，性格特質的平均變化發生在中老年時期，表示性格特質在任何年齡都會改變。

根據這些研究，{{site.data.keyword.IBM_notm}} 建議，{{site.data.keyword.personalityinsightsshort}} 服務的使用者一律使用最新的資料，並盡可能使用最多的可用資料。{{site.data.keyword.IBM_notm}} 進一步建議使用者定期重新整理性格側寫，以擷取個人演變的性格。雖然 {{site.data.keyword.IBM_notm}} 傾向於認為性格演變有特定界限，但並沒有進行研究來調查此演變的上下界限。

可能會有人問多久要重新整理一次個人的性格側寫。{{site.data.keyword.IBM_notm}} 的指引是從指定的個人來尋找新資料和文字的可用性。如果自從取得其性格側寫後，該個人編寫了大量的新文字，可能就值得重新整理該側寫。這種方式可以擷取性格的演變本質（如果個人選擇接受性格會演變），同時又能為 {{site.data.keyword.personalityinsightsshort}} 服務提供使用更多字詞的好處，進而提升服務結果的精準度。

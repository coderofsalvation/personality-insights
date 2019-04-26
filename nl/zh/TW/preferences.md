---

copyright:
  years: 2015, 2019
lastupdated: "2019-03-07"

subcollection: personality-insights

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}
{:important: .important}
{:note: .note}
{:deprecated: .deprecated}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:javascript: .ph data-hd-programlang='javascript'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}

# 消費喜好
{: #preferences}

{{site.data.keyword.personalityinsightsshort}} 服務會針對三種模型來推斷作者的性格特質：「五大性格特質」、「需求」和「價值觀」。根據針對這些模型來推斷的結果，服務還可以針對輸入文字的作者產生消費喜好。將 `consumption_preferences` 查詢參數設為 `true`，即可讓要求取得消費喜好。
{: shortdesc}

服務會將超過 40 種消費喜好分組為八個高階種類。該喜好會指出作者喜好不同產品、服務和活動的可能性。例如，服務可用於識別

-   作者對於衣服（舒適與時尚）及汽車（成本與安全）的愛好。
-   作者的學習朝向不同的音樂、影片和閱讀。
-   作者對於環境及志願服務的態度。

企業使用服務的性格模型，可以更充分地瞭解其客戶，並可設計及開發更為個人化且目標更明確的行銷活動、產品和服務。消費喜好甚至可以讓他們更容易依據服務的結果來採取行動。企業可以輕鬆取得並回應至個人主要特質相關聯的喜好清單。如需消費喜好可能的應用方式的相關資訊，請參閱[使用案例](/docs/services/personality-insights?topic=personality-insights-usecases)和[運作中的服務](/docs/services/personality-insights?topic=personality-insights-applied)。

下列各節列出並說明服務可以傳回的消費喜好。如需解譯喜好數值的相關資訊，請參閱[消費喜好的評分](/docs/services/personality-insights?topic=personality-insights-numeric#scores)。如需 {{site.data.keyword.IBM_notm}} 如何開發這些喜好的相關資訊，請參閱[服務背後的科學](/docs/services/personality-insights?topic=personality-insights-science)。

## 購物喜好
{: #shopping}

購物喜好會指出作者對不同購買類型的興趣、不同外部來源對作者的購買習慣有多大影響，以及作者的消費習慣。種類 ID 和名稱為 `consumption_preferences_shopping` 和 `Purchasing Preferences`。此種類有 12 項喜好。

<table>
  <caption>表 1. 購物喜好</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消費喜好 ID
    </th>
    <th style="width:30%; text-align:left">
      名稱
    </th>
    <th style="text-align:center">
      評分
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_automobile_ownership_cost</code>
    </td>
    <td style="text-align:left">
      購車時可能比較注重擁有成本
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>0.5</code>（中立）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_automobile_safety</code>
    </td>
    <td style="text-align:left">
      購車時可能比較注重安全性
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>0.5</code>（中立）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_quality</code>
    </td>
    <td style="text-align:left">
      購買服飾時可能比較注重品質
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_style</code>
    </td>
    <td style="text-align:left">
      購買服飾時可能比較注重款式
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_comfort</code>
    </td>
    <td style="text-align:left">
      購買服飾時可能比較注重舒適性
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_brand_name</code>
    </td>
    <td style="text-align:left">
      購買產品時可能會受品牌名稱影響
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>0.5</code>（中立）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_utility</code>
    </td>
    <td style="text-align:left">
      購買產品時可能會受產品的實用性影響</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>0.5</code>（中立）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_online_ads</code>
    </td>
    <td style="text-align:left">
      購買產品時可能會受線上廣告影響
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_social_media</code>
    </td>
    <td style="text-align:left">
      購買產品時可能會受社交媒體影響</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_family_members</code>
    </td>
    <td style="text-align:left">
      購買產品時可能會受家人影響
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_spur_of_moment</code>
    </td>
    <td style="text-align:left">
      可能屬於衝動型購物
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>0.5</code>（中立）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_credit_card_payment</code>
    </td>
    <td style="text-align:left">
      可能偏好使用信用卡購物
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
</table>

## 電影喜好
{: #movie}

電影喜好會指出作者對不同類型電影的興趣。種類 ID 和名稱為 `consumption_preferences_movie` 和 `Movie Preferences`。此種類有 10 項喜好。

<table>
  <caption>表 2. 電影喜好</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消費喜好 ID
    </th>
    <th style="width:30%; text-align:left">
      名稱
    </th>
    <th style="text-align:center">
      評分
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_romance</code>
    </td>
    <td style="text-align:left">
      可能喜歡浪漫愛情片
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_adventure</code>
    </td>
    <td style="text-align:left">
      可能喜歡冒險片
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_horror</code>
    </td>
    <td style="text-align:left">
      可能喜歡恐怖片
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_musical</code>
    </td>
    <td style="text-align:left">
      可能喜歡音樂片
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_historical</code>
    </td>
    <td style="text-align:left">
      可能喜歡歷史片
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_science_fiction</code>
    </td>
    <td style="text-align:left">
      可能喜歡科幻片
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_war</code>
    </td>
    <td style="text-align:left">
      可能喜歡戰爭片
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_drama</code>
    </td>
    <td style="text-align:left">
      可能喜歡劇情片
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_action</code>
    </td>
    <td style="text-align:left">
      可能喜歡動作片
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_documentary</code>
    </td>
    <td style="text-align:left">
      可能喜歡紀錄片
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
</table>

## 音樂喜好
{: #music}

音樂喜好會指出作者對不同類型音樂的興趣，以及作者是否喜歡演奏音樂。種類 ID 和名稱為 `consumption_preferences_music` 和 `Music Preferences`。此種類有 9 項喜好。

<table>
  <caption>表 3. 音樂喜好</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消費喜好 ID
    </th>
    <th style="width:30%; text-align:left">
      名稱
    </th>
    <th style="text-align:center">
      評分
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_rap</code>
    </td>
    <td style="text-align:left">
      可能喜歡饒舌樂
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>0.5</code>（中立）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_country</code>
    </td>
    <td style="text-align:left">
      可能喜歡鄉村樂
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>0.5</code>（中立）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_r_b</code>
    </td>
    <td style="text-align:left">
      可能喜歡節奏藍調</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>0.5</code>（中立）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_hip_hop</code>
    </td>
    <td style="text-align:left">
      可能喜歡嘻哈樂
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>0.5</code>（中立）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_live_event</code>
    </td>
    <td style="text-align:left">
      可能會參加現場音樂活動
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_playing</code>
    </td>
    <td style="text-align:left">
      可能有演奏音樂的經驗
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_latin</code>
    </td>
    <td style="text-align:left">
      可能喜歡拉丁樂
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>0.5</code>（中立）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_rock</code>
    </td>
    <td style="text-align:left">
      可能喜歡搖滾樂
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>0.5</code>（中立）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_classical</code>
    </td>
    <td style="text-align:left">
      可能喜歡古典樂
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>0.5</code>（中立）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
</table>

## 閱讀和學習喜好
{: #reading}

閱讀和學習喜好會指出作者閱讀的可能性、作者閱讀的動機，以及作者喜歡閱讀的內容類型。種類 ID 和名稱為 `consumption_preferences_reading` 和 `Reading Preferences`。此種類有 5 項喜好。

<table>
  <caption>表 4. 閱讀和學習喜好</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消費喜好 ID
    </th>
    <th style="width:30%; text-align:left">
      名稱
    </th>
    <th style="text-align:center">
      評分
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_read_frequency</code>
    </td>
    <td style="text-align:left">
      可能經常閱讀
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>0.5</code>（中立）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_entertainment_magazines</code>
    </td>
    <td style="text-align:left">
      可能閱讀娛樂雜誌
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_non_fiction</code>
    </td>
    <td style="text-align:left">
      可能閱讀非小說類的書籍
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_financial_investing</code>
    </td>
    <td style="text-align:left">
      可能閱讀財經投資書籍
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_autobiographies</code>
    </td>
    <td style="text-align:left">
      可能閱讀傳記文學
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
</table>

## 健康和活動喜好
{: #health}

健康和活動喜好會指出作者對健康食物和體能活動的興趣。種類 ID 和名稱為 `consumption_preferences_health_and_activity` 和 `Health & Activity Preferences`。此種類有 3 項喜好。

<table>
  <caption>表 5. 健康和活動喜好</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消費喜好 ID
    </th>
    <th style="width:30%; text-align:left">
      名稱
    </th>
    <th style="text-align:center">
      評分
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_eat_out</code>
    </td>
    <td style="text-align:left">
      可能經常外食
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>0.5</code>（中立）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_gym_membership</code>
    </td>
    <td style="text-align:left">
      可能有健身房會員資格
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_outdoor</code>
    </td>
    <td style="text-align:left">
      可能喜歡戶外活動
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>0.5</code>（中立）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
</table>

## 企業家精神喜好
{: #entrepreneur}

企業家精神喜好會指出作者對創業的興趣。種類 ID 和名稱為 `consumption_preferences_entrepreneurship` 和 `Entrepreneurship Preferences`。此種類有 1 項喜好。

<table>
  <caption>表 6. 企業家精神喜好</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消費喜好 ID
    </th>
    <th style="width:30%; text-align:left">
      名稱
    </th>
    <th style="text-align:center">
      評分
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_start_business</code>
    </td>
    <td style="text-align:left">
      可能考慮在未來幾年內創業
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>0.5</code>（中立）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
</table>

## 環境關懷喜好
{: #environment}

環境關懷喜好會指出作者對環境的興趣。種類 ID 和名稱為 `consumption_preferences_environmental_concern` 和 `Environmental Concern Preferences`。此種類有 1 項喜好。

<table>
  <caption>表 7. 環境關懷喜好</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消費喜好 ID
    </th>
    <th style="width:30%; text-align:left">
      名稱
    </th>
    <th style="text-align:center">
      評分
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_concerned_environment</code>
    </td>
    <td style="text-align:left">
      可能比較注重環境議題
</td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>0.5</code>（中立）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
</table>

## 志願服務喜好
{: #volunteer}

志願服務喜好會指出作者對志願參與社會事業的興趣。種類 ID 和名稱為 `consumption_preferences_volunteering` 和 `Volunteering Preferences`。此種類有 1 項喜好。

<table>
  <caption>表 8. 志願服務喜好</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消費喜好 ID
    </th>
    <th style="width:30%; text-align:left">
      名稱
    </th>
    <th style="text-align:center">
      評分
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_volunteer</code>
    </td>
    <td style="text-align:left">
      可能志願參與社會事業
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不太可能）<br/>
      <code>1.0</code>（可能）
    </td>
  </tr>
</table>

---

copyright:
  years: 2015, 2017
lastupdated: "2017-10-12"

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

# 消費嗜好性
{: #preferences}

{{site.data.keyword.personalityinsightsshort}} サービスは、3 つのモデル (ビッグ・ファイブ、ニーズ、および価値) について筆者のパーソナリティー特性を推論します。本サービスは、これらのモデルでの結果に基づいて、入力テキストの筆者の消費嗜好性も生成できます。消費嗜好性を取得するには、要求の `consumption_preferences` 照会パラメーターを `true` に設定します。
{: shortdesc}

40 を超える消費嗜好性は大きく 8 つのカテゴリーにグループ分けされていて、さまざまな商品、サービス、およびアクティビティーを筆者が好む可能性を示します。例えば、本サービスは、筆者が衣類を購入するときの傾向 (快適 vs. ファッション性) や車を購入するときの傾向 (コスト vs. 安全性) を識別できます。また、音楽、映画、および読書の多様なジャンルに対する好み、環境やボランティア活動に対する態度や、その他さまざまなことを識別できます。

本サービスのパーソナリティー・モデルをビジネスで利用することによって、顧客をより深く理解したり、キャンペーン、商品、およびサービスの設計および開発を、より細かくパーソナライズされ、ターゲットを絞ったものにしたりできます。消費嗜好性を使用すると、本サービスの結果に基づいたアクションを実行するのがより簡単になります。ビジネスでは、個人の主な性格と結び付いている消費嗜好性のリストを簡単に取得し、それに合った対応を取ることができます。消費嗜好性のアプリケーションとしてどのようなものが可能なのかについて詳しくは、『[ユース・ケース](/docs/services/personality-insights/usecases.html)』および『[サービスの応用](/docs/services/personality-insights/applied.html)』を参照してください。

以降のセクションでは、本サービスが返すことのできる消費嗜好性をリストし、説明しています。消費嗜好性の数値の解釈について詳しくは、『[消費嗜好性のスコア](/docs/services/personality-insights/numeric.html#scores)』を参照してください。{{site.data.keyword.IBM_notm}} が消費嗜好性をどのように開発したのかについて詳しくは、『[サービスを支えるサイエンス](/docs/services/personality-insights/science.html)』を参照してください。

## ショッピングの消費嗜好性
{: #shopping}

ショッピングの消費嗜好性は、さまざまな種類の購入に対する筆者の関心、さまざまな外部ソースが筆者の購入習慣に影響を与える程度、および筆者の消費習慣を示します。このカテゴリーの ID と名前は、`consumption_preferences_shopping` および `Purchasing Preferences` です。このカテゴリーには 12 個の消費嗜好性があります。

<table>
  <caption>表 1. ショッピングの消費嗜好性</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消費嗜好性 ID
    </th>
    <th style="width:30%; text-align:left">
      名前
    </th>
    <th style="text-align:center">
      スコア
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_automobile_ownership_cost</code>
    </td>
    <td style="text-align:left">
      車を購入するときに所有コストを重視する可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>0.5</code> (中)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_automobile_safety</code>
    </td>
    <td style="text-align:left">
      車を購入するときに安全性を重視する可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>0.5</code> (中)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_quality</code>
    </td>
    <td style="text-align:left">
      衣類を購入するときに品質を重視する可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_style</code>
    </td>
    <td style="text-align:left">
      衣類を購入するときに流行を重視する可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_comfort</code>
    </td>
    <td style="text-align:left">
      衣類を購入するときに快適性を重視する可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_brand_name</code>
    </td>
    <td style="text-align:left">
      商品購入時にブランド名に影響される可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>0.5</code> (中)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_utility</code>
    </td>
    <td style="text-align:left">
      商品購入時に製品の効用に影響される可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>0.5</code> (中)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_online_ads</code>
    </td>
    <td style="text-align:left">
      商品購入時にオンライン広告に影響される可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_social_media</code>
    </td>
    <td style="text-align:left">
      商品購入時にソーシャル・メディアに影響される可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_family_members</code>
    </td>
    <td style="text-align:left">
      商品購入時に家族に影響される可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_spur_of_moment</code>
    </td>
    <td style="text-align:left">
      衝動買いの可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>0.5</code> (中)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_credit_card_payment</code>
    </td>
    <td style="text-align:left">
      ショッピングでのクレジット・カード使用を好む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
</table>

## 映画の消費嗜好性
{: #movie}

映画の消費嗜好性は、さまざまな種類の映画に対する筆者の関心を示します。このカテゴリーの ID と名前は、`consumption_preferences_movie` および `Movie Preferences` です。このカテゴリーには 10 個の消費嗜好性があります。

<table>
  <caption>表 2. 映画の消費嗜好性</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消費嗜好性 ID
    </th>
    <th style="width:30%; text-align:left">
      名前
    </th>
    <th style="text-align:center">
      スコア
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_romance</code>
    </td>
    <td style="text-align:left">
      ロマンス映画を好む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_adventure</code>
    </td>
    <td style="text-align:left">
      アドベンチャー映画を好む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_horror</code>
    </td>
    <td style="text-align:left">
      ホラー映画を好む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_musical</code>
    </td>
    <td style="text-align:left">
      音楽映画を好む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_historical</code>
    </td>
    <td style="text-align:left">
      歴史映画を好む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_science_fiction</code>
    </td>
    <td style="text-align:left">
      SF 映画を好む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_war</code>
    </td>
    <td style="text-align:left">
      戦争映画を好む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_drama</code>
    </td>
    <td style="text-align:left">
      ドラマ映画を好む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_action</code>
    </td>
    <td style="text-align:left">
      アクション映画を好む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_documentary</code>
    </td>
    <td style="text-align:left">
      ドキュメンタリー映画を好む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
</table>

## 音楽の消費嗜好性
{: #music}

音楽の消費嗜好性は、さまざまな種類の音楽に対する筆者の関心、および筆者が音楽演奏を楽しむかどうかを示します。このカテゴリーの ID と名前は、`consumption_preferences_music` および `Music Preferences` です。このカテゴリーには 9 個の消費嗜好性があります。

<table>
  <caption>表 3. 音楽の消費嗜好性</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消費嗜好性 ID
    </th>
    <th style="width:30%; text-align:left">
      名前
    </th>
    <th style="text-align:center">
      スコア
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_rap</code>
    </td>
    <td style="text-align:left">
      ラップ・ミュージックを好む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>0.5</code> (中)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_country</code>
    </td>
    <td style="text-align:left">
      カントリー・ミュージックを好む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>0.5</code> (中)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_r_b</code>
    </td>
    <td style="text-align:left">
      R&amp;B ミュージックを好む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>0.5</code> (中)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_hip_hop</code>
    </td>
    <td style="text-align:left">
      ヒップホップ・ミュージックを好む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>0.5</code> (中)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_live_event</code>
    </td>
    <td style="text-align:left">
      ライブ音楽イベントに行く可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_playing</code>
    </td>
    <td style="text-align:left">
      音楽演奏の経験がある可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_latin</code>
    </td>
    <td style="text-align:left">
      ラテン・ミュージックを好む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>0.5</code> (中)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_rock</code>
    </td>
    <td style="text-align:left">
      ロック・ミュージックを好む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>0.5</code> (中)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_classical</code>
    </td>
    <td style="text-align:left">
      クラシック音楽を好む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>0.5</code> (中)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
</table>

## 読書および学習の消費嗜好性
{: #reading}

読書および学習の消費嗜好性は、筆者が読書好きである可能性、筆者が読書する動機、および筆者の読書傾向を示します。このカテゴリーの ID と名前は、`consumption_preferences_reading` および `Reading Preferences` です。 このカテゴリーには 5 個の消費嗜好性があります。

<table>
  <caption>表 4. 読書および学習の消費嗜好性</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消費嗜好性 ID
    </th>
    <th style="width:30%; text-align:left">
      名前
    </th>
    <th style="text-align:center">
      スコア
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_read_frequency</code>
    </td>
    <td style="text-align:left">
      頻繁に読書する可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>0.5</code> (中)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_entertainment_magazines</code>
    </td>
    <td style="text-align:left">
      娯楽雑誌を読む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_non_fiction</code>
    </td>
    <td style="text-align:left">
      ノンフィクション本を読む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_financial_investing</code>
    </td>
    <td style="text-align:left">
      金融投資の本を読む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_autobiographies</code>
    </td>
    <td style="text-align:left">
      自伝本を読む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
</table>

## 健康および運動の消費嗜好性
{: #health}

健康および運動の消費嗜好性は、健康的食品および運動に対する筆者の関心を示します。このカテゴリーの ID と名前は、`consumption_preferences_health_and_activity` および `Health & Activity Preferences` です。 このカテゴリーには 3 個の消費嗜好性があります。

<table>
  <caption>表 5. 健康および運動の消費嗜好性</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消費嗜好性 ID
    </th>
    <th style="width:30%; text-align:left">
      名前
    </th>
    <th style="text-align:center">
      スコア
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_eat_out</code>
    </td>
    <td style="text-align:left">
      頻繁に外食する可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>0.5</code> (中)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_gym_membership</code>
    </td>
    <td style="text-align:left">
      ジムのメンバーである可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_outdoor</code>
    </td>
    <td style="text-align:left">
      アウトドア活動を好む可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>0.5</code> (中)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
</table>

## 起業家精神の消費嗜好性
{: #entrepreneur}

起業家精神の消費嗜好性は、ビジネスを始めることに対する筆者の関心を示します。このカテゴリーの ID と名前は、`consumption_preferences_entrepreneurship` および `Entrepreneurship Preferences` です。 このカテゴリーには 1 個の消費嗜好性があります。

<table>
  <caption>表 6. 起業家精神の消費嗜好性</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消費嗜好性 ID
    </th>
    <th style="width:30%; text-align:left">
      名前
    </th>
    <th style="text-align:center">
      スコア
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_start_business</code>
    </td>
    <td style="text-align:left">
      数年以内にビジネスを始めることを検討している可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>0.5</code> (中)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
</table>

## 環境への関心の消費嗜好性
{: #environment}

環境への関心の消費嗜好性は、環境に対する筆者の関心を示します。このカテゴリーの ID と名前は、`consumption_preferences_environmental_concern` および `Environmental Concern Preferences` です。このカテゴリーには 1 個の消費嗜好性があります。

<table>
  <caption>表 7. 環境への関心の消費嗜好性</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消費嗜好性 ID
    </th>
    <th style="width:30%; text-align:left">
      名前
    </th>
    <th style="text-align:center">
      スコア
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_concerned_environment</code>
    </td>
    <td style="text-align:left">
      環境に関心を持っている可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>0.5</code> (中)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
</table>

## ボランティア活動の消費嗜好性
{: #volunteer}

ボランティア活動の消費嗜好性は、社会貢献のためのボランティア活動に対する筆者の関心を示します。このカテゴリーの ID と名前は、`consumption_preferences_volunteering` および `Volunteering Preferences` です。このカテゴリーには 1 個の消費嗜好性があります。

<table>
  <caption>表 8. ボランティア活動の消費嗜好性</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消費嗜好性 ID
    </th>
    <th style="width:30%; text-align:left">
      名前
    </th>
    <th style="text-align:center">
      スコア
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_volunteer</code>
    </td>
    <td style="text-align:left">
      社会貢献のためのボランティア活動を行う可能性
    </td>
    <td style="text-align:center">
      <code>0.0</code> (低)<br/>
      <code>1.0</code> (高)
    </td>
  </tr>
</table>

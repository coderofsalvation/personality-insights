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

# 消费偏好
{: #preferences}

{{site.data.keyword.personalityinsightsshort}} 服务针对三个模型推断作者的个性特征：“大五类人格”、“需求”和“价值观”。根据这些模型的结果，服务还可以生成输入文本作者的消费偏好。将请求的 `consumption_preferences` 查询参数设置为 `true` 可获取消费偏好。
{: shortdesc}

有超过 40 种消费偏好，分组为 8 个高级别类别，用于指示作者偏好不同产品、服务和活动的可能性。例如，服务可以识别作者购买服装（舒适度与时尚）和汽车（成本与安全）时的倾向；作者对不同类型音乐、电影和阅读的倾向；以及作者对环保和志愿活动的态度，等等。

企业使用服务的个性模型可更好地了解客户，设计并开发更具个性化、更有针对性的营销活动、产品和服务。通过消费偏好，可更容易地根据服务的结果来采取行动。企业可以轻松获取与个人的主要特征关联的偏好列表，并相应做出响应。有关可能的消费偏好应用的更多信息，请参阅[用例](/docs/services/personality-insights/usecases.html)和[服务实战](/docs/services/personality-insights/applied.html)。

以下各部分列出并描述服务可返回的消费偏好。有关解读数字偏好的更多信息，请参阅[消费偏好的得分](/docs/services/personality-insights/numeric.html#scores)。有关 {{site.data.keyword.IBM_notm}} 如何开发偏好的信息，请参阅[服务背后的科学](/docs/services/personality-insights/science.html)。

## 购买偏好
{: #shopping}

购买偏好指示作者对不同类型购买内容的兴趣、作者的购买习惯受不同外部来源影响的程度，以及作者的消费习惯。此类别的标识和名称分别为 `consumption_preferences_shopping` 和`购买偏好`。此类别有 12 种偏好。

<table>
  <caption>表 1. 购买偏好</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消费偏好标识
    </th>
    <th style="width:30%; text-align:left">
      名称
    </th>
    <th style="text-align:center">
      得分
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_automobile_ownership_cost</code>
    </td>
    <td style="text-align:left">
      在购买汽车时可能对拥有成本很敏感
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>0.5</code>（中性）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_automobile_safety</code>
    </td>
    <td style="text-align:left">
      在购买汽车时可能更看重安全性
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>0.5</code>（中性）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_quality</code>
    </td>
    <td style="text-align:left">
      在购买衣服时可能更看重质量
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_style</code>
    </td>
    <td style="text-align:left">
      在购买衣服时可能更看重款式
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_comfort</code>
    </td>
    <td style="text-align:left">
      在购买衣服时可能更看重舒适度
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_brand_name</code>
    </td>
    <td style="text-align:left">
      在购买商品时可能会受到品牌名称的影响
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>0.5</code>（中性）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_utility</code>
    </td>
    <td style="text-align:left">
      在购买商品时可能会受到商品效用的影响
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>0.5</code>（中性）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_online_ads</code>
    </td>
    <td style="text-align:left">
      在购买商品时可能会受到在线广告的影响
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_social_media</code>
    </td>
    <td style="text-align:left">
      在购买商品时可能会受到社交媒体的影响
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_family_members</code>
    </td>
    <td style="text-align:left">
      在购买商品时可能会受到家庭的影响
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_spur_of_moment</code>
    </td>
    <td style="text-align:left">
      可能会冲动购物
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>0.5</code>（中性）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_credit_card_payment</code>
    </td>
    <td style="text-align:left">
      可能倾向于使用信用卡购物
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
</table>

## 电影偏好
{: #movie}

电影偏好指示作者对不同类型电影的兴趣。此类别的标识和名称分别为 `consumption_preferences_movie` 和`电影偏好`。此类别有 10 种偏好。

<table>
  <caption>表 2. 电影偏好</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消费偏好标识
    </th>
    <th style="width:30%; text-align:left">
      名称
    </th>
    <th style="text-align:center">
      得分
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_romance</code>
    </td>
    <td style="text-align:left">
      可能喜欢看爱情片
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_adventure</code>
    </td>
    <td style="text-align:left">
      可能喜欢看冒险片
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_horror</code>
    </td>
    <td style="text-align:left">
      可能喜欢看恐怖片
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_musical</code>
    </td>
    <td style="text-align:left">
      可能喜欢看音乐片
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_historical</code>
    </td>
    <td style="text-align:left">
      可能喜欢看历史片
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_science_fiction</code>
    </td>
    <td style="text-align:left">
      可能喜欢看科幻片
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_war</code>
    </td>
    <td style="text-align:left">
      可能喜欢看战争片
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_drama</code>
    </td>
    <td style="text-align:left">
      可能喜欢看剧情片
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_action</code>
    </td>
    <td style="text-align:left">
      可能喜欢看动作片
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_documentary</code>
    </td>
    <td style="text-align:left">
      可能喜欢看纪录片
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
</table>

## 音乐偏好
{: #music}

音乐偏好指示作者对不同类型音乐的兴趣以及作者是否喜欢演奏音乐。此类别的标识和名称分别为 `consumption_preferences_music` 和`音乐偏好`。此类别有 9 种偏好。

<table>
  <caption>表 3. 音乐偏好</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消费偏好标识
    </th>
    <th style="width:30%; text-align:left">
      名称
    </th>
    <th style="text-align:center">
      得分
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_rap</code>
    </td>
    <td style="text-align:left">
      可能喜欢说唱音乐
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>0.5</code>（中性）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_country</code>
    </td>
    <td style="text-align:left">
      可能喜欢乡村音乐
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>0.5</code>（中性）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_r_b</code>
    </td>
    <td style="text-align:left">
      可能喜欢节奏布鲁斯音乐
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>0.5</code>（中性）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_hip_hop</code>
    </td>
    <td style="text-align:left">
      可能喜欢嘻哈音乐
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>0.5</code>（中性）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_live_event</code>
    </td>
    <td style="text-align:left">
      可能参加现场音乐会
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_playing</code>
    </td>
    <td style="text-align:left">
      可能亲身演奏音乐
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_latin</code>
    </td>
    <td style="text-align:left">
      可能喜欢拉丁音乐
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>0.5</code>（中性）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_rock</code>
    </td>
    <td style="text-align:left">
      可能喜欢摇滚音乐
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>0.5</code>（中性）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_classical</code>
    </td>
    <td style="text-align:left">
      可能喜欢古典音乐
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>0.5</code>（中性）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
</table>

## 阅读和学习偏好
{: #reading}

阅读和学习偏好指示作者的阅读可能性、作者的阅读动机以及作者喜欢阅读的内容类型。此类别的标识和名称分别为 `consumption_preferences_reading` 和`阅读偏好`。此类别有 5 种偏好。

<table>
  <caption>表 4. 阅读和学习偏好</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消费偏好标识
    </th>
    <th style="width:30%; text-align:left">
      名称
    </th>
    <th style="text-align:center">
      得分
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_read_frequency</code>
    </td>
    <td style="text-align:left">
      可能会经常阅读
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>0.5</code>（中性）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_entertainment_magazines</code>
    </td>
    <td style="text-align:left">
      可能会阅读娱乐杂志
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_non_fiction</code>
    </td>
    <td style="text-align:left">
      可能会阅读非虚构类书籍
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_financial_investing</code>
    </td>
    <td style="text-align:left">
      可能会阅读金融投资类书籍
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_autobiographies</code>
    </td>
    <td style="text-align:left">
      可能会阅读自传类书籍
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
</table>

## 健康和活动偏好
{: #health}

健康和活动偏好指示作者对健康食品和体育活动的兴趣。此类别的标识和名称分别为 `consumption_preferences_health_and_activity` 和`健康和活动偏好`。此类别有 3 种偏好。

<table>
  <caption>表 5. 健康和活动偏好</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消费偏好标识
    </th>
    <th style="width:30%; text-align:left">
      名称
    </th>
    <th style="text-align:center">
      得分
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_eat_out</code>
    </td>
    <td style="text-align:left">
      可能经常外出就餐
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>0.5</code>（中性）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_gym_membership</code>
    </td>
    <td style="text-align:left">
      可能办理健身房会员卡
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_outdoor</code>
    </td>
    <td style="text-align:left">
      可能喜欢户外活动
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>0.5</code>（中性）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
</table>

## 创业偏好
{: #entrepreneur}

创业偏好指示作者对创业的兴趣。此类别的标识和名称分别为 `consumption_preferences_entrepreneurship` 和`创业偏好`。此类别有 1 种偏好。

<table>
  <caption>表 6. 创业偏好</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消费偏好标识
    </th>
    <th style="width:30%; text-align:left">
      名称
    </th>
    <th style="text-align:center">
      得分
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_start_business</code>
    </td>
    <td style="text-align:left">
      可能考虑在未来几年内创业
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>0.5</code>（中性）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
</table>

## 关注环保偏好
{: #environment}

关注环保偏好指示作者对环保的兴趣。此类别的标识和名称分别为 `consumption_preferences_environmental_concern` 和`关注环保偏好`。此类别有 1 种偏好。

<table>
  <caption>表 7. 关注环保偏好</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消费偏好标识
    </th>
    <th style="width:30%; text-align:left">
      名称
    </th>
    <th style="text-align:center">
      得分
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_concerned_environment</code>
    </td>
    <td style="text-align:left">
      可能关心环保
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>0.5</code>（中性）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
</table>

## 志愿活动偏好
{: #volunteer}

志愿活动偏好指示作者对志愿参加社会事业的兴趣。此类别的标识和名称分别为 `consumption_preferences_volunteering` 和`志愿活动偏好`。此类别有 1 种偏好。

<table>
  <caption>表 8. 志愿活动偏好</caption>
  <tr>
    <th style="width:45%; text-align:left">
      消费偏好标识
    </th>
    <th style="width:30%; text-align:left">
      名称
    </th>
    <th style="text-align:center">
      得分
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_volunteer</code>
    </td>
    <td style="text-align:left">
      可能会志愿参加社会事业
    </td>
    <td style="text-align:center">
      <code>0.0</code>（不可能）<br/>
      <code>1.0</code>（很可能）
    </td>
  </tr>
</table>

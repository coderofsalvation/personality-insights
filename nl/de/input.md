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

# Profil anfordern
{: #input}

Zum Analysieren von Inhalten verwenden Sie die HTTP-Anforderungsmethode `POST`, um die Methode `/v3/profile` des {{site.data.keyword.personalityinsightsshort}}-Service aufzurufen. Sie können dem Service im Hauptteil der Anforderung maximal 20 MB an Inhalt zur Analyse übergeben. Der Service erfordert jedoch wesentlich weniger Eingabevolumen, um ein genaues Persönlichkeitsprofil zu erstellen. Weitere Informationen finden Sie unter [Ausreichende Eingabe bereitstellen](#sufficient).
{: shortdesc}

Die Methode `/v3/profile` enthält Parameter, die den Typ des an den Service zu übergebenden Inhalts und den vom Service zurückzugebenden Typ von Inhalt sowie die Sprache eines jeden Typs von Inhalt angeben. Der Service gibt immer ein Profil zurück, das Erkenntnisse über die Persönlichkeitsmerkmale des Autors des Eingabetexts bereitstellt. Sie können außerdem die Rückgabe von unaufbereiteten Bewertungen und Verbraucherpräferenzen anfordern.

In den folgenden Abschnitten werden die Parameter der Methode `/v3/profile` beschrieben. Informationen zu den Ergebnissen einer Anforderung finden Sie unter [JSON-Profil verstehen](/docs/services/personality-insights?topic=personality-insights-output) und [CSV-Profil verstehen](/docs/services/personality-insights?topic=personality-insights-outputCSV). Detaillierte Informationen zur Methode `/v3/profile` finden Sie in der [API-Referenz ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://{DomainName}/apidocs/personality-insights){: new_window}.

Die Protokollierung von Anforderungen ist für den {{site.data.keyword.personalityinsightsshort}}-Service inaktiviert. Unabhängig davon, ob Sie den Anforderungsheader `X-Watson-Learning-Opt-Out` festlegen, protokolliert der Service Anforderungen und Antworten nicht und bewahrt auch keine Daten aus Anforderungen und Antworten auf.
{: note}

## Anforderungs- und Antwortformat angeben
{: #formats}

Verwenden Sie die Headerparameter `Content-Type` und `Accept` zur Angabe des Formats des Inhalts, den Sie an die Methode übergeben, und zur Angabe des Formats der Antwort des Service. Sie können eine beliebige Kombination unterstützter Formate für die Anforderung und die Antwort verwenden.

<table>
  <caption>Tabelle 1. Anforderungs- und Antwortformat angeben</caption>
  <tr>
    <th style="width:10%; text-align:left; vertical-align:bottom">
      Format
    </th>
    <th style="width:26%; text-align:center; vertical-align:bottom">
      Argument
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      Unterstützt von<br/>
      <code>Content-Type</code>
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      Unterstützt von<br/>
      <code>Accept</code>
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Einfacher Text
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/plain</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Ja (Standard)<br/><br/>
      Der Service verarbeitet einfachen Text ohne Änderung.
    </td>
    <td style="text-align:center; vertical-align:top">
      Nein
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      HTML
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/html</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Ja<br/><br/>
      Der Service entfernt vor der Verarbeitung Tags aus dem Inhalt.
    </td>
    <td style="text-align:center; vertical-align:top">
      Nein
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      JSON
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>application/json</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Ja<br/><br/>
      Der Inhalt muss dem Modell entsprechen, das durch das Objekt
      <code>Content</code> definiert wird, das ein Array
      von Objekten <code>ContentItem</code> ist.
    </td>
    <td style="text-align:center; vertical-align:top">
      Ja<br/><br/>
      Der Service gibt seine Ergebnisse als Objekt <code>Profile</code>
      zurück.
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      CSV
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/csv</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Nein
    </td>
    <td style="text-align:center; vertical-align:top">
      Ja<br/><br/>
      Der Service gibt standardmäßig eine einzelne Zeile mit numerischen Ergebnissen zurück.
      Setzen Sie den optionalen Abfrageparameter <code>csv_headers</code> auf
      <code>true</code>, um Überschriften für jede Spalte der Ausgabe anzufordern.
    </td>
  </tr>
</table>

### Zeichensatz angeben
{: #charset}

Der Service verwendet standardmäßig die folgenden Zeichensätze für Eingabeinhalt:

-   *Für einfachen Text und HTML-Inhalt* verwendet der Service den Zeichensatz ISO-8859-1 (International Standards Organization, d. h. effektiv den ASCII-Zeichensatz) entsprechend der Spezifikation von HTTP Version 1.1.
-   *Für JSON-Inhalt* verwendet der Service praktisch immer den Zeichensatz UTF-8 (Unicode Transformation Format) gemäß [Request for Comment (RFC) 7159 ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://tools.ietf.org/html/rfc7159#section-8.1){: new_window} nach Abschnitt 8.1 der International Engineering Task Force (IETF).

Wenn Sie einfachen Text oder HTML-Inhalt übergeben, schließen Sie den Parameter `charset` in den Header `Content-Type` ein, um die Zeichencodierung des Eingabetexts anzugeben. Im folgenden Beispiel wird die UTF-8-Zeichencodierung für Eingaben mit einfachem Text angegeben:

```
Content-Type: text/plain;charset=utf-8
```
{: codeblock}

Durch die Verwendung des Parameters `charset` können Sie potenzielle Probleme im Zusammenhang mit Nicht-ASCII-Zeichen oder nicht druckbaren Zeichen vermeiden. Wenn Sie UTF8-Daten ohne Angabe des Zeichensatzes übergeben, können Sonderzeichen zu falschen Ergebnissen oder zu Fehlern vom Typ HTTP 4nn oder HTTP 5nn führen.

### cURL-Befehl verwenden
{: #charsetCurl}

Zur Vermeidung von Fehlern bei der Verwendung des `curl`-Befehls sollten Sie den Inhalt stets über die Option `--data-binary` des Befehls `curl` übergeben, um die UTF-8-Codierung des Inhalts beizubehalten. Wenn Sie die Option `--data` zur Übergabe von Inhalt im ASCII-Format verwenden, kann der Befehl die Eingabe verarbeiten, was Probleme für in UTF-8 codierte Daten verursachen kann.

Beispiel: Der folgende Befehl `curl` verwendet die Option `--data-binary` korrekt, um den Inhalt der angegebenen Datei *filename* ohne weitere Verarbeitung in der Methode POST zu senden. Der Befehl gibt außerdem den Parameter `charset` mit dem Header `Content-Type` an und fordert mit dem Header `Accept` das JSON-Antwortformat an.

```bash
curl -X POST -u "apikey:{apikey}"
--header "Content-Type: text/plain;charset=utf-8"
--header "Accept: application/json"
--data-binary @{filename}
"https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
```
{: pre}

Weitere Beispiele für das Aufrufen des Service mit verschiedenen Anforderungs- und Antwortformaten finden Sie im [Lernprogramm zur Einführung](/docs/services/personality-insights?topic=personality-insights-gettingStarted).

## JSON-Eingabe angeben
{: #json}

Zur Übergabe einer JSON-Eingabe verwenden Sie das Objekt `Content`. Das Objekt enthält ein Array von Objekten `ContentItem`, die jeweils ein Element des Inhalts darstellen. Das einzige erforderliche Feld des Objekts ist `content`, das den zu analysierenden Text angibt. Die folgenden Felder sind weitere optionale Felder:

-   `id` (Zeichenfolge) ist eine eindeutige ID für das Inhaltselement.
-   `created` (Integer) ist eine UNIX-Zeitmarke, die angibt, wann das Inhaltselement erstellt wurde.
-   `updated` (Integer) ist eine UNIX-Zeitmarke, die angibt, wann das Inhaltselement zuletzt aktualisiert wurde.
-   `contenttype` (Zeichenfolge) gibt den Typ des Inhaltselements an: `text/plain` oder `text/html`.
-   `language` (Zeichenfolge) gibt die Sprache des Inhaltselements an: `ar` (Arabisch), `en` (Englisch), `es` (Spanisch), `ja` (Japanisch) oder `ko` (Koreanisch). Siehe [Anforderungs- und Antwortsprache angeben](#languages-input).
-   `parentid` (Zeichenfolge) ist die ID (`id`) des übergeordneten Elements des Inhaltselements.
-   `reply` (Boolesch) gibt an, ob das Inhaltselement eine Antwort auf ein anderes Element ist.
-   `forward` (Boolesch) gibt an, ob das Inhaltselement eine Weiterleitung oder eine Kopie eines anderen Elements ist.

JSON-Eingaben eignen sich gut für Inhalte aus Twitter oder anderen sozialen Netzwerken, die aus mehreren Wortmitteilungen oder Beiträgen (Posts) bestehen. Anstatt den gesamten Text des Autors zu einer einzigen Zeichenfolge zusammenzufassen, können Sie mithilfe von JSON die Daten so, wie sie sind, übergeben. Dieser Ansatz bietet den weiteren Vorteil, dass dem Service mitgeteilt wird, welche Teile des Texts zusammengehören.

### Beispiel für eine JSON-Eingabe
{: jsonExample}

Beispiele im [Lernprogramm zur Einführung](/docs/services/personality-insights?topic=personality-insights-gettingStarted) verwenden die JSON-Beispieldatei <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="Symbol für externen Link" title="Symbol für externen Link"></a>. Die Datei enthält eine Reihe von Twitter-Nachrichten. Das folgende Beispiel zeigt einige der ersten Tweets aus der Datei.

```javascript
{
  "contentItems": [
    {
      "content": "Wow, I liked @TheRock before, now I really SEE how special he is. The daughter story was IT for me. So great! #MasterClass",
      "contenttype": "text/plain",
      "created": 1447639154000,
      "id": "666073008692314113",
      "language": "en"
    },
    {
      "content": ".@TheRock how did you Know to listen to your gut and Not go back to football? #MasterClass",
      "contenttype": "text/plain",
      "created": 1447638226000,
      "id": "666069114889179136",
      "language": "en"
    },
    . . .
  ]
}
```
{: codeblock}

## Anforderungs- und Antwortsprache angeben
{: #languages-input}

Mit den Headerparametern `Content-Language` und `Accept-Language` können Sie die Sprache des Eingabeinhalts und die Sprache der Antwort des Service angeben. Sie können eine beliebige Kombination aus unterstützten Sprachen für die Anforderung und die Antwort verwenden. Wenn Sie eine Sprache nicht angeben, verwendet der Service seine in Englisch trainierten Modelle für die Analyse und die englische Sprache für die Ergebnisse. In der folgenden Tabelle sind die unterstützten Ein- und Ausgabesprachen zusammen mit den Argumenten aufgeführt, mit denen die sprachbezogenen Parameter angegeben werden.

<table style="width:90%">
  <caption>Tabelle 2. Anforderungs- und Antwortsprache angeben</caption>
  <tr>
    <th style="width:28%; text-align:left; vertical-align:bottom">
      Sprache
    </th>
    <th style="width:12%; text-align:center; vertical-align:bottom">
      Argument
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      Unterstützt von<br/>
      <code>Content-Language</code>
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      Unterstützt von<br/>
      <code>Accept-Language</code>
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      Arabisch
    </td>
    <td style="text-align:center">
      <code>ar</code>
    </td>
    <td style="text-align:center">
      Ja
    </td>
    <td style="text-align:center">
      Ja
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Englisch
    </td>
    <td style="text-align:center">
      <code>en</code>
    </td>
    <td style="text-align:center">
      Ja
    </td>
    <td style="text-align:center">
      Ja
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Japanisch
    </td>
    <td style="text-align:center">
      <code>ja</code>
    </td>
    <td style="text-align:center">
      Ja
    </td>
    <td style="text-align:center">
      Ja
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Koreanisch
    </td>
    <td style="text-align:center">
      <code>ko</code>
    </td>
    <td style="text-align:center">
      Ja
    </td>
    <td style="text-align:center">
      Ja
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Spanisch
    </td>
    <td style="text-align:center">
      <code>es</code>
    </td>
    <td style="text-align:center">
      Ja
    </td>
    <td style="text-align:center">
      Ja
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Portugiesisch (Brasilien)
    </td>
    <td style="text-align:center">
      <code>pt-br</code>
    </td>
    <td style="text-align:center">
      Nein
    </td>
    <td style="text-align:center">
      Ja
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Französisch
    </td>
    <td style="text-align:center">
      <code>fr</code>
    </td>
    <td style="text-align:center">
      Nein
    </td>
    <td style="text-align:center">
      Ja
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Deutsch
    </td>
    <td style="text-align:center">
      <code>de</code>
    </td>
    <td style="text-align:center">
      Nein
    </td>
    <td style="text-align:center">
      Ja
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Italienisch
    </td>
    <td style="text-align:center">
      <code>it</code>
    </td>
    <td style="text-align:center">
      Nein
    </td>
    <td style="text-align:center">
      Ja
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Vereinfachtes Chinesisch
    </td>
    <td style="text-align:center">
      <code>zh-cn</code>
    </td>
    <td style="text-align:center">
      Nein
    </td>
    <td style="text-align:center">
      Ja
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Traditionelles Chinesisch
    </td>
    <td style="text-align:center">
      <code>zh-tw</code>
    </td>
    <td style="text-align:center">
      Nein
    </td>
    <td style="text-align:center">
      Ja
    </td>
  </tr>
</table>

Übergeben Sie den gesamten Text in derselben Sprache; mischen Sie nicht mehrere Sprachen in derselben Anforderung. Für die zweibuchstabigen Sprachargumente behandelt der Service regionale Varianten wie die übergeordnete Sprache. Beispiel: Der Service interpretiert `en-US` wie `en`.

### Sprache für JSON-Inhalt angeben
{: #languageJSON}

Für Eingaben mit einfachem Text oder HTML-Eingaben ist der Header `Content-Language` die einzige Möglichkeit, die Sprache anzugeben. Für JSON-Eingaben können Sie außerdem die Sprache für jedes einzelne Inhaltselement mit dem Parameter `language` des Objekts `ContentItem` angeben. Die Sprache, die mit dem Header `Content-Language` angegeben wird, überschreibt eine Sprache, die für ein Inhaltselement angegeben ist. Der Service ignoriert Inhaltselemente, für die eine andere Sprache angegeben ist.

Lassen Sie den Header `Content-Type` weg, wenn die Sprache nur auf der Angabe der Inhaltselemente basieren soll. Der Service verwendet die am stärksten vorherrschende Sprache unter den Inhaltselementen aus, was die bestmöglichen Ergebnisse liefert. Er zählt die Anzahl der Inhaltselemente für jede Sprache und wählt die Sprache mit der höchsten Häufigkeit aus. Wenn mehrere Sprachen die gleiche Häufigkeit aufweisen, verwendet der Service die Sprache, die diesen Wert zuerst erreicht. Auch hier ignoriert der Service Inhaltselemente, die eine andere Sprache angeben.

### Hinweise zu Sprachen
{: #languageNotes}

Beachten Sie die folgenden Informationsdetails bei der Übergabe von Eingabetext:

-   *Für Englisch* stützen sich die Ergebnisse des Service auf Kulturnormen der Vereinigten Staaten. Wenn Sie englischen Text aus einer anderen Kultur analysieren, müssen Sie die Ergebnisse gegebenenfalls anpassen.
-   *Für Arabisch* kann der Service die Menge an Eingabetext aus Leistungsgründen beschneiden. Ab einem bestimmten Schwellenwert verbessert sich die Genauigkeit arabischer Ergebnisse mit mehr Wörtern nicht mehr. Wenn der Service eine arabische Eingabe beschneidet, wird eine Warnung zurückgegeben, die Sie informiert, dass der Eingabetext reduziert wurde, der für das Profil verwendet wurde.
-   *Für Arabisch und Koreanisch* ist der Service nicht in der Lage, aussagefähige Ergebnisse für einen Teil der Merkmale zurückzugeben. Weitere Informationen finden Sie unter [Einschränkungen für arabische und koreanische Eingaben](/docs/services/personality-insights?topic=personality-insights-numeric#limitations).

Allgemeine Informationen zur Verwendung von übersetztem Text finden Sie unter [Persönlichkeit aus übersetztem Text ableiten](/docs/services/personality-insights?topic=personality-insights-guidance#translation).

## Ausreichende Eingabe bereitstellen
{: #sufficient}

Ein aussagefähiges Persönlichkeitsprofil kann nur dann erstellt werden, wenn ausreichende Daten in geeigneter Quantität und Qualität bereitgestellt werden. Da der Sprachgebrauch natürlicherweise von Dokument zu Dokument und von Zeit zu Zeit variiert, ist ein kleines Stück Text für die allgemeinen Sprachmuster einer Person möglicherweise nicht repräsentativ. Darüber hinaus konvergieren verschiedene Merkmale und verschiedene Medien jeweils unterschiedlich schnell.

Sie können bis zu 20 MB an Eingabeinhalt an den Service senden. Bis zu einem Punkt liefern mehr Wörter wahrscheinlich auch bessere Ergebnisse, weil sich die Genauigkeit des Service dadurch erhöht, dass sich die Abweichung zwischen den vorhergesagten Ergebnissen und den tatsächlichen Bewertungen des Autors verringert. Ab einer Eingabe von ungefähr 3000 Wörtern stagniert jedoch die Genauigkeit und zusätzlicher Inhalt trägt nicht zu einer gesteigerten Genauigkeit des Profils bei. Daher extrahiert und verarbeitet der Service aus umfangreichen Anforderungen nur die ersten 250 KB des Inhalts (HTML- oder JSON-Markup nicht mitgezählt).

Diese Anzahl entspricht keiner exakten Wortzahl, die je nach Sprache und Spezifik des Texts variiert. In der englischen Sprache liegt die durchschnittliche Wortlänge zum Beispiel zwischen vier und fünf Buchstaben, sodass diese Zahl ungefähr 50.000 Wörtern entspricht. Dies sind 15-mal mehr Wörter, als der Service benötigt, um ein genaues Profil zu generieren. Durch Abschneiden langer Eingaben verbessert der Service die Antwortzeit, ohne an Genauigkeit einzubüßen. Im Feld `word_count` der JSON-Antwort wird die Anzahl der Wörter angegeben, die der Service für eine Anforderung verwendet. Diese Anzahl kann kleiner als die übergebene Anzahl der Wörter sein.

Der Service wertet nur die Anzahl der Wörter aus, die Sie übergeben. Wenn Sie genügend Wörter eingeben, erstellt der Service ein Profil. Der Service prüft nicht, ob Wörter oder Sätze doppelt vorhanden sind. Eine solche Validierung ist subjektiv und sollte dem Benutzer überlassen werden, der triftige Gründe für die Übermittlung solcher Eingaben haben könnte. Daher ist es möglich, durch die mehrfache Übergabe desselben Worts oder Satzes ein Profil zu erhalten, doch dieses Profil, das aus einer solchen Eingabe hervorgeht, ist nicht unbedingt aussagekräftig.
{: note}

### Richtlinien und Empfehlungen
{: #sufficientGuidelines}

In der folgenden Tabelle werden zwei Werte für verschiedene Mengen an Eingabetext aufgeführt:

-   Der *durchschnittliche mittlere absolute Fehler (MAE)* über alle Merkmale hinweg auf der Basis der Anzahl der Wörter, die als Eingabe bereitgestellt werden. Je kleiner der MAE ist, desto näher liegen die Ergebnisse des Service an den Bewertungen, die der Autor erhalten würde, wenn er sich einem Persönlichkeitstest unterziehen würde.
-   Die *durchschnittliche Korrelation* zwischen abgeleiteten und tatsächlichen Bewertungen über alle Merkmale hinweg. Je näher die Korrelation an 1 liegt, desto besser sind die Vorhersagen. Korrelationen größer als 0,2 gelten als akzeptabel, Korrelationen größer als 0,4 sind selten.

Die Informationen basieren auf Daten in englischer Sprache, jedoch gelten die allgemeinen Richtlinien für alle Sprachen. Weitere Informationen zum durchschnittlichen mittleren absoluten Fehler (MAE) und zur durchschnittlichen Korrelation finden Sie unter [Genauigkeit des Service](/docs/services/personality-insights?topic=personality-insights-science#researchPrecise).

<table style="width:80%">
  <caption>Tabelle 3. Durchschnittlicher mittlerer absoluter Fehler (MAE) und durchschnittliche Korrelation</caption>
  <tr>
    <th style="text-align:center; vertical-align:bottom; width:24%">Anzahl Wörter</th>
    <th style="text-align:center; width:38%">Durchschnittlicher MAE<br/>über alle
      Merkmale hinweg</th>
    <th style="text-align:center; width:38%">Durchschnittliche Korrelation<br/>über alle
      Merkmale hinweg</th>
  </tr>
  <tr>
    <td style="text-align:center">3000</td>
    <td style="text-align:center">12,1%</td>
    <td style="text-align:center">0,257</td>
  </tr>
  <tr>
    <td style="text-align:center">1200</td>
    <td style="text-align:center">12,2%</td>
    <td style="text-align:center">0,237</td>
  </tr>
  <tr>
    <td style="text-align:center">600</td>
    <td style="text-align:center">12,3%</td>
    <td style="text-align:center">0,212</td>
  </tr>
  <tr>
    <td style="text-align:center">300</td>
    <td style="text-align:center">12,5%</td>
    <td style="text-align:center">0,175</td>
  </tr>
  <tr>
    <td style="text-align:center">100</td>
    <td style="text-align:center">12,7%</td>
    <td style="text-align:center">0,095</td>
  </tr>
</table>

Wie die folgenden Richtlinien zeigen, empfiehlt {{site.data.keyword.IBM_notm}}, mindestens 1200 Wörter bereitzustellen, jedoch werden akzeptable Ergebnisse schon bei der Bereitstellung von mindestens 600 Wörtern generiert:

-   3000 Wörter sind ausreichend, um die maximale Genauigkeit des Service zu erreichen.
-   Eine Wortzahl von mindestens 1200 Wörtern führt zu einem MAE, der innerhalb der zwei Prozent des besten MAE liegt, den der Service zurückgeben kann.
-   Eine Wortzahl zwischen 600 und 1200 Wörtern führt zu einem MAE, der innerhalb der drei Prozent des besten MAE liegt, den der Service zurückgeben kann.
-   Eine Wortzahl unter 600 Wörtern generiert eine Warnung, jedoch analysiert der Service die Eingabe trotzdem.
-   Eine Wortzahl unter 100 Wörtern verursacht einen Fehler.

Diese Richtlinien können Ihnen helfen, die Zuverlässigkeit der Ergebnisse Ihrer Anwendung anzupassen. Für eine Freizeitanwendung, die Filme empfiehlt, ist vielleicht weniger Genauigkeit durchaus akzeptabel. Für eine Anwendung, die kritischere Empfehlungen generiert, benötigen Sie wahrscheinlich genauere Ergebnisse. Weitere Informationen dazu, wie der Service Persönlichkeitsmerkmale ableitet, finden Sie unter [Ableitung von Persönlichkeitsmerkmalen](/docs/services/personality-insights?topic=personality-insights-science#researchInfer).

## Unaufbereitete Bewertungen anfordern
{: #rawScores-input}

Der Service gibt immer normalisierte Bewertungen für jedes Persönlichkeitsmerkmal (Big Five-Dimension und -Facette, Bedürfnisse und Werte) in der Antwort zurück. Der Service kann außerdem eine unaufbereitete Bewertung (`raw_score`) für jedes Merkmal zurückgeben, wenn Sie den Abfrageparameter `raw_scores` auf den Wert `true` setzen. Unaufbereitete Bewertungen Rohwerte stellen Ergebnisse für die Merkmale dar, die ausschließlich auf dem Text des Autors und dem Modell für dieses Merkmal basieren, ohne dass ein Vergleich der Ergebnisse mit einer Beispielpopulation gezogen wird. Weitere Informationen zur Verwendung unaufbereiteter Bewertungen finden Sie unter [Unaufbereitete Bewertungen für Persönlichkeitsmerkmale](/docs/services/personality-insights?topic=personality-insights-numeric#rawScores-numeric).

## Verbraucherpräferenzen anfordern
{: #preferences-input}

Der Service gibt immer Ergebnisse für die Persönlichkeitsmodelle zurück. Wenn Sie für den Abfrageparameter `consumption_preferences` den Wert `true` festlegen, gibt der Service für verschiedene Verbraucherpräferenzen auch `scores` (Bewertungen) zurück. Der Service stützt die Präferenzen auf die Persönlichkeitsmerkmale, der er aus dem Eingabetext ableitet. Die Ergebnisse geben die Tendenz des Autors an, bestimmte Produkte, Services und Aktivitäten zu bevorzugen. Unternehmen können mithilfe der Ergebnisse die Neigungen des Autors besser verstehen und die Kommunikation mit dem Autor sowie Angebote für den Autor personalisieren.

Weitere Informationen zu den verschiedenen Verbraucherpräferenzen finden Sie unter [Verbraucherpräferenzen](/docs/services/personality-insights?topic=personality-insights-preferences). Informationen zur Interpretation der numerischen Ergebnisse für eine Präferenz finden Sie unter [Bewertungen für Verbraucherpräferenzen](/docs/services/personality-insights?topic=personality-insights-numeric#scores).

## Schnittstellenversion angeben
{: #version}

Alle Aufrufe an die Methode `/v3/profile` müssen den Abfrageparameter `version` einschließen, um die Version der API des Service und das gewünschte Antwortformat anzugeben. Sie geben die Version als Datum im Format `JJJJ-MM-TT` an. Geben Sie zum Beispiel `2017-10-13` für die Version vom 13. Oktober 2017 an. Der Parameter gibt dem Service die Möglichkeit, die API und das Antwortformat für neue Versionen zu aktualisieren, ohne die Funktionsfähigkeit vorhandener Clients zu beeinträchtigen. Informationen zu allen verfügbaren Versionen finden Sie in den [Releaseinformationen](/docs/services/personality-insights?topic=personality-insights-release-notes).

Das Datum, das Sie angeben, muss nicht exakt einer Version des Service entsprechen. Der Service verwendet die Version, die nicht später als das angegebene Datum freigegeben wurde. Wenn Sie ein Datum angeben, das vor dem ersten Release von Version 3 liegt (`2016-10-19`), verwendet der Service diese Version der API. Wenn Sie ein Datum angeben, das in der Zukunft liegt oder auf andere Weise nach dem Release der aktuellsten Version liegt, verwendet der Service die aktuellste Version.

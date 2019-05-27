---
title: データの種類 |Microsoft Docs
description: キャンバス アプリでのデータ型
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/19/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f9acc04a9159349075647ca4e318f15939a230f7
ms.sourcegitcommit: aa9f78c304fe46922aecfe3b3fadb6bda72dfb23
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66216647"
---
# <a name="data-types-in-canvas-apps"></a>キャンバス アプリでのデータ型

非常に小さな、不連続の値でのアプリからの情報フローなど、ワークシートのセルの。 内のデータなど、**誕生日**フィールドおよび**Anniversary**フィールドは両方を通過として、**日付**年、月、および日を含む値。 アプリでは、これらの値を書式設定、新機能ごとに、適切なへの入力を制限、およびデータベースで値を共有する方法を認識します。 ユーザーに記念日と誕生日は異なるが、システムがまったく同じ方法でそれらを処理します。 この場合、**日付**の例を示します、[データ型](https://en.wikipedia.org/wiki/Data_type)します。

この記事では、キャンバス アプリのサポートされるデータ型の詳細を提供します。 アプリは、外部データ ソースに接続するとき、そのソースで各データ型は、キャンバス アプリのデータ型にマップされます。

| データ型 | 説明 | 例 |
|-----------|-------------|---------|
| **ブール値** | A *true*または*false*値。  直接使用できます**場合**、**フィルター**とを比較されず、その他の関数。  | *true* |
| **ハイパーリンク** | ハイパーリンクを保持するテキスト文字列。 | **"http://powerapps.microsoft.com"** |
| **通貨** | 浮動小数点数に格納されている通貨値。 通貨の値は、通貨の書式設定オプションを使用して数値の場合と同じです。  | **123**<br>**4.56** |
| **イメージ** | A [Universal Resource Identifier (URI)](https://en.wikipedia.org/wiki/Uniform_Resource_Identifier) .jpeg、.png、.svg、.gif、およびその他の一般的な web イメージ内のイメージにテキスト文字列の書式設定します。 | **MyImage**アプリのリソースとして追加<br>**"https://northwindtraders.com/logo.jpg"**<br>**"appres://blobmanager/7b12ffa2..."** |
| **色** | アルファ チャネルを含む色仕様。 | **Color.Red**<br>**ColorValue( "#102030" )**<br>**RGBA( 255, 128, 0, 0.5 )** |
| **日付** | アプリのユーザーのタイム ゾーンの時刻のない日付です。 | **Date( 2019, 5, 16 )** |
| **DateTime** | アプリのユーザーのタイム ゾーンの時刻と日付。 | **DateTimeValue( "May 16, 2019 1:23:09 PM" )** |
| **GUID** | A[グローバル一意識別子](https://en.wikipedia.org/wiki/Universally_unique_identifier)します。 | **GUID()**<br>**GUID( "123e4567-e89b-12d3-a456-426655440000" )** |
| **[Media (メディア)]** | ビデオまたはオーディオの記録を URI のテキスト文字列。 | **MyVideo**アプリのリソースとして追加<br>**"https://northwindtraders.com/intro.mp4"**<br>**"appres://blobmanager/3ba411c..."** |
| **数** | 浮動小数点数。 | **123**<br>**-4.567**<br>**8.903e121** |
| **オプション セット** | 一連の数値に支えオプションから選択します。 このデータ型は、数値の値を持つローカライズ可能なテキスト ラベルを結合します。 アプリでは、ラベルが表示されますおよび数値の値が格納されているし、の比較に使用します。 | **ThisItem.OrderStatus** |
| **レコード** | データ値のレコード。 この複合データ型には、このトピックに記載されている他のデータ型のインスタンスが含まれています。 詳細情報:[テーブルの操作](../working-with-tables.md)します。 | **{0} サイト。"Northwind Traders"<br>スタッフ。35、 <br>NonProfit: false}** |
| **レコードの参照** | エンティティ内のレコードへの参照。 このような参照を参照するポリモーフィックなよく使用されます。 詳細情報:[参照操作](../working-with-references.md)します。| **First(Accounts) します。所有者** |
| **テーブル** | レコードのテーブル。  すべてのレコードと同じデータ型では、そのフィールドに同じ名前があります。 また省略されたフィールドはとして扱われます*空白*します。 この複合データ型には、このトピックに記載されている他のデータ型のインスタンスが含まれています。 詳細情報:[テーブルの操作](../working-with-tables.md)します。 | **Table( { FirstName:"Sidney"<br>LastName:"Higa"}、 <br>{FirstName:"Nancy"<br>LastName:"Anderson" } )**
| **[Text (テキスト)]** | Unicode テキスト文字列。 | **"Hello, World"** |
| **時間** | アプリのユーザーのタイム ゾーンの日付のない時間。 | **Time( 11, 23, 45 )** |
| **2 つのオプション** | 一連のブール値によって、2 つのオプションから選択します。 このデータ型は、ブール値を持つローカライズ可能なテキスト ラベルを結合します。 アプリでは、ラベルが表示されます、ブール値が格納されているし、の比較に使用します。 | **ThisItem.Taxable** |

これらのデータ型の多くは似ており、同一の基になる表現をなどがある、**ハイパーリンク**フィールドとして扱われる**テキスト**します。  追加のデータ型は、フォームとその他のコントロールでより適切な既定がエクスペリエンスを提供します。

## <a name="blank"></a>Blank

すべてのデータ型の値を持つことができます*空白*(つまり、値なし)。 "Null"という用語は、この概念の多くの場合、データベースに使用されます。  

使用して、**空白**関数と、**設定**または**パッチ**関数、変数を設定またはフィールドを*空白*します。 たとえば、**セット (x, Blank())** グローバル変数に任意の値を削除します。 **x**します。  

テスト、*空白*値を使用して、 [ **IsBlank** ](function-isblank-isempty.md)関数。 置換可能な限り*空白*値以外を*空白*値を使用して、 [ **Coalesce** ](function-isblank-isempty.md)関数。

すべてのデータ型をサポートしているため*空白*、**ブール**と**2 つのオプション**データ型は、3 つの値を効果的にあります。

## <a name="text-hyperlink-image-and-media"></a>テキスト、ハイパーリンク、画像、およびメディア

これらのデータ型の 4 つすべてがに基づいて、 [Unicode](https://en.wikipedia.org/wiki/Unicode)テキスト文字列。

### <a name="image-and-media-resources"></a>イメージとメディアのリソース

を通じて、**ファイル**] メニューの [アプリのリソースとしてイメージ、ビデオ、およびオーディオ ファイルを追加することができます。 インポートされたファイルの名前では、アプリでリソース名になります。 この図での名前は、Northwind Traders ロゴ**nwindlogo**アプリに追加されました。

![](media/data-types/nwind-resource.png)

アプリでこのリソースを使用するでを指定、**イメージ**のプロパティ、 [**イメージ**](../controls/control-image.md)コントロール。

![](media/data-types/nwind-image.png)

### <a name="uris-for-images-and-other-media"></a>イメージおよびその他のメディアの Uri

調べる深く最後の例を設定して、**テキスト**のプロパティを[**ラベル**](../controls/control-text-box.md)に制御を**nwindlogo**します。 ラベルには、テキスト文字列が表示されます。

![](media/data-types/nwind-text.png)

キャンバス アプリでは、クラウドでは、URI 文字列をアプリのリソースとして追加するかどうか各イメージまたはその他のメディア ファイルを参照します。

たとえば、**イメージ**イメージ コントロールのプロパティがアプリのリソースだけでなく、web 上のイメージへのリンクもでなどは"https://northwindtraders.com/logo.jpg"。 プロパティを使用して、インライン イメージを受け入れることも、[データ URI のスキーム](https://en.wikipedia.org/wiki/Data_URI_scheme)、この例のように。

```powerapps-dot
"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAkAAAAFAQMAAACtnVQoAAAABlBMVEUAAAB0J3UMNU6VAAAAAXRSTlMAQObYZgAAABRJREFUCNdjUGJgCGVg6GgAkkA2AA8/AffqCEBsAAAAAElFTkSuQmCC"
```

その URI では、2 つの紫色のひし形のスケール アップしたバージョンが表示されます。

![](media/data-types/double-diamonds.png)

キャプチャされた最新のイメージを表示することができます、 [**カメラ**](../controls/control-camera.md)を設定する場合は、制御、**イメージ**イメージ コントロールのプロパティ、**フォト**カメラ コントロールのプロパティです。 アプリでは、メモリ内のイメージが保存されていると、**フォト**カメラ コントロールのプロパティは、イメージへの URI 参照を返します。 たとえば、画像、およびカメラのかかる場合があります**フォト**プロパティが返すことができます **"appres://blobmanager/7b12ffa2ea4547e5b3812cb1c7b0a2a0/1"** します。

イメージまたはデータベースに格納されている別のメディア ファイルを参照するのにには、URI を使用します。 そうすることは実際に必要になるまで、アプリで実際のデータを取得しません。 たとえば、Common Data Service エンティティの添付ファイルを返す可能性があります **"appres://datasources/Contacts/table/..."** カメラの使用例のように設定してこのイメージを表示することができます、**イメージ**このリファレンスでは、バイナリ データを取得する、イメージ コントロールのプロパティ。

画像など、メディアのデータ型をデータベースに保存するときに、アプリは、実際の画像または URI 参照ではなく、メディア データを送信します。

### <a name="size-limits"></a>サイズの制限

文字列 Uri としてこれらのデータ型制限がありますありませんプリセットの長さにします。

バイナリ データもこれらのデータ型を参照するには、サイズに事前設定された制限はありません。 たとえば、として参照されるようになりましたカメラ コントロールでキャプチャされたイメージ **"appres://..."** デバイスのカメラを召集するように大規模で高解像度にできます。 解像度、フレーム レート、およびメディア ファイルの他の属性は、データ型によって制限されないが、特定のコントロールの再生とキャプチャ メディアの場合、独自の制限事項があります。

ただし、すべてのデータ サイズは、アプリで使用可能なメモリの量を受けます。 通常のデスクトップ コンピューターで実行されているブラウザーでは、100 メガバイト以上のデータをサポートします。 ただし、携帯電話などのデバイスで使用可能なメモリの量が通常の範囲で大幅に低い可能性があります 30 ~ 70 のメガバイト数。 アプリはこれらの制限内で実行されているかどうかを確認するのが実行されるすべてのデバイスでの一般的なシナリオをテストします。

ベスト プラクティスとしては、必要に応じてのみ限りメモリにデータを保持します。 表示できます。 すぐに、データベースにイメージをアップロードします。アプリのユーザーが要求する場合にのみ、イメージをダウンロードします。

## <a name="number-and-currency"></a>数値と通貨

**数**と**通貨**データ型を使用して、 [IEEE 754 倍精度浮動小数点標準](https://en.wikipedia.org/wiki/IEEE_754)します。 この標準 –1.79769 x 10 から、操作する番号の非常に大きい範囲を提供する<sup>308</sup> 1.79769 x 10<sup>308</sup>します。 表すことができる最小値は 5 x 10<sup>–324</sup>します。

キャンバス アプリできますを正確に表現の整数 (または整数) –9,007,199,254,740,991 間 (– (2<sup>53</sup> – 1)) と 9,007,199,254,740,991 (2<sup>53</sup> – 1) までの値。 この範囲は、データベースがよく使用される 32 ビット (または 4 バイト) の整数データ型を超えています。 ただし、キャンバス アプリでは、64 ビット (または 8 バイト) の整数データ型を表すことはできません。 テキスト フィールドの数を格納またはにマップされているように、テキスト フィールドには、数のコピーを作成する、計算列を使用する場合があります、**テキスト**キャンバス アプリでのデータ型。 この方法で保持することができます、表示、および等しいいるかどうかを判断することを比較するほか、これらの値を入力しますただし、このフォームでに数値の計算を実行することはできません。

文書化されている例の多くで予期しない結果にもできるため、浮動小数点演算は概数、します。 数式が想像**55 100 * 100/** を正確に 55 を返すと **(55/100 * 100) - 55**を厳密に 0 を返します。 ただし、後者の数式を返します 7.1054 x 10<sup>–15</sup>、これは非常に小さいが 0 ではありません。 小さな違いが、問題が発生しない通常しアプリ桁に丸めます、破棄、結果を表示するときにします。 ただし、若干の違いは、後続の計算で複合、間違った答えが得られますが。

多くの場合、データベース システムは、通貨を格納し、有効桁数をより細かく制御がより小さな範囲を提供する 10 進数の数値演算を使用して計算を実行します。 既定では、キャンバス アプリ マップの通貨と浮動小数点値の間そのため、ネイティブの decimal データ型で行われる計算から結果が異なる場合があります。 この種類の不一致の問題が発生するが、場合これらの値として使用する**テキスト**あります前にこのセクションで説明した、大きな整数と同様、します。

## <a name="date-time-and-datetime"></a>日付、時刻、および DateTime

### <a name="time-zones"></a>タイム ゾーン

これらのカテゴリ値 fall を日付/時刻。

- **ユーザー ローカル**:これらの値が格納されている[UTC (世界協定時刻)](https://en.wikipedia.org/wiki/Coordinated_Universal_Time)が、アプリ ユーザーのタイム ゾーンは、アプリがこれらの値を表示する方法と、アプリのユーザーがそれらを指定する方法に影響します。 たとえば、同じ時間が表示されますが異なるカナダ内のユーザーに日本のユーザーにはよりも。
- **タイム ゾーン非依存**:同様に、これらの値を表示するアプリをアプリのユーザーがそれらにタイム ゾーンに関係なく、同じ方法を指定します。 同じ時間では、日本のユーザーには、カナダ内のユーザーに同じ方法が表示されます。 アプリの作成者がアプリの異なるタイム ゾーンで実行する予定がないは、全体的なのも簡単ですので、これらの値を使用します。

次の表では、いくつかの例を示します。

| 日付/時刻型 | データベースに格納された値 | 値が表示され、utc の 7 時間を入力 | 値が表示され、UTC の 4 時間を入力 |
|--------------------------|------------------------------|------------------------------|
| **ローカル ユーザー** | 日曜日、&nbsp;が&nbsp;19、&nbsp;2019<br>4時 00分 AM | 土曜日に、&nbsp;が&nbsp;18、&nbsp;2019<br>9時 00分 PM | 日曜日、&nbsp;が&nbsp;19、&nbsp;2019<br>8時 00分 AM |
| **タイム ゾーン非依存** | 日曜日、&nbsp;が&nbsp;19、&nbsp;2019<br>4時 00分 AM | 日曜日、&nbsp;が&nbsp;19、&nbsp;2019<br>4時 00分 AM | 日曜日、&nbsp;が&nbsp;19、&nbsp;2019<br>4時 00分 AM | 

**ユーザー ローカル**日付/時刻がキャンバス アプリ、ブラウザーまたはデバイスのタイム ゾーンを使用して、モデル駆動型アプリは、ユーザーのデータ サービスを共通の設定を使用します。 これらの設定が通常と一致しますが、これらの設定が異なる場合、結果は異なります。

### <a name="numeric-equivalents"></a>同等の数値

キャンバス アプリを保持し、すべての日付/時刻値、かどうかを計算する**ユーザー ローカル**または**タイム ゾーン非依存**(utc)。 アプリ ベースのアプリ ユーザーのタイム ゾーンに表示されているときに使用して、アプリのユーザーには、これらを指定する値を変換します。

キャンバス アプリを読み取るとき、**タイム ゾーン非依存**値、データ ソースまたは書き込みが、アプリ、データ ソースにこのような値は、補正するため、アプリのユーザーのタイム ゾーンに値を自動的に調整されます。 アプリは、一貫性のあるアプリで他のすべての日付/時刻値を UTC 値として、値を扱います。 この補正では、元のため**タイム ゾーン非依存**アプリ、アプリ ユーザーのタイム ゾーンの UTC 値を調整するときに、値が表示されます。

使用してこの動作を詳しく確認、 [**値**](function-value.md)日付/時刻値の基になる数値にアクセスする関数。 この関数は、1970 年 1 月 1 日以降のミリ秒数として日付/時刻値を返します 00:00:00.000 UTC。

すべての日付/時刻値が UTC、数式に保持されるため**値 (日付 (1970 年 1, 1))** ため、世界中の 0 個のほとんどのパーツが返されません、**日付**関数は、UTC の日付を返します。 など、数式は返します 28,800,000 のタイム ゾーン オフセットである UTC から 8 時間ごと。 その数は、8 時間のミリ秒数を反映します。

上記の例に戻るには。

| 日付/時刻型 | データベースに格納された値 | 値が表示され、utc の 7 時間を入力 | **値**関数が返される |
|--------------------------|------------------------------|------------------------------|
| **ローカル ユーザー** | 日曜日、&nbsp;が&nbsp;19、&nbsp;2019<br>4時 00分 AM | 土曜日に、&nbsp;が&nbsp;18、&nbsp;2019<br>9時 00分 PM | 1,558,238,400,000<br> (日曜日、&nbsp;が&nbsp;19、&nbsp;2019<br>4時 00分 AM UTC) |
| **タイム ゾーン非依存** | 日曜日、&nbsp;が&nbsp;19、&nbsp;2019<br>4時 00分 AM | 日曜日、&nbsp;が&nbsp;19、&nbsp;2019<br>4時 00分 AM |1,558,263,600,000<br> (日曜日、&nbsp;が&nbsp;19、&nbsp;2019<br>11時 00分 AM UTC) |

### <a name="converting-unix-times"></a>Unix の時刻の変換

1970 年 1 月 1 日以降の秒数を反映する Unix 時間 00時 00分: 00 UTC。 キャンバス アプリでは、秒ではなく (ミリ秒) を使用するために乗算または 1000 で除算して、2 つの間で変換できます。

Unix 時間は、2001 年 9 月 9 日を示しています、1時 46分: 40 にたとえば、1,000,000, 000 として UTC。 表示する日付/時刻値でキャンバス アプリをその数を掛けます (ミリ秒単位) に変換する 1,000 でそれを使用して、 [**テキスト**](function-text.md)関数。 数式**テキスト (1000000000 * 1000、DateTimeFormat.UTC)** 文字列を返します**2001-09-09T01:46:40.000Z**します。

ただし、その関数が返す**2001 年 9 月 8 日土曜日 18時 46分: 40**を使用する場合、 **DateTimeFormat.LongDateTime24** -7 時間から UTC (7 時間 utc) オフセットであるタイム ゾーン形式。 この結果、 **DateTime**値が正しく、ローカル タイム ゾーンに基づいています。

Unix 時間に変換する結果を除算**値**1000 で。
<br>**RoundDown (値 (UnixTime)/1000, 0)**

Unix 時間を必要がある場合、**日付**のさらに計算値または PowerApps 内で表示、次の数式を使用します。
<br>**DateAdd( Date( 1970,1,1 ), UnixTime, Seconds )**

### <a name="sql-server"></a>SQL Server

SQL Server が[ **Datetime**、 **Datetime2**、およびその他の日付/時刻データ型](https://docs.microsoft.com/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql?view=sql-server-2017)をタイム ゾーン オフセットは含まれていませんし、あるタイム ゾーンを指定しない中します。 キャンバス アプリでは、これらの値が UTC で格納されますが、として扱う前提としています**ユーザー ローカル**します。 使用して UTC の翻訳の場合は、値は、タイム ゾーンの独立を目的として、修正、 [ **TimeZoneOffset** ](function-dateadd-datediff.md#converting-to-utc)関数。

キャンバス アプリに含まれているタイム ゾーン情報を使用して、 **Datetimeoffset**フィールドの値をアプリの内部の UTC 形式に変換するときにします。 タイム ゾーン (タイム ゾーン オフセット 0) と、アプリが常に UTC を使用すると、書き込むデータ。

キャンバス アプリの値の読み書き、 [**時間**](https://docs.microsoft.com/en-us/sql/t-sql/data-types/time-transact-sql)内のテキスト文字列として SQL Server でのデータ型、 [ISO 8601 期間形式](https://en.wikipedia.org/wiki/ISO_8601#Durations)します。 など、この文字列形式を解析して使用する必要があります、 [**時間**](function-date-time.md)テキスト文字列に変換する関数 **"PT2H1M39S"** を**時間**値:

```powerapps-dot
First(
    ForAll(
        MatchAll( "PT2H1M39S", "PT(?:(?<hours>\d+)H)?(?:(?<minutes>\d+)M)?(?:(?<seconds>\d+)S)?" ),
        Time( Value( hours ), Value( minutes ), Value( seconds ) )
    )
).Value
```

### <a name="mixing-date-and-time-information"></a>日付と時刻の情報を混在させる

**日付**、**時間**、および**DateTime** 、異なる名前が同じ日付と時刻に関する情報を保持します。 

A**日付**値は、通常は、時刻情報を含めることができます午前 0 時です。 A**時間**値が日付については、通常を実行できる 1970 年 1 月 1 日です。 Common Data Service では、使用時の情報も格納されます、**日付のみ**フィールドに既定では、日付情報のみが表示されます。 同様に、キャンバス アプリでは、これらのデータ型を既定の形式を確認して、コントロールの間と区別場合があります。

追加して、日付と時刻の値を直接減算は、タイム ゾーンとその他の変換は混乱を招く結果になるためにお勧めしません。 使用するか、**値**最初の日付/時刻値をミリ秒に変換し、アプリ ユーザーのタイム ゾーンを考慮する関数を使用して、または、 [ **DateAdd** ](function-dateadd-datediff.md)と[ **DateDiff** ](function-dateadd-datediff.md)関数を追加、またはこれらの値のいずれかから減算します。

## <a name="option-sets-and-two-options"></a>オプションのセットと 2 つのオプション

オプション セットと 2 つのオプションのデータ型は、アプリ ユーザーを選択する 2 つまたは複数の選択肢を提供します。 たとえば、**注文ステータス**オプション セットの選択肢を提供する可能性があります**新規**、 **Shipped**、**請求**、および**終了**. 2 つのオプションのデータ型は、のみの 2 つの選択肢を提供します。

両方のデータ型は、テキスト文字列のコンテキスト内のラベルを表示します。 ラベル コントロールが注文状態のオプションのいずれかを示していますなどの場合、コントロールの**テキスト**プロパティがそのオプション セットを参照する数式に設定します。 オプションのラベルは、別の場所でアプリのユーザーのローカライズされた可能性があります。

アプリのユーザーは、オプションを選択すると、その変更を保存、アプリは、データベースでは、言語に依存しない形式でそのデータを格納するデータを送信します。 オプション セットのオプションが転送され、数値として格納されていると、2 つのオプションのデータ型のオプションが送信され、ブール値として格納されています。

ラベルは表示目的でのみです。 特定の言語になるため、ラベルを直接比較を行うことはできません。 代わりに、各オプションのセットには、基になる数値またはブール値で使用する列挙体があります。 たとえば、次の数式を使用することはできません。

`If( ThisItem.OrderStatus = "Active", ...`

ただし、この数式を使用することができます。

`If( ThisItem.OrderStatus = OrderStatus.Active, ...`

グローバル オプション セット (エンティティの共有)、オプション セットの列挙型の名前とグローバル オプション セットの名前が一致します。 (これは、エンティティのスコープは) ローカル オプション セットの名前は、エンティティの名前を含めることがあります。 この動作は、複数のエンティティが同じ名前を持つオプション セットがある場合、競合を回避します。 たとえば、**アカウント**エンティティがあります、 **OrderStatus**オプションを設定し、その名前があります**OrderStatus (アカウント)** します。 その名前には、数式で参照する場合は単一引用符で囲む必要がありますので 1 つ以上の空白とかっこが含まれています。

さらに、2 つのオプションの値もブール値として動作します。 たとえば、という名前の 2 つのオプション値**TaxStatus**ラベルがあります**課税**と**非課税**、に対応する*true* 。*false*それぞれします。 例として、次の数式を使用できます。

`If( ThisItem.Taxable = TaxStatus.Taxable, ...`

同等の数式を使用することもできます。

`If( ThisItem.Taxable, ...`
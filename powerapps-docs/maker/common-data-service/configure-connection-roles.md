---
title: つながりロールを構成 | MicrosoftDocs
ms.custom: ''
ms.date: 05/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.author: matp
manager: brycho
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="configure-connection-roles"></a>つながりロールの構成

アプリの Common Data Service では、エンティティの関連付けを作成しないでもエンティティ レコード間の**つながり**を定義できます。 モデル駆動型アプリでは、レコード間の名前付きのリンクを確立し、実際のエンティティ関係を作成することを正当化しないそれほど形式的でない関連を確立することができます。 たとえば、*友人*、*兄弟*、*配偶者*、*出席者*、*利害関係者*が含まれます。 つながりには、*子*と*親*、*夫*と*妻*、*医師*と*患者*など、相互の関係にできるものもあります。

ユーザーが 2 種類のレコードの間に接続を設定すると、関係の開始日と終了日などの説明や補足情報を追加することができます。 詳細: [レコード間の関連付けを定義および表示するために接続を作成する](/dynamics365/customer-engagement/basics/create-connections-view-relationships-between-records).

**つながりロール**エンティティへの書き込みアクセスを持つユーザーは、ユーザーが使うことができるつながりを確立できます。

## <a name="view-connection-roles"></a>つながりロールの表示

アプリ用に CDS で既に構成されているさまざまな標準つながりロールがあります。 これらを表示するには、設定領域に移動する必要があります。 

### <a name="navigate-to-the-settings-area"></a>設定領域への移動

1. モデル駆動型アプリを表示しながら、URL を編集し、`dynamics.com` の後のすべてを削除してページを更新します。
1. **設定** > **業務** > **事業部管理**に移動し、**つながりロール**を選択します。

![事業部管理設定のつながりロール](media/navigate-settings-connection-roles.png)

このビューでは、この環境で使用できるすべてのつながりロールを確認し、編集できます。

> [!NOTE]
> ソリューションを使ってつながりロールを配布する場合、配布するソリューションに含まれていることを確認します。 詳細: [ソリューションへのつながりロールの追加](#add-connection-roles-to-a-solution)

## <a name="view-connection-roles-in-the-solution-explorer"></a>ソリューション エクスプローラーでつながりロールを表示します。

つながりロールは*ソリューション対応*である、つまりソリューションに含めることができるため、配布するソリューションにつながりロールを追加することもできます。

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

**設定** 領域で表示できるつながりロールのほとんどは、*内部*の**既定のソリューション**内で定義されます (**Common Data Service の既定のソリューション**と混同しないでください)。 この内部の**既定のソリューション**には、システム内のすべてのカスタマイズが含まれます。 **既定のソリューション**を表示するには、**すべてのソリューション - 内部**ビューを選択します。

## <a name="add-connection-roles-to-a-solution"></a>ソリューションへのつながりロールの追加

通常、内部の**既定のソリューション**のコンポーネントを編集することはお勧めしません。 **Common Data Service の既定のソリューション**または作業するために作成したソリューション内で、**既存の追加**コマンドを使用して既定のつながりロールのいずれかをソリューションに取り込むことができます。

![既存のつながりロールの追加](media/add-existing-connection-role.png)

ソリューションにつながりロールを追加すると、表示されたどこででもこれを編集できます。

## <a name="create-or-edit-connection-roles"></a>つながりロールを作成または編集します。

> [!IMPORTANT]
> 新しいつながりロールや既存のつながりロールへの変更が含まれるソリューションを配布する場合、配布するソリューションにそれらを追加する必要があります。 **設定**領域を使って新しいつながりロールを編集または追加すると、**既定のソリューション**にこのようなつながりロールが追加されます。ソリューションに最初に追加したのでない限り、配布するソリューションにそれらは含められません。 詳細: [ソリューションへのつながりロールの追加](#add-connection-roles-to-a-solution)

**つながりロール**リストで、編集するためにつながりロールのいずれかを選択します。
フォームで明確に呼び出されるつながりロールを定義するステップは 3 つです。

![つながりロール フォームの作成](media/create-connection-role-form.png)

### <a name="describe-the-connection-role"></a>つながりロールを記述する

次のフィールドを設定します。

|フィールド|説明|
|--|--|
|**名前**|(必須) 接続の内容を示すテキスト。|
|**つながりロール カテゴリ**|接続のカテゴリについて説明するグループ。 詳細: [つながりロールのカテゴリ値](#connection-role-category-values)|
|**説明**|ロールの定義を入力します。|

#### <a name="connection-role-category-values"></a>つながりロール カテゴリ値

既定の**つながりロールのカテゴリ**の値は次のとおりです。
- 業務
- 家族
- 社会団体
- Sales
- その他
- 関係者
- 営業チーム
- サービス

**カテゴリ** グローバル オプション セットを編集することで、新しいカテゴリを追加したり、既存のカテゴリを変更できます。 詳細: [アプリの Common Data Service のグローバル オプション設定の作成および編集 (候補リスト)](create-edit-global-option-sets.md)

### <a name="select-record-types"></a>レコードの種類の選択

つながりに使用できるようにするレコードの種類を接続します。

> [!NOTE]
> **すべて**が既定で選択されていますが、追加するつながりロールに適した種類について検討してください。

### <a name="matching-connection-roles"></a>マッチングするつながりロール

このオプションの手順では、相互的な方法に適用されるロールを定義できます。 これは必須ではありませんが、これらが定義されているとつながりがより多くの意味を持ちます。

たとえば、Glen が Mary の*友人*であると設定できますが、これは Mary が Glen が*友人*であることを意味するのでしょうか。 そうであってほしいと思います。 しかし、Glen が Mary の*父親*であることは、Mary が Glen の*父親*であることを意味しません。 適切な相互関係を確立するには、この余分な手順が必要です。

マッチングするつながりロールを持たないつながりロールを設定すると、ロールは、つながりを適用済みのレコードからつながりを表示したときのみロールが表示されます。 つなげたレコードから表示すると、ロールは、マッチングするロールが設定されていない限り空になります。

*友人*、*配偶者*、*同僚*、*兄弟*などのロール定義の場合、それ自身にマッチング ロールを割り当てることをお勧めします。 マッチングするつながりロールが 1 つ設定されている場合、1 つのマッチングするつながりロールが両方向に適用されます。

> [!IMPORTANT]
> それ自身にマッチングするつながりロールを設定する前に、このマッチングするつながりロールなしで新しい接続ロールを保存する必要があります。

つながりロールの中には、マッチングするつながりロールを使用して既に設定されているものがあることが分ります。 *以前の社員*は、*以前の雇用主*とマッチングしており、その反対も同様です。 この種類の 1 対 1 のマッチングするつながりロールは、最も一般的です。

複雑な関係を表すため、複数のマッチングするつながりロールを設定できます。 *父親*などのつながりロールを作成する場合、*娘*や*息子*など、複数のロールを設定し、それらの両方をマッチングするつながりロールとして*父親*に適用できます。 言い換えると、*娘*および*息子*のつながりロールは、*父親*とマッチングする必要があります。 もちろん、その後*娘*および*息子*に同様にマッチングする*母*と同等のロールを設定する必要があります。

> [!TIP]
> つながりロールの複雑なセットを作成する前に、簡単な一連のロールで十分かどうかを検討します。 たとえば、*父親*、*母*、*息子*、*娘*のようなつながりロールの複雑なセットを作成する代わりに、*親*と*子*を使うだけでもよいかどうかを検討します。

複数のマッチングするつながりロールを設定すると、それらのつながりロールは有効な相互関係を持つロールのみ表します。 最初の 1 つが既定値として自動的に適用されます。 既定値が正しくない場合、手動でつながりを編集し、構成で定義されている有効なオプションから選択する必要があります。

### <a name="see-also"></a>関連項目
<!-- This is in the basics guide. It needs to be migrated -->
[レコード間の関連付けを定義および表示するために接続を作成する](/dynamics365/customer-engagement/basics/create-connections-view-relationships-between-records)<br />
[アプリの Common Data Service のグローバル オプション設定の作成および編集 (候補リスト)](create-edit-global-option-sets.md)<br />
[エンティティ間の関連付けの作成および編集](create-edit-entity-relationships.md)


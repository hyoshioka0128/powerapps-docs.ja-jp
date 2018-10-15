---
title: Common Data Service for Apps のエンティティ リレーションシップを作成および編集する | MicrosoftDocs
ms.custom: ''
ms.date: 05/26/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: c765b6d9-4d87-4c2d-aae2-5b1c3b664a71
caps.latest.revision: 28
ms.author: matp
manager: brycho
ms.openlocfilehash: 896b026bc72022e66e548db95f78d785e14fdf23
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39690774"
---
# <a name="create-and-edit-relationships-between-entities"></a>エンティティ間のリレーションシップの作成と編集 

エンティティ リレーションシップでは、データベース内でレコードがどのように相互に関連し合えるかを定義します。 最も単純なレベルでは、エンティティに参照フィールドを追加すると、2 つのエンティティの間に新しい 1:N (一対多) リレーションシップが作成され、その参照フィールドをフォームに配置できます。 参照フィールドを使用して、ユーザーはそのエンティティの複数の*子*レコードを 1 つの*親*エンティティ レコードに関連付けることができます。  
  
1:N エンティティ リレーションシップでは、レコードが他のレコードとどのように関連できるかを定義するだけでなく、次の質問に対処するデータも提供されます。  
  
- レコードを削除すると、そのレコードに関連するすべてのレコードも削除されますか。  
- レコードを割り当てる際に、そのレコードに関連するすべてのレコードも新しい所有者に割り当てる必要がありますか。  
- 既存のレコードのコンテキストで新しい関連レコードを作成する際に、データ入力プロセスをどのようにして効率化できますか。  
- レコードを表示しているユーザーは関連するレコードをどのようにして表示できますか。  
  
 また、エンティティは、2 つのエンティティの任意の数のレコードが相互に関連し合える N:N (多対多) リレーションシップに参加することもできます。  

<a name="BKMK_Connections"></a>

## <a name="decide-whether-to-use-entity-relationships-or-connections"></a>エンティティ リレーションシップまたは接続を使用するかどうかを決定する 
 
エンティティ リレーションシップは、データベースを変更するメタデータです。 これらのリレーションシップを使用すると、クエリを実行して、関連するデータを非常に効率的に取得することができます。 エンティティ リレーションシップを使用して、エンティティを定義する、またはほとんどのレコードで使用できる、正式なリレーションシップを定義します。 たとえば、潜在的な顧客のいない営業案件はあまり有効ではありません。 営業案件エンティティには、競合他社エンティティとの N:N リレーションシップもあります。 これにより、営業案件に複数の競合他社を追加できます。 このデータを取り込み、競合他社を表示するレポートを作成することもできます。  
  
レコード間には、*接続*と呼ばれる、正式でないその他のリレーションシップもあります。 たとえば、2 つの連絡先が配偶者同士である、職場外での友人である、または一方の連絡先がもう一方のアカウントの元従業員であるなどのリレーションシップを把握すると、便利な場合があります。 ほとんどの企業では、この種の情報を使用してレポートを生成したり、入力を要求したりすることはないので、エンティティ リレーションシップを作成してもあまり意味がない可能性があります。 詳細情報: [接続ロールを構成する](configure-connection-roles.md)

  
<a name="BKMK_TypesOfRelationships"></a>
 
## <a name="types-of-entity-relationships"></a>エンティティ リレーションシップの種類

ソリューション エクスプローラーを確認すると、エンティティ リレーションシップの種類は 3 つのように見えますが、 実際には次の表に示すように 2 種類しかありません。  
  
|関係の種類|説明|  
|-----------------------|-----------------|  
|**1:N (一対多)**|関連するエンティティの参照フィールドがあるので、**プライマリ エンティティ**の 1 つのエンティティ レコードを、他の多くの**関連エンティティ** レコードに関連付けることができるエンティティ関係。<br /><br /> プライマリ エンティティ レコードを表示すると、関連付けられている関連エンティティ レコードの一覧が表示されます。|  
|**N:N (多対多)**|1 つのエンティティの多くのレコードを別のエンティティの多くのレコードに関連付けることができるように、特殊な**リレーションシップ エンティティ** (インターセクト エンティティとも呼ばれます) に依存しているエンティティ リレーションシップ。<br /><br /> N:N リレーションシップのいずれかのエンティティのレコードを表示すると、それに関連するもう一方のエンティティのすべてのレコードの一覧が表示されます。|  
  
エンティティ別にグループ化されたビューがデザイナーに表示されるので、**N:1 (多対一)** リレーションシップはユーザー インターフェイスに存在します。 エンティティ*間*に 1:N リレーションシップが実際に存在し、各エンティティを**プライマリ エンティティ**または**関連エンティティ**として参照します。 関連エンティティ (*子*エンティティとも呼ばれます) には、プライマリ エンティティ (*親*エンティティとも呼ばれます) のレコードへの参照を格納できる参照フィールドがあります。 N:1 リレーションシップは、単に関連エンティティから見た 1:N リレーションシップです。  
 
## <a name="see-also"></a>関連項目

[エンティティとメタデータの概要](create-edit-metadata.md)<br />
[1:N (一対多) または N:1 (多対一) リレーションシップを作成および編集する](create-edit-1n-relationships.md)<br />
[多対多 (N:N) エンティティ リレーションシップを作成する](create-edit-nn-relationships.md)

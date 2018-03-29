---
title: Skype for Business Server 2015 のエラー リスト レポート
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: '概要: は、ビジネス サーバー 2015 の Skype のエラーの一覧のレポートについて説明します。'
ms.openlocfilehash: ef5b11f92997e6919de0fd9056acdeebddc898d0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="failure-list-report-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 のエラー リスト レポート
 
**の概要:**ビジネス サーバー 2015 の Skype のエラーの一覧のレポートについて説明します。
  
エラー リスト レポートは、エラーが発生したピアツーピア セッションまたは電話会議セッションに参加した個々の参加者に関する情報を提供します。この情報には、問題が発生したユーザーの URI、エラーに関連付けられている SIP 応答コードおよび診断 ID が含まれています。
  
## <a name="accessing-the-failure-list-report"></a>エラー リスト レポートへのアクセス

エラーの一覧のレポートは、[ビジネス サーバー 2015 の Skype でのエラー分布レポート](failure-distribution-report.md)に次の測定値のいずれかをクリックしてアクセスされます。
  
- トップの診断理由 (セッション)
    
- トップのモダリティ (セッション)
    
- トップのプール (セッション)
    
- トップのソース (セッション)
    
- トップのコンポーネント (セッション)
    
- トップの発信元ユーザー (セッション)
    
- トップの発信先ユーザー (セッション)
    
- トップの発信元ユーザー エージェント (セッション)
    
エラーの一覧のレポートからは、ピア ツー ピア セッションのセッションの詳細メトリックをクリックすると、[ビジネス サーバー 2015 の Skype でのピア ツー ピア セッション詳細レポート](peer-to-peer-session-detail-report.md)を表示できます。 また、電話会議の [電話会議] の指標をクリックすると、会議詳細レポートにもアクセスできます。
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>エラー リスト レポートの活用

エラー リスト レポートでは、マウス ポインターを値の上に置くだけで、それぞれの応答コードまたは診断 ID の説明を表示できます。たとえば、診断 ID 7025 の上にマウス ポインターを置くと、次のような説明がヒントに表示されます。
  
ユーザーのメディアの作成中に内部サーバー エラーが発生しました。
  
エラーの一覧のレポートには、直接には、少なくとも 1 つの障害が発生したセッションに参加したすべてのユーザーの一覧を取得する簡単な方法は提供されませんすることが重要も、ユーザーが最も頻繁に関与するかを決定する方法が提供されることで、障害が発生しました。セッションです。 (1 つは、エラーの一覧のレポートがありませんフィルタ リング機能)。ただし、データをエクスポートし、それをコンマ区切り値ファイルに変換する場合は、このような質問に対する回答を検索するのには Windows PowerShell を使用できます。 たとえば、データを保存するのです。CSV ファイルでは、C:\Data\Failure_List.csv という名前です。 そのファイルに保存されているデータに基づいて、このコマンドを少なくとも 1 つの障害が発生したセッションに関与したすべてのユーザーの一覧です。 
  
```
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

このコマンドを実行すると、次のような一覧が返されます。
  
```
From user
----
Pilar.Ackerman@litwareinc.com
Henrik.Jensen@litwareinc.com
Gilead.Amosnino@litwareinc.com
David.Ahs@litwareinc.com
Ken.Myer@litwareinc.com
```

次の 2 つのコマンドは、各ユーザーが参加した、エラーが発生したセッションの総数についてレポートします。
  
```
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

この結果、次のようなデータが返されます。
  
```
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
```

## <a name="filters"></a>フィルター

なし。エラー リスト レポートにフィルターを適用することはできません。
  
## <a name="metrics"></a>指標

次の表に、失敗した呼び出しごとにエラー リスト レポートで提供される情報を示します。
  
**エラー] ボックスの一覧のレポートの判断基準**

|**名**|**この項目を並べ替えることができますか。**|**説明**|
|:-----|:-----|:-----|
|**レポートされた時刻** <br/> |不可  <br/> |レポートが記録された日時。  <br/> |
|**要求** <br/> |不可  <br/> |失敗した SIP 要求の種類 (INVITE、BYE など)。  <br/> |
|**応答コード** <br/> |不可  <br/> |会議にエラーが発生したときに送信された SIP 応答コード。  <br/> |
|**診断 ID** <br/> |不可  <br/> |SIP メッセージに (ms-diagnostics ヘッダーの形で) 添付された一意の識別子。多くの場合、この情報はトラブルシューティングに役立ちます。  <br/> |
|**参加コスト時間 (ミリ秒)** <br/> |不可  <br/> |ユーザーが会議に参加するのに要した時間 (ミリ秒)。  <br/> |
|**移動元ユーザー** <br/> |不可  <br/> |呼び出しを開始したユーザーの SIP アドレス。  <br/> |
|**送信元ユーザー エージェント** <br/> |不可  <br/> |呼び出しを開始したユーザーのエンドポイントで使用されているソフトウェア。  <br/> |
|**対象ユーザー** <br/> |不可  <br/> |呼び出しを受けたユーザーの SIP アドレス。  <br/> |
   


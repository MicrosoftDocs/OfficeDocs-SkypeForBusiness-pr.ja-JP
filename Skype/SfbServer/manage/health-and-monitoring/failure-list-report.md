---
title: Skype for Business Server のエラーリストレポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: '概要: Skype for Business Server のエラーリストレポートについて説明します。'
ms.openlocfilehash: 8d0ca503f1a7883ab9ec1dd4ded8556b2ee3ab0f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817947"
---
# <a name="failure-list-report-in-skype-for-business-server"></a>Skype for Business Server のエラーリストレポート 
 
**概要:** Skype for Business Server のエラーリストレポートについて説明します。
  
エラー リスト レポートは、エラーが発生したピアツーピア セッションまたは電話会議セッションに参加した個々の参加者に関する情報を提供します。この情報には、問題が発生したユーザーの URI、エラーに関連付けられている SIP 応答コードおよび診断 ID が含まれています。
  
## <a name="accessing-the-failure-list-report"></a>エラー リスト レポートへのアクセス

[エラー一覧] レポートにアクセスするには、 [Skype For Business Server のエラー配布レポート](failure-distribution-report.md)で、次のいずれかの指標をクリックします。
  
- トップの診断理由 (セッション)
    
- トップのモダリティ (セッション)
    
- トップのプール (セッション)
    
- トップのソース (セッション)
    
- トップのコンポーネント (セッション)
    
- トップの発信元ユーザー (セッション)
    
- トップの発信先ユーザー (セッション)
    
- トップの発信元ユーザー エージェント (セッション)
    
[エラー一覧] レポートから、 [Skype For Business Server のピアツーピアセッション詳細レポート](peer-to-peer-session-detail-report.md)にアクセスできます。これには、ピアツーピアセッションのセッション詳細メトリックをクリックします。 また、電話会議の [電話会議] の指標をクリックすると、会議詳細レポートにもアクセスできます。
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>エラー リスト レポートの活用

エラー リスト レポートでは、マウス ポインターを値の上に置くだけで、それぞれの応答コードまたは診断 ID の説明を表示できます。たとえば、診断 ID 7025 の上にマウス ポインターを置くと、次のような説明がヒントに表示されます。
  
ユーザーのメディアの作成中に内部サーバー エラーが発生しました。
  
障害リストレポートでは、1つ以上のセッションに参加しているすべてのユーザーの一覧を直接取得する方法はありません。また、どのユーザーが失敗したかを判断する方法も提供されていない点に注意してください。セッション. (1 つの問題については、エラーリストレポートにはフィルター機能はありません)。ただし、データをエクスポートして、コンマ区切り値ファイルに変換した場合は、Windows PowerShell を使用して、そのような質問に対する回答を見つけることができます。 たとえば、データをに保存するとします。"C:\ Data\ Failure_List" という CSV ファイル。 このコマンドは、そのファイルに保存されているデータに基づいて、1つ以上の失敗したセッションに参加していたすべてのユーザーを一覧表示します。 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

このコマンドを実行すると、次のような一覧が返されます。
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

次の 2 つのコマンドは、各ユーザーが参加した、エラーが発生したセッションの総数についてレポートします。
  
```PowerShell
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

この結果、次のようなデータが返されます。
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a>フィルター

なし。エラー リスト レポートにフィルターを適用することはできません。
  
## <a name="metrics"></a>指標

次の表に、失敗した呼び出しごとにエラー リスト レポートで提供される情報を示します。
  
**エラー リスト レポートの指標**

|**名前**|**この項目での並べ替え**|**説明**|
|:-----|:-----|:-----|
|**レポートされた時刻** <br/> |いいえ  <br/> |レポートが記録された日時。  <br/> |
|**要求** <br/> |いいえ  <br/> |失敗した SIP 要求の種類 (INVITE、BYE など)。  <br/> |
|**応答コード** <br/> |いいえ  <br/> |会議にエラーが発生したときに送信された SIP 応答コード。  <br/> |
|**診断 ID** <br/> |いいえ  <br/> |SIP メッセージに (ms-diagnostics ヘッダーの形で) 添付された一意の識別子。多くの場合、この情報はトラブルシューティングに役立ちます。  <br/> |
|**参加コスト時間 (ミリ秒)** <br/> |いいえ  <br/> |ユーザーが会議に参加するのに要した時間 (ミリ秒)。  <br/> |
|**移動元ユーザー** <br/> |いいえ  <br/> |呼び出しを開始したユーザーの SIP アドレス。  <br/> |
|**送信元ユーザー エージェント** <br/> |いいえ  <br/> |呼び出しを開始したユーザーのエンドポイントで使用されているソフトウェア。  <br/> |
|**対象ユーザー** <br/> |不可  <br/> |呼び出しを受けたユーザーの SIP アドレス。  <br/> |
   


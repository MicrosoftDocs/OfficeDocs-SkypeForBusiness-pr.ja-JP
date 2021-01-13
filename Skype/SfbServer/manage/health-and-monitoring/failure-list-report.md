---
title: Skype for Business Server のエラー リスト レポート
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: '概要: Skype for Business Server のエラー リスト レポートについて学習します。'
ms.openlocfilehash: 48654ee827f0d7efcb50bcccc4e1d2f3fdb5422e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816847"
---
# <a name="failure-list-report-in-skype-for-business-server"></a>Skype for Business Server のエラー リスト レポート 
 
**概要:** Skype for Business Server のエラー リスト レポートについて学習します。
  
エラー リスト レポートは、エラーが発生したピアツーピア セッションまたは電話会議セッションに参加した個々の参加者に関する情報を提供します。この情報には、問題が発生したユーザーの URI、エラーに関連付けられている SIP 応答コードおよび診断 ID が含まれています。
  
## <a name="accessing-the-failure-list-report"></a>エラー リスト レポートへのアクセス

エラー リスト レポートにアクセスするには、Skype for Business Server のエラー分布レポートで [次の指標をクリックします](failure-distribution-report.md)。
  
- [トップの診断理由] (セッション)
    
- [トップ モダリティ] (セッション)
    
- [トップ プール] (セッション))
    
- [トップ ソース] (セッション))
    
- [トップ コンポーネント] (セッション)
    
- [トップの発信元ユーザー] (セッション)
    
- [トップの発信先ユーザー] (セッション)
    
- [送信元ユーザー エージェント] (セッション)
    
エラー リスト レポートから、ピアツーピア セッションのセッション詳細メトリックをクリックすると [、Skype for Business Server](peer-to-peer-session-detail-report.md) のピアツーピア セッション詳細レポートにアクセスできます。 また、電話会議の電話会議の指標をクリックすると、会議詳細レポートにもアクセスできます。
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>エラー リスト レポートの活用

エラー リスト レポートでは、マウス ポインターを値の上に置くだけで、それぞれの応答コードまたは診断 ID の説明を表示することができます。たとえば、診断 ID 7025 の上にマウス ポインターを置くと、次の説明がツールチップに表示されます。
  
Internal server error creating media for user. (ユーザーのメディアの作成中に内部サーバー エラーが発生しました。)
  
エラー リスト レポートはエラーが発生した 1 つ以上のセッションに参加したすべてのユーザーの一覧を直接取得する直接的な方法を提供せず、エラーが発生したセッションに最も頻繁に参加したユーザーを特定する方法も提供しないことに注意してください (一例を挙げると、エラー リスト レポートにはフィルター処理機能がありません)。ただし、データをエクスポートしてからコンマ区切り値ファイルに変換すると、Windows PowerShell を使用してこのような質問に対する回答を見つけることができます。たとえば、C:\Data\Failure_List.csv という名前の .CSV ファイルにデータを保存するとします。次のコマンドは、このファイルに保存されたデータに基づいて、エラーが発生した 1 つ以上のセッションに参加したすべてのユーザーの一覧を表示します。 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

このコマンドにより、次にような一覧が返されます。
  
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

これにより、次のようなデータが返されます。
  
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

なし。エラー リスト レポートはフィルターできません。
  
## <a name="metrics"></a>指標

次の表に、失敗した呼び出しごとにエラー リスト レポートで提供される情報を示します。
  
**エラー リスト レポートの指標**

|**名前**|**このアイテムを並べ替えることはできますか?**|**説明**|
|:-----|:-----|:-----|
|**レポートされた時刻** <br/> |いいえ  <br/> |レポートが記録された日時です。  <br/> |
|**要求** <br/> |いいえ  <br/> |失敗した SIP 要求の種類です (INVITE、BYE など)。  <br/> |
|**応答コード** <br/> |いいえ  <br/> |会議にエラーが発生したときに送信された SIP 応答コードです。  <br/> |
|[**診断 ID**] <br/> |いいえ  <br/> |エラーのトラブルシューティングに役立つ情報を得られることが多い、SIP メッセージに添付された一意の識別子です (ms-diagnostics ヘッダーの形式)。  <br/> |
|[**Join cost time (ms)**] (参加に要した時間 (ミリ秒)) <br/> |いいえ  <br/> |ユーザーが会議に参加するのに要した時間 (ミリ秒)。  <br/> |
|**送信元ユーザー** <br/> |いいえ  <br/> |呼び出しを開始したユーザーの SIP アドレスです。  <br/> |
|**送信元ユーザー エージェント** <br/> |いいえ  <br/> |呼び出しを開始したユーザーのエンドポイントで使用されているソフトウェアです。  <br/> |
|**送信先ユーザー** <br/> |いいえ  <br/> |呼び出しを受けたユーザーの SIP アドレスです。  <br/> |
   


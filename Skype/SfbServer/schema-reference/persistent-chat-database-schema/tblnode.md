---
title: tblNode
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode には、コントロールパネルと管理コマンドレットで管理されるオブジェクトツリー (カテゴリまたはチャットルームノードを含む) が含まれています。
ms.openlocfilehash: 99300b6e26a0c173a13e6187680fd150ffa90e0a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814565"
---
# <a name="tblnode"></a>tblNode
 
tblNode には、コントロールパネルと管理コマンドレットで管理されるオブジェクトツリー (カテゴリまたはチャットルームノードを含む) が含まれています。
  
**行**

|**列**|**種類**|**説明**|
|:-----|:-----|:-----|
|nodeID  <br/> |int (null ではない)  <br/> |ノード ID (一意の番号)。  <br/> |
|nodeGuid  <br/> |GUID、null ではない  <br/> |ノード GUID。  <br/> |
|parentID  <br/> |int  <br/> |親のノード ID。 ルートノード (ID 1 の) には、それ自体も親として含まれています。  <br/> |
|nodeType  <br/> |ビット、null ではない  <br/> |ノードがカテゴリの場合は True です。  <br/> ノードがチャットルームの場合は False です。  <br/> |
|nodeName  <br/> |nvarchar (256)、null ではない  <br/> |ノード名。  <br/> |
|nodeDesc  <br/> |nvarchar (256)、null ではない  <br/> |ノードの説明。  <br/> |
|召集  <br/> |bit  <br/> | カテゴリの場合: <br/>  招待がオンの場合は True です。 <br/>  招待がオフの場合は False です。 <br/>  会議室の場合: <br/>  [招待] がオフの場合は False です (親カテゴリを上書きします)。 <br/>  招待設定が親カテゴリから継承されている場合は Null です。 <br/> |
|ログ  <br/> |bit  <br/> | カテゴリの場合: <br/>  チャット履歴がオンの場合は True です。 <br/>  チャット履歴がオフの場合は False です。 <br/>  会議室の場合: <br/>  空. <br/> |
|filePost  <br/> |bit  <br/> | カテゴリの場合: <br/>  ファイルのアップロードが許可されている場合は True です。 <br/>  ファイルのアップロードが許可されていない場合は False です。 <br/>  会議室の場合: <br/>  空. <br/> |
|無効に  <br/> |ビット、null ではない  <br/> |チャットルームが無効になっている場合は True です。 チャットルームにのみ適用されます。 (カテゴリの場合は False)。  <br/> |
|状況  <br/> |smallint (null ではない)  <br/> | 動作 (EnumValue テーブルでの検索): <br/>  4: 標準 (通常のチャットルーム)。 <br/>  5: 聴衆 (聴衆チャットルーム、発表者のみが投稿できます)。 <br/>  チャットルームにのみ適用されます。 <br/> |
|明確化  <br/> |smallint (null ではない)  <br/> | Visibility (EnumValue テーブル上で検索される): <br/>  2: プライベート <br/>  3: 範囲 <br/>  6: 開く <br/>  チャットルームにのみ適用されます。 <br/> |
|siopID  <br/> |GUID  <br/> |アドインがこのチャットルームに関連付けられている場合は、アドインの GUID。 (カテゴリにはアドインがありません。)  <br/> アドイン情報は、SiopWhiteList リスト表で検索されます。  <br/> |
|nodeAddedBy  <br/> |int (null ではない)  <br/> |このノードを作成したプリンシパルの ID です。  <br/> |
|nodeAddedOn  <br/> |bigint (null ではない)  <br/> |ノードの作成のタイムスタンプ。  <br/> |
|nodeUpdatedBy  <br/> |int (null ではない)  <br/> |このノードの最新の更新を実行したプリンシパルの ID です。  <br/> |
|nodeUpdatedOn  <br/> |bigint (null ではない)  <br/> |このノードの最新の更新プログラムのタイムスタンプです。  <br/> |
|purgedOn  <br/> |datetime  <br/> |このノードに影響を与える最新の消去操作 (tblScopedPrincipal テーブルと tblPrincipalRole テーブルからのスコープの削除) の時間。 これは、チャットサービスの内部キャッシュ更新メカニズムによって使用されます。  <br/> |
   
**機能**

|**列**|**説明**|
|:-----|:-----|
|nodeID  <br/> |主キー。  <br/> |
|状況  <br/> |TblEnumValue Id テーブルで参照される外部キー。  <br/> |
|明確化  <br/> |TblEnumValue Id テーブルで参照される外部キー。  <br/> |
|parentID  <br/> |TblNode テーブルで参照される外部キー。  <br/> |
|siopID  <br/> |TblSiopWhiteList テーブルで参照する外部キー。  <br/> |
   


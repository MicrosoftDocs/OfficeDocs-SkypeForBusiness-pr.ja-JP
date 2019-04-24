---
title: tblNode
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode には、コントロール パネル、管理用コマンドレットの管理下にオブジェクト ・ ツリーでノードのカテゴリまたはチャット ルーム) が含まれています。
ms.openlocfilehash: c5028b138711b6f57c0e947ea41572fd9984b3fb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212552"
---
# <a name="tblnode"></a>tblNode
 
tblNode には、コントロール パネル、管理用コマンドレットの管理下にオブジェクト ・ ツリーでノードのカテゴリまたはチャット ルーム) が含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|ノード  <br/> |int 型、null でないです。  <br/> |ノード ID (一意の番号)。  <br/> |
|nodeGuid  <br/> |GUID では、null でないです。  <br/> |ノード GUID です。  <br/> |
|parentID  <br/> |int  <br/> |親ノードの ID。 (ID 1) のルート ノードには、親もとしてそれ自体が含まれます。  <br/> |
|nodeType  <br/> |ビットの null でないです。  <br/> |ノードでは、カテゴリがある場合は true。  <br/> False を指定すると、ノードは、チャット ルームです。  <br/> |
|ノード名  <br/> |nvarchar (256)、null でないです。  <br/> |ノード名です。  <br/> |
|nodeDesc  <br/> |nvarchar (256)、null でないです。  <br/> |ノードの説明です。  <br/> |
|招待  <br/> |bit  <br/> | カテゴリ。 <br/>  招待する場合は true。 <br/>  招待がオフである場合は false。 <br/>  部屋。 <br/>  招待がオフである場合は false (親カテゴリを上書きします)。 <br/>  招待の設定が親カテゴリから継承されている場合は null です。 <br/> |
|記録  <br/> |bit  <br/> | カテゴリ。 <br/>  True を設定するには、チャットの履歴。 <br/>  チャットの履歴が無効になっている場合は false を指定します。 <br/>  部屋。 <br/>  Null です。 <br/> |
|filePost  <br/> |bit  <br/> | カテゴリ。 <br/>  ファイルのアップロードが許可されている場合は true です。 <br/>  ファイルのアップロードが許可されていない場合は false。 <br/>  部屋。 <br/>  Null です。 <br/> |
|無効になっています。  <br/> |ビットの null でないです。  <br/> |チャット ルームが無効になっている場合は true。 チャット ルームにのみ適用されます。 偽のカテゴリです。  <br/> |
|動作  <br/> |smallint、null でないです。  <br/> | (EnumValue テーブルで検索) 動作します。 <br/>  4: 標準 (通常のチャット ルーム)。 <br/>  5: 大 (大会議チャット ルームでは、発表者のみ投稿できますが)。 <br/>  チャット ルームにのみ適用されます。 <br/> |
|可視性  <br/> |smallint、null でないです。  <br/> | (EnumValue テーブル上で検索) を表示します。 <br/>  2: 秘密 <br/>  3: スコープ <br/>  6: オープン <br/>  チャット ルームにのみ適用されます。 <br/> |
|siopID  <br/> |GUID  <br/> |アドインの GUID アドインでは、このチャット ルームに関連付けられている場合です。 (カテゴリは、アドインを必要はありません)。  <br/> SiopWhiteList テーブル内追加の情報が検索されます。  <br/> |
|nodeAddedBy  <br/> |int 型、null でないです。  <br/> |このノードを作成したプリンシパルの ID です。  <br/> |
|nodeAddedOn  <br/> |bigint 型の値、null でないです。  <br/> |ノード作成のタイムスタンプです。  <br/> |
|nodeUpdatedBy  <br/> |int 型、null でないです。  <br/> |このノードの最新の更新をしているプリンシパルの ID です。  <br/> |
|nodeUpdatedOn  <br/> |bigint 型の値、null でないです。  <br/> |このノードの最新の更新のタイム ・ スタンプ。  <br/> |
|purgedOn  <br/> |datetime  <br/> |このノードの影響を最新のパージ操作 (tblScopedPrincipal テーブルからのスコープとロールを tblPrincipalRole テーブルからの削除) の時間です。 チャット サービスの内部キャッシュ更新メカニズムによって使用されます。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|ノード  <br/> |プライマリ ・ キーです。  <br/> |
|動作  <br/> |TblEnumValue.valueID テーブル内の参照と外部キーです。  <br/> |
|可視性  <br/> |TblEnumValue.valueID テーブル内の参照と外部キーです。  <br/> |
|parentID  <br/> |TblNode.nodeID テーブル内の参照と外部キーです。  <br/> |
|siopID  <br/> |TblSiopWhiteList.siopId テーブル内の参照と外部キーです。  <br/> |
   


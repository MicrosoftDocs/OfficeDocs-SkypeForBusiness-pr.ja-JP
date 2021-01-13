---
title: tblNode
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode には、コントロール パネルと管理コマンドレットで管理されるオブジェクト ツリー (カテゴリノードまたはチャット ルーム ノードを含む) が含まれます。
ms.openlocfilehash: cd2353d768ef61787b81efcdfe35f9c57409cc12
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815927"
---
# <a name="tblnode"></a>tblNode
 
tblNode には、コントロール パネルと管理コマンドレットで管理されるオブジェクト ツリー (カテゴリノードまたはチャット ルーム ノードを含む) が含まれます。
  
**Columns**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|nodeID  <br/> |NULL でない int  <br/> |ノード ID (一意の番号)。  <br/> |
|nodeGuid  <br/> |NULL でない GUID  <br/> |ノード GUID。  <br/> |
|parentID  <br/> |int  <br/> |親のノード ID。 ルート ノード (ID 1) には、それ自体も親として含まれます。  <br/> |
|nodeType  <br/> |NULL でない bit  <br/> |True ノードがカテゴリである場合です。  <br/> False ノードがチャット ルームの場合です。  <br/> |
|nodeName  <br/> |NULL でない nvarchar (256)  <br/> |ノード名。  <br/> |
|nodeDesc  <br/> |NULL でない nvarchar (256)  <br/> |ノードの説明。  <br/> |
|invite  <br/> |bit  <br/> | カテゴリの場合: <br/>  招待がオンの場合は True。 <br/>  招待がオフの場合は False。 <br/>  ルームの場合: <br/>  False 招待がオフの場合 (親カテゴリを上書きします)。 <br/>  招待設定が親カテゴリから継承される場合は Null。 <br/> |
|logged  <br/> |bit  <br/> | カテゴリの場合: <br/>  True の 場合は、チャット履歴がオンです。 <br/>  False チャット履歴がオフの場合です。 <br/>  ルームの場合: <br/>  Null。 <br/> |
|filePost  <br/> |bit  <br/> | カテゴリの場合: <br/>  True の 場合は、ファイルのアップロードが許可されます。 <br/>  False ファイルのアップロードが許可されている場合です。 <br/>  ルームの場合: <br/>  Null。 <br/> |
|disabled  <br/> |NULL でない bit  <br/> |True の 場合は、チャット ルームが無効になっています。 チャット ルームにのみ適用されます。 (カテゴリの場合は False)  <br/> |
|behavior  <br/> |NULL でない smallint  <br/> | 動作 (EnumValue テーブルで参照): <br/>  4: 標準 (通常のチャット ルーム)。 <br/>  5: 大会議室 (大会議室のチャット ルーム、発表者だけが投稿可能)。 <br/>  チャット ルームにのみ適用されます。 <br/> |
|visibility  <br/> |NULL でない smallint  <br/> | 可視性 (EnumValue テーブルを参照): <br/>  2: プライベート <br/>  3: スコープ <br/>  6: 開く <br/>  チャット ルームにのみ適用されます。 <br/> |
|siopID  <br/> |GUID  <br/> |Add-Inがチャット ルームに関連付けられている場合は、GUID を取得します。 (カテゴリにはアドインが含まれます。  <br/> アドイン情報は SiopWhiteList テーブルで参照されます。  <br/> |
|nodeAddedBy  <br/> |NULL でない int  <br/> |このノードを作成したプリンシパルの ID。  <br/> |
|nodeAddedOn  <br/> |NULL でない bigint  <br/> |ノード作成のタイム スタンプ。  <br/> |
|nodeUpdatedBy  <br/> |NULL でない int  <br/> |このノードの最新の更新を行ったプリンシパルの ID。  <br/> |
|nodeUpdatedOn  <br/> |NULL でない bigint  <br/> |このノードの最新の更新プログラムのタイム スタンプ。  <br/> |
|purgedOn  <br/> |日付型  <br/> |このノードに影響を与えた最新の削除操作の時刻 (tblScopedPrincipal テーブルからのスコープと tblPrincipalRole テーブルからのロールの削除)。 これは、チャット サービスの内部キャッシュ更新メカニズムによって使用されます。  <br/> |
   
**Keys**

|**列**|**説明**|
|:-----|:-----|
|nodeID  <br/> |主キー。  <br/> |
|behavior  <br/> |tblEnumValue.valueID テーブルを参照する外部キー。  <br/> |
|visibility  <br/> |tblEnumValue.valueID テーブルを参照する外部キー。  <br/> |
|parentID  <br/> |tblNode.nodeID テーブル内の参照による外部キー。  <br/> |
|siopID  <br/> |tblSiopWhiteList.siopId テーブルを参照する外部キー。  <br/> |
   


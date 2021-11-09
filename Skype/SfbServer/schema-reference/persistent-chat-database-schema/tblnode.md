---
title: tblNode
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode には、コントロール パネルおよび管理コマンドレットで管理されるオブジェクト ツリー (カテゴリまたはチャット ルーム ノードを含む) が含まれます。
ms.openlocfilehash: 1e6d3a97f04d614a0993ca06d8a5b2a2f928b39d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846250"
---
# <a name="tblnode"></a>tblNode
 
tblNode には、コントロール パネルおよび管理コマンドレットで管理されるオブジェクト ツリー (カテゴリまたはチャット ルーム ノードを含む) が含まれます。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|nodeID  <br/> |NULL でない int  <br/> |ノード ID (一意の番号)。  <br/> |
|nodeGuid  <br/> |NULL でない GUID  <br/> |ノード GUID。  <br/> |
|parentID  <br/> |int  <br/> |親のノード ID。 ルート ノード (ID 1 を含む) には、それ自体も親として含まれます。  <br/> |
|nodeType  <br/> |NULL でない bit  <br/> |True の場合は、ノードがカテゴリです。  <br/> ノードがチャット ルームの場合は False。  <br/> |
|nodeName  <br/> |NULL でない nvarchar (256)  <br/> |ノード名。  <br/> |
|nodeDesc  <br/> |NULL でない nvarchar (256)  <br/> |ノードの説明。  <br/> |
|invite  <br/> |ビット  <br/> | カテゴリの場合: <br/>  True の場合は、招待がオンです。 <br/>  False の場合は、招待がオフです。 <br/>  ルームの場合: <br/>  False の場合は、招待がオフです (親カテゴリを上書きします)。 <br/>  親カテゴリから招待設定が継承されている場合は Null。 <br/> |
|ログに記録される  <br/> |ビット  <br/> | カテゴリの場合: <br/>  True の場合は、チャットの履歴がオンです。 <br/>  False の場合は、チャットの履歴がオフです。 <br/>  ルームの場合: <br/>  Null。 <br/> |
|filePost  <br/> |ビット  <br/> | カテゴリの場合: <br/>  True の場合は、ファイルのアップロードが許可されます。 <br/>  False の場合は、ファイルのアップロードが許可されません。 <br/>  ルームの場合: <br/>  Null。 <br/> |
|disabled  <br/> |NULL でない bit  <br/> |True の場合は、チャット ルームが無効です。 チャット ルームにのみ適用されます。 (カテゴリの場合は False)。  <br/> |
|動作  <br/> |NULL でない smallint  <br/> | 動作 (EnumValue テーブルで参照): <br/>  4: 標準 (通常のチャット ルーム)。 <br/>  5: 講堂 (講堂チャット ルーム、発表者だけが投稿できます)。 <br/>  チャット ルームにのみ適用されます。 <br/> |
|visibility  <br/> |NULL でない smallint  <br/> | 可視性 (EnumValue テーブルを参照): <br/>  2: プライベート <br/>  3: スコープ <br/>  6: 開く <br/>  チャット ルームにのみ適用されます。 <br/> |
|siopID  <br/> |GUID  <br/> |Add-Inチャット ルームに関連付けられている場合は、GUID を使用します。 (カテゴリにはアドインが含まれています)。  <br/> アドインの情報は、SiopWhiteList テーブルで参照されます。  <br/> |
|nodeAddedBy  <br/> |NULL でない int  <br/> |このノードを作成したプリンシパルの ID。  <br/> |
|nodeAddedOn  <br/> |NULL でない bigint  <br/> |ノード作成のタイム スタンプ。  <br/> |
|nodeUpdatedBy  <br/> |NULL でない int  <br/> |このノードの最新の更新を行ったプリンシパルの ID。  <br/> |
|nodeUpdatedOn  <br/> |NULL でない bigint  <br/> |このノードの最新の更新プログラムのタイムスタンプ。  <br/> |
|purgedOn  <br/> |日付型  <br/> |このノードに影響を与えた最新の削除操作の時間 (tblScopedPrincipal テーブルからのスコープと tblPrincipalRole テーブルからのロールの削除)。 これは、チャット サービスの内部キャッシュ更新メカニズムによって使用されます。  <br/> |
   
**Keys**

|**列**|**説明**|
|:-----|:-----|
|nodeID  <br/> |主キー。  <br/> |
|動作  <br/> |tblEnumValue.valueID テーブル内の参照を含む外部キー。  <br/> |
|visibility  <br/> |tblEnumValue.valueID テーブル内の参照を含む外部キー。  <br/> |
|parentID  <br/> |tblNode.nodeID テーブル内の参照による外部キー。  <br/> |
|siopID  <br/> |tblSiopWhiteList.siopId テーブル内の参照を含む外部キー。  <br/> |
   


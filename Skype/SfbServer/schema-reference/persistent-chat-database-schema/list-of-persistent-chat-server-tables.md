---
title: 常設チャット サーバーのテーブルのリスト
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
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: 常設チャット データベース スキーマは、次の表で構成されます。
ms.openlocfilehash: fc87faee92856f35c1ebd54dae4db1f01cfe646b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813017"
---
# <a name="list-of-persistent-chat-server-tables"></a>常設チャット サーバーのテーブルのリスト
 
常設チャット データベース スキーマは、次の表で構成されます。
  
## <a name="active-directory-sync"></a>Active Directory 同期

|**Table**|**説明**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |現在の LDAP (Lightweight Directory Access Protocol) 同期 Cookie が含まれます。 各行は、常設チャット サーバーが変更を監視している Active Directory ドメイン サービス ドメインに対応します。 (この表では、常設チャット サーバーに関連する Active Directory ドメインのみを表します)。  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |Active Directory 同期の後の手順でまだ処理されていないグループ メンバーシップの変更 (追加および削除されたメンバーの両方) が含まれます。これは、Active Directory 同期の最初の手順で使用される一時テーブル (tblADUpdates テーブルと共に) の 1 つです。  <br/> メンバーシップの変更が格納および処理されるのは、tblPrincipal テーブルにリストされているグループ、またはメンバーが既にここにリストされているグループについてだけです。  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |Active Directory 同期の後の手順でまだ処理されていない Active Directory ドメイン サービスに対する変更が含まれます。これは、Active Directory 同期の最初の手順で使用される一時テーブル (tblPrincipalMemberDifference テーブルと共に) の 1 つです。  <br/> Active Directory に対する変更は、tblPrincipal テーブルに既にリストされているプリンシパルに対してだけ、保存、処理、または両方を行います。  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |プリンシパルのメンバーシップが格納されます。  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |Active Directory から更新する必要があるプリンシパルが含まれます。  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |何らかの理由で更新できない所属 (通常は Active Directory アクセス エラーが原因) が含まれます。  <br/> このテーブルは情報提供のみを目的としています。内容は使用されません。  <br/> 適切に更新できなかった所属のあるプリンシパルは、tblPrincipalMeta テーブルに保持され、再度更新が試みられます。  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>プリンシパル、所属、ノード、スコープ、役割

|**Table**|**説明**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |tblPrincipal テーブルの内容を分類するためのプリンシパルの種類が格納されます。このテーブルは静的です。データベース作成時に設定され、変更されません。  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |すべてのプリンシパル (ユーザー、フォルダー、グループなど) が格納されます。 常設チャット サーバーは、これをフラットな異種リストとして処理します。 さまざまな列は、各プリンシパルの種類に基づきます。  <br/> これらのプリンシパルの大部分は、Active Directory に格納されているオブジェクトのキャッシュ コピーです。 キャッシュされたコピーをこれらの Active Directory オブジェクトのプリンシパル テーブルに作成すると、プロビジョニングと呼ばれます。  <br/> 一部のプリンシパルは他のプリンシパルよりも積極的に作成され、一部の Active Directory オブジェクトは完全に無視されます。  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Active Directory セキュリティ グループ、Active Directory コンテナーなどでのメンバーシップを記述するプリンシパルの所属が含まれます。  <br/> |
|[tblNode](tblnode.md) <br/> |コントロール パネルで管理されるカテゴリ ノードを格納します。  <br/> |
|[tblRoleType](tblroletype.md) <br/> |役割の種類とそれに関連付けられているアクセス許可セットが格納されます。 この検索テーブルは静的です。  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |ノードに割り当てられたスコープが格納されます。  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |ノードに割り当てられた役割が格納されます。  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |ノードと関連付けることのできる登録されたアドインが格納されます。  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |tblNode テーブルで使用されるハードコードされた "表示" および "動作" 属性だけが格納されます。  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |tblNode テーブルで使用されるハードコードされた "Visibility" 属性と "Behavior" 属性の値を格納します。  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>招待、チャット、および他のクライアントのサポート

|**Table**|**説明**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |自動招待が有効になっているすべてのノードに対する、システム内のプロビジョニングされたすべてのユーザーの招待が格納されます。  <br/> |
|[tblChat](tblchat.md) <br/> |すべてのチャット メッセージが格納されます。  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |各ユーザーに対して生成された (そして tblPrincipalInvites テーブルで使用された) 最後の招待 ID が格納されます。  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |各ユーザーに対して生成された (そして tblChat テーブルで使用された) 最後のチャット ID が格納されます。  <br/> |
|[tblPreference](tblpreference.md) <br/> |ユーザーのクライアントの基本設定 (レガシ クライアントでのみ使用される) が格納されます。  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |ファイル送信を目的とする一時的なトークンが格納されます。 ファイルがアップロードまたはダウンロードされるたび、常設チャット サービスは、クライアントが Web サービス ファイル ストアにアクセスするために使用するトークンを生成します。  <br/> |
   
## <a name="server-support"></a>サーバーのサポート

|**Table**|**説明**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |常設チャット サーバー プール内のアクティブなサーバーが含まれます。  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |管理者コマンドを実行するための管理者ロックが格納されます。ロックが解除されるたびに、tblSystemRevision テーブル内のシステム リビジョン エントリがインクリメントされます。  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |複数のサーバー間の整合性を実現するために (tblAdminLock テーブルと共に) 使用されるリビジョン番号エントリが格納されます。  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |常設チャット サービス間の現在のピアツーピア接続が含まれる。  <br/> |
|[tblConfig](tblconfig.md) <br/> |常設チャット サーバーでサポートされていない構成が含まれている。  <br/> |
   


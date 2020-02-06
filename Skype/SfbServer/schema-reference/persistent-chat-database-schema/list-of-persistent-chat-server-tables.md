---
title: 常設チャット サーバーのテーブルのリスト
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
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: 常設チャットデータベーススキーマは、次の表で構成されています。
ms.openlocfilehash: ae6e1a260cb167397da83d79d37b92067d2ae99d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814755"
---
# <a name="list-of-persistent-chat-server-tables"></a>常設チャット サーバーのテーブルのリスト
 
常設チャットデータベーススキーマは、次の表で構成されています。
  
## <a name="active-directory-sync"></a>Active Directory の同期

|**テーブル**|**説明**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |現在のライトウェイトディレクトリアクセスプロトコル (LDAP) 同期 cookie が含まれます。 各行は、常設チャットサーバーが変更を積極的に監視している Active Directory ドメインサービスドメインに対応しています。 (この表では、常設チャットサーバーに関連する Active Directory ドメインのみが示されています。)  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |Active directory 同期の以降の手順でまだ処理されていないグループメンバーシップの変更 (メンバーの追加と削除の両方) が含まれています。また、Active Directory 同期の最初の手順で使用されている一時的なテーブル (tblADUpdates table と共に表示されます) の1つです。  <br/> メンバーシップの変更は、tblPrincipal テーブルに一覧表示されている、または既に表示されているメンバーが含まれているグループに対してのみ、保存、処理、またはその両方になります。  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |Active directory の以降の同期手順でまだ処理されていない Active Directory ドメインサービスへの変更が含まれています。また、Active directory の最初の手順で使用される一時的なテーブル (tblPrincipalMemberDifference テーブルと共に表示されます) の1つです。せる.  <br/> Active Directory への変更は、tblPrincipal テーブルに既に一覧表示されているプリンシパルに対してのみ保存、処理、またはその両方が行われます。  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |プリンシパルメンバーシップが含まれます。  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |Active Directory から更新する必要があるプリンシパルが含まれています。  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |何らかの理由で更新できない所属先が含まれています。通常、Active Directory アクセスエラーが原因です。  <br/> この表は、情報提供のみを目的としています。 コンテンツは使用されません。  <br/> 適切に更新できなかった所属のプリンシパルは、tblPrincipalMeta テーブルに保存され、もう一度更新される可能性があります。  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>プリンシパル、所属、ノード、スコープ、およびロール

|**テーブル**|**説明**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |TblPrincipal テーブルの内容を分類するプリンシパルの型が含まれています。 この表は静的です。 データベースの作成中に設定され、変更されません。  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |すべてのプリンシパル (ユーザー、フォルダー、グループなど) が含まれます。 常設チャットサーバーは、フラットな異種混在リストとして処理します。 さまざまな列は、各プリンシパルの種類に基づいています。  <br/> これらのプリンシパルのほとんどは、Active Directory に保存されているオブジェクトのキャッシュコピーです。 これらの Active Directory オブジェクトのプリンシパルテーブルに、キャッシュされたコピーを作成することは、プロビジョニングと呼ばれます。  <br/> 一部のプリンシパルは、他のプリンシパルよりも積極的に作成され、一部の Active Directory オブジェクトは無視されます。  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Active Directory セキュリティグループ、Active Directory コンテナーなどのメンバーシップについて説明するプリンシパルメンバーが含まれています。  <br/> |
|[tblNode](tblnode.md) <br/> |コントロールパネルで管理されるカテゴリノードが含まれています。  <br/> |
|[tblRoleType](tblroletype.md) <br/> |ロールの種類とそれに関連付けられているアクセス許可セットが含まれます。 この参照テーブルは静的です。  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |ノードに割り当てられたスコープが含まれます。  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |ノードに割り当てられている役割が含まれます。  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |ノードに関連付けることができる登録済みのアドインが含まれています。  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |TblNode テーブルで使用される、ハードコーディングされた "Visibility" 属性と "Behavior" 属性のみが含まれています。  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |TblNode テーブルで使用される、ハードコーディングされた "Visibility" 属性と "Behavior" 属性の値が格納されています。  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>招待、チャット、その他のクライアントのサポート

|**テーブル**|**説明**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |自動招待が有効になっているすべてのノードについて、システム内のプロビジョニングされたすべてのユーザーの招待が含まれます。  <br/> |
|[tblChat](tblchat.md) <br/> |すべてのチャットメッセージが含まれます。  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |各ユーザーに対して生成された (tblPrincipalInvites テーブルで使用される) 最後の招待 ID が含まれています。  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |各ユーザーに対して生成された (tblChat テーブルで使用された) 最後のチャット ID が含まれています。  <br/> |
|[tblPreference](tblpreference.md) <br/> |ユーザークライアントの設定が含まれます (レガシクライアントでのみ使用されます)。  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |ファイル転送のための一時トークンが含まれています。 ファイルがアップロードまたはダウンロードされるたびに、常設チャットサービスは、クライアントが Web サービスファイルストアへのアクセスに使用するトークンを生成します。  <br/> |
   
## <a name="server-support"></a>サーバーのサポート

|**テーブル**|**説明**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |常設チャットサーバープール内のアクティブなサーバーが含まれます。  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |一部の管理者コマンドを実行するための管理者ロックが含まれています。 TblSystemRevision テーブルのシステムリビジョンエントリは、ロックの各リリースの後でインクリメントされます。  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |複数のサーバー間で一貫性を確保するために使用されるリビジョン番号エントリ (tblAdminLock テーブルと共に) が含まれます。  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |常設チャットサービス間の現在のピアツーピア接続が含まれます。  <br/> |
|[tblConfig](tblconfig.md) <br/> |常設チャットサーバーでサポートされていない構成が含まれています。  <br/> |
   


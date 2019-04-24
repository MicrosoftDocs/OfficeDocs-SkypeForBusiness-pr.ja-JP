---
title: 常設チャット サーバーのテーブルのリスト
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: 永続的なチャットのデータベース スキーマは、次の表で構成されています。
ms.openlocfilehash: e2ce24bb37c3ea4eaee0986f0243033ab4a8a18a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213222"
---
# <a name="list-of-persistent-chat-server-tables"></a>常設チャット サーバーのテーブルのリスト
 
永続的なチャットのデータベース スキーマは、次の表で構成されています。
  
## <a name="active-directory-sync"></a>Active Directory の同期

|**テーブル**|**説明**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |現在のライトウェイト ディレクトリ アクセス プロトコル (LDAP) 同期 cookie が含まれています。 各行は、永続的なチャット サーバーが変更を監視する Active Directory ドメイン サービスのドメインに対応しています。 (永続的なチャット サーバーに関連付けられている Active Directory のドメインのみは、次の表で表されます)。  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |グループ メンバーシップの変更 (追加し、削除メンバー) を作業中のディレクトリ同期の後の手順でまだ処理されていないと、作業中のディレクトリ同期の最初のステップで使用されている一時テーブル (および tblADUpdates のテーブル) の 1 つが含まれています。  <br/> メンバーシップの変更は保存、処理、または表示されているメンバーがあるどちらか一方のみまたは tblPrincipal テーブルに既に記載されているグループです。  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |後の作業中のディレクトリ同期手順でまだ処理されていない Active Directory ドメイン サービスへの変更が含まれており (tblPrincipalMemberDifference テーブル) と Active Directory の最初のステップで使用されている一時テーブルのいずれか同期します。  <br/> Active Directory への変更は保存されている、処理、またはその両方は、tblPrincipal テーブルに表示されている主体にだけです。  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |プリンシパルのメンバーシップが含まれています。  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |Active Directory から更新する必要があるプリンシパルが含まれています。  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |通常 Active Directory のアクセス エラーが発生したため、何らかの理由で更新できませんでしたの所属団体が含まれています。  <br/> このテーブルは情報提供のみを目的としておりします。 その内容は使用されません。  <br/> 正しく更新できませんでしたの所属団体でのプリンシパルでは、tblPrincipalMeta テーブルに保持されを更新する別の機会が与えられます。  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>プリンシパル、所属名、ノード、スコープ、およびロール

|**テーブル**|**説明**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |TblPrincipal テーブルに含まれるものを分類するためにプリンシパルの種類が含まれています。 このテーブルは静的です。 データベースの作成時に設定し、変更されません。  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |すべてのプリンシパル (ユーザー、フォルダー、グループ、およびなど) が含まれています。 永続的なチャット サーバーでは、平らな異機種混在のリストとして、これを処理します。 さまざまな列は、各プリンシパルの種類に基づいています。  <br/> これらの主体のほとんどは、Active Directory に格納されているオブジェクトのキャッシュされたコピーです。 キャッシュされたコピーを作成するプリンシパルには、これらの Active Directory オブジェクトのテーブル、プロビジョニングと呼ばれます。  <br/> いくつかのプリンシパルが、他の人よりも積極的に作成され、いくつかの Active Directory オブジェクトを無視します。  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Active Directory セキュリティ グループなど、Active Directory コンテナー内のメンバーシップを表すプリンシパルの所属が含まれています。  <br/> |
|[tblNode](tblnode.md) <br/> |コントロール パネルの管理下に、[カテゴリ] ノードが含まれています。  <br/> |
|[tblRoleType](tblroletype.md) <br/> |ロールの種類と、関連付けられたアクセス許可を設定します。 このルックアップ テーブルは、静的です。  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |ノードに割り当てられたスコープが含まれています。  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |ノードに割り当てられているロールが含まれています。  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |アドインが含まれます、登録されているノードと関連付けることができます。  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |ハードコードされた「表示」と"問題の属性のみ tblNode テーブルで使用されているが含まれています。  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |TblNode テーブルで使用されているハードコードされた「可視性」と「動作」属性の値が含まれています。  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>招待、チャット、およびその他のクライアントのサポート

|**テーブル**|**説明**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |自動招待が有効になっているとのすべてのノードのシステムにプロビジョニングされたすべてのユーザーの招待が含まれています。  <br/> |
|[tblChat](tblchat.md) <br/> |すべてのチャット メッセージが含まれています。  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |ユーザーごとに生成された (および tblPrincipalInvites テーブルで使用されている) 最後の招待 ID が含まれています。  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |ユーザーごとに生成された (および tblChat テーブルで使用されている) 最後のチャット ID が含まれています。  <br/> |
|[tblPreference](tblpreference.md) <br/> |(レガシ クライアントのみが使用されます)、ユーザーのクライアント設定が含まれています。  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |ファイル転送用の一時トークンが含まれています。 たびにファイルをアップロードまたはダウンロードするには、永続的なチャット サービスは、クライアントが Web サービスのファイル ストアへのアクセスに使用するトークンを生成します。  <br/> |
   
## <a name="server-support"></a>サーバーのサポート

|**テーブル**|**説明**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |永続的なチャット サーバー プール内のアクティブなサーバーが含まれています。  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |管理者の一部のコマンドを実行する管理者のロックが含まれています。 システム リビジョン テーブル内のエントリの tblSystemRevision は、ロックの各リリース後にインクリメントされます。  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |複数のサーバー間の一貫性を実現するための (tblAdminLock テーブルと共に) 使用されるリビジョン番号のエントリが含まれています。  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |永続的なチャット サービスの間の現在のピア ツー ピア接続が含まれています。  <br/> |
|[tblConfig](tblconfig.md) <br/> |永続的なチャット サーバーのサポートされていない構成が含まれています。  <br/> |
   


---
title: FocusJoinsAndLeaves テーブル (2015 Skype for Business Server)
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: この表の各レコードには、1 つのユーザーの参加に関する CDR 情報と、1 つの会議の情報を残す情報が含まれている。 各会議は、ユーザーが会議に参加して会議を離れるごとに、この表に 1 つのレコードで表されます。
---

# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>FocusJoinsAndLeaves テーブル (2015 Skype for Business Server)
 
この表の各レコードには、1 つのユーザーの参加に関する CDR 情報と、1 つの会議の情報を残す情報が含まれている。 各会議は、ユーザーが会議に参加して会議を離れるごとに、この表に 1 つのレコードで表されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |主/プライマリ、外部  <br/> |会議インスタンスの時間。 **SessionIdSeq と組み合わせて使用して**、会議インスタンスを一意に識別します。 詳細については[、Skype for Business Server 2015](conferences.md) の電話会議の表を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主/プライマリ、外部  <br/> |会議インスタンスを識別する ID 番号。 **SessionIdTime と組み合わせて使用して**、会議インスタンスを一意に識別します。 詳細については[、Skype for Business Server 2015](conferences.md) の電話会議の表を参照してください。 <br/> |
|**DialogSessionIdTime** <br/> |日付型  <br/> |主/プライマリ、外部  <br/> |セッション要求の時刻。 セッションを一意に識別するために **SessionIdSeq** と併用されます。 詳細については[、2015 Skype for Business Serverの](dialogs.md) Dialogs テーブルを参照してください。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |主/プライマリ、外部  <br/> |セッションを識別するための ID 番号。 セッションを一意に識別するために **SessionIdTime** と併用されます。 詳細については[、「ダイアログ」の表Skype for Business Server 2015](dialogs.md) を参照してください。 <br/> |
|**UserId** <br/> |int  <br/> |外部  <br/> |ユーザー テーブルから参照される、このユーザーを識別する [一意の番号](users.md)。  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||ユーザーが複数のコンピューターまたはデバイスで同時にログオンしている場合、 **UserInstance** を使用してユーザーとデバイスの組み合わせを一意に識別します。 <br/> |
|**IsUserInternal** <br/> |ビット  <br/> | <br/> |ユーザーが内部からログオンしたかどうか。  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |発表者や出席者など、会議でのこのユーザーの役割。  <br/> |
|**UserJoinTime** <br/> |日付型  <br/> | <br/> |このユーザーが会議に参加する時間。  <br/> |
|**UserLeaveTime** <br/> |日付型  <br/> | <br/> |このユーザーが会議を離れる時刻。  <br/> |
|**ClientVerId** <br/> |int  <br/> |外部  <br/> |[2015 年の ClientVersions](clientversions.md) テーブルを参照する、ユーザーのクライアント ソフトウェアSkype for Business Server。  <br/> |
|**UserEndpointId** <br/> |uniqueIdentifier  <br/> ||会議で使用されるエンドポイントのグローバル一意識別子 (GUID)。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスの内部用テーブル。  <br/> このフィールドは、2015 年Skype for Business Serverされました。  <br/> |
   


---
title: McuJoinsAndLeaves テーブル (2015 Skype for Business Server)
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
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: この表の各レコードには、ユーザー参加サーバーまたは退出サーバーと会議サーバーの 1 つの組み合わせに関する通話の詳細が含まれている。 たとえば、ユーザーが Web 会議と音声/ビデオ要素を含む会議に参加した場合、そのユーザーの Web 会議参加用に 1 つのレコードが作成され、ユーザーの電話/ビデオ会議参加用に別のレコードが作成されます。
---

# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>McuJoinsAndLeaves テーブル (2015 Skype for Business Server)
 
この表の各レコードには、ユーザー参加サーバーまたは退出サーバーと会議サーバーの 1 つの組み合わせに関する通話の詳細が含まれている。 たとえば、ユーザーが Web 会議と音声/ビデオ要素を含む会議に参加した場合、そのユーザーの Web 会議参加用に 1 つのレコードが作成され、ユーザーの電話/ビデオ会議参加用に別のレコードが作成されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |主/プライマリ、外部  <br/> |会議インスタンスの時間。 **SessionIdSeq と組み合わせて使用して**、会議インスタンスを一意に識別します。 詳細については[、Skype for Business Server 2015](conferences.md) の電話会議の表を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主/プライマリ、外部  <br/> |会議インスタンスを識別する ID 番号。 **SessionIdTime と組み合わせて使用して**、会議インスタンスを一意に識別します。 詳細については[、Skype for Business Server 2015](conferences.md) の電話会議の表を参照してください。 <br/> |
|**UserId** <br/> |int  <br/> |主/プライマリ、外部  <br/> |このユーザーを識別する一意の番号。 詳細については [、「Users」テーブル](users.md) を参照してください。 <br/> |
|**McuUserInstance** <br/> |int  <br/> |Primary  <br/> |ユーザーが複数のコンピューターまたはデバイスで一度にログオンしている場合、McuUserInstance はユーザーとデバイスの組み合わせを一意に識別します。  <br/> |
|**IsFromPstn** <br/> |ビット  <br/> | <br/> |ユーザーが PSTN から参加するかどうか。  <br/> |
|**McuId** <br/> |int  <br/> |主/プライマリ、外部  <br/> |この会議サーバーを識別する一意の番号。 詳細については[、2015 Skype for Business Serverの Mcus](mcus.md) テーブルを参照してください。 <br/> |
|**DialogSessionIdTime** <br/> |日付型  <br/> |外部  <br/> |セッション要求の時刻。 セッションを一意に識別するために **SessionIdSeq** と併用されます。 詳細については[、2015 Skype for Business Serverの](dialogs.md) Dialogs テーブルを参照してください。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |外部  <br/> |セッションを識別するための ID 番号。 セッションを一意に識別するために **SessionIdTime** と併用されます。 詳細については[、2015 Skype for Business Serverの](dialogs.md) Dialogs テーブルを参照してください。 <br/> |
|**UserJoinTime** <br/> |日付型  <br/> | <br/> |このユーザーがこの会議サーバーに参加する時刻。  <br/> |
|**UserLeaveTime** <br/> |日付型  <br/> | <br/> |このユーザーがこの会議サーバーを離れる時刻。  <br/> |
|**ClientVerId** <br/> |int  <br/> |外部  <br/> |会議で使用するクライアント ソフトウェアのバージョン番号を指定する識別子。 詳細については[、2015 年Skype for Business Server ClientVersions](clientversions.md) テーブルを参照してください。 <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスの内部用テーブル。  <br/> このフィールドは、2015 年Skype for Business Serverされました。  <br/> |
   


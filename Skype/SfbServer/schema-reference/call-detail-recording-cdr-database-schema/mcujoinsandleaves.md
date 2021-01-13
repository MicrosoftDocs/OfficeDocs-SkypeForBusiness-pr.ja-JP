---
title: Skype for Business Server 2015 の McuJoinsAndLeaves テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: この表の各レコードには、ユーザーの参加または退出と会議サーバーの 1 つの組み合わせに関する通話の詳細が含まれている。 たとえば、ユーザーが Web 会議と音声ビデオ要素を含む会議に参加すると、そのユーザーの Web 会議参加用に 1 つのレコードが作成され、ユーザーの音声ビデオ会議参加用に別のレコードが作成されます。
ms.openlocfilehash: 8c9e6cba970e113d119ab3ce894dee8d5b4f6b28
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821497"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の McuJoinsAndLeaves テーブル
 
この表の各レコードには、ユーザーの参加または退出と会議サーバーの 1 つの組み合わせに関する通話の詳細が含まれている。 たとえば、ユーザーが Web 会議と音声ビデオ要素を含む会議に参加する場合、そのユーザーの Web 会議参加用に 1 つのレコードが作成され、ユーザーの音声ビデオ会議参加用に別のレコードが作成されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |主/プライマリ、外部  <br/> |会議インスタンスの時間。 **SessionIdSeq と組み合わせて使用し**、会議インスタンスを一意に識別します。 詳細については [、Skype for Business Server 2015](conferences.md) の電話会議の表を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主/プライマリ、外部  <br/> |会議インスタンスを識別する ID 番号。 **SessionIdTime と組み合わせて使用し**、会議インスタンスを一意に識別します。 詳細については [、Skype for Business Server 2015](conferences.md) の電話会議の表を参照してください。 <br/> |
|**UserId** <br/> |int  <br/> |主/プライマリ、外部  <br/> |このユーザーを識別する一意の番号。 詳細については [、Users の表](users.md) を参照してください。 <br/> |
|**McuUserInstance** <br/> |int  <br/> |Primary  <br/> |ユーザーが複数のコンピューターまたはデバイスで同時にログオンしている場合、McuUserInstance はユーザーとデバイスの組み合わせを一意に識別します。  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |ユーザーが PSTN から参加するかどうか。  <br/> |
|**McuId** <br/> |int  <br/> |主/プライマリ、外部  <br/> |この会議サーバーを識別する一意の番号。 詳細については [、Skype for Business Server 2015 の Mcus の表](mcus.md) を参照してください。 <br/> |
|**DialogSessionIdTime** <br/> |日付型  <br/> |外部  <br/> |セッション要求の時刻。 セッションを一意に識別するために **SessionIdSeq** と併用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |外部  <br/> |セッションを識別するための ID 番号。 セッションを一意に識別するために **SessionIdTime** と併用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。 <br/> |
|**UserJoinTime** <br/> |日付型  <br/> | <br/> |このユーザーがこの会議サーバーに参加した時刻。  <br/> |
|**UserLeaveTime** <br/> |日付型  <br/> | <br/> |このユーザーが会議サーバーを離れる時刻。  <br/> |
|**ClientVerId** <br/> |int  <br/> |外部  <br/> |会議で使用するクライアント ソフトウェアのバージョン番号を指定する識別子。 詳細については [、Skype for Business Server 2015 の ClientVersions テーブル](clientversions.md) を参照してください。 <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスの内部用テーブル。  <br/> このフィールドは、Skype for Business Server 2015 で導入されました。  <br/> |
   


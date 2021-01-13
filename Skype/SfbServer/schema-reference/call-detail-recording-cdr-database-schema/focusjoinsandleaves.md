---
title: Skype for Business Server 2015 の FocusJoinsAndLeaves テーブル
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
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: この表の各レコードには、1 つの会議の 1 人のユーザーの参加および退出情報に関する CDR 情報が含まれている。 この表では、ユーザーが会議に参加および会議から離れるごとに、各会議が 1 つのレコードで表されます。
ms.openlocfilehash: ea3af4da259fe4186a3fa3937fd2977779dafeaa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821627"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の FocusJoinsAndLeaves テーブル
 
この表の各レコードには、1 つの会議の 1 人のユーザーの参加および退出情報に関する CDR 情報が含まれている。 この表の各会議は、ユーザーが会議に参加および会議から離れるごとに 1 つのレコードで表されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |主/プライマリ、外部  <br/> |会議インスタンスの時間。 **SessionIdSeq と組み合わせて使用して**、会議インスタンスを一意に識別します。 詳細については [、Skype for Business Server 2015](conferences.md) の電話会議の表を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主/プライマリ、外部  <br/> |会議インスタンスを識別する ID 番号。 **SessionIdTime と組み合わせて使用し**、会議インスタンスを一意に識別します。 詳細については [、Skype for Business Server 2015](conferences.md) の電話会議の表を参照してください。 <br/> |
|**DialogSessionIdTime** <br/> |日付型  <br/> |主/プライマリ、外部  <br/> |セッション要求の時刻。 セッションを一意に識別するために **SessionIdSeq** と併用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |主/プライマリ、外部  <br/> |セッションを識別するための ID 番号。 セッションを一意に識別するために **SessionIdTime** と併用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。 <br/> |
|**UserId** <br/> |int  <br/> |外部  <br/> |Users テーブルから参照される、このユーザーを識別する一[意の番号。](users.md)  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||ユーザーが複数のコンピューターまたはデバイスで同時にログオンしている場合 **、UserInstance** を使用してユーザーとデバイスの組み合わせを一意に識別します。 <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |ユーザーが内部からログオンしたかどうか。  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |発表者や出席者など、会議でのこのユーザーの役割。  <br/> |
|**UserJoinTime** <br/> |日付型  <br/> | <br/> |このユーザーが会議に参加した時刻。  <br/> |
|**UserLeaveTime** <br/> |日付型  <br/> | <br/> |このユーザーが会議から離れる時刻。  <br/> |
|**ClientVerId** <br/> |int  <br/> |外部  <br/> |ユーザーのクライアント ソフトウェアのバージョン [。Skype for Business Server 2015 の ClientVersions](clientversions.md)テーブルに参照されます。  <br/> |
|**UserEndpointId** <br/> |uniqueIdentifier  <br/> ||会議で使用されるエンドポイントのグローバル一意識別子 (GUID)。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスの内部用テーブル。  <br/> このフィールドは、Skype for Business Server 2015 で導入されました。  <br/> |
   


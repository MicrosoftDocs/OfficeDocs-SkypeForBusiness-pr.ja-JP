---
title: Skype for Business Server 2015 の McuJoinsAndLeaves テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: この表の各レコードには、ユーザーの参加または退出と会議サーバーの1つの組み合わせについての通話の詳細が含まれています。 たとえば、web 会議や音声/ビデオの要素を含む会議にユーザーが参加した場合、そのユーザーの web 会議参加用に1つのレコードが作成され、ユーザーの音声/ビデオ会議の参加用に別のレコードが作成されます。
ms.openlocfilehash: d61b3c1ef1aa6fe481a4022f7bc434b523b68213
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296071"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の McuJoinsAndLeaves テーブル
 
この表の各レコードには、ユーザーの参加または退出と会議サーバーの1つの組み合わせについての通話の詳細が含まれています。 たとえば、web 会議や音声/ビデオの要素を含む会議にユーザーが参加した場合、そのユーザーの web 会議参加用に1つのレコードが作成され、ユーザーの音声/ビデオ会議の参加用に別のレコードが作成されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**セッション Id** <br/> |datetime  <br/> |プライマリ、外部  <br/> |会議インスタンスの時刻。 電話会議インスタンスを一意に識別するために**Sessionidseq**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 の会議の表](conferences.md)」を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |プライマリ、外部  <br/> |会議インスタンスを識別する ID 番号。 電話会議インスタンスを一意に識別するために**Sessionidtime**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 の会議の表](conferences.md)」を参照してください。 <br/> |
|**UserId** <br/> |int  <br/> |プライマリ、外部  <br/> |このユーザーを識別する一意の番号です。 詳細については、「ユーザー」の[表](users.md)を参照してください。 <br/> |
|**McuUserInstance** <br/> |int  <br/> |Primary  <br/> |ユーザーが複数のコンピューターまたはデバイスに一度にログオンしている場合、McuUserInstance はユーザーとデバイスの組み合わせを一意に識別します。  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |ユーザーが PSTN から参加しているかどうかを示します。  <br/> |
|**McuId** <br/> |int  <br/> |プライマリ、外部  <br/> |この会議サーバーを識別する一意の番号です。 詳細については、「 [Skype For Business Server 2015 の mcu の表](mcus.md)」を参照してください。 <br/> |
|**/セッション Id** <br/> |datetime  <br/> |外部  <br/> |セッション要求の時刻。 セッションを一意に識別するために**Sessionidseq**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**"/セッション Id"** <br/> |int  <br/> |外部  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するために**Sessionidtime**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |このユーザーがこの会議サーバーに参加する時刻です。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |このユーザーがこの会議サーバーから退席した時刻。  <br/> |
|**ClientVerId** <br/> |int  <br/> |外部  <br/> |電話会議で使用するクライアントソフトウェアのバージョン番号を指定する識別子。 詳細については、「 [Skype For Business Server 2015 の Clientversions](clientversions.md) 」の表を参照してください。 <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスで内部的に使用されます。  <br/> このフィールドは、Skype for Business Server 2015 で導入されました。  <br/> |
   


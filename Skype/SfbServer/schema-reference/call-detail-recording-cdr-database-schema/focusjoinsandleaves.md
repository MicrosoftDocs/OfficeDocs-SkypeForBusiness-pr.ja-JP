---
title: Skype for Business Server 2015 の FocusJoinsAndLeaves テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: このテーブルの各レコードには、1人のユーザーの参加に関する CDR 情報と、1人の会議に関する情報が含まれています。 各会議は、ユーザーが会議に参加して退席するたびに、1つのレコードでこのテーブルに表示されます。
ms.openlocfilehash: 4eb9f6300613fb61a7173be547aa83adf61d1026
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296211"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の FocusJoinsAndLeaves テーブル
 
このテーブルの各レコードには、1人のユーザーの参加に関する CDR 情報と、1人の会議に関する情報が含まれています。 各会議は、ユーザーが会議に参加して退席するたびに、1つのレコードでこのテーブルに表示されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**セッション Id** <br/> |datetime  <br/> |プライマリ、外部  <br/> |会議インスタンスの時刻。 電話会議インスタンスを一意に識別するために**Sessionidseq**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 の会議の表](conferences.md)」を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |プライマリ、外部  <br/> |会議インスタンスを識別する ID 番号。 電話会議インスタンスを一意に識別するために**Sessionidtime**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 の会議の表](conferences.md)」を参照してください。 <br/> |
|**/セッション Id** <br/> |datetime  <br/> |プライマリ、外部  <br/> |セッション要求の時刻。 セッションを一意に識別するために**Sessionidseq**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**"/セッション Id"** <br/> |int  <br/> |プライマリ、外部  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するために**Sessionidtime**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**UserId** <br/> |int  <br/> |外部  <br/> |[[ユーザー] テーブル](users.md)から参照されている、このユーザーを識別する一意の番号。  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||ユーザーが複数のコンピューターまたはデバイスに同時にログオンしている場合は、 **UserInstance**を使って、ユーザーとデバイスの組み合わせを一意に識別します。 <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |ユーザーが内部からログオンしているかどうか。  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |会議でのこのユーザーの役割 (発表者や出席者など)  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |このユーザーが会議に参加した時刻。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |このユーザーが会議から退席した時刻。  <br/> |
|**ClientVerId** <br/> |int  <br/> |外部  <br/> |ユーザーのクライアントソフトウェアのバージョン。 [Skype For Business Server 2015 の Clientversions テーブル](clientversions.md)に参照されています。  <br/> |
|**UserEndpointId** <br/> |長さ  <br/> ||電話会議で使用されるエンドポイントのグローバル一意識別子 (GUID)。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスで内部的に使用されます。  <br/> このフィールドは、Skype for Business Server 2015 で導入されました。  <br/> |
   


---
title: ビジネス サーバー 2015 の Skype での FocusJoinsAndLeaves テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: このテーブルの各レコードには、CDR の 1 つのユーザーの参加について、1 つの会議のままに情報が含まれています。 各会議は、ユーザーが参加し、会議を離れるたびに、次の表に、1 つのレコードで表されます。
ms.openlocfilehash: 8767b72163be4b90fb06950d3eca33bbe9d9974c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901123"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype での FocusJoinsAndLeaves テーブル
 
このテーブルの各レコードには、CDR の 1 つのユーザーの参加について、1 つの会議のままに情報が含まれています。 各会議は、ユーザーが参加し、会議を離れるたびに、次の表に、1 つのレコードで表されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |プライマリ サーバーで、外部  <br/> |会議インスタンスの時間です。 会議のインスタンスを一意に識別するのには**SessionIdSeq**と組み合わせてを使用します。 [ビジネス サーバー 2015 の Skype での会議のテーブル](conferences.md)の詳細についてを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |会議のインスタンスを識別する ID 番号。 会議のインスタンスを一意に識別するのには**SessionIdTime**と組み合わせてを使用します。 [ビジネス サーバー 2015 の Skype での会議のテーブル](conferences.md)の詳細についてを参照してください。 <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |プライマリ サーバーで、外部  <br/> |セッションの要求の時間です。 セッションを一意に識別するのには**SessionIdSeq**と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するのには**SessionIdTime**と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**ユーザー Id** <br/> |int  <br/> |外部  <br/> |[ユーザー テーブル](users.md)から参照されている、このユーザーを識別する一意の番号です。  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||同時複数のコンピューターまたはデバイスにユーザーがログオン、ユーザーとデバイスの組み合わせを一意に識別するのには**UserInstance**が使用されます。 <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |ユーザー ログオンするか内部からか。  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |など、発表者または出席者の会議内で、このユーザーのロールです。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |このユーザーが会議に参加する時間です。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |このユーザーが会議のままにします。  <br/> |
|**ClientVerId** <br/> |int  <br/> |外部  <br/> |[ビジネス サーバー 2015 の Skype での ClientVersions テーブル](clientversions.md)が参照されているユーザーのクライアント ソフトウェアのバージョンです。  <br/> |
|**UserEndpointId** <br/> |一意識別子  <br/> ||会議で使用されているエンドポイントのグローバル一意識別子 (GUID)。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LastModifiedTime** <br/> |日付時刻  <br/> ||監視サービスによって内部で使用します。  <br/> このフィールドは、ビジネス サーバー 2015 の Skype で導入されました。  <br/> |
   


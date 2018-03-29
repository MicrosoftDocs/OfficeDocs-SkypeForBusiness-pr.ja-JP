---
title: ビジネス サーバー 2015 の Skype での McuJoinsAndLeaves テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: このテーブルの各レコードには、呼び出しの詳細については、ユーザーまたは結合と会議サーバーの 1 つの組み合わせが含まれています。 などのユーザーは、web 会議、オーディオとビデオの要素を含む会議を結合する場合、そのユーザーの web 会議の結合の 1 つのレコードが作成され、ユーザーのオーディオ/ビデオ会議の結合の別のレコードが作成されます。
ms.openlocfilehash: 153da84534dae4a9ad2287c355b93a4477003e6f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype での McuJoinsAndLeaves テーブル
 
このテーブルの各レコードには、呼び出しの詳細については、ユーザーまたは結合と会議サーバーの 1 つの組み合わせが含まれています。 などのユーザーは、web 会議、オーディオとビデオの要素を含む会議を結合する場合、そのユーザーの web 会議の結合の 1 つのレコードが作成され、ユーザーのオーディオ/ビデオ会議の結合の別のレコードが作成されます。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |プライマリ サーバーで、外部  <br/> |会議インスタンスの時間です。 会議のインスタンスを一意に識別するのには**SessionIdSeq**と組み合わせてを使用します。 [ビジネス サーバー 2015 の Skype での会議のテーブル](conferences.md)の詳細についてを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |会議のインスタンスを識別する ID 番号。 会議のインスタンスを一意に識別するのには**SessionIdTime**と組み合わせてを使用します。 [ビジネス サーバー 2015 の Skype での会議のテーブル](conferences.md)の詳細についてを参照してください。 <br/> |
|**ユーザー Id** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |このユーザーを識別する一意の番号です。 詳細については[「ユーザー」テーブル](users.md)を参照してください。 <br/> |
|**McuUserInstance** <br/> |int  <br/> |Primary  <br/> |ユーザー ログオン複数のコンピューターまたはデバイスに一度に、McuUserInstance は、ユーザーとデバイスの組み合わせを一意に識別します。  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |かどうか、ユーザーは、PSTN から参加するか。  <br/> |
|**McuId** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |この会議サーバーを識別する一意の番号です。 詳細については、 [Skype のビジネス サーバー 2015 の Mcu のテーブル](mcus.md)を参照してください。 <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |外部  <br/> |セッションの要求の時間です。 セッションを一意に識別するのには**SessionIdSeq**と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |外部  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するのには**SessionIdTime**と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |このユーザーがこの会議サーバーに参加する時間です。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |このユーザーがこの会議サーバーのままにします。  <br/> |
|**ClientVerId** <br/> |int  <br/> |外部  <br/> |クライアント ソフトウェアのバージョン番号を指定する識別子は、会議に使用します。 詳細については、 [Skype のビジネス サーバー 2015 で ClientVersions テーブル](clientversions.md)を参照してください。 <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LastModifiedTime** <br/> |日付時刻  <br/> ||監視サービスによって内部で使用します。  <br/> このフィールドは、ビジネス サーバー 2015 の Skype で導入されました。  <br/> |
   


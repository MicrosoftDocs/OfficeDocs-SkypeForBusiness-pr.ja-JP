---
title: ビジネス サーバー 2015 の Skype での ConferenceMessageCount テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: このテーブルの各レコードは、1 つの IM 会議に 1 人のユーザーを表し、そのユーザーから送信されたメッセージの数が含まれています。 各会議は、このテーブル内の複数のレコードで表されます。ユーザーごとに 1 つのレコードです。
ms.openlocfilehash: 60fa79de17c2db14116bd0ffe211e25a61ec9136
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874358"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype での ConferenceMessageCount テーブル
 
このテーブルの各レコードは、1 つの IM 会議に 1 人のユーザーを表し、そのユーザーから送信されたメッセージの数が含まれています。 各会議は、このテーブル内の複数のレコードで表されます。ユーザーごとに 1 つのレコードです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |プライマリ サーバーで、外部  <br/> |会議インスタンスの時間です。 会議のインスタンスを一意に識別するのには**SessionIdSeq**と組み合わせてを使用します。 [ビジネス サーバー 2015 の Skype での会議のテーブル](conferences.md)の詳細についてを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |会議のインスタンスを識別する ID 番号。 会議のインスタンスを一意に識別するのには**SessionIdTime**と組み合わせてを使用します。 [ビジネス サーバー 2015 の Skype での会議のテーブル](conferences.md)の詳細についてを参照してください。 <br/> |
|**ユーザー Id** <br/> |int  <br/> |外部  <br/> |[ユーザー テーブル](users.md)から参照されている、このユーザーを識別する一意の番号です。  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |この会議中にこのユーザーによって送信されたメッセージの数です。  <br/> |
   


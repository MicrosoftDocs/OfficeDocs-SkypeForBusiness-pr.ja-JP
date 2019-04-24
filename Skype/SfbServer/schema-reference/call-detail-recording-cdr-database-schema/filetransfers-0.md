---
title: ビジネス サーバー 2015 の Skype での FileTransfers テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: 各レコードは、1 つのファイル転送セッションを表します。
ms.openlocfilehash: fe95db4e023dfb25158cf0bdf1b07f147abe6bd6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213103"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype での FileTransfers テーブル
 
各レコードは、1 つのファイル転送セッションを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |プライマリ サーバーで、外部  <br/> |セッションの要求の時間です。 セッションを一意に識別するのには**SessionIdSeq**と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するのには**SessionIdTime**と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**ファイル名** <br/> |nvarchar(256)  <br/> ||ファイルの名前です。  <br/> |
|**FileIdentity** <br/> |一意識別子  <br/> ||同じ名前のファイルに関連するファイル転送の間で区別するために一意の識別子です。  <br/> |
|**クッキー** <br/> |nvarchar (128)  <br/> |Primary  <br/> |この 1 つに関連付けられたすべてのフォロー アップ メッセージを識別する場合に使用されます。  <br/> |
|**受け入れる** <br/> |bit  <br/> ||真または NULL にすることができます。 TRUE の場合、[元に戻すし、[キャンセル] が NULL になります。  <br/> |
|**元に戻す** <br/> |bit  <br/> ||真または NULL にすることができます。 TRUE の場合、[受信を許可し、[キャンセル] NULL になります。  <br/> |
|**キャンセル** <br/> |bit  <br/> ||真または NULL にすることができます。 TRUE の場合、[承認および却下 NULL になります。  <br/> |
|**LastModifiedTime** <br/> |日付時刻  <br/> ||監視サービスによって内部で使用します。  <br/> このフィールドは、ビジネス サーバー 2015 の Skype で導入されました。  <br/> |
   


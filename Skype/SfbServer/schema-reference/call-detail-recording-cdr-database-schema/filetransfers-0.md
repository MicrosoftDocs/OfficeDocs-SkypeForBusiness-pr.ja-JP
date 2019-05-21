---
title: ファイル転送テーブル (Skype for Business Server 2015)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: 各レコードは、1つのファイル転送セッションを表します。
ms.openlocfilehash: ada437eacfa9a532a4875c3ce1837ccd9d8aed17
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296253"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>ファイル転送テーブル (Skype for Business Server 2015)
 
各レコードは、1つのファイル転送セッションを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**セッション Id** <br/> |datetime  <br/> |プライマリ、外部  <br/> |セッション要求の時刻。 セッションを一意に識別するために**Sessionidseq**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |プライマリ、外部  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するために**Sessionidtime**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**ファイル名** <br/> |nvarchar(256)  <br/> ||ファイルの名前。  <br/> |
|**FileIdentity** <br/> |長さ  <br/> ||同じファイル名を含むファイル転送を区別する一意の識別子。  <br/> |
|**クッキー** <br/> |nvarchar(128  <br/> |Primary  <br/> |すべてのフォローアップメッセージをこのメールに関連付けられているものとして識別するために使用されます。  <br/> |
|**受諾** <br/> |bit  <br/> ||TRUE または NULL を指定できます。 TRUE の場合は、拒否とキャンセルは NULL になります。  <br/> |
|**拒否** <br/> |bit  <br/> ||TRUE または NULL を指定できます。 TRUE の場合は、Accept と Cancel は NULL になります。  <br/> |
|**キャンセル** <br/> |bit  <br/> ||TRUE または NULL を指定できます。 TRUE の場合は、Accept と Reject は NULL になります。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスで内部的に使用されます。  <br/> このフィールドは、Skype for Business Server 2015 で導入されました。  <br/> |
   


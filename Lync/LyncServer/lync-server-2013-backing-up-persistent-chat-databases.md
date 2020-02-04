---
title: 'Lync Server 2013: 常設チャットデータベースのバックアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f186552b9e0d5c78d0f40416cd92e41d5705e93a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a>Lync Server 2013 での常設チャットデータベースのバックアップ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-17_

常設チャットルームのコンテンツは、常設チャットデータベース (行う) に保存されます。 コンプライアンス データは非常に重要なビジネス データであり、定期的なバックアップが必要です。 常設チャットデータベースには、チャットルームのコンテンツに加えて、プリンシパルに関する情報 (ユーザー、ユーザーグループなど) と、チャットルームやチャットルームに必要なロールとアクセスも保存されます。

常設チャットデータをバックアップするには、2つの方法があります。

  - SQL Server バックアップ

  - この`Export-CsPersistentChatData`コマンドレットは永続的なチャットデータをファイルとしてエクスポートします。

SQL Server のバックアップを使用して作成されたデータには、より多くのディスク領域が必要です`Export-CsPersistentChatData`。これは、によって作成された場合よりも20倍ですが、sql Server バックアップは管理者が理解している手順である可能性が高くなります。

</div>

<span> </span>

</div>

</div>

</div>


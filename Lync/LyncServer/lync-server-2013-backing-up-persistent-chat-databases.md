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
ms.openlocfilehash: 9dc1f448c248f80bfcc636c900b6601fda4aa200
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a>Lync Server 2013 での常設チャットデータベースのバックアップ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-17_

常設チャットルームのコンテンツは、常設チャットデータベース (Mgc) に保存されます。 これは、定期的にバックアップする必要があるビジネスクリティカルなデータです。 常設チャットデータベースには、チャットルームのコンテンツに加えて、プリンシパル (ユーザーやユーザーグループなど) に関する情報と、チャットルームやチャットルームに対して必要な役割とアクセスも格納されます。

常設チャットデータをバックアップするには、2つの方法があります。

  - SQL Server のバックアップ

  - `Export-CsPersistentChatData`コマンドレット。常設チャットデータをファイルとしてエクスポートします。

SQL Server のバックアップを使用して作成されたデータには、より多くのディスク領域が必要に`Export-CsPersistentChatData`なります。これは、によって作成されるよりも20倍になることもありますが、SQL server のバックアップは、管理者が熟知している手順になる可能性が高くなります。

</div>

<span> </span>

</div>

</div>

</div>


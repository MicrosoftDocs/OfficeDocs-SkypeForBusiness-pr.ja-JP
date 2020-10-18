---
title: 'Lync Server 2013: 常設チャットデータの復元'
description: 'Lync Server 2013: 常設チャットデータの復元。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring Persistent Chat data
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945649(v=OCS.15)
ms:contentKeyID: 51541516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c75683e151daaadab8374ed5b41886da9a3aea3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575519"
---
# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a>Lync Server 2013 での常設チャットデータの復元

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-18_

常設チャットルームのコンテンツは、常設チャットデータベース (mgc) に保存されます。 これは、定期的にバックアップする必要があるビジネスクリティカルなデータです。 チャットルームのコンテンツに加えて、プリンシパル (ユーザーやグループなど)、およびチャットルームやチャットルームのコンテンツに対して必要な役割とアクセスも常設チャットデータベースに保存されます。

常設チャットデータの復元方法は、バックアップに使用した方法によって異なります。

  - SQL Server のバックアップ手順を使用した場合は、SQL Server の復元手順を使用する必要があります。

  - **Export-cspersistentchatdata**コマンドレットを使用して常設チャットデータをバックアップした場合は、 **export-cspersistentchatdata**コマンドレットを使用してデータを復元する必要があります。

</div>

<span> </span>

</div>

</div>

</div>


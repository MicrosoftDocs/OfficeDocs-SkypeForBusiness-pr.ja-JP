---
title: 'Lync Server 2013: 常設チャットデータを復元する'
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
ms.openlocfilehash: 5734296a9b3463740b28e6ead33cc64234640432
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a>Lync Server 2013 での常設チャットデータの復元

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-18_

常設チャットルームのコンテンツは、常設チャットデータベース (行う) に保存されます。 コンプライアンス データは非常に重要なビジネス データであり、定期的なバックアップが必要です。 チャットルームのコンテンツに加えて、プリンシパル (ユーザーやグループなど)、およびチャットルームやチャットルームのコンテンツに対して必要なロールとアクセスも、常設チャットデータベースに保存されます。

常設チャットのデータを復元する方法は、バックアップに使用した方法によって異なります。

  - SQL Server バックアップ手順を使用した場合は、SQL Server 復元手順を使用する必要があります。

  - **CsPersistentChatData**コマンドレットを使用して常設チャットデータをバックアップする場合は、 **CsPersistentChatData**コマンドレットを使用してデータを復元する必要があります。

</div>

<span> </span>

</div>

</div>

</div>


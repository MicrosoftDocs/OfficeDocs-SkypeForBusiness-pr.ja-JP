---
title: 'Lync Server 2013: ルームの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3521e533dee1ff995fae417b8a7f29a75a77ac63
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a>Lync Server 2013 での会議室の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-06_

常設チャットルームの構成は、通常、Windows PowerShell コマンドラインインターフェイスを使用して、ユーザーまたは他の中央のチームによって処理されます。通常、管理者はチャットルームを管理しません。 ただし、チャットルームを作成して管理する必要がある場合は、Windows PowerShell コマンドラインインターフェイスを使用するか、自分をメンバーとしてチャットルームに追加して、Lync 2013 クライアントを使用することができます。

Windows PowerShell コマンドラインインターフェイスを使用したチャットルームの構成の詳細については、「 [Windows powershell コマンドレットを使用して常設チャットサーバーを構成](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)する」の「Room Management」を参照してください。

<div>

## <a name="managing-data-in-chat-rooms"></a>チャット ルームのデータの管理

常設チャットサーバーを使用すると、ユーザーは永続的なチャットルームにメッセージを投稿して共同作業を行うことができます。 データはサーバーに保持され、チャット ルームのメンバーは、履歴データなどのデータにアクセスできます。 ただし、次に示すように、アクセスできる永続的なデータは、ユーザーの役割によって異なります。

  - 管理者は、データベースが大きくなりすぎないようにチャット ルームから古いコンテンツ (たとえば、特定の日付より前に投稿されたコンテンツ) を削除できます。また、管理者は、特定のチャット ルームにとって不適切と判断されるメッセージを削除または置換することもできます。

  - エンドユーザー (メッセージの作成者を含む) は、チャット ルームのコンテンツを削除できません。

  - チャット ルームの管理者は、チャット ルームを無効にできますが、チャット ルームを削除することはできません。チャット ルームを削除できるのは管理者のみです。

メッセージを削除しても、アクションを元に戻すことはできません。 ただし、バックアップがある場合は、削除されたメッセージを復元できます。 常設チャットコンプライアンスサーバーが有効になっている場合、古いメッセージはコンプライアンスデータベースに保持されます。

<div>


> [!NOTE]  
> このチャットルームのデータ使用法は、管理者の役割が関与している場合を除き、Lync Server 2013、常設チャットサーバー API アプリケーションに適用されます。 常設チャットサーバー API を使用して、管理者の操作を実行することはできません。 これらの操作は、Lync Server 管理シェルで実行する必要があります。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


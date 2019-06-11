---
title: 'Lync Server 2013: ルームを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d08b7cb0146f96b151af021a63ef97a485a0a9dc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a>Lync Server 2013 でルームを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-06_

常設チャットルームの構成は、一般に、Windows PowerShell コマンドラインインターフェイスを使用して、ユーザーまたは他の中央チームによって処理されます。通常、管理者はチャットルームを管理しません。 ただし、チャットルームを作成して管理する必要がある場合は、Windows PowerShell コマンドラインインターフェイスを使用するか、自分をメンバーとしてチャットルームに追加して、Lync 2013 クライアントを使うことができます。

Windows PowerShell コマンドラインインターフェイスを使用してチャットルームを構成する方法について詳しくは、「 [Windows powershell コマンドレットを使用して常設チャットサーバーを構成](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)する」の「会議室の管理」をご覧ください。

<div>

## <a name="managing-data-in-chat-rooms"></a>チャットルームでデータを管理する

常設チャットサーバーを使うと、ユーザーは永続的なチャットルームにメッセージを投稿して共同作業を行うことができます。 データはサーバー上に保持され、会議室のメンバーは履歴データなどのデータにアクセスできます。 ただし、異なるロールを持つユーザーは、次の一覧に示すように、保持されているデータに異なるアクセス権を持っています。

  - 管理者は、データベースが大きくなりすぎないようにチャット ルームから古いコンテンツ (たとえば、特定の日付より前に投稿されたコンテンツ) を削除できます。 また、特定のチャットルームでは不適切と見なされるメッセージを削除したり、置き換えたりすることができます。

  - エンド ユーザーは、メッセージの作成者を含めて、チャット ルームからコンテンツを削除できません。

  - チャットルーム管理者は、ルームを無効にすることはできますが、ルームを削除することはできません。 チャットルームを作成した後に削除できるのは管理者だけです。

メッセージが削除された場合、操作を元に戻すことはできません。 ただし、バックアップがある場合は、削除されたメッセージを復元することができます。 常設チャットのコンプライアンスサーバーが有効になっている場合、古いメッセージはコンプライアンスデータベースに保存されます。

<div>


> [!NOTE]  
> このチャットルームのデータ使用は、管理者の役割が関係する場合を除き、Lync Server 2013、常設 Chat Server API アプリケーションに適用されます。 常設チャットサーバー API を使用して、管理者の操作を実行することはできません。 これらの操作は、Lync Server 管理シェルで実行する必要があります。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


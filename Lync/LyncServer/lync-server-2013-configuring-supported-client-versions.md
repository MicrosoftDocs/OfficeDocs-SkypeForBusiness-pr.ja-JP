---
title: 'Lync Server 2013: サポートされているクライアントバージョンの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34d74de1ae5e25c372e51783d8321ebc8699eaef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a>Lync Server 2013 でサポートされているクライアントバージョンを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-12-14_

Lync Server 2013 では、クライアントバージョンポリシーを設定して、環境でサポートされているクライアントのバージョンを指定することができます。 また、グローバルクライアントバージョン構成を使用して、バージョンポリシーが定義されていないクライアントの既定のアクションを指定することもできます。そのため、明示的にサポートまたは制限されません。

クライアントバージョンポリシーを使用してクライアント更新プログラムを管理することもできます。 クライアントバージョンポリシーを設定し、オプションの**Allow and upgrade** and **upgrade**を使用すると、クライアントは更新されたソフトウェアを Windows Server Update サービス (このサービスを使用している場合) または Microsoft Update から受け取ります。

<div>

## <a name="client-version-policy-settings"></a>クライアントバージョンポリシーの設定

既定のクライアントバージョンポリシーでは、すべてのクライアントが Lync を実行する必要があります。 環境内のクライアントが以前のバージョンの Communicator を実行している場合は、Lync Server 2013 に接続するときにクライアントとデバイスが予期せずブロックまたは更新されないように、クライアントバージョンルールを再構成する必要がある場合があります。 既定のルールを変更するか、[クライアントバージョンポリシー] の一覧で上位のルールを追加して既定のルールを上書きすることができます。 また、累積的な更新プログラム (Cu) がリリースされたため、最新の更新プログラムが必要になるようにクライアントバージョンポリシーを構成する必要があります。 詳細については、「操作」のドキュメントの「 [Lync Server 2013 へのログオンに使用できるクライアントアプリケーションを指定](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md)する」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>


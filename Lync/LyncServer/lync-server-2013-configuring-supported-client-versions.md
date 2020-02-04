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
ms.openlocfilehash: 9a262cab2145013d83cdae573d98b5db17e0e890
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a>Lync Server 2013 でサポートされているクライアントバージョンを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-12-14_

Lync Server 2013 では、環境でサポートされているクライアントのバージョンを指定するように、クライアントのバージョンポリシーを設定できます。 さらに、グローバルクライアントバージョンの構成を使用して、バージョンポリシーが定義されていないクライアントに対して既定のアクションを指定することもできます。そのため、明示的にサポートまたは制限されることはありません。

クライアントのバージョンポリシーを使って、クライアントの更新を管理することもできます。 クライアントのバージョンポリシーを設定して、[ **Allow and upgrade** and upgrade **and upgrade]** オプションを使うと、クライアントは更新されたソフトウェアを Windows Server Update サービス (このサービスを使用している場合) または Microsoft Update から受け取ります。

<div>

## <a name="client-version-policy-settings"></a>クライアントバージョンのポリシー設定

既定のクライアントバージョンポリシーでは、すべてのクライアントが Lync を実行している必要があります。 環境内のクライアントで以前のバージョンの Communicator を実行している場合は、Lync Server 2013 に接続しているときにクライアントとデバイスが予期せずにブロックまたは更新されないように、クライアントのバージョンの規則を再設定する必要がある場合があります。 既定のルールを変更することも、[クライアントのバージョンポリシー] リストでより高いルールを追加して、既定のルールを上書きすることもできます。 さらに、累積更新プログラム (CUs) がリリースされるため、最新の更新プログラムを要求するようにクライアントのバージョンポリシーを構成する必要があります。 詳細については、「運用ドキュメントの[Lync Server 2013 へのログオンに使用できるクライアントアプリケーションの指定](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>


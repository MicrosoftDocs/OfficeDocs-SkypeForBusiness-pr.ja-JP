---
title: 'Lync Server 2013: 事前に証明書を要求する (オプション)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 691efbbc1adad91ce63cfa0bca5fba6f11b5aea2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a>Lync Server 2013 の証明書を事前に要求する (オプション)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

各 Enterprise Edition フロントエンドサーバー、Standard Edition サーバー、ディレクター、エッジサーバー、およびスタンドアロン仲介サーバーを含む、Lync Server 2013 を実行しているすべての内部サーバーに対して証明書が必要です。 内部サーバーには内部のエンタープライズ証明機関 (CA) をお勧めしますが、パブリック CA を使用することもできます。 証明書の要件およびパブリック CA の使用に関する詳細については、「計画」のドキュメントの「 [Lync Server 2013 の内部サーバーの証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md)」を参照してください。

Lync Server 2013 セットアップには、証明書ウィザードが含まれています。これにより、展開時に証明書の要求、割り当て、およびインストールのタスクを容易に実行できます。 サーバーをインストールする前に証明書を要求する必要がある場合 (たとえば、実際にサーバーを展開する時間を節約するため)、Lync Server 2013 管理ツールがインストールされているコンピューター、または証明書要求を使用して証明書を要求することができます。証明書がエクスポート可能で、必要なサブジェクトの別名がすべて含まれている場合に限り、組織内で定義されている手順。 事前に証明書を要求することはオプションです。 事前に要求しない場合は、証明書を必要とする各サーバーのセットアップの一部として要求する必要があります。

この展開ドキュメントでは、証明書ウィザードを使用して、セットアッププロセスの一環として証明書を要求する手順について説明します。「 [lync server 2013 のサーバーの証明](lync-server-2013-configure-certificates-for-servers.md)書の構成」で説明されているように、 [lync Server 2013 でディレクターの証明書を構成](lync-server-2013-configure-certificates-for-the-director.md)し、この展開のドキュメントの「 [lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) 」のセクションに 事前に証明書を要求する場合は、これらのセクションの証明書の展開手順を、展開時に要求するのではなく、証明書のインポートと割り当てに応じて変更する必要があります。

<div>


> [!NOTE]  
> Lync Server 2013 には、Windows Vista、Windows Server&nbsp;2008、windows server&nbsp;2008&nbsp;R2、Windows 7 オペレーティングシステム、および Lync Phone Edition を実行しているクライアントからの接続用の SHA-256 証明書のサポートが含まれています。 SHA-256 を使用する外部アクセスをサポートするには、SHA-256 を使用するパブリック CA が外部証明書を発行する必要があります。



</div>

</div>

<span> </span>

</div>

</div>

</div>


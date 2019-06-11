---
title: 'Lync Server 2013: 事前の証明書の要求 (オプション)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6b376a2c1652dcaf255e39f6d112568b7c3bf31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a>Lync Server 2013 の事前の証明書の要求 (オプション)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

この証明書は、Lync Server 2013 を実行しているすべての内部サーバー、Standard Edition server、監督、エッジサーバー、スタンドアロン仲介サーバーなど、すべての内部サーバーに必要です。 内部サーバーでは社内のエンタープライズ証明機関 (CA) を使うことをお勧めしますが、パブリック CA を使用することもできます。 証明書の要件とパブリック CA の使用について詳しくは、「計画ドキュメントの「 [Lync Server 2013 の内部サーバーの証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md)」をご覧ください。

Lync Server 2013 セットアップには証明書ウィザードが含まれています。これにより、展開中に証明書の要求、割り当て、インストールのタスクを簡単に行うことができます。 サーバーをインストールする前に証明書を要求する場合 (たとえば、サーバーの実際の展開中に時間を節約するため)、Lync Server 2013 管理ツールがインストールされているコンピューター、または証明書の要求を使用して、証明書を要求することができます。組織で定義された手順。証明書がエクスポート可能であり、必要な件名の代替名がすべて含まれていることを確認します。 事前に証明書を要求することは任意です。 事前に要求していない場合は、証明書が必要な各サーバーのセットアップの一部として要求する必要があります。

この展開ドキュメントでは、「 [Lync Server 2013 のサーバー用の証明書を構成](lync-server-2013-configure-certificates-for-servers.md)する」に記載されているように、セットアッププロセスの一環として証明書ウィザードを使用して証明書を要求する手順について説明します。 [Lync Server 2013 のディレクター](lync-server-2013-configure-certificates-for-the-director.md)、およびこの展開ドキュメントの[lync server 2013 セクションに、仲介サーバー用のファイルをインストール](lync-server-2013-install-the-files-for-mediation-server.md)します。 事前に証明書を要求する場合は、展開の時点で証明書を要求する代わりに、証明書のインポートと割り当てに応じて、これらのセクションで証明書の展開手順を変更する必要があります。

<div>


> [!NOTE]  
> Lync Server 2013 には、Windows Vista、Windows Server&nbsp;2008、windows server&nbsp;2008&nbsp;R2、Windows 7 オペレーティングシステム、lync Phone Edition を実行しているクライアントからの接続のための SHA-256 証明書がサポートされています。 SHA-256 を使って外部アクセスをサポートするために、外部証明書は SHA-256 を使ってパブリック CA によって発行されます。



</div>

</div>

<span> </span>

</div>

</div>

</div>


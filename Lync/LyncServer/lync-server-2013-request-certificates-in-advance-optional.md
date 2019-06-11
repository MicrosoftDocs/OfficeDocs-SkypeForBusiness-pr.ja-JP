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

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a><span data-ttu-id="9606c-102">Lync Server 2013 の事前の証明書の要求 (オプション)</span><span class="sxs-lookup"><span data-stu-id="9606c-102">Request certificates in advance (optional) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9606c-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="9606c-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="9606c-104">この証明書は、Lync Server 2013 を実行しているすべての内部サーバー、Standard Edition server、監督、エッジサーバー、スタンドアロン仲介サーバーなど、すべての内部サーバーに必要です。</span><span class="sxs-lookup"><span data-stu-id="9606c-104">Certificates are required for all internal servers that are running Lync Server 2013, including each Enterprise Edition Front End Server, Standard Edition server, Director, Edge Server and stand-alone Mediation Server.</span></span> <span data-ttu-id="9606c-105">内部サーバーでは社内のエンタープライズ証明機関 (CA) を使うことをお勧めしますが、パブリック CA を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9606c-105">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="9606c-106">証明書の要件とパブリック CA の使用について詳しくは、「計画ドキュメントの「 [Lync Server 2013 の内部サーバーの証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9606c-106">For details about certificate requirements and about the use of a public CA, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="9606c-107">Lync Server 2013 セットアップには証明書ウィザードが含まれています。これにより、展開中に証明書の要求、割り当て、インストールのタスクを簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9606c-107">Lync Server 2013 setup includes the Certificate Wizard, which facilitates the tasks of requesting, assigning, and installing certificates during deployment.</span></span> <span data-ttu-id="9606c-108">サーバーをインストールする前に証明書を要求する場合 (たとえば、サーバーの実際の展開中に時間を節約するため)、Lync Server 2013 管理ツールがインストールされているコンピューター、または証明書の要求を使用して、証明書を要求することができます。組織で定義された手順。証明書がエクスポート可能であり、必要な件名の代替名がすべて含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9606c-108">If you want to request certificates prior to installing servers (for instance, to save time during actual deployment of servers), you can do so by using a computer on which the Lync Server 2013 administrative tools are installed or by using a certificate request procedure defined in your organization, as long as you make sure that the certificates are exportable and contain all the required subject alternative names.</span></span> <span data-ttu-id="9606c-109">事前に証明書を要求することは任意です。</span><span class="sxs-lookup"><span data-stu-id="9606c-109">Requesting certificates in advance is optional.</span></span> <span data-ttu-id="9606c-110">事前に要求していない場合は、証明書が必要な各サーバーのセットアップの一部として要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9606c-110">If you do not request them in advance, you must request them as part of the setup of each server that requires a certificate.</span></span>

<span data-ttu-id="9606c-111">この展開ドキュメントでは、「 [Lync Server 2013 のサーバー用の証明書を構成](lync-server-2013-configure-certificates-for-servers.md)する」に記載されているように、セットアッププロセスの一環として証明書ウィザードを使用して証明書を要求する手順について説明します。 [Lync Server 2013 のディレクター](lync-server-2013-configure-certificates-for-the-director.md)、およびこの展開ドキュメントの[lync server 2013 セクションに、仲介サーバー用のファイルをインストール](lync-server-2013-install-the-files-for-mediation-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="9606c-111">This Deployment documentation provides procedures for using the Certificate Wizard to request certificates as part of the setup process, as described in the [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md), and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) sections of this Deployment documentation.</span></span> <span data-ttu-id="9606c-112">事前に証明書を要求する場合は、展開の時点で証明書を要求する代わりに、証明書のインポートと割り当てに応じて、これらのセクションで証明書の展開手順を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9606c-112">If you request certificates in advance, you must modify the certificate deployment procedures in those sections as appropriate to importing and assigning the certificates instead of requesting them at the time of deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9606c-113">Lync Server 2013 には、Windows Vista、Windows Server&nbsp;2008、windows server&nbsp;2008&nbsp;R2、Windows 7 オペレーティングシステム、lync Phone Edition を実行しているクライアントからの接続のための SHA-256 証明書がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9606c-113">Lync Server 2013 includes support for SHA-256 certificates for connections from clients running the Windows Vista, Windows Server&nbsp;2008, Windows Server&nbsp;2008&nbsp;R2, and Windows 7 operating systems, and Lync Phone Edition.</span></span> <span data-ttu-id="9606c-114">SHA-256 を使って外部アクセスをサポートするために、外部証明書は SHA-256 を使ってパブリック CA によって発行されます。</span><span class="sxs-lookup"><span data-stu-id="9606c-114">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


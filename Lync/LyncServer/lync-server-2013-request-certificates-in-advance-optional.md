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
ms.openlocfilehash: 7c2df4d328154133df91503877a22234e6a05aa3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a><span data-ttu-id="84a4b-102">Lync Server 2013 の証明書を事前に要求する (オプション)</span><span class="sxs-lookup"><span data-stu-id="84a4b-102">Request certificates in advance (optional) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84a4b-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="84a4b-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="84a4b-104">各 Enterprise Edition フロントエンドサーバー、Standard Edition サーバー、ディレクター、エッジサーバー、およびスタンドアロン仲介サーバーを含む、Lync Server 2013 を実行しているすべての内部サーバーに対して証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="84a4b-104">Certificates are required for all internal servers that are running Lync Server 2013, including each Enterprise Edition Front End Server, Standard Edition server, Director, Edge Server and stand-alone Mediation Server.</span></span> <span data-ttu-id="84a4b-105">内部サーバーには内部のエンタープライズ証明機関 (CA) をお勧めしますが、パブリック CA を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="84a4b-105">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="84a4b-106">証明書の要件およびパブリック CA の使用に関する詳細については、「計画」のドキュメントの「 [Lync Server 2013 の内部サーバーの証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84a4b-106">For details about certificate requirements and about the use of a public CA, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="84a4b-107">Lync Server 2013 セットアップには、証明書ウィザードが含まれています。これにより、展開時に証明書の要求、割り当て、およびインストールのタスクを容易に実行できます。</span><span class="sxs-lookup"><span data-stu-id="84a4b-107">Lync Server 2013 setup includes the Certificate Wizard, which facilitates the tasks of requesting, assigning, and installing certificates during deployment.</span></span> <span data-ttu-id="84a4b-108">サーバーをインストールする前に証明書を要求する必要がある場合 (たとえば、実際にサーバーを展開する時間を節約するため)、Lync Server 2013 管理ツールがインストールされているコンピューター、または証明書要求を使用して証明書を要求することができます。証明書がエクスポート可能で、必要なサブジェクトの別名がすべて含まれている場合に限り、組織内で定義されている手順。</span><span class="sxs-lookup"><span data-stu-id="84a4b-108">If you want to request certificates prior to installing servers (for instance, to save time during actual deployment of servers), you can do so by using a computer on which the Lync Server 2013 administrative tools are installed or by using a certificate request procedure defined in your organization, as long as you make sure that the certificates are exportable and contain all the required subject alternative names.</span></span> <span data-ttu-id="84a4b-109">事前に証明書を要求することはオプションです。</span><span class="sxs-lookup"><span data-stu-id="84a4b-109">Requesting certificates in advance is optional.</span></span> <span data-ttu-id="84a4b-110">事前に要求しない場合は、証明書を必要とする各サーバーのセットアップの一部として要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84a4b-110">If you do not request them in advance, you must request them as part of the setup of each server that requires a certificate.</span></span>

<span data-ttu-id="84a4b-111">この展開ドキュメントでは、証明書ウィザードを使用して、セットアッププロセスの一環として証明書を要求する手順について説明します。「 [lync server 2013 のサーバーの証明](lync-server-2013-configure-certificates-for-servers.md)書の構成」で説明されているように、 [lync Server 2013 でディレクターの証明書を構成](lync-server-2013-configure-certificates-for-the-director.md)し、この展開のドキュメントの「 [lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) 」のセクションに</span><span class="sxs-lookup"><span data-stu-id="84a4b-111">This Deployment documentation provides procedures for using the Certificate Wizard to request certificates as part of the setup process, as described in the [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md), and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) sections of this Deployment documentation.</span></span> <span data-ttu-id="84a4b-112">事前に証明書を要求する場合は、これらのセクションの証明書の展開手順を、展開時に要求するのではなく、証明書のインポートと割り当てに応じて変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84a4b-112">If you request certificates in advance, you must modify the certificate deployment procedures in those sections as appropriate to importing and assigning the certificates instead of requesting them at the time of deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="84a4b-113">Lync Server 2013 には、Windows Vista、Windows Server&nbsp;2008、windows server&nbsp;2008&nbsp;R2、Windows 7 オペレーティングシステム、および Lync Phone Edition を実行しているクライアントからの接続用の SHA-256 証明書のサポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="84a4b-113">Lync Server 2013 includes support for SHA-256 certificates for connections from clients running the Windows Vista, Windows Server&nbsp;2008, Windows Server&nbsp;2008&nbsp;R2, and Windows 7 operating systems, and Lync Phone Edition.</span></span> <span data-ttu-id="84a4b-114">SHA-256 を使用する外部アクセスをサポートするには、SHA-256 を使用するパブリック CA が外部証明書を発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84a4b-114">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


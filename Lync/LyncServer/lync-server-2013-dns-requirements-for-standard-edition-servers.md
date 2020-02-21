---
title: 'Lync Server 2013: Standard Edition サーバーの DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Standard Edition servers
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425900(v=OCS.15)
ms:contentKeyID: 48183920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 903243e846fee2a0b874a50fb529b533c1658fc2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="6209e-102">Lync Server 2013 の Standard Edition サーバーの DNS 要件</span><span class="sxs-lookup"><span data-stu-id="6209e-102">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6209e-103">_**トピックの最終更新日:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="6209e-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="6209e-104">ここでは、Standard Edition サーバーの展開に必要なドメイン ネーム システム (DNS) レコードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6209e-104">This section describes the Domain Name System (DNS) records that are required for deployment of Standard Edition servers.</span></span>

<div>

## <a name="dns-records-for-standard-edition-servers"></a><span data-ttu-id="6209e-105">Standard Edition サーバーの DNS レコード</span><span class="sxs-lookup"><span data-stu-id="6209e-105">DNS Records for Standard Edition Servers</span></span>

<span data-ttu-id="6209e-106">次の表は、Lync Server 2013 Standard Edition サーバー展開の DNS 要件を示しています。</span><span class="sxs-lookup"><span data-stu-id="6209e-106">The following table specifies DNS requirements for Lync Server 2013 Standard Edition server deployment.</span></span>

### <a name="dns-requirements-for-a-standard-edition-server"></a><span data-ttu-id="6209e-107">Standard Edition サーバーの DNS 要件</span><span class="sxs-lookup"><span data-stu-id="6209e-107">DNS Requirements for a Standard Edition Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6209e-108">展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="6209e-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="6209e-109">DNS 要件</span><span class="sxs-lookup"><span data-stu-id="6209e-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6209e-110">Standard Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="6209e-110">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="6209e-111">サーバーの完全修飾ドメイン名 (FQDN) を、そのサーバーの IP アドレスに解決する内部 A レコード。</span><span class="sxs-lookup"><span data-stu-id="6209e-111">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6209e-112">自動クライアント サインイン</span><span class="sxs-lookup"><span data-stu-id="6209e-112">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="6209e-113">サポートされている各 SIP ドメインについて、_sipinternaltls の SRV レコード。 _tcp。&lt;サインイン&gt;のためのクライアント要求を認証およびリダイレクトする STANDARD Edition サーバーの FQDN にマップされる、ドメインのポート5061。</span><span class="sxs-lookup"><span data-stu-id="6209e-113">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Standard Edition server that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="6209e-114">詳細については、「 <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 での自動クライアントサインインの DNS 要件</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6209e-114">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6209e-115">統合コミュニケーション (UC) デバイスによるデバイス更新 Web サービスの検出</span><span class="sxs-lookup"><span data-stu-id="6209e-115">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="6209e-116">Ucupdates-r2 という名前の内部 A レコード。&lt;デバイス更新&gt; Web サービスをホストする STANDARD Edition サーバーの IP アドレスに解決される SIP ドメイン。</span><span class="sxs-lookup"><span data-stu-id="6209e-116">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Standard Edition server hosting Device Update Web service.</span></span> <span data-ttu-id="6209e-117">UC デバイスが有効になっていても、ユーザーがデバイスにログインしたことがない場合、デバイスは、A レコードを使用して、デバイス更新 Web サービスをホストするサーバーを検出し、更新プログラムを取得できます。</span><span class="sxs-lookup"><span data-stu-id="6209e-117">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the server hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="6209e-118">この方法を実行しない場合、デバイスはユーザーが最初にログインしたときにインバンド プロビジョニングを通じてサーバー情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="6209e-118">Otherwise, devices obtain the server information though in-band provisioning the first time a user logs in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6209e-119">HTTP トラフィックをサポートするためのリバース プロキシ</span><span class="sxs-lookup"><span data-stu-id="6209e-119">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="6209e-120">Web ファームの外部 FQDN を、リバース プロキシの外部 IP アドレスに解決する外部 A レコード。</span><span class="sxs-lookup"><span data-stu-id="6209e-120">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="6209e-121">クライアントと UC デバイスは、このレコードを使用してリバース プロキシに接続します。</span><span class="sxs-lookup"><span data-stu-id="6209e-121">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="6209e-122">詳細については、「計画」のドキュメントの「 <a href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013 の DNS 要件を決定</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6209e-122">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Standard Edition サーバーの DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for a Standard Edition server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48184259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ab4280ca3ed329d0dc926756f6bfd933595ca08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="c4662-102">Lync Server 2013 の Standard Edition サーバーの DNS 要件</span><span class="sxs-lookup"><span data-stu-id="c4662-102">DNS requirements for a Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4662-103">_**最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="c4662-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="c4662-104">このセクションでは、Standard Edition サーバーの展開に必要なドメインネームシステム (DNS) レコードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c4662-104">This section describes the Domain Name System (DNS) records that are required for deployment of Standard Edition servers.</span></span>

<div>

## <a name="dns-records-for-standard-edition-servers"></a><span data-ttu-id="c4662-105">Standard Edition サーバーの DNS レコード</span><span class="sxs-lookup"><span data-stu-id="c4662-105">DNS Records for Standard Edition Servers</span></span>

<span data-ttu-id="c4662-106">次の表では、Lync Server 2013 Standard Edition server の展開の DNS 要件を示します。</span><span class="sxs-lookup"><span data-stu-id="c4662-106">The following table specifies DNS requirements for Lync Server 2013 Standard Edition server deployment.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4662-107">展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="c4662-107">Deployment scenario</span></span></th>
<th><span data-ttu-id="c4662-108">DNS 要件</span><span class="sxs-lookup"><span data-stu-id="c4662-108">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4662-109">Standard Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="c4662-109">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="c4662-110">内部の A レコード。サーバーの完全修飾ドメイン名 (FQDN) を IP アドレスに解決します。</span><span class="sxs-lookup"><span data-stu-id="c4662-110">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4662-111">自動クライアントサインイン</span><span class="sxs-lookup"><span data-stu-id="c4662-111">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="c4662-112">サポートされている各 SIP ドメインについて、_sipinternaltls の SRV レコード。 _tcp。&lt;サインイン&gt;のためのクライアント要求を認証してリダイレクトする標準エディションサーバーの FQDN にマップされる、ポート5061経由のドメイン。</span><span class="sxs-lookup"><span data-stu-id="c4662-112">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Standard Edition server that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="c4662-113">詳細については、「 <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 での自動クライアントサインインの DNS 要件</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4662-113">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4662-114">ユニファイドコミュニケーション (UC) デバイスによるデバイス更新 Web サービスの検出</span><span class="sxs-lookup"><span data-stu-id="c4662-114">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="c4662-115">"Ucupdates-r2" という名前の内部 A レコード。&lt;デバイス更新&gt; Web サービスをホストしている STANDARD Edition サーバーの IP アドレスに解決される SIP ドメイン。</span><span class="sxs-lookup"><span data-stu-id="c4662-115">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Standard Edition server hosting Device Update Web service.</span></span> <span data-ttu-id="c4662-116">UC デバイスが有効になっている状態で、ユーザーがデバイスにログインしたことがない場合、A レコードによってデバイス更新 Web サービスをホストするサーバーがデバイスで検出され、更新プログラムが取得されます。</span><span class="sxs-lookup"><span data-stu-id="c4662-116">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the server hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="c4662-117">そうしないと、デバイスは、ユーザーが初めてログインしたときに、インバンドプロビジョニングでサーバー情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="c4662-117">Otherwise, devices obtain the server information though in-band provisioning the first time a user logs in.</span></span> <span data-ttu-id="c4662-118">詳細については、操作のドキュメントの「 <a href="lync-server-2013-device-update-web-service.md">Lync Server 2013 のデバイス更新 Web サービス</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4662-118">For details, see <a href="lync-server-2013-device-update-web-service.md">Device Update Web service in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4662-119">HTTP トラフィックをサポートする逆プロキシ</span><span class="sxs-lookup"><span data-stu-id="c4662-119">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="c4662-120">外部の web ファーム FQDN をリバースプロキシの外部 IP アドレスに解決する外部の A レコード。</span><span class="sxs-lookup"><span data-stu-id="c4662-120">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="c4662-121">クライアントと UC デバイスこのレコードを使ってリバースプロキシに接続します。</span><span class="sxs-lookup"><span data-stu-id="c4662-121">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="c4662-122">詳細については、「計画ドキュメントの「 <a href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013 の DNS 要件を決定</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4662-122">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c4662-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4662-123">See Also</span></span>


[<span data-ttu-id="c4662-124">Lync Server 2013 での自動クライアントサインインの DNS 要件</span><span class="sxs-lookup"><span data-stu-id="c4662-124">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[<span data-ttu-id="c4662-125">Lync Server 2013 の DNS の要件を確認する</span><span class="sxs-lookup"><span data-stu-id="c4662-125">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="c4662-126">Lync Server 2013 のデバイス更新 Web サービス</span><span class="sxs-lookup"><span data-stu-id="c4662-126">Device Update Web service in Lync Server 2013</span></span>](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


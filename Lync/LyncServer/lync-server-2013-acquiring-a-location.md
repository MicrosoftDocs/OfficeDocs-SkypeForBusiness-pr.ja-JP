---
title: 'Lync Server 2013: 場所の取得'
description: 'Lync Server 2013: 場所を取得しています。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25aa907b5373cadd9eb8ffe9e32a7531afa01deb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571113"
---
# <a name="acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="99081-103">Lync Server 2013 での場所の取得</span><span class="sxs-lookup"><span data-stu-id="99081-103">Acquiring a location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99081-104">_**トピックの最終更新日:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="99081-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="99081-105">Lync Server 2013 E9-1-1 展開では、内部接続された Lync または Lync Phone Edition クライアントはそれぞれ、自分の場所を実際に取得します。</span><span class="sxs-lookup"><span data-stu-id="99081-105">In a Lync Server 2013 E9-1-1 deployment, each internally-connected Lync or Lync Phone Edition client actively acquires its own location.</span></span> <span data-ttu-id="99081-106">SIP 登録の後、クライアントは、furnishes について認識しているすべてのネットワーク接続情報を、レプリケートされた SQL Server データベースによってサポートされている web サービスである場所情報サービスへの場所要求に格納します。</span><span class="sxs-lookup"><span data-stu-id="99081-106">After SIP registration, the client furnishes all the network connectivity information that it knows about itself it in a location request to the Location Information service, which is a web service backed by a replicated SQL Server database.</span></span> <span data-ttu-id="99081-107">各中央サイトプールには、場所情報サービスがあります。これは、ネットワーク情報を使用して、一致する場所についてのレコードを照会します。</span><span class="sxs-lookup"><span data-stu-id="99081-107">Each central site pool has a Location Information service, which uses the network information to query its records for a matching location.</span></span> <span data-ttu-id="99081-108">一致するものがある場合、Location Information service はクライアントに場所を返します。</span><span class="sxs-lookup"><span data-stu-id="99081-108">If there is a match, the Location Information service returns a location to the client.</span></span> <span data-ttu-id="99081-109">一致しない場合は、場所を手動で入力するようにユーザーに求められることがあります (場所のポリシー設定によって異なります)。</span><span class="sxs-lookup"><span data-stu-id="99081-109">If there is not a match, the user may be prompted to enter a location manually (depending on location policy settings).</span></span> <span data-ttu-id="99081-110">場所データは、プレゼンス情報のデータ形式の場所オブジェクト (PIDF-LO) と呼ばれる、インターネット技術標準化委員会 (IETF) の標準化された XML 形式でクライアントに転送されます。</span><span class="sxs-lookup"><span data-stu-id="99081-110">The location data are transmitted back to the client in an Internet Engineering Task Force (IETF) standardized XML format called Presence Information Data Format Location Object (PIDF-LO).</span></span>

<span data-ttu-id="99081-111">Lync Server クライアントには、緊急電話の一部として PIDF-LO のデータが含まれており、E9-1-1 サービスプロバイダーがこのデータを使用して適切な PSAP を決定し、適切な ESQK を使用してその PSAP に通話をルーティングします。これにより、PSAP ディスパッチャーは発信者の場所を取得できます</span><span class="sxs-lookup"><span data-stu-id="99081-111">The Lync Server client includes the PIDF-LO data as part of an emergency call, and this data is used by the E9-1-1 service provider to determine the appropriate PSAP and route the call to that PSAP along with the correct ESQK, which allows the PSAP dispatcher to obtain the caller’s location.</span></span>

<span data-ttu-id="99081-112">次の図は、Lync Server クライアントが場所を取得する方法を示しています (サードパーティクライアントの MAC アドレスベースの場所の方法を除く)。</span><span class="sxs-lookup"><span data-stu-id="99081-112">The following diagram shows how a Lync Server client acquires a location (except for the third-party client MAC address–based location method):</span></span>

<span data-ttu-id="99081-113">![クライアントが場所の図を取得する方法](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "クライアントが場所の図を取得する方法")</span><span class="sxs-lookup"><span data-stu-id="99081-113">![How Client Acquires a Location diagram](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "How Client Acquires a Location diagram")</span></span>

<span data-ttu-id="99081-114">クライアントが場所情報を取得するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99081-114">For a client to acquire a location, the following steps must take place:</span></span>

1.  <span data-ttu-id="99081-115">管理者は、場所情報サービスデータベースを network ワイヤマップ (さまざまな種類のネットワークアドレスを対応する緊急応答の場所 (erls) にマップするテーブル) に設定します。</span><span class="sxs-lookup"><span data-stu-id="99081-115">The administrator populates the Location Information service database with the network wiremap (tables that map various types of network addresses to corresponding Emergency Response Locations (ERLs)).</span></span>

2.  <span data-ttu-id="99081-p102">SIP トランクの E9-1-1 サービス プロバイダーを使用する場合、その E9-1-1 サービス プロバイダーが維持する主要道路住所案内 (MSAG) データベースに対して、管理者は ERL の公的アドレス部分を確認します。ELIN ゲートウェイを使用する場合、管理者は、PSTN キャリアが自動ロケーション識別 (ALI) データベースに ELIN をアップロードすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="99081-p102">If you use a SIP trunk E9-1-1 service provider, the administrator validates the civic address portions of the ERLs against a Master Street Address Guide (MSAG) database maintained by the E9-1-1 service provider. If you use an ELIN gateway, the administrator ensures that the PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

3.  <span data-ttu-id="99081-118">登録中、またはネットワークの変更が発生するたびに、内部接続のクライアントは、検出されたクライアントのネットワークアドレスを含む場所要求を場所情報サービスに送信します。</span><span class="sxs-lookup"><span data-stu-id="99081-118">During registration or whenever a network change occurs, an internally-connected client sends a location request that contains the client's discovered network addresses to the Location Information service.</span></span>

4.  <span data-ttu-id="99081-119">場所情報サービスは、発行されたレコードに対して1つの場所を照会し、一致するものが見つかった場合は、ERL を PIDF-LO 形式でクライアントに返します。</span><span class="sxs-lookup"><span data-stu-id="99081-119">The Location Information service queries its published records for a location, and, if a match is found, returns the ERL to the client in PIDF-LO format.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


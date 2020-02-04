---
title: 'Lync Server 2013: 場所の取得'
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
ms.openlocfilehash: e54c7032973f75922f6c6893a0c758409ec945be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="8bcd2-102">Lync Server 2013 での場所の取得</span><span class="sxs-lookup"><span data-stu-id="8bcd2-102">Acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bcd2-103">_**最終更新日:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="8bcd2-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="8bcd2-104">Lync Server 2013 E9 の展開では、内部接続された Lync または Lync Phone Edition クライアントはそれぞれ、自分の場所をアクティブに取得しています。</span><span class="sxs-lookup"><span data-stu-id="8bcd2-104">In a Lync Server 2013 E9-1-1 deployment, each internally-connected Lync or Lync Phone Edition client actively acquires its own location.</span></span> <span data-ttu-id="8bcd2-105">SIP 登録後、クライアントは、furnishes について知っているすべてのネットワーク接続情報を、レプリケートされた SQL Server データベースによってサポートされている web サービスである位置情報サービスへの場所要求で認識します。</span><span class="sxs-lookup"><span data-stu-id="8bcd2-105">After SIP registration, the client furnishes all the network connectivity information that it knows about itself it in a location request to the Location Information service, which is a web service backed by a replicated SQL Server database.</span></span> <span data-ttu-id="8bcd2-106">各セントラルサイトプールには、位置情報サービスがあります。これにより、ネットワーク情報を使用して、一致する場所についてレコードを照会します。</span><span class="sxs-lookup"><span data-stu-id="8bcd2-106">Each central site pool has a Location Information service, which uses the network information to query its records for a matching location.</span></span> <span data-ttu-id="8bcd2-107">一致する場合は、位置情報サービスによってクライアントに位置情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="8bcd2-107">If there is a match, the Location Information service returns a location to the client.</span></span> <span data-ttu-id="8bcd2-108">一致していない場合、場所を手動で入力するように求めるメッセージが表示されることがあります (場所のポリシーの設定によって異なります)。</span><span class="sxs-lookup"><span data-stu-id="8bcd2-108">If there is not a match, the user may be prompted to enter a location manually (depending on location policy settings).</span></span> <span data-ttu-id="8bcd2-109">場所データは、プレゼンス情報データ形式の場所オブジェクト (PIDF) と呼ばれるインターネットエンジニアリングタスクフォース (IETF) の標準化された XML 形式でクライアントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="8bcd2-109">The location data are transmitted back to the client in an Internet Engineering Task Force (IETF) standardized XML format called Presence Information Data Format Location Object (PIDF-LO).</span></span>

<span data-ttu-id="8bcd2-110">Lync Server クライアントには、緊急通話の一部として PIDF データが含まれており、このデータは E9 サービスプロバイダーによって、適切な PSAP を特定し、その PSAP に呼び出しをルーティングするために、正しい ESQK と共に使用されます。これにより、PSAP ディスパッチャーは、発信者の場所。</span><span class="sxs-lookup"><span data-stu-id="8bcd2-110">The Lync Server client includes the PIDF-LO data as part of an emergency call, and this data is used by the E9-1-1 service provider to determine the appropriate PSAP and route the call to that PSAP along with the correct ESQK, which allows the PSAP dispatcher to obtain the caller’s location.</span></span>

<span data-ttu-id="8bcd2-111">次の図は、Lync Server クライアントで場所を取得する方法を示しています (サードパーティのクライアント MAC アドレスベースの場所のメソッドを除く)。</span><span class="sxs-lookup"><span data-stu-id="8bcd2-111">The following diagram shows how a Lync Server client acquires a location (except for the third-party client MAC address–based location method):</span></span>

<span data-ttu-id="8bcd2-112">![クライアントが場所を取得する方法の図](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "クライアントが場所を取得する方法の図")</span><span class="sxs-lookup"><span data-stu-id="8bcd2-112">![How Client Acquires a Location diagram](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "How Client Acquires a Location diagram")</span></span>

<span data-ttu-id="8bcd2-113">クライアントが場所情報を取得するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bcd2-113">For a client to acquire a location, the following steps must take place:</span></span>

1.  <span data-ttu-id="8bcd2-114">管理者は、場所情報サービスデータベースに network wiremap (さまざまな種類のネットワークアドレスを対応する緊急対応の場所 (ERLs) にマップするテーブル) を設定します。</span><span class="sxs-lookup"><span data-stu-id="8bcd2-114">The administrator populates the Location Information service database with the network wiremap (tables that map various types of network addresses to corresponding Emergency Response Locations (ERLs)).</span></span>

2.  <span data-ttu-id="8bcd2-p102">SIP トランクの E9-1-1 サービス プロバイダーを使用する場合、その E9-1-1 サービス プロバイダーが維持する主要道路住所案内 (MSAG) データベースに対して、管理者は ERL の公的アドレス部分を確認します。ELIN ゲートウェイを使用する場合、管理者は、PSTN キャリアが自動ロケーション識別 (ALI) データベースに ELIN をアップロードすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8bcd2-p102">If you use a SIP trunk E9-1-1 service provider, the administrator validates the civic address portions of the ERLs against a Master Street Address Guide (MSAG) database maintained by the E9-1-1 service provider. If you use an ELIN gateway, the administrator ensures that the PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

3.  <span data-ttu-id="8bcd2-117">登録中、またはネットワークの変更が発生するたびに、内部接続クライアントは、クライアントの検出されたネットワークアドレスを含む位置情報要求を、位置情報サービスに送信します。</span><span class="sxs-lookup"><span data-stu-id="8bcd2-117">During registration or whenever a network change occurs, an internally-connected client sends a location request that contains the client's discovered network addresses to the Location Information service.</span></span>

4.  <span data-ttu-id="8bcd2-118">位置情報サービスは、発行されたレコードに対して場所を照会します。一致するものが見つかった場合は、ERL を PIDF 形式でクライアントに返します。</span><span class="sxs-lookup"><span data-stu-id="8bcd2-118">The Location Information service queries its published records for a location, and, if a match is found, returns the ERL to the client in PIDF-LO format.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


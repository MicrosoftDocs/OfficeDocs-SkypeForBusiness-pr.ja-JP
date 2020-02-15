---
title: 'Lync Server 2013: Microsoft Lync クライアントのポート範囲の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea0300b042dc124f0fb8bf523221e39128cbf57a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a><span data-ttu-id="4e05e-102">Lync Server 2013 での Microsoft Lync クライアントのポート範囲の構成</span><span class="sxs-lookup"><span data-stu-id="4e05e-102">Configuring port ranges for your Microsoft Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e05e-103">_**トピックの最終更新日:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="4e05e-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="4e05e-104">既定では、Lync クライアントアプリケーションは、通信セッションに参加するときにポート1024と65535の間の任意のポートを使用できます。これは、特定のポート範囲がクライアントに対して自動的に有効にならないためです。</span><span class="sxs-lookup"><span data-stu-id="4e05e-104">By default, Lync client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="4e05e-105">ただし、サービスの品質を使用するためには、さまざまな種類のトラフィック (オーディオ、ビデオ、メディア、アプリケーション共有、およびファイル転送) を一連の固有のポート範囲に再割り当てする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e05e-105">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="4e05e-106">これは、Get-csconferencingconfiguration コマンドレットを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4e05e-106">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4e05e-107">エンドユーザーは、これらの変更を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="4e05e-107">End users cannot make these changes themselves.</span></span> <span data-ttu-id="4e05e-108">ポートの変更は、管理者のみが Get-csconferencingconfiguration コマンドレットを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4e05e-108">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>



</div>

<span data-ttu-id="4e05e-109">Microsoft Lync Server 2013 管理シェルで次のコマンドを実行することにより、現在通信セッションで使用されているポート範囲を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4e05e-109">You can determine which port ranges are currently used for communication sessions by running the following command from within the Microsoft Lync Server 2013 Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="4e05e-110">Lync Server 2013 をインストールした後に会議の設定を変更していない場合は、次のプロパティ値を含む情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="4e05e-110">Assuming that you have not made any changes to your conferencing settings since you installed Lync Server 2013, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="4e05e-111">ここに示した出力には、重要な情報が 2 つ含まれています。</span><span class="sxs-lookup"><span data-stu-id="4e05e-111">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="4e05e-112">1 つ目は、ClientMediaPortRangeEnabled プロパティが False に設定されていることです。</span><span class="sxs-lookup"><span data-stu-id="4e05e-112">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="4e05e-113">このプロパティが False に設定されている場合、Lync クライアントは、通信セッションに参加するときにポート1024と65535の間で使用可能なポートを使用することに注意してください。これは、他のポート設定 (たとえば、ClientMediaPort または ClientVideoPort) に関係なく該当します。</span><span class="sxs-lookup"><span data-stu-id="4e05e-113">That's important because, when this property is set to False, Lync clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="4e05e-114">指定したポートのセットのみを使用するように制限する場合 (サービス品質の実装を計画している場合はこのような制限を行います)、最初にクライアントのメディア ポート範囲を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e05e-114">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service) then you must first enable client media port ranges.</span></span> <span data-ttu-id="4e05e-115">これは、次の Windows PowerShell コマンドを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="4e05e-115">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="4e05e-p105">上記のコマンドを実行すると、会議の構成設定のグローバル コレクションに対してクライアントのメディア ポート範囲が有効化されます。ただし、これらの設定は、サイト範囲またはサービスの範囲 (電話会議サーバー サービスのみ) に対しても適用できます。特定のサイトまたはサーバーに対してクライアントのメディア ポート範囲を有効にするには、Set-CsConferencingConfiguration の呼び出し時にそのサイトまたはサーバーの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e05e-p105">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only). To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="4e05e-118">次のコマンドを使用して、会議のすべての構成設定に対して同時にポート範囲を有効化することもできます。</span><span class="sxs-lookup"><span data-stu-id="4e05e-118">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="4e05e-119">2 つ目の重要な情報は、サンプルの出力では、既定で、各種類のネットワーク トラフィックに対して同じメディア ポート範囲が設定されていることです。</span><span class="sxs-lookup"><span data-stu-id="4e05e-119">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="4e05e-p106">QoS を実装するためには、これらの各ポート範囲が一意であることが必要です。たとえば、次のようにポート範囲を構成します。</span><span class="sxs-lookup"><span data-stu-id="4e05e-p106">In order to implement QoS, each of these port ranges will need to be unique. For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e05e-122">クライアント トラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="4e05e-122">Client Traffic Type</span></span></th>
<th><span data-ttu-id="4e05e-123">開始ポート</span><span class="sxs-lookup"><span data-stu-id="4e05e-123">Port Start</span></span></th>
<th><span data-ttu-id="4e05e-124">ポート範囲</span><span class="sxs-lookup"><span data-stu-id="4e05e-124">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e05e-125">オーディオ</span><span class="sxs-lookup"><span data-stu-id="4e05e-125">Audio</span></span></p></td>
<td><p><span data-ttu-id="4e05e-126">50020</span><span class="sxs-lookup"><span data-stu-id="4e05e-126">50020</span></span></p></td>
<td><p><span data-ttu-id="4e05e-127">1280</span><span class="sxs-lookup"><span data-stu-id="4e05e-127">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e05e-128">ビデオ</span><span class="sxs-lookup"><span data-stu-id="4e05e-128">Video</span></span></p></td>
<td><p><span data-ttu-id="4e05e-129">58000</span><span class="sxs-lookup"><span data-stu-id="4e05e-129">58000</span></span></p></td>
<td><p><span data-ttu-id="4e05e-130">1280</span><span class="sxs-lookup"><span data-stu-id="4e05e-130">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e05e-131">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="4e05e-131">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="4e05e-132">42000</span><span class="sxs-lookup"><span data-stu-id="4e05e-132">42000</span></span></p></td>
<td><p><span data-ttu-id="4e05e-133">1280</span><span class="sxs-lookup"><span data-stu-id="4e05e-133">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e05e-134">ファイル送信</span><span class="sxs-lookup"><span data-stu-id="4e05e-134">File transfer</span></span></p></td>
<td><p><span data-ttu-id="4e05e-135">42020</span><span class="sxs-lookup"><span data-stu-id="4e05e-135">42020</span></span></p></td>
<td><p><span data-ttu-id="4e05e-136">1280</span><span class="sxs-lookup"><span data-stu-id="4e05e-136">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4e05e-p107">上記の表では、クライアントのポート範囲はサーバーに構成されたポート範囲のサブセットを表しています。たとえば、サーバーではアプリケーション共有が 40803 ～ 49151 のポートを使用するように構成されており、クライアント コンピューターではアプリケーション共有が 42000 ～ 42019 のポートを使用するように構成されています。このように構成されているのは、主に QoS を管理しやすくするためです。クライアントのポートは、サーバーで使用されるポートのサブセットになっている必要はありません (たとえば、クライアント コンピューターで、アプリケーション共有が 10000 ～ 10019 のポートを使用するように構成できます)。ただし、クライアントのポート範囲がサーバーのポート範囲のサブセットになるように構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4e05e-p107">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers. For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019. This, too is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server. (For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="4e05e-p108">また、サーバー上でアプリケーション共有のために 8348 個のポートが用意されているにもかかわらず、クライアントでアプリケーション共有のために確保されているポートが 20 個のみであることに気付きます。これも推奨されるルールですが、どのような場合でも必ず守る必要があるルールではありません。一般的に、1 つの利用可能なポートは、それぞれ 1 件の通信セッションを表していると考えることができます。ポート範囲に 100 個の利用可能なポートがある場合は、そのコンピューターが任意の時点で最大 100 件の通信セッションに参加する可能性があることを意味します。通常、サーバーはクライアントよりも多くの通信に参加するため、サーバー上でクライアントよりもはるかに多くのポートが開かれるのは当然のことです。クライアントでアプリケーション共有のために 20 個のポートを確保するということは、ユーザーが、指定したデバイスで同時に 20 のアプリケーション共有セッションに参加できることを意味します。大多数のユーザーにとっては、セッション数が 20 あれば十分です。</span><span class="sxs-lookup"><span data-stu-id="4e05e-p108">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients. This, too is recommended, but is not a hard-and-fast rule. In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range that means that the computer in question could participate in, at most, 100 communication sessions at any given time. Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients. Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time. That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="4e05e-147">会議構成設定のグローバルコレクションに上記のポート範囲を割り当てるには、次の Lync Server 管理シェルコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4e05e-147">To assign the preceding port ranges to your global collection of conferencing configuration settings you can use the following Lync Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="4e05e-148">または、次のコマンドを使用して、この同じポート範囲を会議のすべての構成設定に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4e05e-148">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="4e05e-149">個々のユーザーは、実際には Lync からログオフしてから再度ログオンする必要があります。これらの変更は実際に有効になります。</span><span class="sxs-lookup"><span data-stu-id="4e05e-149">Individual users must log off from Lync and then log back on before these changes will actually take effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4e05e-150">1 つのコマンドで、クライアントのメディア ポート範囲を有効化し、これらのポート範囲を割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="4e05e-150">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="4e05e-151">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4e05e-151">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>


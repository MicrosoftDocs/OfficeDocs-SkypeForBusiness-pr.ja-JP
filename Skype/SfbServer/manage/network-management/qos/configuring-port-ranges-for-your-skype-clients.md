---
title: クライアントのポート範囲とサービス品質ポリシーを構成する
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: この記事では、Windows 10 で実行されているクライアントのために、クライアントのポート範囲を構成し、サービスの品質ポリシーを構成する方法について説明します。
ms.openlocfilehash: ce1690c295f1f5ed991780919370e5dbf5b5d6b1
ms.sourcegitcommit: f7ec026accb0bb91ce62a9d5f24ac4b70a514c4e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35204015"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="2e9e8-103">Skype for Business Server でのクライアントのポート範囲とサービス品質ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="2e9e8-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="2e9e8-104">この記事では、Windows 10 で実行されているクライアントのために、クライアントのポート範囲を構成し、サービスの品質ポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="2e9e8-105">ポート範囲を構成する</span><span class="sxs-lookup"><span data-stu-id="2e9e8-105">Configure port ranges</span></span>

<span data-ttu-id="2e9e8-106">既定では、Skype for Business クライアントアプリケーションは、通信セッションに参加している場合は、ポート1024と65535の間の任意のポートを使用できます。これは、特定のポート範囲がクライアントに対して自動的に有効にならないためです。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="2e9e8-107">ただし、サービスの品質を使用するためには、さまざまな種類のトラフィック (オーディオ、ビデオ、メディア、アプリケーション共有、ファイル転送) を、一連の固有のポート範囲に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="2e9e8-108">これを行うには、CsConferencingConfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="2e9e8-109">エンドユーザーはこれらの変更を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="2e9e8-110">ポートの変更は、CsConferencingConfiguration コマンドレットを使用している管理者のみが実行できます。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="2e9e8-111">現在通信セッションに使用されているポート範囲を特定するには、Skype for Business Server 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="2e9e8-112">Skype for Business Server をインストールしてから会議の設定を変更していない場合は、次のプロパティ値を含む情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="2e9e8-113">上記の出力をよく見ると、2つの重要な点が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="2e9e8-114">まず、ClientMediaPortRangeEnabled プロパティが False に設定されます。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="2e9e8-115">このプロパティが False に設定されている場合、Skype for Business クライアントは、通信セッションに関与するときに、ポート1024と65535の間で使用可能なポートを使用します。これは、他のポート設定 (ClientMediaPort や ClientVideoPort など) に関係なく true になります。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="2e9e8-116">指定した一連のポートに使用を制限する場合 (これは、サービスの品質の実装を計画している場合に実行します)、まずクライアントのメディアポート範囲を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="2e9e8-117">この操作を行うには、次の Windows PowerShell コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="2e9e8-118">上のコマンドを実行すると、会議構成設定のグローバルコレクションに対してクライアントのメディアポート範囲が有効になります。ただし、これらの設定は、サイトのスコープやサービスの範囲 (会議サーバーサービスのみ) に適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-118">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="2e9e8-119">特定のサイトまたはサーバーに対してクライアントのメディアポート範囲を有効にするには、Set-CsConferencingConfiguration を呼び出すときにそのサイトまたはサーバーの Id を指定します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-119">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="2e9e8-120">または、このコマンドを使用して、すべての会議構成設定のポート範囲を同時に有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="2e9e8-121">2番目の重要な点は、既定では、各種類のネットワークトラフィックに設定されたメディアポート範囲が同じであることを示しています。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="2e9e8-122">QoS を実装するために、これらの各ポート範囲は一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-122">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="2e9e8-123">たとえば、次のようなポート範囲を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-123">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e9e8-124">クライアントトラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="2e9e8-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="2e9e8-125">ポートの開始</span><span class="sxs-lookup"><span data-stu-id="2e9e8-125">Port Start</span></span></th>
<th><span data-ttu-id="2e9e8-126">ポートの範囲</span><span class="sxs-lookup"><span data-stu-id="2e9e8-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e9e8-127">オーディオ</span><span class="sxs-lookup"><span data-stu-id="2e9e8-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="2e9e8-128">50020</span><span class="sxs-lookup"><span data-stu-id="2e9e8-128">50020</span></span></p></td>
<td><p><span data-ttu-id="2e9e8-129">超える</span><span class="sxs-lookup"><span data-stu-id="2e9e8-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e9e8-130">ビデオ</span><span class="sxs-lookup"><span data-stu-id="2e9e8-130">Video</span></span></p></td>
<td><p><span data-ttu-id="2e9e8-131">58000</span><span class="sxs-lookup"><span data-stu-id="2e9e8-131">58000</span></span></p></td>
<td><p><span data-ttu-id="2e9e8-132">超える</span><span class="sxs-lookup"><span data-stu-id="2e9e8-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e9e8-133">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="2e9e8-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="2e9e8-134">42000</span><span class="sxs-lookup"><span data-stu-id="2e9e8-134">42000</span></span></p></td>
<td><p><span data-ttu-id="2e9e8-135">超える</span><span class="sxs-lookup"><span data-stu-id="2e9e8-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e9e8-136">ファイル転送</span><span class="sxs-lookup"><span data-stu-id="2e9e8-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="2e9e8-137">42020</span><span class="sxs-lookup"><span data-stu-id="2e9e8-137">42020</span></span></p></td>
<td><p><span data-ttu-id="2e9e8-138">超える</span><span class="sxs-lookup"><span data-stu-id="2e9e8-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2e9e8-139">上の表のクライアントポート範囲は、サーバーに構成されているポート範囲のサブセットを表しています。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="2e9e8-140">たとえば、サーバー上では、40803 ~ 49151 のポートを使用するようにアプリケーション共有が構成されています。クライアントコンピューターでは、[アプリケーション共有] は、42000 ~ 42019 のポートを使用するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="2e9e8-141">これは主に、QoS の管理を簡単にするために行われています。クライアントポートは、サーバーで使われているポートのサブセットを表す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="2e9e8-142">(たとえば、クライアントコンピューターで、1万 ~ 10019 のポートを使用するようにアプリケーション共有を構成することができます)。ただし、クライアントポート範囲をサーバーのポート範囲のサブセットにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="2e9e8-143">また、サーバー上でのアプリケーション共有のために8348のポートが設定されていても、クライアントでのアプリケーション共有については20個のポートしか設定されていないことに気付いた場合もあります。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="2e9e8-144">これもお勧めしますが、これは、ハードとファーストのルールではありません。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="2e9e8-145">一般的に、1つの通信セッションを表すために使用可能な各ポートを検討することができます。ポート範囲で利用可能な100ポートがある場合、そのコンピューターは、いつでも最大100の通信セッションに参加できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="2e9e8-146">サーバーはクライアントよりも多くの会話に参加する可能性があるため、クライアントよりも多くのポートをサーバー上で開くことが適切です。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="2e9e8-147">クライアント上のアプリケーション共有に20個のポートを確保することは、ユーザーが指定したデバイスで20個のアプリケーション共有セッションに参加することを意味します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="2e9e8-148">これは、ほとんどのユーザーにとって十分なものであることを証明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="2e9e8-149">上のポート範囲を会議の構成設定のグローバルコレクションに割り当てるには、次の Skype for Business Server 管理シェルコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="2e9e8-150">または、このコマンドを使用して、すべての会議の構成設定にこれらと同じポート範囲を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="2e9e8-151">個々のユーザーは、Skype for Business からログオフしてから再びログインする必要があります。これらの変更は実際に有効になります。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="2e9e8-152">クライアントのメディアポート範囲を有効にして、1つのコマンドを使用してこれらのポート範囲を割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="2e9e8-153">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="2e9e8-154">Windows 10 で実行されているクライアントのサービス品質ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="2e9e8-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="2e9e8-155">Skype for Business クライアントで使用するポート範囲を指定するだけでなく、クライアントコンピューターに適用されるサービスの品質ポリシーを個別に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="2e9e8-156">(会議、アプリケーション、および仲介サーバー用に作成されたサービスの品質ポリシーは、クライアントコンピューターに適用しないでください)。この情報は、Skype for Business クライアントと Windows 10 を実行しているコンピューターにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="2e9e8-157">次の例では、この一連のポート範囲を使ってオーディオポリシーとビデオポリシーを作成しています。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e9e8-158">クライアントトラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="2e9e8-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="2e9e8-159">ポートの開始</span><span class="sxs-lookup"><span data-stu-id="2e9e8-159">Port Start</span></span></th>
<th><span data-ttu-id="2e9e8-160">ポートの範囲</span><span class="sxs-lookup"><span data-stu-id="2e9e8-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e9e8-161">オーディオ</span><span class="sxs-lookup"><span data-stu-id="2e9e8-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="2e9e8-162">50020</span><span class="sxs-lookup"><span data-stu-id="2e9e8-162">50020</span></span></p></td>
<td><p><span data-ttu-id="2e9e8-163">超える</span><span class="sxs-lookup"><span data-stu-id="2e9e8-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e9e8-164">ビデオ</span><span class="sxs-lookup"><span data-stu-id="2e9e8-164">Video</span></span></p></td>
<td><p><span data-ttu-id="2e9e8-165">58000</span><span class="sxs-lookup"><span data-stu-id="2e9e8-165">58000</span></span></p></td>
<td><p><span data-ttu-id="2e9e8-166">超える</span><span class="sxs-lookup"><span data-stu-id="2e9e8-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e9e8-167">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="2e9e8-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="2e9e8-168">42000</span><span class="sxs-lookup"><span data-stu-id="2e9e8-168">42000</span></span></p></td>
<td><p><span data-ttu-id="2e9e8-169">超える</span><span class="sxs-lookup"><span data-stu-id="2e9e8-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e9e8-170">ファイル転送</span><span class="sxs-lookup"><span data-stu-id="2e9e8-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="2e9e8-171">42020</span><span class="sxs-lookup"><span data-stu-id="2e9e8-171">42020</span></span></p></td>
<td><p><span data-ttu-id="2e9e8-172">超える</span><span class="sxs-lookup"><span data-stu-id="2e9e8-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2e9e8-173">Windows 10 コンピューターのサービス品質のオーディオポリシーを作成するには、まずグループポリシー管理がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="2e9e8-174">[グループポリシーの管理] を開き ([**スタート**] をクリックし、[**管理ツール**] をポイントして、[**グループポリシーの管理**] をクリックし)、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="2e9e8-175">[グループポリシーの管理] で、新しいポリシーを作成するコンテナーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="2e9e8-176">たとえば、すべてのクライアントコンピューターがクライアントという名前の OU に配置されている場合、新しいポリシーがクライアント OU に作成されます。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="2e9e8-177">適切なコンテナーを右クリックし、[**このドメインに GPO を作成**] をクリックして、ここにリンクを設定します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="2e9e8-178">[**新しい GPO** ] ダイアログボックスの [**名前**] ボックスに新しいグループポリシーオブジェクトの名前を入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="2e9e8-179">新しく作成したポリシーを右クリックし、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="2e9e8-180">グループポリシー管理エディターで、[**コンピューターの構成**]、[ **Windows の設定**] の順に展開し、[**ポリシーベースの QoS**] を右クリックして、[**新しいポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="2e9e8-181">[**ポリシーベースの QoS** ] ダイアログボックスの [開く] ページで、[**名前**] ボックスに新しいポリシーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="2e9e8-182">[ **DSCP 値の指定**] を選択し、値を**46**に設定します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="2e9e8-183">[**送信スロットルの比率を指定する**] をオフにして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="2e9e8-184">次のページで、[**この実行可能ファイル名のアプリケーションのみ**] を選択し、名前として「 **Lync** 」と入力して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-184">On the next page, select **Only applications with this executable name**, enter **Lync.exe** as the name, and then click **Next**.</span></span> <span data-ttu-id="2e9e8-185">この設定では、Skype for Business クライアントからの一致トラフィックのみの優先順位付けをポリシーに指示します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-185">This setting instructs the policy to only prioritize matching traffic from the Skype for Business client.</span></span>

8.  <span data-ttu-id="2e9e8-186">3番目のページで、[**ソース ip アドレス**] と [**宛先 ip アドレス**] の両方が選択されていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="2e9e8-187">この2つの設定では、どのコンピューター (IP アドレス) がそれらのパケットを送信したか、どのコンピューター (IP アドレス) がそれらのパケットを受信するかに関係なく、パケットが管理されるようにします。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="2e9e8-188">4ページ目で、[**この QoS ポリシーが適用されるプロトコルを選択**してください] ドロップダウンリストから [ **TCP および UDP** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="2e9e8-189">TCP (伝送制御プロトコル) と UDP (ユーザーデータグラムプロトコル) は、Skype for Business Server およびそのクライアントアプリケーションで最も一般的に使用される2つのネットワークプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="2e9e8-190">見出しの下で、**ソースポート番号を指定**して、[**このソースポートまたは範囲から**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-190">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="2e9e8-191">[付随するテキスト] ボックスに、オーディオ送信用に予約されているポート範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-191">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="2e9e8-192">たとえば、ポート50020からオーディオトラフィック用にポート50039を予約した場合、次の形式を使用してポート範囲を入力します**50020:50039**。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-192">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="2e9e8-193">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-193">Click **Finish**.</span></span>

<span data-ttu-id="2e9e8-194">オーディオの QoS ポリシーを作成したら、ビデオ用の第2のポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-194">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="2e9e8-195">ビデオのポリシーを作成するには、オーディオポリシーを作成する場合と同じ基本的な手順に従い、次のように置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-195">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="2e9e8-196">別の (一意の) ポリシー名を使用します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="2e9e8-197">DSCP 値を46ではなく、 **34**に設定します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-197">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="2e9e8-198">(前に説明したように、DSCP 値34を使用する必要はありません。単に、オーディオに使用されている別の DSCP 値を割り当てる必要があります)。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-198">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="2e9e8-199">以前に構成されたポート範囲をビデオトラフィックに使用します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="2e9e8-200">たとえば、ビデオ用にポート 58000 ~ 58019 を予約している場合は、ポート範囲を次のよう**58000:58019**に設定します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="2e9e8-201">アプリケーション共有トラフィックを管理するためのポリシーを作成する場合は、次のように置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="2e9e8-202">別の (一意の) ポリシー名 (「 **Skype For Business Server アプリケーション共有**」など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="2e9e8-203">DSCP 値を46の代わりに**24**に設定します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-203">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="2e9e8-204">(この値は、必ずしも24である必要はありません。単に、音声とビデオに使われる DSCP 値とは異なる必要があります)。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-204">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="2e9e8-205">以前に構成されたポート範囲をビデオトラフィックに使用します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="2e9e8-206">たとえば、アプリケーション共有用にポート 42000 ~ 42019 を予約している場合は、ポート範囲を " **42000:42019**" に設定します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="2e9e8-207">ファイル転送ポリシーの場合:</span><span class="sxs-lookup"><span data-stu-id="2e9e8-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="2e9e8-208">別の (一意の) ポリシー名を使用します (たとえば、 **Skype For Business Server ファイル転送**)。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="2e9e8-209">DSCP 値を**14**に設定します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="2e9e8-210">(この値は、14でなくてもかまいません。単に一意の DSCP コードである必要があります)。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="2e9e8-211">以前に構成されたアプリケーションのポート範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="2e9e8-212">たとえば、アプリケーション共有用にポート 42020 ~ 42039 を予約している場合は、ポート範囲を " **42020:42039**" に設定します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="2e9e8-213">クライアントコンピューターでグループポリシーが更新されるまで、作成した新しいポリシーは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-213">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="2e9e8-214">グループ ポリシーは定期的に自動更新されますが、グループ ポリシーを更新する必要がある各コンピューター上で次のコマンドを実行すると、即座に強制的に更新することができます。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-214">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="2e9e8-215">このコマンドは、管理者の資格情報のもとで実行されているコマンド ウィンドウから実行できます。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-215">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="2e9e8-216">管理者の資格情報のもとでコマンド ウィンドウを開くには、[**スタート**] メニューをクリックし、[**コマンド プロンプト**] を右クリックして、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-216">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="2e9e8-217">これらのポリシーは、クライアントコンピューターのターゲットにする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="2e9e8-218">Skype for Business Server を実行しているサーバーには適用しないでください。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="2e9e8-219">ネットワークパケットが適切な DSCP 値でマークされていることを確認するには、次の手順に従って、各コンピューターに新しいレジストリエントリを作成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="2e9e8-220">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="2e9e8-221">[**実行**] ダイアログボックスで、「 **regedit**」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="2e9e8-222">レジストリエディターで、[ **\_HKEY ローカル\_コンピューター**]、[**システム**]、[ **CurrentControlSet**] の順に展開し、[**サービス**] を展開して、[ **Tcpip**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="2e9e8-223">[ **Tcpip**] を右クリックし、[**新規作成**] をポイントして、[**キー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="2e9e8-224">新しいレジストリキーが作成されたら、「 **QoS**」と入力し、enter キーを押してキーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="2e9e8-225">[ **QoS**] を右クリックし、[**新規作成**] をポイントして、[**文字列値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="2e9e8-226">新しいレジストリ値が作成されたら、[ **NLA を使用しない**] と入力し、enter キーを押して値の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="2e9e8-227">[ **NLA を使わない**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="2e9e8-228">[**文字列の編集**] ダイアログボックスで、[**値のデータ**] ボックスに「 **1** 」と入力して、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="2e9e8-229">レジストリエディターを終了し、コンピューターを起動します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="2e9e8-230">複数のネットワークアダプターを搭載したコンピューターでサービスの品質を設定する</span><span class="sxs-lookup"><span data-stu-id="2e9e8-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="2e9e8-231">複数のネットワークアダプターを搭載したコンピューターを使用している場合、DSCP 値が構成された値ではなく0x00 として表示される問題が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="2e9e8-232">これは通常、1つ以上のネットワークアダプターが Active Directory ドメインにアクセスできない (たとえば、これらのアダプターがプライベートネットワーク用に使用されている) 場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="2e9e8-233">このような場合、DSCP 値は、ドメインにアクセスできるアダプターに対してタグ付けされますが、ドメインにアクセスできないアダプターにはタグ付けされません。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="2e9e8-234">ドメインへのアクセス権を持たないアダプターも含め、コンピューターのすべてのネットワークアダプターの DSCP 値にタグを付ける場合は、レジストリに値を追加して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="2e9e8-235">この操作を行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="2e9e8-236">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="2e9e8-237">[**実行**] ダイアログボックスで、「 **regedit**」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="2e9e8-238">レジストリエディターで、[ **\_HKEY ローカル\_コンピューター**]、[**システム**]、[ **CurrentControlSet**] の順に展開し、[**サービス**] を展開して、[ **Tcpip**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="2e9e8-239">[ **QoS** ] というラベルのレジストリキーが表示されない場合は、[ **Tcpip**] を右クリックし、[**新規**] をポイントして、[**キー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="2e9e8-240">新しいキーを作成したら、「 **QoS**」と入力し、enter キーを押してキーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="2e9e8-241">[ **QoS**] を右クリックし、[**新規作成**] をポイントして、[**文字列値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="2e9e8-242">新しいレジストリ値が作成されたら、[ **NLA を使用しない**] と入力し、enter キーを押して値の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="2e9e8-243">[ **NLA を使わない**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="2e9e8-244">[**文字列の編集**] ダイアログボックスで、[**値のデータ**] ボックスに「 **1** 」と入力して、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="2e9e8-245">新しいレジストリ値を作成して構成した後、変更を有効にするには、コンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e9e8-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e9e8-246">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e9e8-246">See also</span></span>

[<span data-ttu-id="2e9e8-247">Windows 10 でグループポリシーオブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="2e9e8-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)

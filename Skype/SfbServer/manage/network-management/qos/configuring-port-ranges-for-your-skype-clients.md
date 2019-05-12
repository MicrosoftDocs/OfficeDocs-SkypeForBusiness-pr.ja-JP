---
title: クライアント用のポートの範囲とサービスの品質ポリシーを構成します。
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: この資料では、Skype のサービスの品質ポリシーを構成、クライアントのビジネスのサーバーの 10 の Windows で実行されているクライアントのポート範囲を構成する方法について説明します。
ms.openlocfilehash: 9377274b625af7a4ed93b46a0f6a741e89eee1eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913070"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="d9ca1-103">Skype で、クライアントのビジネスのサーバーのポート範囲およびサービスの品質ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="d9ca1-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="d9ca1-104">この資料では、Skype のサービスの品質ポリシーを構成、クライアントのビジネスのサーバーの 10 の Windows で実行されているクライアントのポート範囲を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="d9ca1-105">ポート範囲を構成します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-105">Configure port ranges</span></span>

<span data-ttu-id="d9ca1-106">既定では、Skype クライアントのビジネス アプリケーションとの間の任意のポートを使用できます、ポート 1024 から 65535 までの通信セッションに関与する場合特定のポート範囲が自動的に有効になっていないクライアントのためです。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="d9ca1-107">品質のサービスを使用するには、ただし、する必要がさまざまなトラフィックの種類 (オーディオ、ビデオ、メディア、アプリケーション共有、およびファイル転送) を再割り当てするのには一連の一意のポート範囲に。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="d9ca1-108">これは、セット CsConferencingConfiguration コマンドレットを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="d9ca1-109">エンド ・ ユーザーは、これらの変更自体を作成できません。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="d9ca1-110">ポートの変更をできるセット CsConferencingConfiguration コマンドレットを使用して管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="d9ca1-111">ビジネス サーバー管理シェルには、Skype 内で次のコマンドを実行して、ポート範囲が通信セッションで使用されてを判断できます。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="d9ca1-112">変更を加えていないの会議の設定にビジネス サーバーの Skype をインストールして以来、ことを前提としてする必要があります情報が得られるこれらのプロパティ値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="d9ca1-113">上記の出力をよく見る、重要性の 2 つの点が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="d9ca1-114">最初に、ClientMediaPortRangeEnabled プロパティは False に設定します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="d9ca1-115">重要なため、このプロパティは False に設定、Skype ビジネス クライアントが利用可能なポートの間を使用してポート 1024 から 65535 までの通信セッションに関与する場合(ClientMediaPort や ClientVideoPort などの) 他のポート設定とは無関係です。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="d9ca1-116">場合、ポートの指定したセットの使用を制限する (これは、サービスの品質を実装することを計画する場合に実行するようにするもの)、最初にクライアントのメディア ポート範囲を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="d9ca1-117">次の Windows PowerShell コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="d9ca1-118">上記のコマンドにより、会議の構成設定のグローバル コレクションのクライアントのメディア ポート範囲ただし、これらの設定はサイト スコープやサービス スコープの会議サーバー サービスの場合のみ) にも適用できます。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-118">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="d9ca1-119">セット CsConferencingConfiguration を呼び出すときに、そのサイトまたはサーバーの Id を指定するを有効にするクライアントのメディアのポート範囲を特定のサイトまたはサーバー。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-119">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="d9ca1-120">代わりに、同時にすべての会議構成設定のポート範囲を有効にするのにこのコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="d9ca1-121">2 つ目の重要度が表示されますが、既定では、メディア ポートのネットワーク トラフィックの種類ごとに設定する範囲の例の出力結果が同じであります。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="d9ca1-122">QoS を実装するためには、一意であるこれらのポート範囲の必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-122">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="d9ca1-123">たとえば、次のようにポートの範囲を構成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-123">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9ca1-124">クライアントのトラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="d9ca1-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="d9ca1-125">ポートの開始</span><span class="sxs-lookup"><span data-stu-id="d9ca1-125">Port Start</span></span></th>
<th><span data-ttu-id="d9ca1-126">ポートの範囲</span><span class="sxs-lookup"><span data-stu-id="d9ca1-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9ca1-127">オーディオ</span><span class="sxs-lookup"><span data-stu-id="d9ca1-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="d9ca1-128">50020</span><span class="sxs-lookup"><span data-stu-id="d9ca1-128">50020</span></span></p></td>
<td><p><span data-ttu-id="d9ca1-129">20</span><span class="sxs-lookup"><span data-stu-id="d9ca1-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9ca1-130">ビデオ</span><span class="sxs-lookup"><span data-stu-id="d9ca1-130">Video</span></span></p></td>
<td><p><span data-ttu-id="d9ca1-131">58000</span><span class="sxs-lookup"><span data-stu-id="d9ca1-131">58000</span></span></p></td>
<td><p><span data-ttu-id="d9ca1-132">20</span><span class="sxs-lookup"><span data-stu-id="d9ca1-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9ca1-133">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="d9ca1-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="d9ca1-134">42000</span><span class="sxs-lookup"><span data-stu-id="d9ca1-134">42000</span></span></p></td>
<td><p><span data-ttu-id="d9ca1-135">20</span><span class="sxs-lookup"><span data-stu-id="d9ca1-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9ca1-136">ファイル転送</span><span class="sxs-lookup"><span data-stu-id="d9ca1-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="d9ca1-137">42020</span><span class="sxs-lookup"><span data-stu-id="d9ca1-137">42020</span></span></p></td>
<td><p><span data-ttu-id="d9ca1-138">20</span><span class="sxs-lookup"><span data-stu-id="d9ca1-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d9ca1-139">上記の表では、クライアントのポートの範囲は、サーバー用に構成されたポートの範囲のサブセットを表しています。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="d9ca1-140">たとえば、サーバーで、アプリケーションの共有構成されていた 49151。 40803 のポートを使用するにはクライアントのコンピューターにアプリケーションの共有は、ポートを通じて 42019 42000 を使用する構成します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="d9ca1-141">、すぎる、これは主に、QoS の管理を容易に: クライアントのポートは、サーバー上で使用されるポートのサブセットを表す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="d9ca1-142">(などのクライアント コンピューターに構成できますアプリケーションの共有ポートを使用すると答えると、10019 から 10000。)ただし、お勧めしてクライアントを使用するようにポートの範囲は、サーバーのポート範囲のサブセットです。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="d9ca1-143">さらに、お気付き 8348 ポートが、サーバー上の共有アプリケーションの脇にいたは 20 個のポートが、クライアント上の共有アプリケーションの脇にいたことです。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="d9ca1-144">すぎます、これで、お勧めですが、明確なルールではありません。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="d9ca1-145">表す 1 つの通信セッションごとの利用可能なポートを考慮する一般に、: 対象のコンピューターが関与できることを意味するポートの範囲で使用可能な 100 個のポートがある場合、100 の通信セッションのいずれかの時間が与えられています。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="d9ca1-146">サーバー クライアントよりもより多くの交換の一部がかかるでしょう、ので意味はクライアント上よりもサーバー上の多くのより多くのポートを開きます。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="d9ca1-147">クライアント上の共有アプリケーションのアサイド 20 ポートの設定は、ユーザーが指定したデバイスで、アプリケーション共有セッションを 20 と同時にすべての参加可能性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="d9ca1-148">大多数のユーザーのための十分なのことを証明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="d9ca1-149">会議構成設定のグローバル コレクションには、前述のポート範囲を割り当て、ビジネス サーバー管理シェル コマンドの次の Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="d9ca1-150">または、構成の設定、すべての会議のためのこれらの同じポート範囲を割り当てるにはこのコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="d9ca1-151">個々 のユーザーは、ビジネスの Skype からログオフし、再度ログオンこれらの変更が実際に有効にするにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="d9ca1-152">クライアントのメディア ポート範囲を有効にし、1 つのコマンドを使用してこれらのポート範囲を割り当てることがことができます。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="d9ca1-153">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="d9ca1-154">10 の Windows で実行されているクライアントのサービスの品質ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="d9ca1-155">ビジネス クライアント用の Skype で使用するポート範囲を指定するだけでなく、クライアント コンピューターに適用される個別のサービスの品質ポリシーを作成することもする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="d9ca1-156">(会議、アプリケーション、および仲介サーバー用に作成されたサービスの品質ポリシーする必要がありますいないするクライアント コンピューターに適用します。)この情報は、ビジネス クライアント用の Skype と 10 の Windows を実行しているコンピューターにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="d9ca1-157">次の使用例は、オーディオ ポリシーとビデオ ポリシーを作成するのにはこのポートの範囲のセットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9ca1-158">クライアントのトラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="d9ca1-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="d9ca1-159">ポートの開始</span><span class="sxs-lookup"><span data-stu-id="d9ca1-159">Port Start</span></span></th>
<th><span data-ttu-id="d9ca1-160">ポートの範囲</span><span class="sxs-lookup"><span data-stu-id="d9ca1-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9ca1-161">オーディオ</span><span class="sxs-lookup"><span data-stu-id="d9ca1-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="d9ca1-162">50020</span><span class="sxs-lookup"><span data-stu-id="d9ca1-162">50020</span></span></p></td>
<td><p><span data-ttu-id="d9ca1-163">20</span><span class="sxs-lookup"><span data-stu-id="d9ca1-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9ca1-164">ビデオ</span><span class="sxs-lookup"><span data-stu-id="d9ca1-164">Video</span></span></p></td>
<td><p><span data-ttu-id="d9ca1-165">58000</span><span class="sxs-lookup"><span data-stu-id="d9ca1-165">58000</span></span></p></td>
<td><p><span data-ttu-id="d9ca1-166">20</span><span class="sxs-lookup"><span data-stu-id="d9ca1-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9ca1-167">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="d9ca1-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="d9ca1-168">42000</span><span class="sxs-lookup"><span data-stu-id="d9ca1-168">42000</span></span></p></td>
<td><p><span data-ttu-id="d9ca1-169">20</span><span class="sxs-lookup"><span data-stu-id="d9ca1-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9ca1-170">ファイル転送</span><span class="sxs-lookup"><span data-stu-id="d9ca1-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="d9ca1-171">42020</span><span class="sxs-lookup"><span data-stu-id="d9ca1-171">42020</span></span></p></td>
<td><p><span data-ttu-id="d9ca1-172">20</span><span class="sxs-lookup"><span data-stu-id="d9ca1-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d9ca1-173">10 の Windows コンピューターのサービスの品質の音声ポリシーを作成するには、まずコンピューターにログオン、グループ ポリシーの管理がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="d9ca1-174">グループ ポリシーの管理] を開きます ([**スタート**] ボタン、 **[管理ツール**] をポイントし、[**グループ ポリシーの管理**] をクリック) し、次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="d9ca1-175">グループ ポリシーの管理では、新しいポリシーを作成するコンテナーを探します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="d9ca1-176">たとえば、OU という名前のクライアントには、すべてのクライアント コンピューターが存在する場合、クライアント OU で新しいポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="d9ca1-177">適切なコンテナーを右クリックし、**このドメインに GPO を作成しここにリンク**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="d9ca1-178">**新しい GPO** ] ダイアログ ボックスで **[名前**] ボックスに新しいグループ ポリシー オブジェクトの名前を入力し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="d9ca1-179">新しく作成したポリシーを右クリックし、し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="d9ca1-180">グループ ポリシー管理エディターで、**コンピューター**の構成**Windows の設定**を展開し、**ポリシー ベースの QoS**を右クリックし、**新規ポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="d9ca1-181">**ポリシー ベースの QoS** ] ダイアログ ボックスで [開始] ページで、 **[名前**] ボックスで新しいポリシーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="d9ca1-182">**DSCP 値を指定**を選択し、 **46**に値を設定します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="d9ca1-183">オフの場合、**アウト バウンドのスロットル率を指定**のままにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="d9ca1-184">次のページでは、**すべてのアプリケーション**が選択されているかどうかを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-184">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="d9ca1-185">この設定は、特定のアプリケーションによって作成された、46 のだけではなくパケットの DSCP のマークが付いたすべてのパケットを検索するネットワークを指示します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-185">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

8.  <span data-ttu-id="d9ca1-186">3 番目のページでは、**任意の発信元 IP アドレス**と**宛先の IP アドレス**の両方が選択されているし、[**次へ**] をクリックを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="d9ca1-187">これら 2 つの設定では、パケットが管理されることを確認してどのコンピューター (IP アドレス) は、これらのパケットを送信し、これらのパケットをどのコンピューター (IP アドレス) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="d9ca1-188">[4] ページでは、**この QoS ポリシーを適用するプロトコルを選択して**ドロップダウン リストから**TCP および UDP**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="d9ca1-189">TCP (伝送制御プロトコル) と UDP (ユーザー データグラム プロトコル) は、最も一般的使用 Skype ビジネス サーバーとそのクライアント アプリケーションの 2 つのネットワーク プロトコルです。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="d9ca1-190">**発信元ポート番号の指定**の見出しの下には、**この送信元ポートまたは範囲から**選択します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-190">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="d9ca1-191">付随するテキスト ボックスで、オーディオの転送用に予約されたポートの範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-191">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="d9ca1-192">たとえば、~ 50020 のポートを予約する場合は、ポート 50039 音声トラフィックがこの形式を使用してポート範囲を入力して、: **50020:50039**。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-192">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="d9ca1-193">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-193">Click **Finish**.</span></span>

<span data-ttu-id="d9ca1-194">オーディオの QoS ポリシーを作成した後、ビデオの 2 番目のポリシーを作成してください。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-194">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="d9ca1-195">ビデオのポリシーを作成するにした後に、オーディオのポリシーを作成するときにこれらの置換を行うと同じ基本的な手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-195">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="d9ca1-196">別など固有のポリシーの名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="d9ca1-197">46 ではなく**34** DSCP 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-197">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="d9ca1-198">(前述のように、34 の DSCP 値を使用する必要はありません。 単にオーディオを使用したものの別の DSCP 値を割り当てる必要があります)</span><span class="sxs-lookup"><span data-stu-id="d9ca1-198">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="d9ca1-199">ビデオのトラフィックには、以前に構成されたポートの範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="d9ca1-200">、58019 のビデオでは、ポート 58000 で確保されている、設定ポートの範囲になります: **58000:58019**。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="d9ca1-201">アプリケーション共有トラフィックを管理するポリシーを作成する場合は、これらの置換を行います。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="d9ca1-202">異なる (そして固有) のポリシーの名前 (たとえば、**ビジネス サーバー アプリケーションを共有するための Skype**) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="d9ca1-203">46 ではなく**24**に DSCP 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-203">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="d9ca1-204">(再度、この値を 24 にする必要はありません、単純にする必要がありますオーディオおよびビデオのために使用する DSCP 値とは異なる)。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-204">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="d9ca1-205">ビデオのトラフィックには、以前に構成されたポートの範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="d9ca1-206">などのポート 42000 42019 アプリケーションを共有するため、確保されている場合、このポートの範囲をこれに設定: **42000:42019**。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="d9ca1-207">ファイル転送ポリシー。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="d9ca1-208">異なる (そして固有) のポリシーの名前 (たとえば、**ビジネスのサーバー間のファイル転送の Skype**) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="d9ca1-209">**14**DSCP 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="d9ca1-210">(もう一度、この値を 14 にする必要はありません。 単に DSCP コードが、一意でなければなりません)</span><span class="sxs-lookup"><span data-stu-id="d9ca1-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="d9ca1-211">アプリケーションを以前に構成されたポートの範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="d9ca1-212">などのポート 42020 42039 アプリケーションを共有するため、確保されている場合、このポートの範囲をこれに設定: **42020:42039**。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="d9ca1-213">クライアント コンピューターにグループ ポリシーを更新するまで、作成した新しいポリシーは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-213">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="d9ca1-214">グループ ポリシーは定期的に自動更新されますが、グループ ポリシーを更新する必要がある各コンピューター上で次のコマンドを実行すると、即座に強制的に更新することができます。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-214">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="d9ca1-215">このコマンドは、管理者の資格情報のもとで実行されているコマンド ウィンドウから実行できます。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-215">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="d9ca1-216">管理者の資格情報のもとでコマンド ウィンドウを開くには、[**スタート**] メニューをクリックし、[**コマンド プロンプト**] を右クリックして、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-216">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="d9ca1-217">クライアント コンピューターにこれらのポリシーの対象とすることに留意してください。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="d9ca1-218">ビジネス サーバーの Skype を実行するサーバーに適用する必要がありますされません。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="d9ca1-219">ネットワーク パケットが DSCP 値でマークされていることを確認するには、次の手順を完了して新しいレジストリ エントリの各コンピューターで作成することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="d9ca1-220">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="d9ca1-221">**実行**] ダイアログ ボックスで **「regedit」** と入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="d9ca1-222">レジストリ エディターで、拡張**HKEY\_ローカル\_マシン**、**システム**を展開し、 **CurrentControlSet**を展開し、**サービス**の展開および**Tcpip**を展開し、します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="d9ca1-223">**Tcpip**] を右クリックして、**新規**作成] をポイントし、[**キー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="d9ca1-224">新しいレジストリ キーが作成されるは、 **QoS**を入力し、enter キーを押してキーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="d9ca1-225">**QoS**を右クリックし、**新規**作成] をポイントし、[**文字列値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="d9ca1-226">新しいレジストリ値を作成すると後、は、 **NLA を使用しない**を入力し、値の名前を変更するのには ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="d9ca1-227">**NLA を使用しない**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="d9ca1-228">**文字列の編集**] ダイアログ ボックスで、[**値データ**] ボックスに**1**を入力し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="d9ca1-229">コンピューター eboot とレジストリ エディターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="d9ca1-230">複数のネットワーク アダプターを持つコンピューターでサービスの品質を構成します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="d9ca1-231">複数のネットワーク アダプターを搭載したコンピューターがあれば、場合によってを実行できます構成されている値ではなく、DSCP 値が 0x00 として表示される場所の問題に。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="d9ca1-232">これが 1 つまたは複数のネットワーク アダプターがない (たとえば、プライベート ネットワークには、これらのアダプターが使用される) 場合、Active Directory ドメインにアクセスできないコンピューターで通常発生します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="d9ca1-233">このような場合は、DSCP 値はタグをドメインにアクセスできますが、タグが付いていないドメインにアクセスできないようにアダプターのアダプターをできます。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="d9ca1-234">自分のドメインにアクセスを持たないアダプターを含む、コンピューター内のすべてのネットワーク アダプターの DSCP 値をタグにしたい場合は、追加し、レジストリに値を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="d9ca1-235">行うには、次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="d9ca1-236">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="d9ca1-237">**実行**] ダイアログ ボックスで **「regedit」** と入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="d9ca1-238">レジストリ エディターで、拡張**HKEY\_ローカル\_マシン**、**システム**を展開し、 **CurrentControlSet**を展開し、**サービス**の展開および**Tcpip**を展開し、します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="d9ca1-239">**Tcpip**] を右クリックし、 **QoS**をラベル付けされたレジストリ キーがない場合は、**新規**作成] をポイントし、**キー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="d9ca1-240">新しいキーが作成されるは、 **QoS**を入力し、enter キーを押してキーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="d9ca1-241">**QoS**を右クリックし、**新規**作成] をポイントし、[**文字列値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="d9ca1-242">新しいレジストリ値を作成すると後、は、 **NLA を使用しない**を入力し、値の名前を変更するのには ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="d9ca1-243">**NLA を使用しない**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="d9ca1-244">**文字列の編集**] ダイアログ ボックスで、[**値データ**] ボックスに**1**を入力し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="d9ca1-245">作成し、新しいレジストリ値を構成する、変更を反映させるには、コンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9ca1-246">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9ca1-246">See also</span></span>

[<span data-ttu-id="d9ca1-247">10 の Windows でグループ ポリシー オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)

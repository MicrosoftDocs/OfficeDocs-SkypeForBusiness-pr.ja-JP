---
title: クライアントのポート範囲とサービス品質ポリシーの構成
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
f1.keywords:
- NOCSH
localization_priority: Normal
description: この記事では、クライアントのポート範囲を構成する方法と、Windows 10 で実行しているクライアントのために Skype for Business Server でサービスの品質 (Qos) ポリシーを構成する方法について説明します。
ms.openlocfilehash: 95fe768333a01aff165e74eec334f14bf23d69dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045890"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="69bdf-103">Skype for Business Server でのクライアントのポート範囲とサービス品質ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="69bdf-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="69bdf-104">この記事では、クライアントのポート範囲を構成する方法と、Windows 10 で実行しているクライアントのために Skype for Business Server でサービスの品質 (Qos) ポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="69bdf-105">ポート範囲を構成する</span><span class="sxs-lookup"><span data-stu-id="69bdf-105">Configure port ranges</span></span>

<span data-ttu-id="69bdf-106">既定では、Skype for Business クライアントアプリケーションは、通信セッションに参加するときにポート1024と65535の間の任意のポートを使用できます。これは、特定のポート範囲がクライアントに対して自動的に有効にならないためです。</span><span class="sxs-lookup"><span data-stu-id="69bdf-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="69bdf-107">ただし、サービスの品質を使用するためには、さまざまな種類のトラフィック (オーディオ、ビデオ、メディア、アプリケーション共有、およびファイル転送) を一連の固有のポート範囲に再割り当てする必要があります。</span><span class="sxs-lookup"><span data-stu-id="69bdf-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="69bdf-108">これは、Get-csconferencingconfiguration コマンドレットを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="69bdf-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="69bdf-109">エンドユーザーは、これらの変更を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="69bdf-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="69bdf-110">ポートの変更は、管理者のみが Get-csconferencingconfiguration コマンドレットを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="69bdf-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="69bdf-111">現在通信セッションで使用されているポート範囲を確認するには、Skype for Business Server 管理シェルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="69bdf-112">Skype for Business Server をインストールした後に会議の設定を変更していない場合は、次のプロパティ値を含む情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="69bdf-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="69bdf-113">ここに示した出力には、重要な情報が 2 つ含まれています。</span><span class="sxs-lookup"><span data-stu-id="69bdf-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="69bdf-114">1 つ目は、ClientMediaPortRangeEnabled プロパティが False に設定されていることです。</span><span class="sxs-lookup"><span data-stu-id="69bdf-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="69bdf-115">このプロパティが False に設定されている場合、Skype for Business クライアントは通信セッションに参加するときにポート1024と65535の間で使用可能なポートを使用します。これは、他のポート設定 (たとえば、ClientMediaPort または ClientVideoPort) に関係なく該当します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="69bdf-116">指定したポートセットの使用を制限する場合 (これは、サービスの品質を実装することを計画している場合に実行します)、まずクライアントのメディアポート範囲を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="69bdf-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="69bdf-117">これは、次の Windows PowerShell コマンドを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="69bdf-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="69bdf-p105">上記のコマンドを実行すると、会議の構成設定のグローバル コレクションに対してクライアントのメディア ポート範囲が有効化されます。ただし、これらの設定は、サイト範囲またはサービスの範囲 (電話会議サーバー サービスのみ) に対しても適用できます。特定のサイトまたはサーバーに対してクライアントのメディア ポート範囲を有効にするには、Set-CsConferencingConfiguration の呼び出し時にそのサイトまたはサーバーの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-p105">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only). To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="69bdf-120">次のコマンドを使用して、会議のすべての構成設定に対して同時にポート範囲を有効化することもできます。</span><span class="sxs-lookup"><span data-stu-id="69bdf-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="69bdf-121">2 つ目の重要な情報は、サンプルの出力では、既定で、各種類のネットワーク トラフィックに対して同じメディア ポート範囲が設定されていることです。</span><span class="sxs-lookup"><span data-stu-id="69bdf-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="69bdf-p106">QoS を実装するためには、これらの各ポート範囲が一意であることが必要です。たとえば、次のようにポート範囲を構成します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-p106">In order to implement QoS, each of these port ranges will need to be unique. For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69bdf-124">クライアント トラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="69bdf-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="69bdf-125">開始ポート</span><span class="sxs-lookup"><span data-stu-id="69bdf-125">Port Start</span></span></th>
<th><span data-ttu-id="69bdf-126">ポート範囲</span><span class="sxs-lookup"><span data-stu-id="69bdf-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69bdf-127">オーディオ</span><span class="sxs-lookup"><span data-stu-id="69bdf-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="69bdf-128">50020</span><span class="sxs-lookup"><span data-stu-id="69bdf-128">50020</span></span></p></td>
<td><p><span data-ttu-id="69bdf-129">1280</span><span class="sxs-lookup"><span data-stu-id="69bdf-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bdf-130">ビデオ</span><span class="sxs-lookup"><span data-stu-id="69bdf-130">Video</span></span></p></td>
<td><p><span data-ttu-id="69bdf-131">58000</span><span class="sxs-lookup"><span data-stu-id="69bdf-131">58000</span></span></p></td>
<td><p><span data-ttu-id="69bdf-132">1280</span><span class="sxs-lookup"><span data-stu-id="69bdf-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bdf-133">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="69bdf-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="69bdf-134">42000</span><span class="sxs-lookup"><span data-stu-id="69bdf-134">42000</span></span></p></td>
<td><p><span data-ttu-id="69bdf-135">1280</span><span class="sxs-lookup"><span data-stu-id="69bdf-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bdf-136">ファイル送信</span><span class="sxs-lookup"><span data-stu-id="69bdf-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="69bdf-137">42020</span><span class="sxs-lookup"><span data-stu-id="69bdf-137">42020</span></span></p></td>
<td><p><span data-ttu-id="69bdf-138">1280</span><span class="sxs-lookup"><span data-stu-id="69bdf-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="69bdf-139">上記の表では、クライアントのポート範囲はサーバーに構成されたポート範囲のサブセットを表しています。</span><span class="sxs-lookup"><span data-stu-id="69bdf-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="69bdf-140">たとえば、サーバーではアプリケーション共有が 40803 ～ 49151 のポートを使用するように構成されており、クライアント コンピューターではアプリケーション共有が 42000 ～ 42019 のポートを使用するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="69bdf-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="69bdf-141">これも、主に QoS の管理を容易にするために行われています。クライアントポートは、サーバーで使用されるポートのサブセットを表す必要がありません。</span><span class="sxs-lookup"><span data-stu-id="69bdf-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="69bdf-142">(たとえば、クライアントコンピューター上で、ポート 1万 ~ 10019 を使用するようにアプリケーション共有を構成することができます)。ただし、クライアントのポート範囲をサーバーのポート範囲のサブセットにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="69bdf-143">さらに、サーバー上でのアプリケーション共有のために8348ポートが確保されていても、クライアント上でのアプリケーション共有に関しては20個のポートしか設定されていないことに気付いたかもしれません。</span><span class="sxs-lookup"><span data-stu-id="69bdf-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="69bdf-144">これも、推奨されていますが、ハードおよび高速ルールではありません。</span><span class="sxs-lookup"><span data-stu-id="69bdf-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="69bdf-145">一般に、1つの通信セッションを表すために使用可能な各ポートを考慮することができます。ポート範囲に100のポートを使用できる場合は、そのコンピューターがいつでも最大で100の通信セッションに参加できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="69bdf-146">サーバーは、多くの場合、クライアントよりも多くの会話に参加しているので、クライアントよりも多くのポートをサーバーで開くことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="69bdf-147">クライアントでアプリケーション共有用に20個のポートを設定することは、1人のユーザーが、指定されたデバイスで20個のアプリケーション共有セッションに参加でき、同時にすべて同時に参加できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="69bdf-148">ユーザーの大部分に十分な証明を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69bdf-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="69bdf-149">会議構成設定のグローバルコレクションに上記のポート範囲を割り当てるには、次の Skype for Business Server 管理シェルコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="69bdf-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="69bdf-150">または、次のコマンドを使用して、この同じポート範囲を会議のすべての構成設定に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="69bdf-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="69bdf-151">個々のユーザーが Skype for Business からログオフしてから再度ログオンする必要があります。これらの変更は実際に有効になります。</span><span class="sxs-lookup"><span data-stu-id="69bdf-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="69bdf-152">1 つのコマンドで、クライアントのメディア ポート範囲を有効化し、これらのポート範囲を割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="69bdf-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="69bdf-153">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="69bdf-154">Windows 10 で実行しているクライアントのサービスの品質ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="69bdf-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="69bdf-155">Skype for Business クライアントで使用するポート範囲を指定することに加えて、クライアントコンピューターに適用されるサービスの品質を個別に作成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="69bdf-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="69bdf-156">(会議、アプリケーション、および仲介サーバー用に作成されたサービスの品質をクライアントコンピューターに適用する必要はありません)。この情報は、Skype for Business クライアントと Windows 10 を実行しているコンピューターにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="69bdf-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="69bdf-157">次の例では、このポート範囲のセットを使用して、オーディオ ポリシーとビデオ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69bdf-158">クライアント トラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="69bdf-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="69bdf-159">開始ポート</span><span class="sxs-lookup"><span data-stu-id="69bdf-159">Port Start</span></span></th>
<th><span data-ttu-id="69bdf-160">ポート範囲</span><span class="sxs-lookup"><span data-stu-id="69bdf-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69bdf-161">オーディオ</span><span class="sxs-lookup"><span data-stu-id="69bdf-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="69bdf-162">50020</span><span class="sxs-lookup"><span data-stu-id="69bdf-162">50020</span></span></p></td>
<td><p><span data-ttu-id="69bdf-163">1280</span><span class="sxs-lookup"><span data-stu-id="69bdf-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bdf-164">ビデオ</span><span class="sxs-lookup"><span data-stu-id="69bdf-164">Video</span></span></p></td>
<td><p><span data-ttu-id="69bdf-165">58000</span><span class="sxs-lookup"><span data-stu-id="69bdf-165">58000</span></span></p></td>
<td><p><span data-ttu-id="69bdf-166">1280</span><span class="sxs-lookup"><span data-stu-id="69bdf-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bdf-167">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="69bdf-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="69bdf-168">42000</span><span class="sxs-lookup"><span data-stu-id="69bdf-168">42000</span></span></p></td>
<td><p><span data-ttu-id="69bdf-169">1280</span><span class="sxs-lookup"><span data-stu-id="69bdf-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bdf-170">ファイル送信</span><span class="sxs-lookup"><span data-stu-id="69bdf-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="69bdf-171">42020</span><span class="sxs-lookup"><span data-stu-id="69bdf-171">42020</span></span></p></td>
<td><p><span data-ttu-id="69bdf-172">1280</span><span class="sxs-lookup"><span data-stu-id="69bdf-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="69bdf-173">Windows 10 コンピューターのサービス品質のオーディオポリシーを作成するには、まずグループポリシー管理がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="69bdf-174">グループポリシーの管理を開きます ([**スタート**] をクリックし、[**管理ツール**] をポイントし、[**グループポリシーの管理**] をクリックします)。次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="69bdf-175">[グループ ポリシーの管理] で、新しいポリシーを作成する必要のあるコンテナーを探します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="69bdf-176">たとえば、すべてのクライアントコンピューターがクライアントという名前の OU に配置されている場合は、クライアント OU に新しいポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69bdf-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="69bdf-177">適切なコンテナーを右クリックし、[**このドメインに GPO を作成し、ここにリンクする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="69bdf-178">[**新しい GPO** ] ダイアログボックスで、[**名前**] ボックスに新しいグループポリシーオブジェクトの名前を入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="69bdf-179">新しく作成したポリシーを右クリックし、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="69bdf-180">グループポリシー管理エディターで、[**コンピューターの構成**]、[ **Windows の設定**] の順に展開し、[**ポリシーベースの QoS**] を右クリックして、[**新規ポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="69bdf-181">[**ポリシーベースの QoS** ] ダイアログボックスの [開始] ページで、[**名前**] ボックスに新しいポリシーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="69bdf-182">[**DSCP 値を指定する**] を選択し、値を **46** に設定します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="69bdf-183">[**出力方向のスロットル率を指定する**] をオフのままにして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="69bdf-184">次のページで、[**この実行可能ファイル名を持つアプリケーションのみ**] を選択し、名前として「 **Lync.** 」と入力して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-184">On the next page, select **Only applications with this executable name**, enter **Lync.exe** as the name, and then click **Next**.</span></span> <span data-ttu-id="69bdf-185">この設定では、Skype for Business クライアントからの一致するトラフィックのみに優先順位を付けるようにポリシーに指示します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-185">This setting instructs the policy to only prioritize matching traffic from the Skype for Business client.</span></span>

8.  <span data-ttu-id="69bdf-186">3番目のページで、[**送信元 ip アドレス**] と [**宛先 ip アドレス**] の両方が選択されていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="69bdf-187">この 2 つの設定により、これらのパケットを送信したコンピューター (IP アドレス) やこれらのパケットを受信するコンピューター (IP アドレス) にかかわらず、パケットが管理されます。</span><span class="sxs-lookup"><span data-stu-id="69bdf-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="69bdf-188">4 番目のページで、[**この QoS ポリシーを適用するプロトコルを選択してください**] ドロップダウン リストから [**TCP と UDP**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="69bdf-189">TCP (伝送制御プロトコル) と UDP (ユーザーデータグラムプロトコル) は、Skype for Business Server およびそのクライアントアプリケーションで最も一般的に使用される2つのネットワークプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="69bdf-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="69bdf-p117">[**発信元ポート番号を指定してください**] という見出しの下にある [**次の発信元ポート番号か範囲**] を選択します。付随するテキスト ボックスに、オーディオ送信用に予約されたポート範囲を入力します。たとえば、50020 から 50039 までのポートをオーディオ トラフィック用に予約した場合は、「**50020:50039**」という形式でポート範囲を入力します。[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-p117">Under the heading **Specify the source port number**, select **From this source port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**. Click **Finish**.</span></span>

<span data-ttu-id="69bdf-p118">オーディオ用の QoS ポリシーを作成した後で、2 番目にビデオ用のポリシーを作成する必要があります。ビデオ用のポリシーを作成するには、オーディオ ポリシーを作成したときと基本的には同じ手順に従い、次の点を変えます。</span><span class="sxs-lookup"><span data-stu-id="69bdf-p118">After you have created the QoS policy for audio you should then create a second policy for video. To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="69bdf-196">異なる (一意の) ポリシー名を使用します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="69bdf-p119">DSCP の値を 46 ではなく「**34**」に設定します。(前に説明したとおり、DSCP の値に 34 を使用する必要はありません。ただ、オーディオに使用したのとは異なる DSCP の値を割り当てる必要があります。)</span><span class="sxs-lookup"><span data-stu-id="69bdf-p119">Set the DSCP value to **34** instead of 46. (As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="69bdf-199">ビデオトラフィックに対して以前に構成されたポート範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="69bdf-200">たとえば、ビデオに対してポート 58000 ~ 58019 を予約している場合は、ポート範囲を次のように設定します。 **58000:58019**。</span><span class="sxs-lookup"><span data-stu-id="69bdf-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="69bdf-201">アプリケーション共有トラフィックを管理するポリシーを作成する場合は、次のように置き換えます。</span><span class="sxs-lookup"><span data-stu-id="69bdf-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="69bdf-202">別の (一意の) ポリシー名 (たとえば、 **Skype For Business Server アプリケーション共有**) を使用します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="69bdf-p121">DSCP の値を 46 ではなく「**24**」に設定します。(この値も 24 にする必要はありません。ただ、オーディオとビデオに使用した DSCP の値とは別にする必要があります。)</span><span class="sxs-lookup"><span data-stu-id="69bdf-p121">Set the DSCP value to **24** instead of 46. (Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="69bdf-205">ビデオトラフィックに対して以前に構成されたポート範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="69bdf-206">たとえば、アプリケーション共有用にポート 42000 ~ 42019 を予約している場合は、ポート範囲を次のように設定します。 **42000:42019**。</span><span class="sxs-lookup"><span data-stu-id="69bdf-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="69bdf-207">ファイル転送ポリシーは次のようにします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="69bdf-208">別の (一意の) ポリシー名 (たとえば、 **Skype For Business Server ファイル転送**) を使用します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="69bdf-209">DSCP 値を**14**に設定します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="69bdf-210">(この値は、14にする必要はありません。また、単に一意の DSCP コードでなければなりません)。</span><span class="sxs-lookup"><span data-stu-id="69bdf-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="69bdf-211">アプリケーションに対して以前に構成したポート範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="69bdf-212">たとえば、アプリケーション共有用にポート 42020 ~ 42039 を予約している場合は、ポート範囲を次のように設定します。 **42020:42039**。</span><span class="sxs-lookup"><span data-stu-id="69bdf-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="69bdf-p125">新しく作成したポリシーは、クライアント コンピューター上でグループ ポリシーが更新されるまで有効になりません。グループ ポリシーは定期的に自動更新を行いますが、グループ ポリシーの更新が必要な各コンピューター上で次のコマンドを実行することにより、強制的に即時更新できます。</span><span class="sxs-lookup"><span data-stu-id="69bdf-p125">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="69bdf-p126">このコマンドは、管理者の資格情報で実行されていれば、どのコマンド ウィンドウからでも実行できます。コマンド ウィンドウを管理者の資格情報で実行するには、[**スタート**]をクリックして、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-p126">This command can be run from any command window that is running under administrator credentials. To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="69bdf-217">なお、これらのポリシーが対象とするのはクライアント コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="69bdf-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="69bdf-218">これらは、Skype for Business Server を実行しているサーバーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="69bdf-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="69bdf-219">ネットワーク パケットが適切な DSCP 値でマークされるようにするには、次の手順を実行して、各コンピューターに新しいレジストリ エントリを作成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="69bdf-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="69bdf-220">**[スタート]** ボタンをクリックし、 **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="69bdf-221">[**実行**] ダイアログボックスで、「 **regedit**」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="69bdf-222">レジストリエディターで、[ **HKEY\_LOCAL\_MACHINE**] を展開し、[**システム**] を展開し、[ **CurrentControlSet**] を展開し、[**サービス**] を展開して、[ **Tcpip**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="69bdf-223">[**Tcpip**] を右クリックし、[**新規**] をポイントして [**キー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="69bdf-224">新しいレジストリキーを作成したら、「 **QoS**」と入力し、enter キーを押してキーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="69bdf-225">[**QoS**] を右クリックし、[**新規**] をポイントして [**文字列値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="69bdf-226">新しいレジストリ値が作成されたら、 **NLA を使用しない**と入力し、enter キーを押して値の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="69bdf-227">[**Do no use NLA**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="69bdf-228">[**文字列の編集**] ダイアログボックスで、[**値のデータ**] ボックスに「 **1** 」と入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="69bdf-229">レジストリエディターを閉じ、コンピューターを起動します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="69bdf-230">複数のネットワークアダプターがあるコンピューターでサービスの品質を構成する</span><span class="sxs-lookup"><span data-stu-id="69bdf-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="69bdf-231">複数のネットワークアダプターを備えたコンピューターがある場合は、構成された値ではなく0x00 として DSCP 値が表示される問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="69bdf-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="69bdf-232">通常、このような表示になるのは、1 つ以上のネットワーク アダプターが Active Directory ドメインにアクセスできないコンピューターです (たとえば、アダプターがプライベート ネットワークに使用されている場合)。</span><span class="sxs-lookup"><span data-stu-id="69bdf-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="69bdf-233">そのような場合、ドメインへアクセスできるアダプターには DSCP の値がマークされますが、ドメインへアクセスできないアダプターにはマークされません。</span><span class="sxs-lookup"><span data-stu-id="69bdf-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="69bdf-234">ドメインにアクセスできないアダプターを含む、コンピューター内のすべてのネットワークアダプターの DSCP 値にタグを付ける場合は、レジストリに値を追加して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69bdf-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="69bdf-235">このためには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="69bdf-236">**[スタート]** ボタンをクリックし、 **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="69bdf-237">[**実行**] ダイアログボックスで、「 **regedit**」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="69bdf-238">レジストリエディターで、[ **HKEY\_LOCAL\_MACHINE**] を展開し、[**システム**] を展開し、[ **CurrentControlSet**] を展開し、[**サービス**] を展開して、[ **Tcpip**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="69bdf-239">「**QoS**」というレジストリ キーがない場合は、 [**Tcpip**] 右クリックし、[**新規**] をポイントして、[**キー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="69bdf-240">新しいキーを作成したら、「 **QoS**」と入力し、enter キーを押してキーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="69bdf-241">[**QoS**] を右クリックし、[**新規**] をポイントして [**文字列値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="69bdf-242">新しいレジストリ値が作成されたら、 **NLA を使用しない**と入力し、enter キーを押して値の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="69bdf-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="69bdf-243">[**Do no use NLA**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="69bdf-244">[**文字列の編集**] ダイアログボックスで、[**値のデータ**] ボックスに「 **1** 」と入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69bdf-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="69bdf-245">新しいレジストリ値を作成して構成した後、変更を有効にするためにコンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69bdf-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="69bdf-246">関連項目</span><span class="sxs-lookup"><span data-stu-id="69bdf-246">See also</span></span>

[<span data-ttu-id="69bdf-247">Windows 10 でグループポリシーオブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="69bdf-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)

---
title: クライアントのポート範囲とサービス品質ポリシーの構成
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: この記事では、クライアントのポート範囲を構成し、Windows 10 で実行されているクライアントの Skype for Business Server でサービス品質ポリシーを構成する方法について説明します。
ms.openlocfilehash: b2961193bef799742ac3b79a4f421a7aa50c5a03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814207"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="c29fb-103">Skype for Business Server でのクライアントのポート範囲とサービス品質ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="c29fb-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="c29fb-104">この記事では、クライアントのポート範囲を構成し、Windows 10 で実行されているクライアントの Skype for Business Server でサービス品質ポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="c29fb-105">ポート範囲を構成する</span><span class="sxs-lookup"><span data-stu-id="c29fb-105">Configure port ranges</span></span>

<span data-ttu-id="c29fb-106">既定では、Skype for Business クライアント アプリケーションは、通信セッションに参加するときにポート 1024 とポート 65535 の間の任意のポートを使用できます。これは、特定のポート範囲がクライアントに対して自動的に有効になっていないためです。</span><span class="sxs-lookup"><span data-stu-id="c29fb-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="c29fb-107">ただし、サービスの品質を使用するには、さまざまなトラフィックの種類 (オーディオ、ビデオ、メディア、アプリケーション共有、ファイル転送) を一連の一意のポート範囲に再割り当てする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c29fb-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="c29fb-108">これは、次のコマンドレットを使用Set-CsConferencingConfigurationできます。</span><span class="sxs-lookup"><span data-stu-id="c29fb-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="c29fb-109">エンド ユーザーは、これらの変更を自分で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c29fb-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="c29fb-110">ポートの変更は、管理者が Set-CsConferencingConfigurationできます。</span><span class="sxs-lookup"><span data-stu-id="c29fb-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="c29fb-111">Skype for Business Server 管理シェル内から次のコマンドを実行して、通信セッションに現在使用されているポート範囲を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c29fb-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="c29fb-112">Skype for Business Server のインストール以降に会議設定に変更を加えしていない場合は、次のプロパティ値を含む情報を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c29fb-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="c29fb-113">ここに示した出力には、重要な情報が 2 つ含まれています。</span><span class="sxs-lookup"><span data-stu-id="c29fb-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="c29fb-114">1 つ目は、ClientMediaPortRangeEnabled プロパティが False に設定されていることです。</span><span class="sxs-lookup"><span data-stu-id="c29fb-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="c29fb-115">このプロパティが False に設定されている場合、Skype for Business クライアントは通信セッションに参加するときにポート 1024 から 65535 の間で使用可能なポートを使用するため、これは重要です。これは、その他のポート設定 (ClientMediaPort や ClientVideoPort など) に関係なく true です。</span><span class="sxs-lookup"><span data-stu-id="c29fb-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="c29fb-116">使用を指定したポートのセットに制限する場合 (サービスの品質の実装を計画している場合は、この操作を行う必要があります)、最初にクライアント メディア ポート範囲を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c29fb-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="c29fb-117">これは、次のコマンドを使用してWindows PowerShellできます。</span><span class="sxs-lookup"><span data-stu-id="c29fb-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="c29fb-p105">上記のコマンドを実行すると、会議の構成設定のグローバル コレクションに対してクライアントのメディア ポート範囲が有効化されます。ただし、これらの設定は、サイト範囲またはサービスの範囲 (電話会議サーバー サービスのみ) に対しても適用できます。特定のサイトまたはサーバーに対してクライアントのメディア ポート範囲を有効にするには、Set-CsConferencingConfiguration の呼び出し時にそのサイトまたはサーバーの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-p105">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only). To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="c29fb-120">次のコマンドを使用して、会議のすべての構成設定に対して同時にポート範囲を有効化することもできます。</span><span class="sxs-lookup"><span data-stu-id="c29fb-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="c29fb-121">2 つ目の重要な情報は、サンプルの出力では、既定で、各種類のネットワーク トラフィックに対して同じメディア ポート範囲が設定されていることです。</span><span class="sxs-lookup"><span data-stu-id="c29fb-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="c29fb-p106">QoS を実装するためには、これらの各ポート範囲が一意であることが必要です。たとえば、次のようにポート範囲を構成します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-p106">In order to implement QoS, each of these port ranges will need to be unique. For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c29fb-124">クライアント トラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="c29fb-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="c29fb-125">開始ポート</span><span class="sxs-lookup"><span data-stu-id="c29fb-125">Port Start</span></span></th>
<th><span data-ttu-id="c29fb-126">ポート範囲</span><span class="sxs-lookup"><span data-stu-id="c29fb-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c29fb-127">オーディオ</span><span class="sxs-lookup"><span data-stu-id="c29fb-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="c29fb-128">50020</span><span class="sxs-lookup"><span data-stu-id="c29fb-128">50020</span></span></p></td>
<td><p><span data-ttu-id="c29fb-129">20</span><span class="sxs-lookup"><span data-stu-id="c29fb-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c29fb-130">ビデオ</span><span class="sxs-lookup"><span data-stu-id="c29fb-130">Video</span></span></p></td>
<td><p><span data-ttu-id="c29fb-131">58000</span><span class="sxs-lookup"><span data-stu-id="c29fb-131">58000</span></span></p></td>
<td><p><span data-ttu-id="c29fb-132">20</span><span class="sxs-lookup"><span data-stu-id="c29fb-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c29fb-133">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="c29fb-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="c29fb-134">42000</span><span class="sxs-lookup"><span data-stu-id="c29fb-134">42000</span></span></p></td>
<td><p><span data-ttu-id="c29fb-135">20</span><span class="sxs-lookup"><span data-stu-id="c29fb-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c29fb-136">ファイル送信</span><span class="sxs-lookup"><span data-stu-id="c29fb-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="c29fb-137">42020</span><span class="sxs-lookup"><span data-stu-id="c29fb-137">42020</span></span></p></td>
<td><p><span data-ttu-id="c29fb-138">20</span><span class="sxs-lookup"><span data-stu-id="c29fb-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c29fb-139">上記の表では、クライアントのポート範囲はサーバーに構成されたポート範囲のサブセットを表しています。</span><span class="sxs-lookup"><span data-stu-id="c29fb-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="c29fb-140">たとえば、サーバーではアプリケーション共有が 40803 ～ 49151 のポートを使用するように構成されており、クライアント コンピューターではアプリケーション共有が 42000 ～ 42019 のポートを使用するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="c29fb-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="c29fb-141">また、これは主に QoS の管理を容易にするために行われます。クライアント ポートは、サーバーで使用されるポートのサブセットを表す必要がなされません。</span><span class="sxs-lookup"><span data-stu-id="c29fb-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="c29fb-142">(たとえば、クライアント コンピューターでは、ポート 10000 から 10019 までを使用するアプリケーション共有を構成できます)。ただし、クライアント ポート範囲をサーバー ポート範囲のサブセットに設定してください。</span><span class="sxs-lookup"><span data-stu-id="c29fb-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="c29fb-143">さらに、サーバー上のアプリケーション共有用に 8348 個のポートが確保されているが、クライアント上のアプリケーション共有用に確保されたポートは 20 個のみである点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c29fb-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="c29fb-144">この規則も推奨されますが、高速な規則ではありません。</span><span class="sxs-lookup"><span data-stu-id="c29fb-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="c29fb-145">一般に、使用可能な各ポートを 1 つの通信セッションと見なして、1 つのポート範囲で 100 個のポートを使用できる場合は、問題のコンピューターが一度に最大で 100 個の通信セッションに参加する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c29fb-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="c29fb-146">サーバーはクライアントよりも多くの会話に参加する可能性が高いので、クライアントよりも多くのポートをサーバーで開くのが理にかなっています。</span><span class="sxs-lookup"><span data-stu-id="c29fb-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="c29fb-147">クライアントでアプリケーション共有用に 20 個のポートを確保すると、ユーザーは指定したデバイスで 20 個のアプリケーション共有セッションに同時に参加できます。</span><span class="sxs-lookup"><span data-stu-id="c29fb-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="c29fb-148">大多数のユーザーにとって十分なことを証明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c29fb-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="c29fb-149">上のポート範囲を会議構成設定のグローバル コレクションに割り当てるには、次の Skype for Business Server 管理シェル コマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c29fb-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="c29fb-150">または、次のコマンドを使用して、この同じポート範囲を会議のすべての構成設定に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c29fb-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="c29fb-151">個々のユーザーは、Skype for Business からログオフしてから、これらの変更を実際に有効にする前にログオンし戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c29fb-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="c29fb-152">1 つのコマンドで、クライアントのメディア ポート範囲を有効化し、これらのポート範囲を割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="c29fb-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="c29fb-153">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="c29fb-154">Windows 10 で実行されているクライアントのサービス品質ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="c29fb-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="c29fb-155">Skype for Business クライアントで使用するポート範囲を指定する以外に、クライアント コンピューターに適用されるサービス品質ポリシーを個別に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c29fb-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="c29fb-156">(会議サーバー、アプリケーション サーバー、および仲介サーバー用に作成されたサービス品質ポリシーは、クライアント コンピューターには適用されません。この情報は、Skype for Business クライアントと Windows 10 を実行しているコンピューターにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c29fb-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="c29fb-157">次の例では、このポート範囲のセットを使用して、オーディオ ポリシーとビデオ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c29fb-158">クライアント トラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="c29fb-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="c29fb-159">開始ポート</span><span class="sxs-lookup"><span data-stu-id="c29fb-159">Port Start</span></span></th>
<th><span data-ttu-id="c29fb-160">ポート範囲</span><span class="sxs-lookup"><span data-stu-id="c29fb-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c29fb-161">オーディオ</span><span class="sxs-lookup"><span data-stu-id="c29fb-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="c29fb-162">50020</span><span class="sxs-lookup"><span data-stu-id="c29fb-162">50020</span></span></p></td>
<td><p><span data-ttu-id="c29fb-163">20</span><span class="sxs-lookup"><span data-stu-id="c29fb-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c29fb-164">ビデオ</span><span class="sxs-lookup"><span data-stu-id="c29fb-164">Video</span></span></p></td>
<td><p><span data-ttu-id="c29fb-165">58000</span><span class="sxs-lookup"><span data-stu-id="c29fb-165">58000</span></span></p></td>
<td><p><span data-ttu-id="c29fb-166">20</span><span class="sxs-lookup"><span data-stu-id="c29fb-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c29fb-167">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="c29fb-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="c29fb-168">42000</span><span class="sxs-lookup"><span data-stu-id="c29fb-168">42000</span></span></p></td>
<td><p><span data-ttu-id="c29fb-169">20</span><span class="sxs-lookup"><span data-stu-id="c29fb-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c29fb-170">ファイル送信</span><span class="sxs-lookup"><span data-stu-id="c29fb-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="c29fb-171">42020</span><span class="sxs-lookup"><span data-stu-id="c29fb-171">42020</span></span></p></td>
<td><p><span data-ttu-id="c29fb-172">20</span><span class="sxs-lookup"><span data-stu-id="c29fb-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c29fb-173">Windows 10 コンピューターのサービス品質オーディオ ポリシーを作成するには、まず、グループ ポリシーの管理がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c29fb-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="c29fb-174">グループ ポリシーの管理を開き ([スタート] ボタンを **クリック** し、[管理ツール] をポイントし、[グループ ポリシーの管理] をクリックします)、次の手順を実行します。 </span><span class="sxs-lookup"><span data-stu-id="c29fb-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="c29fb-175">[グループ ポリシーの管理] で、新しいポリシーを作成する必要のあるコンテナーを探します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="c29fb-176">たとえば、すべてのクライアント コンピューターが Clients という名前の OU にある場合は、新しいポリシーをクライアント OU に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c29fb-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="c29fb-177">適切なコンテナーを右クリックし、[このドメインに GPO を作成する] をクリックし、 **ここにリンクします**。</span><span class="sxs-lookup"><span data-stu-id="c29fb-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="c29fb-178">[新 **しい GPO] ダイアログ** ボックスで、[名前] ボックスに新しいグループ ポリシー オブジェクトの名前を入力し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c29fb-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="c29fb-179">新しく作成したポリシーを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c29fb-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="c29fb-180">グループ ポリシー管理エディターで、[コンピューターの構成] を展開し **、[Windows の** 設定] を展開し、[ポリシー ベース **の QoS]** を右クリックして、[新しいポリシーの作成]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c29fb-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="c29fb-181">[ **ポリシーベースの QoS]** ダイアログ ボックスの開始ページで、[名前] ボックスに新しいポリシーの名前を **入力** します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="c29fb-182">[**DSCP 値を指定する**] を選択し、値を **46** に設定します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="c29fb-183">[**出力方向のスロットル率を指定する**] をオフのままにして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c29fb-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="c29fb-184">次のページで、[この実行可能ファイル名を持つアプリケーションのみ]を選択し、Lync.exeを入力して、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c29fb-184">On the next page, select **Only applications with this executable name**, enter **Lync.exe** as the name, and then click **Next**.</span></span> <span data-ttu-id="c29fb-185">この設定は、Skype for Business クライアントからの一致トラフィックのみを優先順位付けするようにポリシーに指示します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-185">This setting instructs the policy to only prioritize matching traffic from the Skype for Business client.</span></span>

8.  <span data-ttu-id="c29fb-186">3 番目のページで、[すべての送信元 **IP** アドレス] と [すべての宛先 **IP** アドレス] の両方が選択され、[次へ] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c29fb-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="c29fb-187">この 2 つの設定により、これらのパケットを送信したコンピューター (IP アドレス) やこれらのパケットを受信するコンピューター (IP アドレス) にかかわらず、パケットが管理されます。</span><span class="sxs-lookup"><span data-stu-id="c29fb-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="c29fb-188">4 番目のページで、[**この QoS ポリシーを適用するプロトコルを選択してください**] ドロップダウン リストから [**TCP と UDP**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="c29fb-189">TCP (伝送制御プロトコル) と UDP (ユーザー データグラム プロトコル) は、Skype for Business Server とそのクライアント アプリケーションで最も一般的に使用される 2 つのネットワーク プロトコルです。</span><span class="sxs-lookup"><span data-stu-id="c29fb-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="c29fb-p117">[**発信元ポート番号を指定してください**] という見出しの下にある [**次の発信元ポート番号か範囲**] を選択します。付随するテキスト ボックスに、オーディオ送信用に予約されたポート範囲を入力します。たとえば、50020 から 50039 までのポートをオーディオ トラフィック用に予約した場合は、「**50020:50039**」という形式でポート範囲を入力します。[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c29fb-p117">Under the heading **Specify the source port number**, select **From this source port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**. Click **Finish**.</span></span>

<span data-ttu-id="c29fb-p118">オーディオ用の QoS ポリシーを作成した後で、2 番目にビデオ用のポリシーを作成する必要があります。ビデオ用のポリシーを作成するには、オーディオ ポリシーを作成したときと基本的には同じ手順に従い、次の点を変えます。</span><span class="sxs-lookup"><span data-stu-id="c29fb-p118">After you have created the QoS policy for audio you should then create a second policy for video. To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="c29fb-196">別の (および一意の) ポリシー名を使用します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="c29fb-p119">DSCP の値を 46 ではなく「**34**」に設定します。(前に説明したとおり、DSCP の値に 34 を使用する必要はありません。ただ、オーディオに使用したのとは異なる DSCP の値を割り当てる必要があります。)</span><span class="sxs-lookup"><span data-stu-id="c29fb-p119">Set the DSCP value to **34** instead of 46. (As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="c29fb-199">ビデオ トラフィックには、以前に構成したポート範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="c29fb-200">たとえば、ポート 58000 ~ 58019 をビデオ用に予約している場合は、ポート範囲を **58000:58019** に設定します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="c29fb-201">アプリケーション共有トラフィックを管理するためのポリシーを作成する場合は、次の代替を行います。</span><span class="sxs-lookup"><span data-stu-id="c29fb-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="c29fb-202">別の (および一意の) ポリシー名 **(Skype for Business Server アプリケーション** 共有など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="c29fb-p121">DSCP の値を 46 ではなく「**24**」に設定します。(この値も 24 にする必要はありません。ただ、オーディオとビデオに使用した DSCP の値とは別にする必要があります。)</span><span class="sxs-lookup"><span data-stu-id="c29fb-p121">Set the DSCP value to **24** instead of 46. (Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="c29fb-205">ビデオ トラフィックには、以前に構成したポート範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="c29fb-206">たとえば、アプリケーション共有用にポート 42000 ~ 42019 を予約している場合、ポート範囲を **42000:42019** に設定します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="c29fb-207">ファイル転送ポリシーは次のようにします。</span><span class="sxs-lookup"><span data-stu-id="c29fb-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="c29fb-208">別の (および一意の) ポリシー名 **(Skype for Business Server ファイル** 転送など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="c29fb-209">DSCP 値を **14 に設定します**。</span><span class="sxs-lookup"><span data-stu-id="c29fb-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="c29fb-210">(繰り返しますが、この値は 14 である必要はありません。単に一意の DSCP コードである必要があります)。</span><span class="sxs-lookup"><span data-stu-id="c29fb-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="c29fb-211">アプリケーションに対して以前に構成したポート範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="c29fb-212">たとえば、アプリケーション共有用にポート 42020 ~ 42039 を予約している場合は、ポート範囲を **42020:42039** に設定します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="c29fb-p125">新しく作成したポリシーは、クライアント コンピューター上でグループ ポリシーが更新されるまで有効になりません。グループ ポリシーは定期的に自動更新を行いますが、グループ ポリシーの更新が必要な各コンピューター上で次のコマンドを実行することにより、強制的に即時更新できます。</span><span class="sxs-lookup"><span data-stu-id="c29fb-p125">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="c29fb-p126">このコマンドは、管理者の資格情報で実行されていれば、どのコマンド ウィンドウからでも実行できます。コマンド ウィンドウを管理者の資格情報で実行するには、[**スタート**]をクリックして、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c29fb-p126">This command can be run from any command window that is running under administrator credentials. To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="c29fb-217">なお、これらのポリシーが対象とするのはクライアント コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="c29fb-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="c29fb-218">Skype for Business Server を実行しているサーバーには適用できません。</span><span class="sxs-lookup"><span data-stu-id="c29fb-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="c29fb-219">ネットワーク パケットが適切な DSCP 値でマークされるようにするには、次の手順を実行して、各コンピューターに新しいレジストリ エントリを作成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="c29fb-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="c29fb-220">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c29fb-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="c29fb-221">[ファイル名 **を指定** して実行] ダイアログ ボックスに **「regedit」と** 入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="c29fb-222">レジストリ エディターで **、HKEY \_ LOCAL \_ MACHINE、\*\*\*\*システム\*\*\*\*、CurrentControlSet、** サービス、Tcpip の順に **展開します**。 </span><span class="sxs-lookup"><span data-stu-id="c29fb-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="c29fb-223">[**Tcpip**] を右クリックし、[**新規**] をポイントして [**キー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c29fb-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="c29fb-224">新しいレジストリ キーを作成したら **、「QoS」** と入力し、Enter キーを押してキーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="c29fb-225">[**QoS**] を右クリックし、[**新規**] をポイントして [**文字列値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c29fb-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="c29fb-226">新しいレジストリ値を作成したら **、「NLA** を使用しない」と入力し、Enter キーを押して値の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="c29fb-227">[**Do no use NLA**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c29fb-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="c29fb-228">[文字列の **編集]** ダイアログ ボックスで、[値のデータ] ボックスに **「1」** と **入力し\*\*\*\*、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c29fb-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="c29fb-229">レジストリ エディターを閉じて、コンピューターを起動します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="c29fb-230">複数のネットワーク アダプターを使用するコンピューターでサービスの品質を構成する</span><span class="sxs-lookup"><span data-stu-id="c29fb-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="c29fb-231">複数のネットワーク アダプターを備えるコンピューターがある場合、DSCP 値が構成された値ではなく 0x00 として表示される問題が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="c29fb-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="c29fb-232">通常、このような表示になるのは、1 つ以上のネットワーク アダプターが Active Directory ドメインにアクセスできないコンピューターです (たとえば、アダプターがプライベート ネットワークに使用されている場合)。</span><span class="sxs-lookup"><span data-stu-id="c29fb-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="c29fb-233">そのような場合、ドメインへアクセスできるアダプターには DSCP の値がマークされますが、ドメインへアクセスできないアダプターにはマークされません。</span><span class="sxs-lookup"><span data-stu-id="c29fb-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="c29fb-234">ドメインにアクセスできないアダプターを含め、コンピューター内のすべてのネットワーク アダプターの DSCP 値にタグを付けしたい場合は、レジストリに値を追加して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c29fb-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="c29fb-235">このためには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="c29fb-236">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c29fb-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="c29fb-237">[ファイル名 **を指定** して実行] ダイアログ ボックスに **「regedit」と** 入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="c29fb-238">レジストリ エディターで **、HKEY \_ LOCAL \_ MACHINE、\*\*\*\*システム\*\*\*\*、CurrentControlSet、** サービス、Tcpip の順に **展開します**。 </span><span class="sxs-lookup"><span data-stu-id="c29fb-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="c29fb-239">「**QoS**」というレジストリ キーがない場合は、 [**Tcpip**] 右クリックし、[**新規**] をポイントして、[**キー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c29fb-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="c29fb-240">新しいキーを作成したら **、「QoS」** と入力し、Enter キーを押してキーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="c29fb-241">[**QoS**] を右クリックし、[**新規**] をポイントして [**文字列値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c29fb-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="c29fb-242">新しいレジストリ値を作成したら **、「NLA** を使用しない」と入力し、Enter キーを押して値の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="c29fb-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="c29fb-243">[**Do no use NLA**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c29fb-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="c29fb-244">[文字列の **編集]** ダイアログ ボックスで、[値のデータ] ボックスに **「1」** と **入力し\*\*\*\*、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c29fb-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="c29fb-245">新しいレジストリ値を作成して構成した後、変更を有効にするためにコンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c29fb-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="c29fb-246">関連項目</span><span class="sxs-lookup"><span data-stu-id="c29fb-246">See also</span></span>

[<span data-ttu-id="c29fb-247">Windows 10 でグループ ポリシー オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="c29fb-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)

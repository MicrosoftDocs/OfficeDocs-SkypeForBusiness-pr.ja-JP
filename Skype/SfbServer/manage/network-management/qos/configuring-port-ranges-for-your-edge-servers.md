---
title: エッジ サーバーのポート範囲と品質のサービスを構成します。
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: エッジ トランスポート サーバーのポート範囲を構成する方法と、1 つのサービスの品質ポリシーを構成する方法について説明/V エッジ サーバー。
ms.openlocfilehash: b0f0b9c974b547004204a624840877aed71a02ff
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223130"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a><span data-ttu-id="a3fba-103">Skype でエッジ サーバーのビジネス サーバーのポート範囲およびサービスの品質ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="a3fba-103">Configuring port ranges and a Quality of Service policy for your Edge Servers in Skype for Business Server</span></span>

<span data-ttu-id="a3fba-104">エッジ トランスポート サーバーのポート範囲を構成する方法と、1 つのサービスの品質ポリシーを構成する方法について説明/V エッジ サーバー。</span><span class="sxs-lookup"><span data-stu-id="a3fba-104">This article describes how to configure port ranges for Edge Servers and how to configure a Quality of Service policy for your A/V Edge Servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="a3fba-105">ポート範囲を構成します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-105">Configure port ranges</span></span>

<span data-ttu-id="a3fba-106">エッジ サーバーを使用する必要はありませんオーディオ、ビデオ、およびアプリケーション共有の別のポート範囲を構成するには同様に、エッジ サーバーで使用するポートの範囲では、会議、アプリケーション、および仲介サーバーで使用されるポートの範囲に一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a3fba-106">With Edge servers, you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="a3fba-107">例を進める前にすることが重要このオプションがありますが、お勧めしないポートの範囲を変更するこの低下する可能性がいくつかのシナリオ 50000 のポートの範囲からを移動した場合とを強調します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-107">Before we proceed with our example, it's important to stress that while this option exists, we recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="a3fba-108">たとえば、これらのポート範囲を使用するのには、会議、アプリケーション、および仲介サーバーを構成したとします。</span><span class="sxs-lookup"><span data-stu-id="a3fba-108">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3fba-109">パケットの種類</span><span class="sxs-lookup"><span data-stu-id="a3fba-109">Packet Type</span></span></th>
<th><span data-ttu-id="a3fba-110">開始ポート</span><span class="sxs-lookup"><span data-stu-id="a3fba-110">Starting Port</span></span></th>
<th><span data-ttu-id="a3fba-111">予約されているポートの数</span><span class="sxs-lookup"><span data-stu-id="a3fba-111">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3fba-112">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="a3fba-112">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="a3fba-113">40803</span><span class="sxs-lookup"><span data-stu-id="a3fba-113">40803</span></span></p></td>
<td><p><span data-ttu-id="a3fba-114">8348</span><span class="sxs-lookup"><span data-stu-id="a3fba-114">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3fba-115">オーディオ</span><span class="sxs-lookup"><span data-stu-id="a3fba-115">Audio</span></span></p></td>
<td><p><span data-ttu-id="a3fba-116">49152</span><span class="sxs-lookup"><span data-stu-id="a3fba-116">49152</span></span></p></td>
<td><p><span data-ttu-id="a3fba-117">8348</span><span class="sxs-lookup"><span data-stu-id="a3fba-117">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3fba-118">ビデオ</span><span class="sxs-lookup"><span data-stu-id="a3fba-118">Video</span></span></p></td>
<td><p><span data-ttu-id="a3fba-119">57500</span><span class="sxs-lookup"><span data-stu-id="a3fba-119">57500</span></span></p></td>
<td><p><span data-ttu-id="a3fba-120">8034</span><span class="sxs-lookup"><span data-stu-id="a3fba-120">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3fba-121"><strong>合計</strong></span><span class="sxs-lookup"><span data-stu-id="a3fba-121"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="a3fba-122">24730</span><span class="sxs-lookup"><span data-stu-id="a3fba-122">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a3fba-123">参照してください、ポート範囲のオーディオ、ビデオ、およびアプリケーション共有の開始ポート 40803、24732 ポートの合計が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a3fba-123">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="a3fba-124">これらを使用する特定のエッジ サーバーを構成することができる場合は、全体的なビジネス サーバー管理シェルには、Skype 内からは、この 1 のようなコマンドを実行することによって値を移植します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-124">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Skype for Business Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="a3fba-125">または、次のコマンドを使用して、同時に、組織内のすべてのエッジ トランスポート サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-125">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="a3fba-126">この Skype ビジネス サーバー管理シェル コマンドを使用して、エッジ トランスポート サーバーの現在のポートの設定を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a3fba-126">You can verify the current port settings for your Edge Servers by using this Skype for Business Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="a3fba-127">もう一度、これらのオプションを提供するは、強くお勧めするものはそのままにそれらのポートの構成は。</span><span class="sxs-lookup"><span data-stu-id="a3fba-127">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a><span data-ttu-id="a3fba-128">QoS ポリシーを構成する、1 つの/V エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="a3fba-128">Configure a QoS policy for your A/V Edge Servers</span></span>

<span data-ttu-id="a3fba-129">だけでなく、会議、アプリケーション、および仲介サーバーの QoS ポリシーを作成するには、必要がありますもポリシーを作成するオーディオとビデオの両方、A の内部に表示すると音声ビデオ エッジ サーバー。</span><span class="sxs-lookup"><span data-stu-id="a3fba-129">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="a3fba-130">ただし、エッジ サーバーで使用されているポリシーでは、会議、アプリケーション、および仲介サーバーで使用されているポリシーとは異なる。</span><span class="sxs-lookup"><span data-stu-id="a3fba-130">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="a3fba-131">ソース ポート範囲を指定した、会議、アプリケーション、および仲介サーバーのエッジ トランスポート サーバーでは、送信先のポート範囲を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3fba-131">For the Conferencing, Application, and Mediation servers, you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="a3fba-132">このため、単には適用できません会議、アプリケーション、および仲介サーバーの QoS ポリシー、エッジ トランスポート サーバー: 単にこれらのポリシーは機能しません。</span><span class="sxs-lookup"><span data-stu-id="a3fba-132">Because of this, you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="a3fba-133">代わりに、新しいポリシーを作成し、これらのポリシーをエッジ トランスポート サーバーのみに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3fba-133">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="a3fba-134">次の手順では、エッジ トランスポート サーバー上のサービスの品質を管理するために使用できる Active Directory グループ ポリシー オブジェクトを作成するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-134">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="a3fba-135">もちろん、エッジ サーバーは、Active Directory アカウントを持たないスタンドアロンのサーバーを使用可能なです。</span><span class="sxs-lookup"><span data-stu-id="a3fba-135">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="a3fba-136">場合は、Active Directory グループ ポリシーではなくローカルのグループ ポリシーを使用することができます。 唯一の違いは、ローカル グループ ポリシー エディターを使用してローカル ポリシーを作成する必要があります各エッジ サーバー上で同じ一連のポリシーを個別に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3fba-136">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="a3fba-137">エッジ サーバー上でローカル グループ ポリシー エディターを起動するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a3fba-137">To start the Local Group Policy Editor on an Edge server, do the following:</span></span>

1.  <span data-ttu-id="a3fba-138">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3fba-138">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="a3fba-139">**実行**] ダイアログ ボックスに「 **gpedit.msc**」とし、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-139">In the **Run** dialog box, type **gpedit.msc**, and then press ENTER.</span></span>

<span data-ttu-id="a3fba-140">Active Directory ベースのポリシーを作成する場合、必要がありますにログオンするコンピューターのグループ ポリシーの管理がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="a3fba-140">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="a3fba-141">その場合は、グループ ポリシーの管理を開きます ([**スタート**] ボタン、 **[管理ツール**] をポイントし、[**グループ ポリシーの管理**] をクリック) し、次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-141">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following steps:</span></span>

1.  <span data-ttu-id="a3fba-142">グループ ポリシーの管理では、新しいポリシーを作成するコンテナーを探します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-142">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="a3fba-143">などのビジネス サーバー コンピューターに対して、すべての Skype は Skype をという名前のビジネス サーバー OU に存在する場合、新しいポリシーする必要がありますを作成する、Skype でビジネス サーバー OU の。</span><span class="sxs-lookup"><span data-stu-id="a3fba-143">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="a3fba-144">適切なコンテナーを右クリックし、**このドメインに GPO を作成しここにリンク**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3fba-144">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="a3fba-145">**新しい GPO** ] ダイアログ ボックスで (たとえば、 **Skype ビジネス サーバー オーディオ用**) の [**名前**] ボックスに新しいグループ ポリシー オブジェクトの名前を入力し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3fba-145">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server Audio**), and then click **OK**.</span></span>

4.  <span data-ttu-id="a3fba-146">新しく作成したポリシーを右クリックし、し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3fba-146">Right-click the newly-created policy, and then click **Edit**.</span></span>

<span data-ttu-id="a3fba-147">ここから、手順は、Active Directory ポリシーまたはローカル ポリシーを作成するかどうかに関係なく同じです。</span><span class="sxs-lookup"><span data-stu-id="a3fba-147">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="a3fba-148">グループ ポリシー管理エディターまたはローカル グループ ポリシー エディターでは、**コンピューター**の構成**ポリシー**] を展開、 **Windows の設定**を展開し、**ポリシー ベースの QoS**では、右、[**新規ポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3fba-148">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="a3fba-149">**ポリシー ベースの QoS** ] ダイアログ ボックスで [開始] ページで、 **[名前**] ボックスで新しいポリシー (たとえば、**ビジネス サーバー オーディオを Skype**) の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-149">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server Audio**) in the **Name** box.</span></span> <span data-ttu-id="a3fba-150">**DSCP 値を指定**を選択し、 **46**に値を設定します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-150">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="a3fba-151">オフの場合、**アウト バウンドのスロットル率を指定**のままにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3fba-151">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="a3fba-152">次のページでは、**すべてのアプリケーション**が選択されているかどうかを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3fba-152">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="a3fba-153">この設定は、特定のアプリケーションによって作成された、46 のだけではなくパケットの DSCP のマークが付いたすべてのパケットを検索するネットワークを指示します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-153">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="a3fba-154">3 番目のページでは、**任意の発信元 IP アドレス**と**宛先の IP アドレス**の両方が選択されているし、[**次へ**] をクリックを確認します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-154">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="a3fba-155">これら 2 つの設定では、パケットが管理されることを確認してどのコンピューター (IP アドレス) は、これらのパケットを送信し、これらのパケットをどのコンピューター (IP アドレス) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3fba-155">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="a3fba-156">[4] ページでは、**この QoS ポリシーを適用するプロトコルを選択して**ドロップダウン リストから**TCP および UDP**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-156">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="a3fba-157">TCP (伝送制御プロトコル) と UDP (ユーザー データグラム プロトコル) は、最も一般的使用 Skype ビジネス サーバーとそのクライアント アプリケーションの 2 つのネットワーク プロトコルです。</span><span class="sxs-lookup"><span data-stu-id="a3fba-157">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

6.  <span data-ttu-id="a3fba-158">**指定する宛先ポート番号**の見出しの下には、**この宛先ポートまたは範囲から**選択します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-158">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="a3fba-159">付随するテキスト ボックスで、オーディオの転送用に予約されたポートの範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-159">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="a3fba-160">57500 オーディオ トラフィック用のポートをポート 49152 を予約する場合のこの形式を使用するポートの範囲を入力するたとえば、: **49152:57500**。</span><span class="sxs-lookup"><span data-stu-id="a3fba-160">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="a3fba-161">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3fba-161">Click **Finish**.</span></span>

<span data-ttu-id="a3fba-162">オーディオ トラフィックの QoS ポリシーを作成した後は、ビデオのトラフィックを 2 番目のポリシーを作成してください。</span><span class="sxs-lookup"><span data-stu-id="a3fba-162">After you have created the QoS policy for audio traffic, you should create a second policy for video traffic.</span></span> <span data-ttu-id="a3fba-163">ビデオのポリシーを作成するにした後に、オーディオのポリシーを作成するときにこれらの置換を行うと同じ基本的な手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a3fba-163">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="a3fba-164">異なる (そして固有) のポリシーの名前 (たとえば、**ビジネス サーバー ビデオ Skype**) を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-164">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="a3fba-165">46 ではなく**34** DSCP 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-165">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="a3fba-166">(注 34 の DSCP 値を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a3fba-166">(Note that you do not have to use a DSCP value of 34.</span></span> <span data-ttu-id="a3fba-167">唯一の要件はオーディオ用に使用すると、ビデオの別の DSCP 値を使用すること) です。</span><span class="sxs-lookup"><span data-stu-id="a3fba-167">The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="a3fba-168">ビデオのトラフィックには、以前に構成されたポートの範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-168">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="a3fba-169">たとえば、57501 ビデオの 65535 までからのポートを予約する場合、このポート範囲をこれに設定: **57501:65535**。</span><span class="sxs-lookup"><span data-stu-id="a3fba-169">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="a3fba-170">繰り返しますが、これは送信先ポートの範囲として構成してください。</span><span class="sxs-lookup"><span data-stu-id="a3fba-170">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="a3fba-171">アプリケーション共有トラフィックを管理するポリシーを作成する場合は、作成する必要が 3 つ目のポリシーでは、次の置換を行います。</span><span class="sxs-lookup"><span data-stu-id="a3fba-171">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="a3fba-172">異なる (そして固有) のポリシーの名前 (たとえば、**ビジネス サーバー アプリケーションを共有するための Skype**) を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-172">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="a3fba-173">46 ではなく**24**に DSCP 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-173">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="a3fba-174">(繰り返しますが、必要はありません 24 の DSCP 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-174">(Again, you do not have to use a DSCP value of 24.</span></span> <span data-ttu-id="a3fba-175">唯一の要件は、オーディオやビデオを使用するよりもアプリケーションの共有には、別の DSCP 値を使用すること。)</span><span class="sxs-lookup"><span data-stu-id="a3fba-175">The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="a3fba-176">ビデオのトラフィックには、以前に構成されたポートの範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-176">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="a3fba-177">など 40803 49151 アプリケーションを共有するためのポートを予約する場合、このポートの範囲をこれに設定: **40803:49151**。</span><span class="sxs-lookup"><span data-stu-id="a3fba-177">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="a3fba-178">エッジ サーバーにグループ ポリシーを更新するまで、作成した新しいポリシーは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="a3fba-178">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers.</span></span> <span data-ttu-id="a3fba-179">グループ ポリシーは定期的に自動更新されますが、グループ ポリシーを更新する必要がある各コンピューター上で次のコマンドを実行すると、即座に強制的に更新することができます。</span><span class="sxs-lookup"><span data-stu-id="a3fba-179">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="a3fba-180">ビジネス サーバーまたは管理者の資格情報で実行されている任意のコマンド ウィンドウから、Skype 内でこのコマンドから実行することができます。</span><span class="sxs-lookup"><span data-stu-id="a3fba-180">This command can be run from within the Skype for Business Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="a3fba-181">管理者の資格情報のもとでコマンド ウィンドウを開くには、[**スタート**] メニューをクリックし、[**コマンド プロンプト**] を右クリックして、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3fba-181">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="a3fba-182">Gpudate.exe を実行した後でも、エッジ サーバーを再起動するのには必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a3fba-182">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="a3fba-183">ネットワーク パケットが DSCP 値でマークされていることを確認するには、次の手順を完了して新しいレジストリ エントリの各コンピューターで作成することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3fba-183">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="a3fba-184">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3fba-184">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="a3fba-185">**実行**] ダイアログ ボックスで **「regedit」** と入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-185">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="a3fba-186">レジストリ エディターで、拡張**HKEY\_ローカル\_マシン**、**システム**を展開し、 **CurrentControlSet**を展開し、**サービス**の展開および**Tcpip**を展開し、します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-186">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="a3fba-187">**Tcpip**] を右クリックして、**新規**作成] をポイントし、[**キー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3fba-187">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="a3fba-188">新しいレジストリ キーが作成されるは、 **QoS**を入力し、enter キーを押してキーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-188">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="a3fba-189">**QoS**を右クリックし、**新規**作成] をポイントし、[**文字列値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3fba-189">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="a3fba-190">新しいレジストリ値を作成すると後、は、 **NLA を使用しない**を入力し、値の名前を変更するのには ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-190">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="a3fba-191">**NLA を使用しない操作を行います**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3fba-191">Double-click **Do no use NLA**.</span></span> <span data-ttu-id="a3fba-192">**文字列の編集**] ダイアログ ボックスで、[**値データ**] ボックスに**1**を入力し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3fba-192">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="a3fba-193">レジストリ エディターを終了し、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a3fba-193">Close the Registry Editor and reboot your computer.</span></span>
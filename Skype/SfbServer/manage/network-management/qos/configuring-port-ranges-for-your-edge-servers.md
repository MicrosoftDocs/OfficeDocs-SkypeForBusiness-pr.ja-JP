---
title: エッジサーバーのポート範囲とサービス品質を構成する
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
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
description: この記事では、エッジサーバーのポート範囲を構成する方法と、A/V エッジサーバーのサービス品質ポリシーを構成する方法について説明します。
ms.openlocfilehash: 5762cb6861552696f160dfe69459c357f6b63452
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817436"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a><span data-ttu-id="f7f9b-103">Skype for Business Server でのエッジサーバーのポート範囲とサービス品質ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="f7f9b-103">Configuring port ranges and a Quality of Service policy for your Edge Servers in Skype for Business Server</span></span>

<span data-ttu-id="f7f9b-104">この記事では、エッジサーバーのポート範囲を構成する方法と、A/V エッジサーバーのサービス品質ポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-104">This article describes how to configure port ranges for Edge Servers and how to configure a Quality of Service policy for your A/V Edge Servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="f7f9b-105">ポート範囲を構成する</span><span class="sxs-lookup"><span data-stu-id="f7f9b-105">Configure port ranges</span></span>

<span data-ttu-id="f7f9b-106">エッジサーバーでは、音声、ビデオ、アプリケーション共有のために個別のポート範囲を構成する必要はありません。同様に、エッジサーバーに使われるポート範囲も、会議、アプリケーション、および仲介サーバーで使用されるポート範囲と一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-106">With Edge servers, you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="f7f9b-107">例を始める前に、このオプションが存在している間は、ポート範囲を変更しないことをお勧めします。これは、5万のポート範囲から移動した場合に、一部のシナリオに悪影響を与える可能性があるため、これを強調することが重要です。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-107">Before we proceed with our example, it's important to stress that while this option exists, we recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="f7f9b-108">たとえば、次のようなポート範囲を使用するように会議、アプリケーション、および仲介業者を構成したとします。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-108">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7f9b-109">パケットの種類</span><span class="sxs-lookup"><span data-stu-id="f7f9b-109">Packet Type</span></span></th>
<th><span data-ttu-id="f7f9b-110">開始ポート</span><span class="sxs-lookup"><span data-stu-id="f7f9b-110">Starting Port</span></span></th>
<th><span data-ttu-id="f7f9b-111">予約されているポートの数</span><span class="sxs-lookup"><span data-stu-id="f7f9b-111">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7f9b-112">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="f7f9b-112">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="f7f9b-113">40803</span><span class="sxs-lookup"><span data-stu-id="f7f9b-113">40803</span></span></p></td>
<td><p><span data-ttu-id="f7f9b-114">8348</span><span class="sxs-lookup"><span data-stu-id="f7f9b-114">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7f9b-115">オーディオ</span><span class="sxs-lookup"><span data-stu-id="f7f9b-115">Audio</span></span></p></td>
<td><p><span data-ttu-id="f7f9b-116">49152</span><span class="sxs-lookup"><span data-stu-id="f7f9b-116">49152</span></span></p></td>
<td><p><span data-ttu-id="f7f9b-117">8348</span><span class="sxs-lookup"><span data-stu-id="f7f9b-117">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7f9b-118">ビデオ</span><span class="sxs-lookup"><span data-stu-id="f7f9b-118">Video</span></span></p></td>
<td><p><span data-ttu-id="f7f9b-119">57500</span><span class="sxs-lookup"><span data-stu-id="f7f9b-119">57500</span></span></p></td>
<td><p><span data-ttu-id="f7f9b-120">8034</span><span class="sxs-lookup"><span data-stu-id="f7f9b-120">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7f9b-121"><strong>合計</strong></span><span class="sxs-lookup"><span data-stu-id="f7f9b-121"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="f7f9b-122">24730</span><span class="sxs-lookup"><span data-stu-id="f7f9b-122">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f7f9b-123">ご覧のとおり、オーディオ、ビデオ、およびアプリケーション共有のポート範囲は、ポート40803から始まり、24732ポートの合計をカバーしています。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-123">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="f7f9b-124">必要に応じて、Skype for Business Server 管理シェルで、次のようなコマンドを実行して、これらの全体的なポート値を使用するように特定のエッジサーバーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-124">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Skype for Business Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="f7f9b-125">または、次のコマンドを使用して、組織内のすべてのエッジサーバーを同時に構成します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-125">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="f7f9b-126">次の Skype for Business Server 管理シェルコマンドを使用して、エッジサーバーの現在のポート設定を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-126">You can verify the current port settings for your Edge Servers by using this Skype for Business Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="f7f9b-127">ここでも、これらのオプションを用意していますが、ポート構成のためにそのままにしておくことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-127">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a><span data-ttu-id="f7f9b-128">A/V エッジサーバーの QoS ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="f7f9b-128">Configure a QoS policy for your A/V Edge Servers</span></span>

<span data-ttu-id="f7f9b-129">会議、アプリケーション、および仲介サーバーの QoS ポリシーの作成に加えて、A/V エッジサーバーの内部側のオーディオとビデオの両方のポリシーも作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-129">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="f7f9b-130">ただし、エッジサーバーで使用されるポリシーは、会議、アプリケーション、および仲介サーバーで使われるポリシーとは異なります。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-130">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="f7f9b-131">会議、アプリケーション、および仲介サーバーの場合、ソースポートの範囲を指定しています。エッジサーバーでは、宛先ポートの範囲を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-131">For the Conferencing, Application, and Mediation servers, you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="f7f9b-132">このため、会議、アプリケーション、および仲介サーバーの QoS ポリシーをエッジサーバーに適用することはできません。これらのポリシーは、単に機能しません。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-132">Because of this, you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="f7f9b-133">代わりに、新しいポリシーを作成して、それらのポリシーを Edge サーバーのみに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-133">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="f7f9b-134">次の手順では、エッジサーバー上のサービスの品質を管理するために使用できる Active Directory グループポリシーオブジェクトを作成するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-134">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="f7f9b-135">ただし、エッジサーバーがスタンドアロンサーバーであり、Active Directory アカウントを持っていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-135">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="f7f9b-136">このような場合は、Active Directory グループポリシーの代わりにローカルグループポリシーを使用できます。唯一の違いは、ローカルグループポリシーエディターを使ってこれらのローカルポリシーを作成する必要があります。また、各エッジサーバー上で同じポリシーセットを個別に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-136">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="f7f9b-137">エッジサーバーでローカルグループポリシーエディターを起動するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-137">To start the Local Group Policy Editor on an Edge server, do the following:</span></span>

1.  <span data-ttu-id="f7f9b-138">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-138">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="f7f9b-139">[**実行**] ダイアログボックスで、「 **gpedit.msc**」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-139">In the **Run** dialog box, type **gpedit.msc**, and then press ENTER.</span></span>

<span data-ttu-id="f7f9b-140">Active Directory ベースのポリシーを作成する場合は、グループポリシー管理がインストールされているコンピューターにログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-140">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="f7f9b-141">その場合は、[グループポリシーの管理] を開き ([**スタート**] をクリックし、[**管理ツール**] をポイントし、[**グループポリシーの管理**] をクリックします)、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-141">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following steps:</span></span>

1.  <span data-ttu-id="f7f9b-142">[グループポリシーの管理] で、新しいポリシーを作成するコンテナーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-142">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="f7f9b-143">たとえば、すべての Skype for Business Server コンピューターが Skype for Business Server という名前の OU にある場合、新しいポリシーは Skype for Business Server OU で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-143">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="f7f9b-144">適切なコンテナーを右クリックし、[**このドメインに GPO を作成**] をクリックして、ここにリンクを設定します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-144">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="f7f9b-145">[**新しい GPO** ] ダイアログボックスで、[**名前**] ボックスに新しいグループポリシーオブジェクトの名前を入力し (たとえば、[ **Skype for business Server Audio**])、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-145">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server Audio**), and then click **OK**.</span></span>

4.  <span data-ttu-id="f7f9b-146">新しく作成したポリシーを右クリックし、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-146">Right-click the newly-created policy, and then click **Edit**.</span></span>

<span data-ttu-id="f7f9b-147">ここからは、Active Directory ポリシーとローカルポリシーのどちらを作成するかに関係なく、プロセスは同じになります。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-147">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="f7f9b-148">グループポリシー管理エディターまたはローカルグループポリシーエディターで、[**コンピューターの構成**]、[**ポリシー**]、[ **Windows 設定**] の順に展開し、[**ポリシーベースの QoS**] を右クリックして、[**新しいポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-148">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="f7f9b-149">[**ポリシーベースの QoS** ] ダイアログボックスの [開く] ページで、[**名前**] ボックスに新しいポリシーの名前 (「 **Skype for business Server Audio**」など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-149">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server Audio**) in the **Name** box.</span></span> <span data-ttu-id="f7f9b-150">[ **DSCP 値の指定**] を選択し、値を**46**に設定します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-150">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="f7f9b-151">[**送信スロットルの比率を指定する**] をオフにして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-151">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="f7f9b-152">次のページで、[すべての**アプリケーション**] が選択されていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-152">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="f7f9b-153">この設定は、特定のアプリケーションによって作成されたパケットだけでなく、すべてのパケットを検索して46の DSCP マークを付けて、ネットワークに指示します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-153">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="f7f9b-154">3番目のページで、[**ソース ip アドレス**] と [**宛先 ip アドレス**] の両方が選択されていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-154">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="f7f9b-155">この2つの設定では、どのコンピューター (IP アドレス) がそれらのパケットを送信したか、どのコンピューター (IP アドレス) がそれらのパケットを受信するかに関係なく、パケットが管理されるようにします。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-155">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="f7f9b-156">4ページ目で、[**この QoS ポリシーが適用されるプロトコルを選択**してください] ドロップダウンリストから [ **TCP および UDP** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-156">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="f7f9b-157">TCP (伝送制御プロトコル) と UDP (ユーザーデータグラムプロトコル) は、Skype for Business Server およびそのクライアントアプリケーションで最も一般的に使用される2つのネットワークプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-157">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

6.  <span data-ttu-id="f7f9b-158">見出しの下で、**宛先ポート番号を指定**して、[**この宛先ポートまたは範囲から**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-158">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="f7f9b-159">[付随するテキスト] ボックスに、オーディオ送信用に予約されているポート範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-159">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="f7f9b-160">たとえば、ポート49152からオーディオトラフィック用にポート57500を予約した場合は、「 **49152:57500**」の形式でポート範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-160">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="f7f9b-161">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-161">Click **Finish**.</span></span>

<span data-ttu-id="f7f9b-162">オーディオトラフィックの QoS ポリシーを作成したら、ビデオトラフィック用の第2のポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-162">After you have created the QoS policy for audio traffic, you should create a second policy for video traffic.</span></span> <span data-ttu-id="f7f9b-163">ビデオのポリシーを作成するには、オーディオポリシーを作成する場合と同じ基本的な手順に従い、次のように置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-163">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="f7f9b-164">別の (一意の) ポリシー名 (「 **Skype For Business Server のビデオ**」など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-164">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="f7f9b-165">DSCP 値を46ではなく、 **34**に設定します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-165">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="f7f9b-166">(DSCP 値34は使う必要がないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-166">(Note that you do not have to use a DSCP value of 34.</span></span> <span data-ttu-id="f7f9b-167">唯一の要件は、オーディオに使用したものとは異なる DSCP 値をビデオに使用することです。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-167">The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="f7f9b-168">以前に構成されたポート範囲をビデオトラフィックに使用します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-168">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="f7f9b-169">たとえば、ビデオ用にポート 57501 ~ 65535 を予約している場合は、ポート範囲を次のよう**57501:65535**に設定します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-169">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="f7f9b-170">この場合も、送信先ポートの範囲として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-170">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="f7f9b-171">アプリケーション共有トラフィックを管理するためのポリシーを作成する場合は、3番目のポリシーを作成し、次のように置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-171">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="f7f9b-172">別の (一意の) ポリシー名 (「 **Skype For Business Server アプリケーション共有**」など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-172">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="f7f9b-173">DSCP 値を46の代わりに**24**に設定します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-173">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="f7f9b-174">(この場合も、DSCP 値24を使用する必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-174">(Again, you do not have to use a DSCP value of 24.</span></span> <span data-ttu-id="f7f9b-175">唯一の要件として、アプリケーション共有には、オーディオまたはビデオに使用したのとは異なる DSCP 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-175">The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="f7f9b-176">以前に構成されたポート範囲をビデオトラフィックに使用します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-176">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="f7f9b-177">たとえば、アプリケーション共有用にポート 40803 ~ 49151 を予約している場合は、ポート範囲を " **40803:49151**" に設定します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-177">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="f7f9b-178">作成した新しいポリシーは、エッジサーバーのグループポリシーが更新されるまで有効になりません。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-178">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers.</span></span> <span data-ttu-id="f7f9b-179">グループ ポリシーは定期的に自動更新されますが、グループ ポリシーを更新する必要がある各コンピューター上で次のコマンドを実行すると、即座に強制的に更新することができます。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-179">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="f7f9b-180">このコマンドは、Skype for Business Server、または管理者の資格情報で実行されているコマンドウィンドウから実行できます。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-180">This command can be run from within the Skype for Business Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="f7f9b-181">管理者の資格情報のもとでコマンド ウィンドウを開くには、[**スタート**] メニューをクリックし、[**コマンド プロンプト**] を右クリックして、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-181">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="f7f9b-182">Gpudate を実行した後でも、エッジサーバーの再起動が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-182">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="f7f9b-183">ネットワークパケットが適切な DSCP 値でマークされていることを確認するには、次の手順に従って、各コンピューターに新しいレジストリエントリを作成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-183">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="f7f9b-184">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-184">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="f7f9b-185">[**実行**] ダイアログボックスで、「 **regedit**」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-185">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="f7f9b-186">レジストリエディターで、[ **\_HKEY ローカル\_コンピューター**]、[**システム**]、[ **CurrentControlSet**] の順に展開し、[**サービス**] を展開して、[ **Tcpip**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-186">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="f7f9b-187">[ **Tcpip**] を右クリックし、[**新規作成**] をポイントして、[**キー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-187">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="f7f9b-188">新しいレジストリキーが作成されたら、「 **QoS**」と入力し、enter キーを押してキーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-188">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="f7f9b-189">[ **QoS**] を右クリックし、[**新規作成**] をポイントして、[**文字列値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-189">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="f7f9b-190">新しいレジストリ値が作成されたら、[ **NLA を使用しない**] と入力し、enter キーを押して値の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-190">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="f7f9b-191">[実行し**ない] を**ダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-191">Double-click **Do no use NLA**.</span></span> <span data-ttu-id="f7f9b-192">[**文字列の編集**] ダイアログボックスで、[**値のデータ**] ボックスに「 **1** 」と入力して、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-192">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="f7f9b-193">レジストリエディターを終了し、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f7f9b-193">Close the Registry Editor and reboot your computer.</span></span>

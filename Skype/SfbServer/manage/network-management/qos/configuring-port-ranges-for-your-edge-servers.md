---
title: エッジ サーバーのポート範囲とサービスの品質の構成
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
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
description: この記事では、エッジ サーバーのポート範囲を構成する方法と、A/V エッジ サーバーのサービス品質ポリシーを構成する方法について説明します。
ms.openlocfilehash: c88f784fe1956fa16b8464caa4f9f26e5c61005e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832907"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a><span data-ttu-id="a6a45-103">Skype for Business Server でエッジ サーバーのポート範囲とサービス品質ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="a6a45-103">Configuring port ranges and a Quality of Service policy for your Edge Servers in Skype for Business Server</span></span>

<span data-ttu-id="a6a45-104">この記事では、エッジ サーバーのポート範囲を構成する方法と、A/V エッジ サーバーのサービス品質ポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6a45-104">This article describes how to configure port ranges for Edge Servers and how to configure a Quality of Service policy for your A/V Edge Servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="a6a45-105">ポート範囲を構成する</span><span class="sxs-lookup"><span data-stu-id="a6a45-105">Configure port ranges</span></span>

<span data-ttu-id="a6a45-106">エッジ サーバーでは、オーディオ、ビデオ、およびアプリケーション共有用に個別のポート範囲を構成する必要はありません。同様に、エッジ サーバーに使用されるポート範囲は、会議サーバー、アプリケーション サーバー、および仲介サーバーで使用されるポート範囲と一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a6a45-106">With Edge servers, you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="a6a45-107">この例を続行する前に、このオプションが存在する間はポート範囲を変更しないというストレスが重要です。これは、50000 ポート範囲から移行する場合、一部のシナリオに悪影響を及ぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a6a45-107">Before we proceed with our example, it's important to stress that while this option exists, we recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="a6a45-108">たとえば、次のポート範囲を使用するように会議サーバー、アプリケーション サーバー、および仲介サーバーを構成したとします。</span><span class="sxs-lookup"><span data-stu-id="a6a45-108">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a6a45-109">パケットの種類</span><span class="sxs-lookup"><span data-stu-id="a6a45-109">Packet Type</span></span></th>
<th><span data-ttu-id="a6a45-110">開始ポート</span><span class="sxs-lookup"><span data-stu-id="a6a45-110">Starting Port</span></span></th>
<th><span data-ttu-id="a6a45-111">予約されたポートの数</span><span class="sxs-lookup"><span data-stu-id="a6a45-111">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6a45-112">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="a6a45-112">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="a6a45-113">40803</span><span class="sxs-lookup"><span data-stu-id="a6a45-113">40803</span></span></p></td>
<td><p><span data-ttu-id="a6a45-114">8348</span><span class="sxs-lookup"><span data-stu-id="a6a45-114">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6a45-115">オーディオ</span><span class="sxs-lookup"><span data-stu-id="a6a45-115">Audio</span></span></p></td>
<td><p><span data-ttu-id="a6a45-116">49152</span><span class="sxs-lookup"><span data-stu-id="a6a45-116">49152</span></span></p></td>
<td><p><span data-ttu-id="a6a45-117">8348</span><span class="sxs-lookup"><span data-stu-id="a6a45-117">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6a45-118">ビデオ</span><span class="sxs-lookup"><span data-stu-id="a6a45-118">Video</span></span></p></td>
<td><p><span data-ttu-id="a6a45-119">57500</span><span class="sxs-lookup"><span data-stu-id="a6a45-119">57500</span></span></p></td>
<td><p><span data-ttu-id="a6a45-120">8034</span><span class="sxs-lookup"><span data-stu-id="a6a45-120">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6a45-121"><strong>合計</strong></span><span class="sxs-lookup"><span data-stu-id="a6a45-121"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="a6a45-122">24730</span><span class="sxs-lookup"><span data-stu-id="a6a45-122">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a6a45-123">ご覧のように、音声、ビデオ、アプリケーション共有のポート範囲はポート 40803 から始まるので、合計 24732 ポートが含されます。</span><span class="sxs-lookup"><span data-stu-id="a6a45-123">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="a6a45-124">必要に応じて、Skype for Business Server 管理シェルから次のようなコマンドを実行して、特定のエッジ サーバーでこれらのポート値全体を使用することを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a6a45-124">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Skype for Business Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="a6a45-125">または、次のコマンドを使用して、組織内のすべてのエッジ サーバーを同時に構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="a6a45-125">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="a6a45-126">次の Skype for Business Server 管理シェル コマンドを使用して、エッジ サーバーの現在のポート設定を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a6a45-126">You can verify the current port settings for your Edge Servers by using this Skype for Business Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="a6a45-127">ここでも、これらのオプションを提供しますが、ポート構成の場合はそのままにすることを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="a6a45-127">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a><span data-ttu-id="a6a45-128">A/V エッジ サーバーの QoS ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="a6a45-128">Configure a QoS policy for your A/V Edge Servers</span></span>

<span data-ttu-id="a6a45-129">会議サーバー、アプリケーション サーバー、および仲介サーバーの QoS ポリシーのほか、音声ビデオ エッジ サーバーの内部側用にも音声ポリシーとビデオ ポリシーの両方を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6a45-129">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="a6a45-130">ただし、エッジ サーバーで使用するポリシーは、会議サーバー、アプリケーション サーバー、および仲介サーバーで使用するポリシーとは異なります。</span><span class="sxs-lookup"><span data-stu-id="a6a45-130">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="a6a45-131">会議サーバー、アプリケーション サーバー、および仲介サーバーでは、送信元ポート範囲を指定しました。エッジ サーバーでは、宛先ポート範囲を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6a45-131">For the Conferencing, Application, and Mediation servers, you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="a6a45-132">この理由から、単に会議、アプリケーション、および仲介サーバーの QoS ポリシーをエッジ サーバーに適用することはできません。これらのポリシーは単に機能しません。</span><span class="sxs-lookup"><span data-stu-id="a6a45-132">Because of this, you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="a6a45-133">代わりに、新しいポリシーを作成してエッジ サーバーのみにそれを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6a45-133">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="a6a45-134">次の手順では、エッジ サーバー上のサービスの品質を管理するために使用できる Active Directory グループ ポリシー オブジェクトを作成するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a6a45-134">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="a6a45-135">もちろん、エッジ サーバーが、Active Directory アカウントを持たないスタンドアロン サーバーである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a6a45-135">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="a6a45-136">その場合は、Active Directory グループ ポリシーの代わりにローカル グループ ポリシーを使用できます。唯一の違いは、ローカル グループ ポリシー エディターを使用してこれらのローカル ポリシーを作成し、各エッジ サーバーで同じポリシーセットを個別に作成する必要がある点です。</span><span class="sxs-lookup"><span data-stu-id="a6a45-136">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="a6a45-137">エッジ サーバーでローカル グループ ポリシー エディターを開始するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a6a45-137">To start the Local Group Policy Editor on an Edge server, do the following:</span></span>

1.  <span data-ttu-id="a6a45-138">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6a45-138">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="a6a45-139">[ファイル名 **を指定** して実行] ダイアログ ボックスに **「gpedit.msc」** と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a6a45-139">In the **Run** dialog box, type **gpedit.msc**, and then press ENTER.</span></span>

<span data-ttu-id="a6a45-140">Active Directory ベースのポリシーを作成する場合は、グループ ポリシーの管理がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a6a45-140">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="a6a45-141">その場合は、グループ ポリシーの管理を開き ([スタート] ボタンをクリックし、[管理ツール] をポイントし、[グループ ポリシーの管理] をクリックします)、次の手順を実行します。 </span><span class="sxs-lookup"><span data-stu-id="a6a45-141">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following steps:</span></span>

1.  <span data-ttu-id="a6a45-142">[グループ ポリシーの管理] で、新しいポリシーを作成する必要のあるコンテナーを探します。</span><span class="sxs-lookup"><span data-stu-id="a6a45-142">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="a6a45-143">たとえば、すべての Skype for Business Server コンピューターが Skype for Business Server という名前の OU にある場合は、Skype for Business Server OU に新しいポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6a45-143">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="a6a45-144">適切なコンテナーを右クリックし、[このドメインに GPO を作成する] をクリックし、 **ここにリンクします**。</span><span class="sxs-lookup"><span data-stu-id="a6a45-144">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="a6a45-145">[新 **しい GPO]** ダイアログ ボックスで、[名前] ボックスに新しいグループ ポリシー オブジェクトの名前 **(Skype for Business Server Audio** など) を入力し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6a45-145">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server Audio**), and then click **OK**.</span></span>

4.  <span data-ttu-id="a6a45-146">新しく作成したポリシーを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="a6a45-146">Right-click the newly-created policy, and then click **Edit**.</span></span>

<span data-ttu-id="a6a45-147">これ以降のプロセスは、Active Directory ポリシーを作成する場合もローカル ポリシーを作成する場合も同じです。</span><span class="sxs-lookup"><span data-stu-id="a6a45-147">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="a6a45-148">グループ ポリシー管理エディターまたはローカル グループ ポリシー エディターで、[**コンピューターの構成**]、[**ポリシー**]、[**Windows の設定**] の順に展開し、[**ポリシー ベースの QoS**] を右クリックし、[**新規ポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6a45-148">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="a6a45-149">[ **ポリシーベースの QoS]** ダイアログ ボックスの開始ページで、[名前] ボックスに新しいポリシーの名前 **(Skype for Business Server Audio** など) を **入力** します。</span><span class="sxs-lookup"><span data-stu-id="a6a45-149">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server Audio**) in the **Name** box.</span></span> <span data-ttu-id="a6a45-150">[**DSCP 値を指定する**] を選択し、値を **46** に設定します。</span><span class="sxs-lookup"><span data-stu-id="a6a45-150">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="a6a45-151">[**出力方向のスロットル率を指定する**] をオフのままにして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6a45-151">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="a6a45-152">次のページで、[すべてのアプリケーション]が選択されているのを確認し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="a6a45-152">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="a6a45-153">この設定はネットワークに対し、特定のアプリケーションが作成したパケットのみではなく、DSCP マーキングが 46 のパケットをすべて見つけるよう指示します。</span><span class="sxs-lookup"><span data-stu-id="a6a45-153">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="a6a45-154">3 番目のページで、[すべての送信元 **IP** アドレス] と [すべての宛先 **IP** アドレス] の両方が選択され、[次へ] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a6a45-154">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="a6a45-155">この 2 つの設定により、これらのパケットを送信したコンピューター (IP アドレス) やこれらのパケットを受信するコンピューター (IP アドレス) にかかわらず、パケットが管理されます。</span><span class="sxs-lookup"><span data-stu-id="a6a45-155">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="a6a45-156">4 番目のページで、[**この QoS ポリシーを適用するプロトコルを選択してください**] ドロップダウン リストから [**TCP と UDP**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6a45-156">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="a6a45-157">TCP (伝送制御プロトコル) と UDP (ユーザー データグラム プロトコル) は、Skype for Business Server とそのクライアント アプリケーションで最も一般的に使用される 2 つのネットワーク プロトコルです。</span><span class="sxs-lookup"><span data-stu-id="a6a45-157">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

6.  <span data-ttu-id="a6a45-158">[**宛先ポート番号を指定してください**] で [**次の宛先ポート番号か範囲**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="a6a45-158">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="a6a45-159">この項目のテキスト ボックスに、音声伝送用に予約されているポート範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="a6a45-159">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="a6a45-160">たとえば、ポート 49152 からポート 57500 までをオーディオ トラフィック用に予約した場合は、次の形式でポート範囲を入力します **。49152:57500**。</span><span class="sxs-lookup"><span data-stu-id="a6a45-160">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="a6a45-161">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6a45-161">Click **Finish**.</span></span>

<span data-ttu-id="a6a45-162">音声トラフィックの QoS ポリシーを作成したら、ビデオ トラフィック用の 2 つ目のポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6a45-162">After you have created the QoS policy for audio traffic, you should create a second policy for video traffic.</span></span> <span data-ttu-id="a6a45-163">ビデオのポリシーを作成するには、次の点を置き換えて、音声ポリシーの作成時に従ったのと同じ基本手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a6a45-163">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="a6a45-164">別の (および一意の) ポリシー名 ( **たとえば、Skype for Business Server ビデオ) を使用します**。</span><span class="sxs-lookup"><span data-stu-id="a6a45-164">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="a6a45-p113">DSCP 値を 46 ではなく **34** に設定します (34 の DSCP 値の使用は必須ではありません。要件は、音声に使用したのとは異なる DSCP 値をビデオに使用することだけです)。</span><span class="sxs-lookup"><span data-stu-id="a6a45-p113">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="a6a45-168">ビデオ トラフィックには、以前に構成したポート範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="a6a45-168">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="a6a45-169">たとえば、ポート 57501 ~ 65535 をビデオ用に予約している場合、ポート範囲を次に設定します **。57501:65535**。</span><span class="sxs-lookup"><span data-stu-id="a6a45-169">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="a6a45-170">これも宛先ポート範囲として構成します。</span><span class="sxs-lookup"><span data-stu-id="a6a45-170">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="a6a45-171">アプリケーション共有トラフィックを管理するポリシーを作成する場合は、3 つ目のポリシーを作成して、次の代替を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6a45-171">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="a6a45-172">別の (および一意の) ポリシー名 **(Skype for Business Server アプリケーション** 共有など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="a6a45-172">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="a6a45-p115">DSCP 値を 46 ではなく **24** に設定します (この場合も、24 の DSCP 値の使用は必須ではありません。要件は、音声またはビデオに使用したのとは異なる DSCP 値をアプリケーション共有に使用することだけです)。</span><span class="sxs-lookup"><span data-stu-id="a6a45-p115">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="a6a45-176">ビデオ トラフィックには、以前に構成したポート範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="a6a45-176">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="a6a45-177">たとえば、アプリケーション共有用にポート 40803 ~ 49151 を予約している場合は、ポート範囲を **40803:49151** に設定します。</span><span class="sxs-lookup"><span data-stu-id="a6a45-177">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="a6a45-p117">作成した新しいポリシーは、エッジ サーバーでグループ ポリシーが最新の状態に更新されるまで有効になりません。グループ ポリシーは自動で定期的に最新の状態に更新されますが、グループ ポリシーを更新する必要のあるコンピューターごとに次のコマンドを実行すると、即座に強制更新できます。</span><span class="sxs-lookup"><span data-stu-id="a6a45-p117">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="a6a45-180">このコマンドは、Skype for Business Server 内から、または管理者の資格情報で実行されている任意のコマンド ウィンドウから実行できます。</span><span class="sxs-lookup"><span data-stu-id="a6a45-180">This command can be run from within the Skype for Business Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="a6a45-181">管理者資格情報でコマンド ウィンドウを実行するには、[**スタート**] メニューの [**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6a45-181">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="a6a45-182">Gpudate.exe を実行した後はエッジ サーバーの再起動が必要になる場合があるので注意してください。</span><span class="sxs-lookup"><span data-stu-id="a6a45-182">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="a6a45-183">ネットワーク パケットが確実に適切な DSCP 値でマークされるようにするために、次の手順を実行して各コンピューターに新しいレジストリ エントリを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="a6a45-183">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="a6a45-184">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6a45-184">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="a6a45-185">[ファイル名 **を指定** して実行] ダイアログ ボックスに **「regedit」と** 入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a6a45-185">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="a6a45-186">レジストリ エディターで **、HKEY \_ LOCAL \_ MACHINE、\*\*\*\*システム\*\*\*\*、CurrentControlSet、** サービス、Tcpip の順に **展開します**。 </span><span class="sxs-lookup"><span data-stu-id="a6a45-186">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="a6a45-187">[**Tcpip**] を右クリックし、[**新規**] をポイントして [**キー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6a45-187">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="a6a45-188">新しいレジストリ キーを作成したら **、「QoS」** と入力し、Enter キーを押してキーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="a6a45-188">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="a6a45-189">[**QoS**] を右クリックし、[**新規**] をポイントして [**文字列値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6a45-189">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="a6a45-190">新しいレジストリ値を作成したら **、「NLA** を使用しない」と入力し、Enter キーを押して値の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="a6a45-190">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="a6a45-191">[**NLA を使用しない**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6a45-191">Double-click **Do no use NLA**.</span></span> <span data-ttu-id="a6a45-192">[文字列の **編集]** ダイアログ ボックスで、[値のデータ] ボックスに **「1」** と **入力し\*\*\*\*、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6a45-192">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="a6a45-193">レジストリ エディターを閉じて、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a6a45-193">Close the Registry Editor and reboot your computer.</span></span>

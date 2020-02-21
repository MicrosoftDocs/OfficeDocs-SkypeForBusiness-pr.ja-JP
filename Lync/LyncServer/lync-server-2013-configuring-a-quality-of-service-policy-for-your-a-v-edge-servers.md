---
title: 音声ビデオエッジサーバーの Qos (Quality of Service) ポリシーの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30fece45c4b13bd9cd2c9243dd21cdac1d779733
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="c6665-102">Lync Server 2013 での音声ビデオエッジサーバーの Qos (Quality of Service) ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="c6665-102">Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6665-103">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="c6665-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="c6665-p101">会議サーバー、アプリケーション サーバー、および仲介サーバーの QoS ポリシーのほか、音声ビデオ エッジ サーバーの内部側用にも音声ポリシーとビデオ ポリシーの両方を作成する必要があります。ただし、エッジ サーバーで使用するポリシーは、会議サーバー、アプリケーション サーバー、および仲介サーバーで使用するポリシーとは異なります。会議サーバー、アプリケーション サーバー、および仲介サーバーでは発信元ポート範囲を指定しましたが、エッジ サーバーでは宛先ポート範囲を指定します。したがって、会議サーバー、アプリケーション サーバー、および仲介サーバーの QoS ポリシーをそのままエッジ サーバーには適用できず、それでは動作しません。代わりに、新しいポリシーを作成してエッジ サーバーのみにそれを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6665-p101">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers. However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers. For the Conferencing, Application, and Mediation servers you specified a source port range; with Edge servers, you need to specify a destination port range. Because of that you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work. Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="c6665-p102">ここでは、エッジ サーバーでサービス品質を管理するために使用できる Active Directory グループ ポリシー オブジェクトを作成する手順を説明します。エッジ サーバーがスタンドアロン サーバーになっており、Active Directory アカウントがない場合もあります。その場合は、Active Directory グループ ポリシーの代わりにローカル グループ ポリシーを作成します。違うところは、ローカル グループ ポリシー エディターを使用して作成する点と、エッジ サーバーごとに同じポリシー セットを作成する必要がある点のみです。エッジ サーバーでローカル グループ ポリシー エディターを起動するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c6665-p102">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers. Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts. If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server. To start the Local Group Policy Editor on an Edge server do the following:</span></span>

1.  <span data-ttu-id="c6665-113">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6665-113">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="c6665-114">[**ファイル名を指定して実行**] ダイアログ ボックスで、「**gpedit.msc**」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c6665-114">In the **Run** dialog box, type **gpedit.msc** and then press ENTER.</span></span>

<span data-ttu-id="c6665-p103">Active Directory ベースのポリシーを作成する場合は、グループ ポリシーの管理がインストールされているコンピューターにログオンします。この場合、グループ ポリシーの管理を開き ([**スタート**] ボタンをクリックし、[**管理ツール**] をポイントし、[**グループ ポリシーの管理**] をクリックします)、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c6665-p103">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed. In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following steps:</span></span>

1.  <span data-ttu-id="c6665-p104">グループ ポリシーの管理で、新しいポリシーを作成するコンテナーを特定します。たとえば、すべての Lync Server コンピューターが Lync Server という名前の OU にある場合、新しいポリシーはその Lync Server OU に作成します。</span><span class="sxs-lookup"><span data-stu-id="c6665-p104">In Group Policy Management, locate the container where the new policy should be created. For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="c6665-119">目的のコンテナーを右クリックし、[**このドメインに GPO を作成し、このコンテナーにリンクする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6665-119">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="c6665-120">[**新しい GPO**] ダイアログ ボックスで、[**名前**] ボックスに新しいグループ ポリシー オブジェクトの名前 (**Lync Server 音声**など) を入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6665-120">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="c6665-121">新しく作成したポリシーを右クリックし、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6665-121">Right-click the newly-created policy and then click **Edit**.</span></span>

<span data-ttu-id="c6665-122">これ以降のプロセスは、Active Directory ポリシーを作成する場合もローカル ポリシーを作成する場合も同じです。</span><span class="sxs-lookup"><span data-stu-id="c6665-122">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="c6665-123">グループ ポリシー管理エディターまたはローカル グループ ポリシー エディターで、[**コンピューターの構成**]、[**ポリシー**]、[**Windows の設定**] の順に展開し、[**ポリシー ベースの QoS**] を右クリックし、[**新規ポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6665-123">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="c6665-p105">[**ポリシー ベースの QoS**] ダイアログ ボックスの先頭ページの [**名前**] ボックスに新しいポリシーの名前 (たとえば、「**Lync Server Audio**」) を入力します。[**DSCP 値を指定する**] をオンにし、値を **46** に設定します。[**出力方向のスロットル率を指定する**] はオフのままにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6665-p105">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server Audio**) in the **Name** box. Select **Specify DSCP Value** and set the value to **46**. Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="c6665-p106">次のページで、[**すべてのアプリケーション**] がオンになっていることを確認し、[**次へ**] をクリックします。この設定は、特定のアプリケーションで作成されたパケットだけではなく、DSCP マーキングが 46 のパケットをすべてネットワークで検出することを指定します。</span><span class="sxs-lookup"><span data-stu-id="c6665-p106">On the next page, make sure that **All applications** is selected and then click **Next**. This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="c6665-p107">3 ページ目で、[**すべての発信元 IP アドレス**] と [**すべての宛先 IP アドレス**] の両方が選択されていることを確認し、[**次へ**] をクリックします。この 2 つの設定によって、どのコンピューター (IP アドレス) がパケットを送信したか、およびどのコンピューター (IP アドレス) がパケットを受信するかにかかわらず、パケットが管理されるようになります。</span><span class="sxs-lookup"><span data-stu-id="c6665-p107">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="c6665-131">4 番目のページで、[**この QoS ポリシーを適用するプロトコルを選択してください**] ドロップダウン リストから [**TCP と UDP**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6665-131">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="c6665-132">TCP (伝送制御プロトコル) と UDP (ユーザーデータグラムプロトコル) は、Lync Server とそのクライアントアプリケーションでよく使用される2つのネットワークプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="c6665-132">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

6.  <span data-ttu-id="c6665-p109">[**宛先ポート番号を指定してください**] で [**次の宛先ポート番号か範囲**] をオンにします。この項目のテキスト ボックスに、音声伝送用に予約されているポート範囲を入力します。たとえば、ポート 49152 ～ 57500 を音声トラフィック用に予約した場合、「**49152:57500**」という形式でポート範囲を入力します。[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6665-p109">Under the heading **Specify the destination port number**, select **From this destination port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 49152 through ports 57500 for audio traffic then enter the port range using this format: **49152:57500**. Click **Finish**.</span></span>

<span data-ttu-id="c6665-p110">音声トラフィック用の QoS ポリシーを作成した後、ビデオ トラフィック用に 2 つ目のポリシーも作成する必要があります。ビデオ用のポリシーを作成する基本的な手順は、音声ポリシーの作成手順と同じですが、次の点が異なります。</span><span class="sxs-lookup"><span data-stu-id="c6665-p110">After you have created the QoS policy for audio traffic you should create a second policy for video traffic. To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="c6665-139">異なる (一意の) ポリシー名 (たとえば、「**Lync Server Video**」) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6665-139">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="c6665-p111">DSCP 値は 46 ではなく **34** に設定します (DSCP 値は必ずしも 34 にする必要はありません。唯一の要件は、音声用に使用した DSCP 値とは異なる値をビデオ用に使用することです)。</span><span class="sxs-lookup"><span data-stu-id="c6665-p111">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="c6665-p112">ビデオ トラフィック用にあらかじめ構成したポート範囲を使用します。たとえば、ポート 57501 ～ 65535 をビデオ用に予約した場合、「**57501:65535**」のようにポート範囲を設定します。これも宛先ポート範囲として構成します。</span><span class="sxs-lookup"><span data-stu-id="c6665-p112">Use the previously-configured port range for video traffic. For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**. Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="c6665-146">アプリケーション共有トラフィックを管理するためのポリシーを作成する場合は、次の点を変えて 3 つ目のポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6665-146">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="c6665-147">別の (一意の) ポリシー名 (**Lync Server アプリケーション共有**など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6665-147">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="c6665-p113">DSCP 値を 46 ではなく **24** に設定します (この場合も、24 の DSCP 値の使用は必須ではありません。要件は、音声またはビデオに使用したのとは異なる DSCP 値をアプリケーション共有に使用することだけです)。</span><span class="sxs-lookup"><span data-stu-id="c6665-p113">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="c6665-p114">アプリケーション共有用にあらかじめ構成したポート範囲を使用します。たとえば、ポート 40803 ～ 49151 をアプリケーション共有用に予約した場合、「**40803:49151**」のようにポート範囲を設定します。</span><span class="sxs-lookup"><span data-stu-id="c6665-p114">Use the previously-configured port range for video traffic. For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="c6665-p115">作成した新しいポリシーは、エッジ サーバーでグループ ポリシーが最新の状態に更新されるまで有効になりません。グループ ポリシーは自動で定期的に最新の状態に更新されますが、グループ ポリシーを更新する必要のあるコンピューターごとに次のコマンドを実行すると、即座に強制更新できます。</span><span class="sxs-lookup"><span data-stu-id="c6665-p115">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="c6665-155">このコマンドは、Lync Server 内から、または管理者の資格情報で実行されている任意のコマンドウィンドウから実行できます。</span><span class="sxs-lookup"><span data-stu-id="c6665-155">This command can be run from within the Lync Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="c6665-156">管理者資格情報でコマンド ウィンドウを実行するには、[**スタート**] メニューの [**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6665-156">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="c6665-157">Gpudate.exe を実行した後はエッジ サーバーの再起動が必要になる場合があるので注意してください。</span><span class="sxs-lookup"><span data-stu-id="c6665-157">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="c6665-158">ネットワーク パケットが確実に適切な DSCP 値でマークされるようにするために、次の手順を実行して各コンピューターに新しいレジストリ エントリを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="c6665-158">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="c6665-159">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6665-159">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="c6665-160">[**ファイル名を指定して実行**] ダイアログ ボックスで「**regedit**」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c6665-160">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="c6665-161">レジストリエディターで、[ **HKEY\_LOCAL\_MACHINE**] を展開し、[**システム**] を展開し、[ **CurrentControlSet**] を展開し、[**サービス**] を展開して、[ **Tcpip**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="c6665-161">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="c6665-p117">[**Tcpip**] を右クリックし、[**新規**] をポイントして [**キー**] をクリックします。新しいレジストリ キーを作成した後、「**QoS**」と入力して Enter キーを押し、キーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="c6665-p117">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="c6665-p118">[**QoS**] を右クリックし、[**新規**] をポイントして [**文字列値**] をクリックします。新しいレジストリ値を作成した後、「**NLA を使用しない**」と入力して Enter キーを押し、キーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="c6665-p118">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="c6665-p119">[**NLA を使用しない**] をダブルクリックします。[**文字列値の編集**] ダイアログ ボックスで、[**値データ**] ボックスに「**1**」と入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6665-p119">Double-click **Do no use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="c6665-168">レジストリ エディターを閉じて、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="c6665-168">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


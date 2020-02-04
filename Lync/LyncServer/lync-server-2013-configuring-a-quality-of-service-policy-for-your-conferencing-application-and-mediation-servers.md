---
title: 'Lync Server 2013: 電話会議、アプリケーションおよび仲介サーバーの QoS (Quality of Service) ポリシーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your Conferencing, Application, and Mediation servers
ms:assetid: 8adcbbc5-c9f5-476d-ab7f-72e61859cacf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205076(v=OCS.15)
ms:contentKeyID: 48184769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 385530e45c208ced2cce4815d1f60e596c2a08b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="cf47d-102">電話会議、アプリケーションおよび仲介サーバーの Lync Server 2013 における QoS (Quality of Service) ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="cf47d-102">Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf47d-103">_**最終更新日:** 2014-06-23_</span><span class="sxs-lookup"><span data-stu-id="cf47d-103">_**Topic Last Modified:** 2014-06-23_</span></span>

<span data-ttu-id="cf47d-104">ポート範囲を構成すると、指定した種類のすべてのトラフィック (たとえば、すべての音声トラフィック) が同じポートセットを通過するようにすることで、サービスの品質を活用できます。</span><span class="sxs-lookup"><span data-stu-id="cf47d-104">Configuring port ranges facilitates the use of Quality of Service by ensuring that all traffic of a specified type (for example, all audio traffic) travels through the same set of ports.</span></span> <span data-ttu-id="cf47d-105">これにより、特定のパケットをシステムで識別してマークすることが簡単になります。ポート49152が音声トラフィック用に予約されている場合は、ポート49152経由で移動したパケットは、オーディオパケットであることを示す DSCP コードでマークできます。</span><span class="sxs-lookup"><span data-stu-id="cf47d-105">This makes it easy for the system to identify and mark a given packet: if port 49152 is reserved for audio traffic, then any packet traveling through port 49152 can be marked with a DSCP code that indicates that this is an audio packet.</span></span> <span data-ttu-id="cf47d-106">これにより、ルーターは、パケットをオーディオパケットとして識別し、マークされていないパケット (あるサーバーから別のサーバーにファイルをコピーするために使用されるパケットなど) よりも高い優先順位を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="cf47d-106">In turn, this enables routers to identify the packet as an audio packet, and give it higher priority than unmarked packets (such as packets used to copy a file from one server to another).</span></span>

<span data-ttu-id="cf47d-107">ただし、ポートのセットを特定の種類のトラフィックに制限するだけでは、適切な DSCP コードでマークされているポートを経由してパケットが移動されることはありません。</span><span class="sxs-lookup"><span data-stu-id="cf47d-107">However, simply restricting a set of ports to a specific type of traffic does not result in packets traveling through those ports being marked with the appropriate DSCP code.</span></span> <span data-ttu-id="cf47d-108">ポート範囲の定義に加えて、各ポート範囲に関連付ける DSCP コードを指定するサービス品質ポリシーも作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf47d-108">In addition to defining port ranges you must also create Quality of Service policies that specify the DSCP code to be associated with each port range.</span></span> <span data-ttu-id="cf47d-109">Microsoft Lync Server 2013 では、通常、オーディオ用とビデオ用の2つのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-109">For Microsoft Lync Server 2013 that typically means creating two policies: one for audio and one for video.</span></span>

<span data-ttu-id="cf47d-110">サービス品質ポリシーは、グループポリシーを使って、最も簡単に作成、管理できます。</span><span class="sxs-lookup"><span data-stu-id="cf47d-110">Quality of Service policies are most-easily created, and managed, by using Group Policy.</span></span> <span data-ttu-id="cf47d-111">(これらのポリシーは、ローカルセキュリティポリシーを使用して作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf47d-111">(These same policies can also be created by using local security policies.</span></span> <span data-ttu-id="cf47d-112">ただし、そのためには、すべてのコンピューターで同じ手順を繰り返す必要があります。)最初の QoS ポリシーのセット (1 つはオーディオ用とビデオ用) を、会議サーバー、アプリケーションサーバー、または仲介サーバーサービスを実行している Lync Server コンピューターにのみ適用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cf47d-112">However, that requires you to repeat the same procedure on each and every computer.) Your initial set of QoS policies (one for audio and one for video) should be applied only to Lync Server computers running the Conferencing server, Application server, and/or Mediation server services.</span></span> <span data-ttu-id="cf47d-113">これらのすべてのコンピューターが同じ Active Directory OU に配置されている場合は、その OU に新しいグループポリシーオブジェクト (GPO) を割り当てるだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="cf47d-113">If all of these computers are located in the same Active Directory OU then you can simply assign the new Group Policy object (GPO) to that OU.</span></span> <span data-ttu-id="cf47d-114">または、別の手順を実行して、指定したコンピューターに新しいポリシーを作成することもできます。たとえば、セキュリティグループに適切なコンピューターを配置し、グループポリシーセキュリティフィルターを使用して、そのセキュリティグループだけに GPO を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="cf47d-114">Alternatively, you can take other steps to target the new policy to the specified computers; for example, you can place the appropriate computers in a security group, then use Group Policy security filtering to apply the GPO just to that security group.</span></span>

<span data-ttu-id="cf47d-115">音声を管理するためのサービス品質ポリシーを作成するには、グループポリシー管理がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="cf47d-115">In order to create a Quality of Service policy for managing audio, log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="cf47d-116">[グループポリシーの管理] を開き ([**スタート**] をクリックし、[**管理ツール**] をポイントして、[**グループポリシーの管理**] をクリックし)、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-116">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="cf47d-117">[グループポリシーの管理] で、新しいポリシーを作成するコンテナーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="cf47d-117">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="cf47d-118">たとえば、すべての Lync Server コンピューターが Lync Server という名前の OU にある場合、新しいポリシーは Lync Server OU で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf47d-118">For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="cf47d-119">適切なコンテナーを右クリックし、[**このドメインに GPO を作成**] をクリックして、ここにリンクを設定します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-119">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="cf47d-120">[**新しい GPO** ] ダイアログボックスで、[**名前**] ボックスに新しいグループポリシーオブジェクトの名前を入力し (「 **Lync Server QoS**」など)、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf47d-120">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server QoS**) and then click **OK**.</span></span>

4.  <span data-ttu-id="cf47d-121">新しく作成したポリシーを右クリックし、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf47d-121">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="cf47d-122">グループポリシー管理エディターで、[**コンピューターの構成**]、[**ポリシー**]、[ **Windows 設定**] の順に展開し、[**ポリシーベースの QoS**] を右クリックして、[**新しいポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf47d-122">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="cf47d-123">[**ポリシーベースの QoS** ] ダイアログボックスの [開く] ページで、[**名前**] ボックスに新しいポリシーの名前 (例: **Lync Server QoS**) を入力します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-123">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server QoS**) in the **Name** box.</span></span> <span data-ttu-id="cf47d-124">[ **DSCP 値の指定**] を選択し、値を**46**に設定します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-124">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="cf47d-125">[**送信スロットルの比率を指定する**] をオフにして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf47d-125">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="cf47d-126">次のページで、[すべての**アプリケーション**] が選択されていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf47d-126">On the next page, make sure that **All applications** is selected and then click **Next**.</span></span> <span data-ttu-id="cf47d-127">これにより、すべてのアプリケーションが指定のポート範囲のパケットを指定した DSCP コードに一致させるだけです。</span><span class="sxs-lookup"><span data-stu-id="cf47d-127">This simply ensures that all applications will match packets from the specified port range with the specified DSCP code.</span></span>

8.  <span data-ttu-id="cf47d-128">3番目のページで、**すべてのソース ip アドレスと宛先 ip アドレス**が選択されていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf47d-128">On the third page, make sure that both **Any source IP address and Any destination IP address** are selected and then click **Next**.</span></span> <span data-ttu-id="cf47d-129">この2つの設定では、どのコンピューター (IP アドレス) がそれらのパケットを送信したか、どのコンピューター (IP アドレス) がそれらのパケットを受信するかに関係なく、パケットが管理されるようにします。</span><span class="sxs-lookup"><span data-stu-id="cf47d-129">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="cf47d-130">4ページ目で、[**この QoS ポリシーが適用されるプロトコルを選択**してください] ドロップダウンリストから [ **TCP および UDP** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cf47d-130">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="cf47d-131">TCP (伝送制御プロトコル) と UDP (ユーザーデータグラムプロトコル) は、Lync Server およびそのクライアントアプリケーションで最も一般的に使用される2つのネットワークプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="cf47d-131">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="cf47d-132">見出しの下で、**ソースポート番号を指定**して、[**このソースポートまたは範囲から**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-132">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="cf47d-133">[付随するテキスト] ボックスに、オーディオ送信用に予約されているポート範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-133">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="cf47d-134">たとえば、ポート49152からオーディオトラフィック用にポート57500を予約した場合、次の形式を使用してポート範囲を入力します**49152:57500**。</span><span class="sxs-lookup"><span data-stu-id="cf47d-134">For example, if you reserved ports 49152 through ports 57500 for audio traffic enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="cf47d-135">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf47d-135">Click **Finish**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf47d-136">46の DSCP 値は、何らかの方法で行うことができます。 DSCP 46 はオーディオパケットをマークするために使われることが多いのですが、オーディオ通信には DSCP 46 を使う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cf47d-136">The DSCP value of 46 is somewhat arbitrary: although DSCP 46 is often used for marking audio packets, you do not have to use DSCP 46 for audio communications.</span></span> <span data-ttu-id="cf47d-137">既に QoS を実装していて、オーディオ用に別の DSCP コード (たとえば、DSCP 40) を使用している場合は、その同じコードを使用するようにサービスの品質ポリシーを構成する必要があります (例:40 for audio)。</span><span class="sxs-lookup"><span data-stu-id="cf47d-137">If you have already implemented QoS and you are using a different DSCP code for audio (for example, DSCP 40) then you should configure your Quality of Service policy to use that same code (i.e., 40 for audio).</span></span> <span data-ttu-id="cf47d-138">現在、サービスの品質を実装している場合は、その値が一般的にオーディオパケットをマークするために使用されるため、オーディオには DSCP 46 を使うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cf47d-138">If you are just now implementing Quality of Service, then it is recommended that you use DSCP 46 for audio, simply because that value is commonly used to mark audio packets.</span></span>



</div>

<span data-ttu-id="cf47d-139">音声トラフィックの QoS ポリシーを作成したら、次に、ビデオトラフィックに対して2番目のポリシーを作成します (必要に応じて、アプリケーション共有トラフィックを管理するための第3のポリシーを作成します)。</span><span class="sxs-lookup"><span data-stu-id="cf47d-139">After you have created the QoS policy for audio traffic you should then create a second policy for video traffic (and, optionally, a third policy for managing application sharing traffic).</span></span> <span data-ttu-id="cf47d-140">ビデオのポリシーを作成するには、オーディオポリシーを作成する場合と同じ基本的な手順に従い、次のように置き換えます。</span><span class="sxs-lookup"><span data-stu-id="cf47d-140">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="cf47d-141">別の (一意の) ポリシー名 (「 **Lync Server Video**」など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-141">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="cf47d-142">DSCP 値を46ではなく、 **34**に設定します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-142">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="cf47d-143">(DSCP 値34は使う必要がないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cf47d-143">(Note that you do not have to use a DSCP value of 34.</span></span> <span data-ttu-id="cf47d-144">唯一の要件は、オーディオに使用したものとは異なる DSCP 値をビデオに使用することです。</span><span class="sxs-lookup"><span data-stu-id="cf47d-144">The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="cf47d-145">以前に構成したポート範囲をビデオトラフィックに使用します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-145">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="cf47d-146">たとえば、57501 ~ 65535 のビデオ用の予約ポートがある場合は、ポート範囲**57501:65535**を次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-146">For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**.</span></span>

<span data-ttu-id="cf47d-147">アプリケーション共有トラフィックを管理するためのポリシーを作成する場合は、3番目のポリシーを作成し、次のように置き換えます。</span><span class="sxs-lookup"><span data-stu-id="cf47d-147">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="cf47d-148">別の (一意の) ポリシー名 (「 **Lync Server アプリケーション共有**」など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-148">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="cf47d-149">DSCP 値を46の代わりに**24**に設定します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-149">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="cf47d-150">(この場合も、DSCP 値24を使用する必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="cf47d-150">(Again, you do not have to use a DSCP value of 24.</span></span> <span data-ttu-id="cf47d-151">唯一の要件として、アプリケーション共有には、オーディオまたはビデオに使用したのとは異なる DSCP 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-151">The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="cf47d-152">以前に構成したポート範囲をビデオトラフィックに使用します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-152">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="cf47d-153">たとえば、アプリケーション共有用にポート 40803 ~ 49151 を予約している場合は、ポート範囲**40803:49151**を次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-153">For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="cf47d-154">作成した新しいポリシーは、Lync Server コンピューターのグループポリシーが更新されるまで有効になりません。</span><span class="sxs-lookup"><span data-stu-id="cf47d-154">The new policies you have created will not take effect until Group Policy has been refreshed on your Lync Server computers.</span></span> <span data-ttu-id="cf47d-155">グループ ポリシーは定期的に自動更新されますが、グループ ポリシーを更新する必要がある各コンピューター上で次のコマンドを実行すると、即座に強制的に更新することができます。</span><span class="sxs-lookup"><span data-stu-id="cf47d-155">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="cf47d-156">このコマンドは、Lync Server 管理シェルから、または管理者の資格情報で実行されているコマンドウィンドウから実行できます。</span><span class="sxs-lookup"><span data-stu-id="cf47d-156">This command can be run from within the Lync Server Management Shell or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="cf47d-157">管理者の資格情報のもとでコマンド ウィンドウを開くには、[**スタート**] メニューをクリックし、[**コマンド プロンプト**] を右クリックして、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf47d-157">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="cf47d-158">新しい QoS ポリシーが適用されていることを確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cf47d-158">To verify that the new QoS policies have been applied, do the following:</span></span>

1.  <span data-ttu-id="cf47d-159">Lync Server コンピューターで、[**スタート**] をクリックし、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf47d-159">On a Lync Server computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="cf47d-160">[**実行**] ダイアログボックスで、「 **regedit** 」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-160">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="cf47d-161">レジストリエディターで、[**コンピューター**] を展開し、[ **\_HKEY ローカル\_コンピューター**]、[**ソフトウェア**]、[**ポリシー**]、[ **Microsoft**]、[ **Windows**]、[ **QoS**] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-161">In Registry Editor, expand **Computer**, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Policies**, expand **Microsoft**, expand **Windows**, and then click **QoS**.</span></span> <span data-ttu-id="cf47d-162">[ **Qos** ] の下に、作成した各 qos ポリシーのレジストリキーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf47d-162">Under **QoS** you should see registry keys for each of the QoS policies you just created.</span></span> <span data-ttu-id="cf47d-163">たとえば、2つの新しいポリシー (Lync Server Audio QoS という名前の別の Lync Server ビデオ QoS という名前) を作成した場合、Lync Server Audio QoS および Lync Server Video qos のレジストリエントリが必要です。</span><span class="sxs-lookup"><span data-stu-id="cf47d-163">For example, if you created two new policies (one named Lync Server Audio QoS and the other named Lync Server Video QoS) you should registry entries for Lync Server Audio QoS and Lync Server Video QoS.</span></span>

<span data-ttu-id="cf47d-164">ネットワークパケットが適切な DSCP 値でマークされていることを確認するには、次の手順に従って、各コンピューターに新しいレジストリエントリを作成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="cf47d-164">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="cf47d-165">[**スタート**] をクリックし、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf47d-165">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="cf47d-166">[**実行**] ダイアログボックスで、「 **regedit** 」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-166">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="cf47d-167">レジストリエディターで、[ **\_HKEY ローカル\_コンピューター**]、[**システム**]、[ **CurrentControlSet**] の順に展開し、[**サービス**] を展開して、[ **Tcpip**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-167">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="cf47d-168">[ **Tcpip**] を右クリックし、[**新規作成**] をポイントして、[**キー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf47d-168">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="cf47d-169">新しいレジストリキーが作成されたら、「 **QoS** 」と入力し、enter キーを押してキーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-169">After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="cf47d-170">[ **QoS**] を右クリックし、[**新規作成**] をポイントして、[**文字列値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf47d-170">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="cf47d-171">新しいレジストリ値が作成されたら、[ **NLA を使用しない**] と入力し、enter キーを押して値の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-171">After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="cf47d-172">[ **NLA を使わない**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf47d-172">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="cf47d-173">[**文字列の編集**] ダイアログボックスで、[**値のデータ**] ボックスに「 **1** 」と入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf47d-173">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="cf47d-174">レジストリエディターを終了し、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="cf47d-174">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


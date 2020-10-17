---
title: 'Lync Server 2013: 会議、アプリケーション、および仲介サーバーのサービス品質ポリシーの構成'
description: 'Lync Server 2013: 会議、アプリケーション、および仲介サーバーのサービス品質ポリシーの構成。'
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
ms.openlocfilehash: 0ee82c5f1f6b3025c4052b7e27c1013e0624b756
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545643"
---
# <a name="configuring-a-quality-of-service-policy-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="6e1f4-103">Lync Server 2013 での会議、アプリケーション、および仲介サーバーの Qos (Quality of Service) ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="6e1f4-103">Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e1f4-104">_**トピックの最終更新日:** 2014-06-23_</span><span class="sxs-lookup"><span data-stu-id="6e1f4-104">_**Topic Last Modified:** 2014-06-23_</span></span>

<span data-ttu-id="6e1f4-p101">ポート範囲を構成すると、指定した種類のすべてのトラフィック (すべての音声トラフィックなど) が同じポート セットを通過するようになるため、サービス品質の使用が促進されます。これにより、システムは特定のパケットを簡単に識別およびマークできるようになります。ポート 49152 が音声トラフィック用に予約されている場合、ポート 49152 を通過するパケットは、これが音声パケットであることを示す DSCP コードでマークできます。さらに、これによりルーターはパケットを音声パケットとして識別し、マークされていないパケット (サーバーからサーバーへのファイルのコピーに使用されるパケットなど) よりも高い優先順位を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-p101">Configuring port ranges facilitates the use of Quality of Service by ensuring that all traffic of a specified type (for example, all audio traffic) travels through the same set of ports. This makes it easy for the system to identify and mark a given packet: if port 49152 is reserved for audio traffic, then any packet traveling through port 49152 can be marked with a DSCP code that indicates that this is an audio packet. In turn, this enables routers to identify the packet as an audio packet, and give it higher priority than unmarked packets (such as packets used to copy a file from one server to another).</span></span>

<span data-ttu-id="6e1f4-108">ただし、ポートのセットを特定の種類のトラフィックに限定するだけでは、これらのポートを通過するパケットは適切な DSCP コードでマークされません。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-108">However, simply restricting a set of ports to a specific type of traffic does not result in packets traveling through those ports being marked with the appropriate DSCP code.</span></span> <span data-ttu-id="6e1f4-109">ポート範囲の定義に加えて、各ポート範囲に関連付ける DSCP コードを指定するサービス品質ポリシーを作成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-109">In addition to defining port ranges you must also create Quality of Service policies that specify the DSCP code to be associated with each port range.</span></span> <span data-ttu-id="6e1f4-110">Microsoft Lync Server 2013 の場合、通常は2つのポリシーを作成します。1つはオーディオ用、もう1つはビデオ用です。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-110">For Microsoft Lync Server 2013 that typically means creating two policies: one for audio and one for video.</span></span>

<span data-ttu-id="6e1f4-111">サービスの品質ポリシーは、グループポリシーを使用して、最も簡単に作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-111">Quality of Service policies are most-easily created, and managed, by using Group Policy.</span></span> <span data-ttu-id="6e1f4-112">(これらの同じポリシーは、ローカルセキュリティポリシーを使用して作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-112">(These same policies can also be created by using local security policies.</span></span> <span data-ttu-id="6e1f4-113">ただし、すべてのコンピューターで同じ手順を繰り返す必要があります。)最初の QoS ポリシーのセット (オーディオとビデオ用に1つ) は、会議サーバー、アプリケーションサーバー、または仲介サーバーサービスを実行している Lync Server コンピューターにのみ適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-113">However, that requires you to repeat the same procedure on each and every computer.) Your initial set of QoS policies (one for audio and one for video) should be applied only to Lync Server computers running the Conferencing server, Application server, and/or Mediation server services.</span></span> <span data-ttu-id="6e1f4-114">これらのすべてのコンピューターが同じ Active Directory OU に配置されている場合は、その OU に新しいグループポリシーオブジェクト (GPO) を簡単に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-114">If all of these computers are located in the same Active Directory OU then you can simply assign the new Group Policy object (GPO) to that OU.</span></span> <span data-ttu-id="6e1f4-115">または、指定したコンピューターに新しいポリシーを適用するために、他の手順を実行することもできます。たとえば、適切なコンピューターをセキュリティグループに配置した後、グループポリシーセキュリティフィルターを使用して、そのセキュリティグループに GPO を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-115">Alternatively, you can take other steps to target the new policy to the specified computers; for example, you can place the appropriate computers in a security group, then use Group Policy security filtering to apply the GPO just to that security group.</span></span>

<span data-ttu-id="6e1f4-116">音声管理用のサービス品質ポリシーを作成するには、グループ ポリシーの管理がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-116">In order to create a Quality of Service policy for managing audio, log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="6e1f4-117">グループ ポリシー管理を開き ([**スタート**] をクリックし、[**管理ツール**] をポイントし、[**グループ ポリシーの管理**] をクリックして、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-117">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="6e1f4-p105">グループ ポリシーの管理で、新しいポリシーを作成するコンテナーを特定します。たとえば、すべての Lync Server コンピューターが Lync Server という名前の OU にある場合、新しいポリシーはその Lync Server OU に作成します。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-p105">In Group Policy Management, locate the container where the new policy should be created. For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="6e1f4-120">目的のコンテナーを右クリックし、[**このドメインに GPO を作成し、このコンテナーにリンクする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-120">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="6e1f4-121">[ **新しい GPO** ] ダイアログボックスで、[ **名前** ] ボックスに新しいグループポリシーオブジェクトの名前 (「 **Lync Server QoS**」など) を入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-121">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server QoS**) and then click **OK**.</span></span>

4.  <span data-ttu-id="6e1f4-122">新規に作成したポリシーを右クリックし、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-122">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="6e1f4-123">グループ ポリシー管理エディターで、[**コンピューターの構成**]、[**ポリシー**]、[**Windows の設定**] の順に展開し、[**ポリシー ベースの QoS**] を右クリックして [**新規ポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-123">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="6e1f4-124">[**ポリシーベースの QoS** ] ダイアログボックスの [開始] ページで、[**名前**] ボックスに新しいポリシーの名前 ( **Lync Server QoS**など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-124">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server QoS**) in the **Name** box.</span></span> <span data-ttu-id="6e1f4-125">[**DSCP 値を指定する**] を選択し、値を **46** に設定します。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-125">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="6e1f4-126">[**出力方向のスロットル率を指定する**] をオフのままにして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-126">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="6e1f4-p107">次のページで、[**すべてのアプリケーション**] が選択されていることを確認し、[**次へ**] をクリックします。これにより、すべてのアプリケーションが、指定した DSCP コードを持つ指定したポート範囲からのパケットに一致するようになります。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-p107">On the next page, make sure that **All applications** is selected and then click **Next**. This simply ensures that all applications will match packets from the specified port range with the specified DSCP code.</span></span>

8.  <span data-ttu-id="6e1f4-p108">3 番目のページで、[**すべての発信元 IP アドレス] と [すべての宛先 IP アドレス**] の両方が選択されていることを確認し、[**次へ**] をクリックします。この 2 つの設定により、これらのパケットを送信したコンピューター (IP アドレス) やこれらのパケットを受信するコンピューター (IP アドレス) にかかわらず、パケットが管理されます。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-p108">On the third page, make sure that both **Any source IP address and Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="6e1f4-131">4 番目のページで、[**この QoS ポリシーを適用するプロトコルを選択してください**] ドロップダウン リストから [**TCP と UDP**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-131">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="6e1f4-132">TCP (伝送制御プロトコル) と UDP (ユーザーデータグラムプロトコル) は、Lync Server とそのクライアントアプリケーションでよく使用される2つのネットワークプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-132">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="6e1f4-p110">[**発信元ポート番号を指定してください**] 見出しの下で、[**次の発信元ポート番号か範囲**] をクリックします。付随するテキスト ボックスに、オーディオ送信用に予約されたポート範囲を入力します。たとえば、ポート 49152 からポート 57500 までを音声トラフィック用に予約した場合は、**49152:57500** という形式を使用してポート範囲を入力します。[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-p110">Under the heading **Specify the source port number**, select **From this source port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 49152 through ports 57500 for audio traffic enter the port range using this format: **49152:57500**. Click **Finish**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e1f4-p111">46 の DSCP 値はある程度任意です。DSCP 46 は多くの場合に音声パケットのマーキングに使用されますが、音声通信に必ずしも DSCP 46 を使用する必要はありません。QoS を既に実装してあり、音声に別の DSCP コード (たとえば DSCP 40) を使用している場合は、その同じコードを使用 (つまり、音声に 40 を使用) するようにサービス品質ポリシーを構成する必要があります。通常は音声パケットのマーキングに DSCP 46 が使用されるため、サービス品質を実装したばかりの場合は、この値を音声に使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-p111">The DSCP value of 46 is somewhat arbitrary: although DSCP 46 is often used for marking audio packets, you do not have to use DSCP 46 for audio communications. If you have already implemented QoS and you are using a different DSCP code for audio (for example, DSCP 40) then you should configure your Quality of Service policy to use that same code (i.e., 40 for audio). If you are just now implementing Quality of Service, then it is recommended that you use DSCP 46 for audio, simply because that value is commonly used to mark audio packets.</span></span>



</div>

<span data-ttu-id="6e1f4-p112">音声トラフィックの QoS ポリシーを作成した後で、ビデオ トラフィック用の 2 つ目のポリシー (また、オプションでアプリケーション共有トラフィックの管理用の 3 つ目のポリシー) を作成する必要があります。ビデオのポリシーを作成するには、次の点を置き換えて、音声ポリシーの作成時に従ったのと同じ基本手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-p112">After you have created the QoS policy for audio traffic you should then create a second policy for video traffic (and, optionally, a third policy for managing application sharing traffic). To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="6e1f4-142">別の (一意の) ポリシー名 (**Lync Server ビデオ**など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-142">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="6e1f4-p113">DSCP 値を 46 ではなく **34** に設定します (34 の DSCP 値の使用は必須ではありません。要件は、音声に使用したのとは異なる DSCP 値をビデオに使用することだけです)。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-p113">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="6e1f4-p114">ビデオ トラフィックには以前に構成したポート範囲を使用します。たとえば、ポート 57501 から 65535 までをビデオ用に予約した場合は、ポート範囲を **57501:65535** に設定します。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-p114">Use the previously-configured port range for video traffic. For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**.</span></span>

<span data-ttu-id="6e1f4-148">アプリケーション共有トラフィックの管理用のポリシーを作成する場合は、次の点を置き換えて 3 つ目のポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-148">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="6e1f4-149">別の (一意の) ポリシー名 (**Lync Server アプリケーション共有**など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-149">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="6e1f4-p115">DSCP 値を 46 ではなく **24** に設定します (この場合も、24 の DSCP 値の使用は必須ではありません。要件は、音声またはビデオに使用したのとは異なる DSCP 値をアプリケーション共有に使用することだけです)。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-p115">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="6e1f4-p116">ビデオ トラフィックには以前に構成したポート範囲を使用します。たとえば、ポート 40803 から 49151 までをアプリケーション共有に予約した場合は、ポート範囲を **40803:49151** に設定します。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-p116">Use the previously-configured port range for video traffic. For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="6e1f4-155">作成した新しいポリシーは、グループポリシーが Lync Server コンピューター上で更新されるまで有効になりません。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-155">The new policies you have created will not take effect until Group Policy has been refreshed on your Lync Server computers.</span></span> <span data-ttu-id="6e1f4-156">グループ ポリシーは自身を定期的に更新しますが、グループ ポリシーを更新する必要のある各コンピューターで次のコマンドを実行することにより、強制的に即時に更新できます。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-156">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="6e1f4-157">このコマンドは、Lync Server 管理シェルから、または管理者の資格情報で実行されている任意のコマンドウィンドウから実行できます。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-157">This command can be run from within the Lync Server Management Shell or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="6e1f4-158">管理者の資格情報でコマンド ウィンドウを実行するには、[**スタート**] ボタンをクリックして、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-158">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="6e1f4-159">新しい QoS ポリシーが適用されたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-159">To verify that the new QoS policies have been applied, do the following:</span></span>

1.  <span data-ttu-id="6e1f4-160">Lync Server コンピューターで、[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-160">On a Lync Server computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="6e1f4-161">[**ファイル名を指定して実行**] ダイアログ ボックスで、「**regedit**」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-161">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="6e1f4-162">レジストリエディターで、[ **コンピューター**] を展開し、[ **HKEY \_ ローカル \_ コンピューター**]、[ **ソフトウェア**]、[ **ポリシー**]、[ **Microsoft**]、[ **Windows**] の順に展開し、[ **QoS**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-162">In Registry Editor, expand **Computer**, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Policies**, expand **Microsoft**, expand **Windows**, and then click **QoS**.</span></span> <span data-ttu-id="6e1f4-163">[**QoS**] に、作成した各 QoS ポリシーのレジストリ キーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-163">Under **QoS** you should see registry keys for each of the QoS policies you just created.</span></span> <span data-ttu-id="6e1f4-164">たとえば、2つの新しいポリシー (Lync server Audio QoS、もう1つは Lync Server Video QoS という名前) を作成した場合は、Lync Server Audio QoS および Lync Server Video QoS のレジストリエントリを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-164">For example, if you created two new policies (one named Lync Server Audio QoS and the other named Lync Server Video QoS) you should registry entries for Lync Server Audio QoS and Lync Server Video QoS.</span></span>

<span data-ttu-id="6e1f4-165">ネットワーク パケットが適切な DSCP 値でマークされるようにするには、次の手順を実行して、各コンピューターに新しいレジストリ エントリを作成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-165">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="6e1f4-166">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-166">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="6e1f4-167">[**ファイル名を指定して実行**] ダイアログ ボックスで「**regedit**」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-167">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="6e1f4-168">レジストリエディターで、[ **HKEY \_ LOCAL \_ MACHINE**] を展開し、[ **システム**] を展開し、[ **CurrentControlSet**] を展開し、[ **サービス**] を展開して、[ **Tcpip**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-168">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="6e1f4-p120">[**Tcpip**] を右クリックし、[**新規**] をポイントして [**キー**] をクリックします。新しいレジストリ キーを作成した後、「**QoS**」と入力して Enter キーを押し、キーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-p120">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="6e1f4-p121">[**QoS**] を右クリックし、[**新規**] をポイントして、[**文字列値**] をクリックします。新しいレジストリ値を作成した後で、「**Do not use NLA**」と入力し、Enter キーを押して値の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-p121">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="6e1f4-p122">[**Do no use NLA**] をダブルクリックします。[**文字列の編集**] ダイアログ ボックスで、[**値のデータ**] ボックスに「**1**」と入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-p122">Double-click **Do not use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="6e1f4-175">レジストリ エディターを閉じて、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6e1f4-175">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


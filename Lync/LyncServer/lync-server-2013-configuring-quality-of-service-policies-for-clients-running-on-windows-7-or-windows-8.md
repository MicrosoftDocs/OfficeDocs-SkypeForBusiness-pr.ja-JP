---
title: 'Lync Server 2013: Windows 7 または Windows 8 で実行されているクライアントのサービス品質ポリシーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cd058e2903160f1c9f4ea06e30959b63953ab01
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534974"
---
# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a><span data-ttu-id="6cae2-102">Windows 7 または Windows 8 で実行しているクライアントの Lync Server 2013 でのサービスの品質ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="6cae2-102">Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cae2-103">_**トピックの最終更新日:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="6cae2-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="6cae2-104">Lync クライアントで使用するポート範囲を指定することに加えて、クライアントコンピューターに適用されるサービスの品質を個別に作成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="6cae2-104">In addition to specifying port ranges for use by your Lync clients you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="6cae2-105">(会議、アプリケーション、および仲介サーバー用に作成されたサービスの品質をクライアントコンピューターに適用する必要はありません)。この情報は、Lync 2013 クライアントと Windows 7 または Windows 8 のどちらかを実行しているコンピューターにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="6cae2-105">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Lync 2013 client and either Windows 7 or Windows 8.</span></span>

<span data-ttu-id="6cae2-106">次の例では、このポート範囲のセットを使用して、オーディオ ポリシーとビデオ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6cae2-106">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6cae2-107">クライアント トラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="6cae2-107">Client Traffic Type</span></span></th>
<th><span data-ttu-id="6cae2-108">開始ポート</span><span class="sxs-lookup"><span data-stu-id="6cae2-108">Port Start</span></span></th>
<th><span data-ttu-id="6cae2-109">ポート範囲</span><span class="sxs-lookup"><span data-stu-id="6cae2-109">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6cae2-110">オーディオ</span><span class="sxs-lookup"><span data-stu-id="6cae2-110">Audio</span></span></p></td>
<td><p><span data-ttu-id="6cae2-111">50020</span><span class="sxs-lookup"><span data-stu-id="6cae2-111">50020</span></span></p></td>
<td><p><span data-ttu-id="6cae2-112">1280</span><span class="sxs-lookup"><span data-stu-id="6cae2-112">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cae2-113">ビデオ</span><span class="sxs-lookup"><span data-stu-id="6cae2-113">Video</span></span></p></td>
<td><p><span data-ttu-id="6cae2-114">58000</span><span class="sxs-lookup"><span data-stu-id="6cae2-114">58000</span></span></p></td>
<td><p><span data-ttu-id="6cae2-115">1280</span><span class="sxs-lookup"><span data-stu-id="6cae2-115">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cae2-116">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="6cae2-116">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="6cae2-117">42000</span><span class="sxs-lookup"><span data-stu-id="6cae2-117">42000</span></span></p></td>
<td><p><span data-ttu-id="6cae2-118">1280</span><span class="sxs-lookup"><span data-stu-id="6cae2-118">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cae2-119">ファイル送信</span><span class="sxs-lookup"><span data-stu-id="6cae2-119">File transfer</span></span></p></td>
<td><p><span data-ttu-id="6cae2-120">42020</span><span class="sxs-lookup"><span data-stu-id="6cae2-120">42020</span></span></p></td>
<td><p><span data-ttu-id="6cae2-121">1280</span><span class="sxs-lookup"><span data-stu-id="6cae2-121">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6cae2-122">Windows 7 または Windows 8 コンピューターのサービス品質のオーディオポリシーを作成するには、まずグループポリシー管理がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6cae2-122">To create a Quality of Service audio policy for Windows 7 or Windows 8 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="6cae2-123">グループ ポリシー管理を開き ([**スタート**] をクリックし、[**管理ツール**] をポイントし、[**グループ ポリシーの管理**] をクリックして、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6cae2-123">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="6cae2-p103">グループ ポリシーの管理で、新しいポリシーのを作成するコンテナーを見つけます。たとえば、クライアント コンピューターすべてが Clients という名前の OU にある場合、新しいポリシーは Client OU に作成します。</span><span class="sxs-lookup"><span data-stu-id="6cae2-p103">In Group Policy Management, locate the container where the new policy should be created. For example, if all your client computers are located in an OU named Clients then the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="6cae2-126">適切なコンテナーを右クリックし、[**このドメインに GPO を作成し、このコンテナにリンクする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cae2-126">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="6cae2-127">[**新しい GPO**] ダイアログ ボックスで、新しいグループ ポリシー オブジェクトの名前を [**名前**] ボックスに入力し (たとえば「**Lync Audio**」)、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cae2-127">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="6cae2-128">新しく作成したポリシーを右クリックし、[**編集**]　をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cae2-128">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="6cae2-129">グループ ポリシー管理エディターで [**コンピューターの構成**]、[**ポリシー**]、[**Windows の設定**] の順に展開し、[**ポリシー ベースの QoS**] を右クリックし、[**新規ポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cae2-129">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="6cae2-p104">[**ポリシー ベースの QoS**] ダイアログ ボックスの開始ページで、新しいポリシーの名前を [**名前**] ボックスに入力します (たとえば「**Lync Audio**」)。[**DSCP 値を指定する**] を選択し、値を「**46**」に設定します。[**出力方向のスロットル率を指定する**] はオフのままで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cae2-p104">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Audio**) in the **Name** box. Select **Specify DSCP Value** and set the value to **46**. Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="6cae2-133">次のページで、[ **この実行可能ファイル名を持つアプリケーションのみ** ] を選択し **Lync.exe**名前を入力して、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cae2-133">On the next page, select **Only applications with this executable name** and enter the name **Lync.exe**, and then click **Next**.</span></span> <span data-ttu-id="6cae2-134">この設定では、Lync クライアントからの一致するトラフィックのみに優先順位を付けるようにポリシーに指示します。</span><span class="sxs-lookup"><span data-stu-id="6cae2-134">This setting instructs the policy to only prioritize matching traffic from the Lync client.</span></span>

8.  <span data-ttu-id="6cae2-p106">3 ページ目で、[**すべての発信元 IP アドレス**] と [**すべての宛先 IP アドレス**] の両方が選択されていることを確認し、[**次へ**] をクリックします。この 2 つの設定によって、どのコンピューター (IP アドレス) がパケットを送信したか、およびどのコンピューター (IP アドレス) がパケットを受信するかにかかわらず、パケットが管理されるようになります。</span><span class="sxs-lookup"><span data-stu-id="6cae2-p106">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="6cae2-137">4 番目のページで、[**この QoS ポリシーを適用するプロトコルを選択してください**] ドロップダウン リストから [**TCP と UDP**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cae2-137">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="6cae2-138">TCP (伝送制御プロトコル) と UDP (ユーザーデータグラムプロトコル) は、Lync Server とそのクライアントアプリケーションでよく使用される2つのネットワークプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="6cae2-138">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="6cae2-p108">[**発信元ポート番号を指定してください**] という見出しの下にある [**次の発信元ポート番号か範囲**] を選択します。付随するテキスト ボックスに、オーディオ送信用に予約されたポート範囲を入力します。たとえば、50020 から 50039 までのポートをオーディオ トラフィック用に予約した場合は、「**50020:50039**」という形式でポート範囲を入力します。[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cae2-p108">Under the heading **Specify the source port number**, select **From this source port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**. Click **Finish**.</span></span>

<span data-ttu-id="6cae2-p109">オーディオ用の QoS ポリシーを作成した後で、2 番目にビデオ用のポリシーを作成する必要があります。ビデオ用のポリシーを作成するには、オーディオ ポリシーを作成したときと基本的には同じ手順に従い、次の点を変えます。</span><span class="sxs-lookup"><span data-stu-id="6cae2-p109">After you have created the QoS policy for audio you should then create a second policy for video. To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="6cae2-145">異なる（かつ一意の）ポリシー名を使用します (たとえば「**Lync Video**」)。</span><span class="sxs-lookup"><span data-stu-id="6cae2-145">Use a different (and unique) policy name (for example, **Lync Video**).</span></span>

  - <span data-ttu-id="6cae2-p110">DSCP の値を 46 ではなく「**34**」に設定します。(前に説明したとおり、DSCP の値に 34 を使用する必要はありません。ただ、オーディオに使用したのとは異なる DSCP の値を割り当てる必要があります。)</span><span class="sxs-lookup"><span data-stu-id="6cae2-p110">Set the DSCP value to **34** instead of 46. (As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="6cae2-p111">ビデオ トラフィック用に構成しておいたポート範囲を使用します。たとえば、58000 から 58019 までのポートをビデオ用に予約した場合は、ポート範囲を「**58000:58019**」に設定します。</span><span class="sxs-lookup"><span data-stu-id="6cae2-p111">Use the previously-configured port range for video traffic. For example, if you have reserved ports 58000 through 58019 for video, then set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="6cae2-150">アプリケーション共有トラフィックを管理するポリシーを作成する場合は、次の点を変えます。</span><span class="sxs-lookup"><span data-stu-id="6cae2-150">If you decide to create a policy for managing application sharing traffic make these substitutions:</span></span>

  - <span data-ttu-id="6cae2-151">異なる（かつ一意の）ポリシー名を使用します (たとえば「**Lync Server Application Sharing**」)。</span><span class="sxs-lookup"><span data-stu-id="6cae2-151">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="6cae2-p112">DSCP の値を 46 ではなく「**24**」に設定します。(この値も 24 にする必要はありません。ただ、オーディオとビデオに使用した DSCP の値とは別にする必要があります。)</span><span class="sxs-lookup"><span data-stu-id="6cae2-p112">Set the DSCP value to **24** instead of 46. (Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="6cae2-p113">ビデオ トラフィック用に構成しておいたポート範囲を使用します。たとえば、42000 から 42019 までのポートをアプリケーション共有用に予約した場合は、ポート範囲を「**42000:42019**」に設定します。</span><span class="sxs-lookup"><span data-stu-id="6cae2-p113">Use the previously-configured port range for video traffic. For example, if you have reserved ports 42000 through 42019 for application sharing, then set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="6cae2-156">ファイル転送ポリシーは次のようにします。</span><span class="sxs-lookup"><span data-stu-id="6cae2-156">For a file transfer policy:</span></span>

  - <span data-ttu-id="6cae2-157">異なる（かつ一意の）ポリシー名を使用します (たとえば「**Lync Server File Transfers**」)。</span><span class="sxs-lookup"><span data-stu-id="6cae2-157">Use a different (and unique) policy name (for example, **Lync Server File Transfers**).</span></span>

  - <span data-ttu-id="6cae2-p114">DSCP の値を「**14**」に設定します。(この値も 14 にする必要はありません。ただ、一意の DSCP にする必要があります。)</span><span class="sxs-lookup"><span data-stu-id="6cae2-p114">Set the DSCP value to **14**. (Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="6cae2-160">アプリケーションに対して事前に構成されたポート範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="6cae2-160">Use the previously-configured port range for application.</span></span> <span data-ttu-id="6cae2-161">たとえば、42020 から 42039 までのポートをアプリケーション共有用に予約した場合は、ポート範囲を「**42020:42039**」に設定します。</span><span class="sxs-lookup"><span data-stu-id="6cae2-161">For example, if you have reserved ports 42020 through 42039 for application sharing, then set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="6cae2-p116">新しく作成したポリシーは、クライアント コンピューター上でグループ ポリシーが更新されるまで有効になりません。グループ ポリシーは定期的に自動更新を行いますが、グループ ポリシーの更新が必要な各コンピューター上で次のコマンドを実行することにより、強制的に即時更新できます。</span><span class="sxs-lookup"><span data-stu-id="6cae2-p116">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="6cae2-p117">このコマンドは、管理者の資格情報で実行されていれば、どのコマンド ウィンドウからでも実行できます。コマンド ウィンドウを管理者の資格情報で実行するには、[**スタート**]をクリックして、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cae2-p117">This command can be run from any command window that is running under administrator credentials. To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="6cae2-166">なお、これらのポリシーが対象とするのはクライアント コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="6cae2-166">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="6cae2-167">これらは、Lync Server を実行しているサーバーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="6cae2-167">They should not be applied to servers running Lync Server.</span></span>

<span data-ttu-id="6cae2-168">ネットワーク パケットが適切な DSCP 値でマークされるようにするには、次の手順を実行して、各コンピューターに新しいレジストリ エントリを作成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="6cae2-168">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="6cae2-169">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cae2-169">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="6cae2-170">[**ファイル名を指定して実行**] ダイアログ ボックスで「**regedit**」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6cae2-170">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="6cae2-171">レジストリエディターで、[ **HKEY \_ LOCAL \_ MACHINE**] を展開し、[ **システム**] を展開し、[ **CurrentControlSet**] を展開し、[ **サービス**] を展開して、[ **Tcpip**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="6cae2-171">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="6cae2-p119">[**Tcpip**] を右クリックし、[**新規**] をポイントして [**キー**] をクリックします。新しいレジストリ キーを作成した後、「**QoS**」と入力して Enter キーを押し、キーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="6cae2-p119">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="6cae2-p120">[**QoS**] を右クリックし、[**新規**] をポイントして、[**文字列値**] をクリックします。新しいレジストリ値を作成した後で、「**Do not use NLA**」と入力し、Enter キーを押して値の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="6cae2-p120">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="6cae2-p121">[**Do no use NLA**] をダブルクリックします。[**文字列の編集**] ダイアログ ボックスで、[**値のデータ**] ボックスに「**1**」と入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cae2-p121">Double-click **Do not use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="6cae2-178">レジストリ エディターを閉じ、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6cae2-178">Close the Registry Editor and then reboot your computer.</span></span>

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="6cae2-179">複数のネットワーク アダプターがあるコンピューター上での品質サービスの構成</span><span class="sxs-lookup"><span data-stu-id="6cae2-179">Configuring Quality of Service on Computers with Multiple Network Adapters</span></span>

<span data-ttu-id="6cae2-p122">複数のネットワーク アダプターを持つコンピューターがある場合、DSCP 値が、構成した値ではなく 0x00 と表示される場合があります。通常、このような表示になるのは、1 つ以上のネットワーク アダプターが Active Directory ドメインにアクセスできないコンピューターです (たとえば、アダプターがプライベート ネットワークに使用されている場合)。そのような場合、ドメインへアクセスできるアダプターには DSCP の値がマークされますが、ドメインへアクセスできないアダプターにはマークされません。</span><span class="sxs-lookup"><span data-stu-id="6cae2-p122">If you have a computer that has multiple network adapters you might occasionally run into issues where DSCP values are shown as 0x00 rather than the configured value. This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network). In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="6cae2-p123">ドメインへアクセスできないアダプターも含めて、コンピューターのネットワーク アダプターすべてに DSCP の値をマークしたい場合は、レジストリに値を追加して構成する必要があります。そのためには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6cae2-p123">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, then you will need to add and configure a value to the registry. That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="6cae2-185">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cae2-185">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="6cae2-186">[**ファイル名を指定して実行**] ダイアログ ボックスで「**regedit**」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6cae2-186">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="6cae2-187">レジストリエディターで、[ **HKEY \_ LOCAL \_ MACHINE**] を展開し、[ **システム**] を展開し、[ **CurrentControlSet**] を展開し、[ **サービス**] を展開して、[ **Tcpip**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="6cae2-187">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="6cae2-p124">「**QoS**」というレジストリ キーがない場合は、 [**Tcpip**] 右クリックし、[**新規**] をポイントして、[**キー**] をクリックします。新しいキーを作成した後で、「**QoS**」と入力し、Enter キーを押してキーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="6cae2-p124">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**. After the new key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="6cae2-p125">[**QoS**] を右クリックし、[**新規**] をポイントして、[**文字列値**] をクリックします。新しいレジストリ値を作成した後で、「**Do not use NLA**」と入力し、Enter キーを押して値の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="6cae2-p125">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="6cae2-p126">[**Do no use NLA**] をダブルクリックします。[**文字列の編集**] ダイアログ ボックスで、[**値のデータ**] ボックスに「**1**」と入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cae2-p126">Double-click **Do not use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

<span data-ttu-id="6cae2-194">変更を有効にするには、新しいレジストリ値を作成して構成した後でコンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cae2-194">After creating and configuring the new registry value you will need to reboot your computer in order for the changes to take effect.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


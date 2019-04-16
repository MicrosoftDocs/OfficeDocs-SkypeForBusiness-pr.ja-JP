---
title: Microsoft Teams クライアントでサービスの品質 (QoS) を実施する
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: マイクロソフト チームのクライアントにサービスの品質 (QoS) を導入します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 101deb10cf3d86dbc97116cad269556683d03be4
ms.sourcegitcommit: 946c77b847c1b2c5c43802ecfb0a918fa4f562d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2019
ms.locfileid: "31869847"
---
# <a name="set-qos-on-windows-clients"></a><span data-ttu-id="efc4c-103">Windows クライアントで QoS を設定する</span><span class="sxs-lookup"><span data-stu-id="efc4c-103">Set QoS on Windows clients</span></span>

<span data-ttu-id="efc4c-104">チーム クライアントの DSCP 値を定義済みのソースのポート範囲を設定するのには、グループ ポリシー内のポリシー ベースの QoS を使用できます。</span><span class="sxs-lookup"><span data-stu-id="efc4c-104">You can use policy-based QoS within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="efc4c-105">次の表で指定されたポートの範囲は、各作業負荷のポリシーを作成する開始点です。</span><span class="sxs-lookup"><span data-stu-id="efc4c-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="efc4c-106">_最初のポートの範囲を推奨_</span><span class="sxs-lookup"><span data-stu-id="efc4c-106">_Recommended initial port ranges_</span></span>

<span data-ttu-id="efc4c-107">メディア トラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="efc4c-107">Media traffic type</span></span>| <span data-ttu-id="efc4c-108">クライアント ソース ポートの範囲</span><span class="sxs-lookup"><span data-stu-id="efc4c-108">Client source port range</span></span> |<span data-ttu-id="efc4c-109">プロトコル</span><span class="sxs-lookup"><span data-stu-id="efc4c-109">Protocol</span></span>|<span data-ttu-id="efc4c-110">DSCP 値</span><span class="sxs-lookup"><span data-stu-id="efc4c-110">DSCP value</span></span>|<span data-ttu-id="efc4c-111">DSCP クラス</span><span class="sxs-lookup"><span data-stu-id="efc4c-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="efc4c-112">オーディオ</span><span class="sxs-lookup"><span data-stu-id="efc4c-112">Audio</span></span>| <span data-ttu-id="efc4c-113">50,000 – 50,019</span><span class="sxs-lookup"><span data-stu-id="efc4c-113">50,000–50,019</span></span>|<span data-ttu-id="efc4c-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="efc4c-114">TCP/UDP</span></span>|<span data-ttu-id="efc4c-115">46</span><span class="sxs-lookup"><span data-stu-id="efc4c-115">46</span></span>|<span data-ttu-id="efc4c-116">完全優先転送 (EF)</span><span class="sxs-lookup"><span data-stu-id="efc4c-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="efc4c-117">ビデオ</span><span class="sxs-lookup"><span data-stu-id="efc4c-117">Video</span></span>| <span data-ttu-id="efc4c-118">50,020 – 50,039</span><span class="sxs-lookup"><span data-stu-id="efc4c-118">50,020–50,039</span></span>|<span data-ttu-id="efc4c-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="efc4c-119">TCP/UDP</span></span>|<span data-ttu-id="efc4c-120">34</span><span class="sxs-lookup"><span data-stu-id="efc4c-120">34</span></span>|<span data-ttu-id="efc4c-121">相対的優先転送 (AF41)</span><span class="sxs-lookup"><span data-stu-id="efc4c-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="efc4c-122">アプリケーションと画面の共有</span><span class="sxs-lookup"><span data-stu-id="efc4c-122">Application/Screen Sharing</span></span>| <span data-ttu-id="efc4c-123">50,040-50,059</span><span class="sxs-lookup"><span data-stu-id="efc4c-123">50,040–50,059</span></span>|<span data-ttu-id="efc4c-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="efc4c-124">TCP/UDP</span></span>|<span data-ttu-id="efc4c-125">18</span><span class="sxs-lookup"><span data-stu-id="efc4c-125">18</span></span>|<span data-ttu-id="efc4c-126">相対的優先転送 (AF21)</span><span class="sxs-lookup"><span data-stu-id="efc4c-126">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="efc4c-127">可能な限り、グループ ポリシー オブジェクト内のポリシー ベースの QoS 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="efc4c-128">次の手順は、[ポートの範囲および Skype ビジネス サーバー用のクライアントにサービスの品質ポリシーの構成](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)、必要なことができない可能性がある追加の詳細情報を持っている非常に似ています。</span><span class="sxs-lookup"><span data-stu-id="efc4c-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="efc4c-129">10 の Windows コンピューターのドメインに参加しているオーディオ QoS ポリシーを作成するには、最初にログオン グループ ポリシーの管理がインストールされているコンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="efc4c-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="efc4c-130">グループ ポリシーの管理] を開きます ([開始] をクリックして、管理ツール] をポイントし、[グループ ポリシーの管理] をクリック) し、次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="efc4c-131">グループ ポリシーの管理では、新しいポリシーを作成するコンテナーを探します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="efc4c-132">たとえば、OU という名前の**クライアント**には、すべてのクライアント コンピューターが存在する場合、クライアント OU で新しいポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efc4c-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Client OU.</span></span>

2. <span data-ttu-id="efc4c-133">適切なコンテナーを右クリックし、**このドメインに GPO を作成しここにリンク**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efc4c-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3. <span data-ttu-id="efc4c-134">**新しい GPO** ] ダイアログ ボックスで **[名前**] ボックスに新しいグループ ポリシー オブジェクトの名前を入力し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efc4c-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4. <span data-ttu-id="efc4c-135">新しく作成したポリシーを右クリックし、し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efc4c-135">Right-click the newly created policy, and then click **Edit**.</span></span>

5. <span data-ttu-id="efc4c-136">グループ ポリシー管理エディターで、**コンピューター**の構成**Windows の設定**を展開し、**ポリシー ベースの QoS**を右クリックし、**新規ポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efc4c-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6. <span data-ttu-id="efc4c-137">**ポリシー ベースの QoS** ] ダイアログ ボックスで [開始] ページで、 **[名前**] ボックスで新しいポリシーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="efc4c-138">**DSCP 値を指定**を選択し、 **46**に値を設定します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="efc4c-139">オフの場合、**アウト バウンドのスロットル率を指定**のままにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efc4c-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="efc4c-140">次のページでは、**この実行可能ファイル名を持つアプリケーションのみ**を選択し、 **Teams.exe**名前を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efc4c-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="efc4c-141">この設定では、のみのチームのクライアントからのトラフィックが一致する優先順位付けポリシーを指示します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

8. <span data-ttu-id="efc4c-142">3 番目のページでは、**任意の発信元 IP アドレス**と**宛先の IP アドレス**の両方が選択されているし、[**次へ**] をクリックを確認します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="efc4c-143">これら 2 つの設定では、パケットが管理されることを確認してどのコンピューター (IP アドレス) がパケットを送信し、パケットをどのコンピューター (IP アドレス) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="efc4c-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

9. <span data-ttu-id="efc4c-144">[4] ページでは、**この QoS ポリシーを適用するプロトコルを選択**」ドロップ ダウン リストから**TCP および UDP**を選択します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="efc4c-145">TCP (伝送制御プロトコル) と UDP (ユーザー データグラム プロトコル) は、最も一般的に使用される 2 つのネットワーク プロトコルです。</span><span class="sxs-lookup"><span data-stu-id="efc4c-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

10. <span data-ttu-id="efc4c-146">**発信元ポート番号の指定**の見出しの下には、**この送信元ポートまたは範囲から**選択します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="efc4c-147">付随するテキスト ボックスで、オーディオの転送用に予約されたポートの範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="efc4c-148">50019 オーディオ トラフィック用のポートをポート 50000 を予約する場合のこの形式を使用するポートの範囲を入力するたとえば、: **50000:50019**。</span><span class="sxs-lookup"><span data-stu-id="efc4c-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="efc4c-149">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efc4c-149">Click **Finish**.</span></span>

11. <span data-ttu-id="efc4c-150">ビデオ、アプリケーションとデスクトップの共有、6 と 10 の手順で適切な値を代入するためのポリシーを作成する手順 5 ~ 10 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="efc4c-151">クライアント コンピューターにグループ ポリシーを更新するまでは、作成した新しいポリシーを有効になります。</span><span class="sxs-lookup"><span data-stu-id="efc4c-151">The new policies you’ve created won’t take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="efc4c-152">グループ ポリシーは、独自に定期的に更新されたが、次の手順で即時更新を強制することができます。</span><span class="sxs-lookup"><span data-stu-id="efc4c-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="efc4c-153">グループ ポリシーを更新する各コンピューターでは、コマンド コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="efc4c-153">On each computer for which you want to refresh Group Policy, open a command console.</span></span> <span data-ttu-id="efc4c-154">コマンド コンソールを管理者として実行するように設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-154">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="efc4c-155">コマンド プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-155">At the command prompt, enter</span></span>

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="efc4c-156">グループ ポリシー オブジェクト内の DSCP マーキングを確認します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-156">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="efc4c-157">グループ ポリシー オブジェクトの値が設定されていることを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-157">To verify that the values from the Group Policy object have been set, perform the following steps.</span></span>

1. <span data-ttu-id="efc4c-158">コマンド コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="efc4c-158">Open a command console.</span></span> <span data-ttu-id="efc4c-159">コマンド コンソールを管理者として実行するように設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-159">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="efc4c-160">コマンド プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-160">At the command prompt, enter:</span></span>

   ``` powershell
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="efc4c-161">レポートを生成、gp.txt をという名前のテキスト ファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-161">This will generate a report and send it to a text file named gp.txt.</span></span> <span data-ttu-id="efc4c-162">代わりに、gp.html という名前の読みやすい html 形式のレポートで同じデータを生成するのには次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-162">Alternatively, you can enter the following command to produce the same data in a more readable HTML report named gp.html:</span></span>

   ``` powershell
   gpresult /H >gp.html
   ```

   <span data-ttu-id="efc4c-163">![Gpresult コマンドを実行しているコンソール ・ ウィンドウのスクリーン ショットです]。(media/Qos-in-Teams-Image3.png "Gpresult コマンドを実行しているコンソール ・ ウィンドウのスクリーン ショットです")。</span><span class="sxs-lookup"><span data-stu-id="efc4c-163">![Screenshot of the console window running the gpresult command.](media/Qos-in-Teams-Image3.png "Screenshot of the console window running the gpresult command.")</span></span>

3. <span data-ttu-id="efc4c-164">、生成されたファイルで**適用されたグループ ポリシー オブジェクト**の見出しを検索し、以前に作成したグループ ポリシー オブジェクトの名前に適用されたポリシーの一覧であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-164">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

4. <span data-ttu-id="efc4c-165">レジストリ エディターを開きとに移動します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-165">Open the Registry Editor, and go to:</span></span>

   <span data-ttu-id="efc4c-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\\</span><span class="sxs-lookup"><span data-stu-id="efc4c-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\\</span></span>

   <span data-ttu-id="efc4c-167">表 4 に記載されているレジストリ エントリの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-167">Verify the values for the registry entries listed in Table 4.</span></span>

   <span data-ttu-id="efc4c-168">_表 4 です。QoS の Windows のレジストリ エントリの値_</span><span class="sxs-lookup"><span data-stu-id="efc4c-168">_Table 4. Values for Windows registry entries for QoS_</span></span>

   |          <span data-ttu-id="efc4c-169">名前</span><span class="sxs-lookup"><span data-stu-id="efc4c-169">Name</span></span>          |  <span data-ttu-id="efc4c-170">種類</span><span class="sxs-lookup"><span data-stu-id="efc4c-170">Type</span></span>  |    <span data-ttu-id="efc4c-171">データ</span><span class="sxs-lookup"><span data-stu-id="efc4c-171">Data</span></span>     |
   |         :---:          |:---:   |    :---:    |
   |    <span data-ttu-id="efc4c-172">Application Name</span><span class="sxs-lookup"><span data-stu-id="efc4c-172">Application Name</span></span>    | <span data-ttu-id="efc4c-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="efc4c-173">REG_SZ</span></span> |  <span data-ttu-id="efc4c-174">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="efc4c-174">Teams.exe</span></span>  |
   |       <span data-ttu-id="efc4c-175">DSCP Value</span><span class="sxs-lookup"><span data-stu-id="efc4c-175">DSCP Value</span></span>       | <span data-ttu-id="efc4c-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="efc4c-176">REG_SZ</span></span> |     <span data-ttu-id="efc4c-177">46</span><span class="sxs-lookup"><span data-stu-id="efc4c-177">46</span></span>      |
   |        <span data-ttu-id="efc4c-178">Local IP</span><span class="sxs-lookup"><span data-stu-id="efc4c-178">Local IP</span></span>        | <span data-ttu-id="efc4c-179">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="efc4c-179">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="efc4c-180">Local IP Prefix Length</span><span class="sxs-lookup"><span data-stu-id="efc4c-180">Local IP Prefix Length</span></span> | <span data-ttu-id="efc4c-181">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="efc4c-181">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="efc4c-182">Local Port</span><span class="sxs-lookup"><span data-stu-id="efc4c-182">Local Port</span></span>       | <span data-ttu-id="efc4c-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="efc4c-183">REG_SZ</span></span> | <span data-ttu-id="efc4c-184">50000-50019</span><span class="sxs-lookup"><span data-stu-id="efc4c-184">50000-50019</span></span> |
   |        <span data-ttu-id="efc4c-185">プロトコル</span><span class="sxs-lookup"><span data-stu-id="efc4c-185">Protocol</span></span>        | <span data-ttu-id="efc4c-186">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="efc4c-186">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="efc4c-187">Remote IP</span><span class="sxs-lookup"><span data-stu-id="efc4c-187">Remote IP</span></span>        | <span data-ttu-id="efc4c-188">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="efc4c-188">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="efc4c-189">リモート IP プレフィックス</span><span class="sxs-lookup"><span data-stu-id="efc4c-189">Remote IP Prefix</span></span>    | <span data-ttu-id="efc4c-190">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="efc4c-190">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="efc4c-191">Remote Port</span><span class="sxs-lookup"><span data-stu-id="efc4c-191">Remote Port</span></span>       | <span data-ttu-id="efc4c-192">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="efc4c-192">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="efc4c-193">Throttle Rate</span><span class="sxs-lookup"><span data-stu-id="efc4c-193">Throttle Rate</span></span>      | <span data-ttu-id="efc4c-194">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="efc4c-194">REG_SZ</span></span> |     <span data-ttu-id="efc4c-195">-1</span><span class="sxs-lookup"><span data-stu-id="efc4c-195">-1</span></span>      |

5. <span data-ttu-id="efc4c-196">アプリケーション名のエントリの値が使用しているクライアントに対して適切であることを確認し、DSCP 値とローカル ・ ポートの両方のエントリに、グループ ポリシー オブジェクトの設定が反映されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="efc4c-196">Verify that the value for the Application Name entry is correct for the client you’re using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>

---
title: Microsoft Teams クライアントでサービスの品質 (QoS) を実装する
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: サービスの品質 (QoS) を使用して、Microsoft Teams デスクトップ クライアントのネットワーク トラフィックを最適化する方法について説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 263e2d07992bd491259b82856413548fcd9741fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094785"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a><span data-ttu-id="62805-103">Microsoft Teams クライアントでサービスの品質 (QoS) を実装する</span><span class="sxs-lookup"><span data-stu-id="62805-103">Implement Quality of Service (QoS) in Microsoft Teams clients</span></span>

<span data-ttu-id="62805-104">グループ ポリシー内でポリシーベースのサービス品質 (QoS) を使用して、Teams クライアントで定義済みの DSCP 値のソース ポート範囲を設定できます。</span><span class="sxs-lookup"><span data-stu-id="62805-104">You can use policy-based Quality of Service (QoS) within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="62805-105">次の表に示すポート範囲は、ワークロードごとにポリシーを作成する開始点です。</span><span class="sxs-lookup"><span data-stu-id="62805-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="62805-106">*表 1。推奨される初期ポート範囲*</span><span class="sxs-lookup"><span data-stu-id="62805-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="62805-107">メディア トラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="62805-107">Media traffic type</span></span>| <span data-ttu-id="62805-108">クライアントの送信元ポート範囲</span><span class="sxs-lookup"><span data-stu-id="62805-108">Client source port range</span></span> |<span data-ttu-id="62805-109">プロトコル</span><span class="sxs-lookup"><span data-stu-id="62805-109">Protocol</span></span>|<span data-ttu-id="62805-110">DSCP 値</span><span class="sxs-lookup"><span data-stu-id="62805-110">DSCP value</span></span>|<span data-ttu-id="62805-111">DSCP クラス</span><span class="sxs-lookup"><span data-stu-id="62805-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="62805-112">オーディオ</span><span class="sxs-lookup"><span data-stu-id="62805-112">Audio</span></span>| <span data-ttu-id="62805-113">50,000–50,019</span><span class="sxs-lookup"><span data-stu-id="62805-113">50,000–50,019</span></span>|<span data-ttu-id="62805-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="62805-114">TCP/UDP</span></span>|<span data-ttu-id="62805-115">46</span><span class="sxs-lookup"><span data-stu-id="62805-115">46</span></span>|<span data-ttu-id="62805-116">完全優先転送 (EF)</span><span class="sxs-lookup"><span data-stu-id="62805-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="62805-117">ビデオ</span><span class="sxs-lookup"><span data-stu-id="62805-117">Video</span></span>| <span data-ttu-id="62805-118">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="62805-118">50,020–50,039</span></span>|<span data-ttu-id="62805-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="62805-119">TCP/UDP</span></span>|<span data-ttu-id="62805-120">34</span><span class="sxs-lookup"><span data-stu-id="62805-120">34</span></span>|<span data-ttu-id="62805-121">相対的優先転送 (AF41)</span><span class="sxs-lookup"><span data-stu-id="62805-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="62805-122">アプリケーション/画面共有</span><span class="sxs-lookup"><span data-stu-id="62805-122">Application/Screen Sharing</span></span>| <span data-ttu-id="62805-123">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="62805-123">50,040–50,059</span></span>|<span data-ttu-id="62805-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="62805-124">TCP/UDP</span></span>|<span data-ttu-id="62805-125">18</span><span class="sxs-lookup"><span data-stu-id="62805-125">18</span></span>|<span data-ttu-id="62805-126">相対的優先転送 (AF21)</span><span class="sxs-lookup"><span data-stu-id="62805-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="62805-127">可能な限り、グループ ポリシー オブジェクト内でポリシー ベースの QoS 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="62805-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="62805-128">次の手順は  [、Skype for Business Server](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)上のクライアントのポート範囲とサービスの品質ポリシーの構成と非常に似ています。このポリシーには、必要ない詳細情報がいくつか含まれます。</span><span class="sxs-lookup"><span data-stu-id="62805-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="62805-129">ドメインに参加している Windows 10 コンピューターの QoS オーディオ ポリシーを作成するには、最初にグループ ポリシー管理がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="62805-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="62805-130">グループ ポリシー管理を開き ([スタート] をクリックし、[管理ツール] をポイントして、[グループ ポリシー管理] をクリック)、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="62805-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="62805-131">グループ ポリシー管理で、新しいポリシーを作成するコンテナーを見つける。</span><span class="sxs-lookup"><span data-stu-id="62805-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="62805-132">たとえば、すべてのクライアント コンピューターが **Client** という名前の OU にある場合、新しいポリシーを Client OU に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62805-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="62805-133">適切なコンテナーを右クリックし、[このドメインで GPO を作成] をクリックして、ここに **リンクします**。</span><span class="sxs-lookup"><span data-stu-id="62805-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="62805-134">[新 **しい GPO]** ダイアログ ボックスの [名前] ボックスに新しいグループ ポリシー オブジェクトの名前を入力し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62805-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="62805-135">新しく作成したポリシーを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="62805-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="62805-136">グループ ポリシー管理エディターで、[コンピューターの構成] を展開し **、[Windows の** 設定] を展開し、[ポリシー ベース **の QoS]** を右クリックして、[新しいポリシーの作成]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="62805-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="62805-137">[ポリシー ベース **の QoS]** ダイアログ ボックスの開きページで、[名前] ボックスに新しいポリシーの名前を **入力** します。</span><span class="sxs-lookup"><span data-stu-id="62805-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="62805-138">**[DSCP 値の指定] を選択** し、値を **46 に設定します**。</span><span class="sxs-lookup"><span data-stu-id="62805-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="62805-139">[ **送信制限レートの指定]** をオフのままにして、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="62805-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="62805-140">次のページで、[この実行可能ファイル名を持つアプリケーションのみ] を選択し、Teams.exeを入力し、[**次** へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="62805-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="62805-141">この設定は、Teams クライアントからの一致トラフィックのみを優先順位付けするようにポリシーに指示します。</span><span class="sxs-lookup"><span data-stu-id="62805-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="62805-142">3 番目のページで、[すべてのソース **IP** アドレス] と [すべての宛先 **IP** アドレス] の両方が選択され、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="62805-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="62805-143">これら 2 つの設定により、パケットを送信するコンピューター (IP アドレス) と、パケットを受信するコンピューター (IP アドレス) に関係なく、パケットが管理されます。</span><span class="sxs-lookup"><span data-stu-id="62805-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="62805-144">4 ページで、[この **QoS** ポリシーがドロップダウン リストに適用するプロトコルの選択] から **[TCP] と [UDP]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="62805-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="62805-145">TCP (伝送制御プロトコル) と UDP (ユーザー データグラム プロトコル) は、最も一般的に使用される 2 つのネットワーク プロトコルです。</span><span class="sxs-lookup"><span data-stu-id="62805-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="62805-146">見出しの [ **ソース ポート番号を指定してください**] で、[このソース ポート **または範囲から] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="62805-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="62805-147">付属のテキスト ボックスに、オーディオ転送用に予約されているポート範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="62805-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="62805-148">たとえば、ポート 50000 からポート 50019 をオーディオ トラフィック用に予約した場合は、ポート範囲を **50000:50019** という形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="62805-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="62805-149">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62805-149">Click **Finish**.</span></span>

1. <span data-ttu-id="62805-150">手順 5 ~ 10 を繰り返して、手順 6 と 10 で適切な値に置き換え、ビデオとアプリケーション/デスクトップ共有のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="62805-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="62805-151">作成した新しいポリシーは、クライアント コンピューターでグループ ポリシーが更新されるまで有効にされません。</span><span class="sxs-lookup"><span data-stu-id="62805-151">The new policies you've created won't take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="62805-152">グループ ポリシーは定期的に独自に更新しますが、次の手順に従って、直ちに更新を強制することができます。</span><span class="sxs-lookup"><span data-stu-id="62805-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="62805-153">グループ ポリシーを更新する各コンピューターで、管理者としてコマンド プロンプトを開きます (*管理者として実行)。*</span><span class="sxs-lookup"><span data-stu-id="62805-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="62805-154">コマンド プロンプトで、</span><span class="sxs-lookup"><span data-stu-id="62805-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="62805-155">グループ ポリシー オブジェクトで DSCP マーキングを確認する</span><span class="sxs-lookup"><span data-stu-id="62805-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="62805-156">グループ ポリシー オブジェクトの値が設定されているのを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="62805-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="62805-157">管理者としてコマンド プロンプトを開きます (*管理者として実行)。*</span><span class="sxs-lookup"><span data-stu-id="62805-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="62805-158">コマンド プロンプトで、</span><span class="sxs-lookup"><span data-stu-id="62805-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="62805-159">これにより、適用された GPO のレポートが生成され、そのレポートがgp.txtという名前 *のテキスト ファイルに送信されます*。</span><span class="sxs-lookup"><span data-stu-id="62805-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="62805-160">l という名前のより読みgp.htmHTML レポート *の場合は、次* のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="62805-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="62805-161">生成されたファイルで、"適用されたグループポリシー オブジェクト" という見出しを探し、前に作成したグループ ポリシー オブジェクトの名前が適用されたポリシーの一覧に含まれています。</span><span class="sxs-lookup"><span data-stu-id="62805-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="62805-162">レジストリ エディターを開き、</span><span class="sxs-lookup"><span data-stu-id="62805-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="62805-163">HKEY \_ LOCAL \_ MACHINE \\ Software \\ Policies \\ Microsoft \\ Windows \\ QoS</span><span class="sxs-lookup"><span data-stu-id="62805-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="62805-164">表 2 に記載されているレジストリ エントリの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="62805-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="62805-165">*表 2.QoS の Windows レジストリ エントリの値*</span><span class="sxs-lookup"><span data-stu-id="62805-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="62805-166">名前</span><span class="sxs-lookup"><span data-stu-id="62805-166">Name</span></span>          |  <span data-ttu-id="62805-167">種類</span><span class="sxs-lookup"><span data-stu-id="62805-167">Type</span></span>  |    <span data-ttu-id="62805-168">データ</span><span class="sxs-lookup"><span data-stu-id="62805-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="62805-169">Application Name</span><span class="sxs-lookup"><span data-stu-id="62805-169">Application Name</span></span>    | <span data-ttu-id="62805-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="62805-170">REG_SZ</span></span> |  <span data-ttu-id="62805-171">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="62805-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="62805-172">DSCP Value</span><span class="sxs-lookup"><span data-stu-id="62805-172">DSCP Value</span></span>       | <span data-ttu-id="62805-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="62805-173">REG_SZ</span></span> |     <span data-ttu-id="62805-174">46</span><span class="sxs-lookup"><span data-stu-id="62805-174">46</span></span>      |
   |        <span data-ttu-id="62805-175">Local IP</span><span class="sxs-lookup"><span data-stu-id="62805-175">Local IP</span></span>        | <span data-ttu-id="62805-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="62805-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="62805-177">Local IP Prefix Length</span><span class="sxs-lookup"><span data-stu-id="62805-177">Local IP Prefix Length</span></span> | <span data-ttu-id="62805-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="62805-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="62805-179">Local Port</span><span class="sxs-lookup"><span data-stu-id="62805-179">Local Port</span></span>       | <span data-ttu-id="62805-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="62805-180">REG_SZ</span></span> | <span data-ttu-id="62805-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="62805-181">50000-50019</span></span> |
   |        <span data-ttu-id="62805-182">プロトコル</span><span class="sxs-lookup"><span data-stu-id="62805-182">Protocol</span></span>        | <span data-ttu-id="62805-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="62805-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="62805-184">Remote IP</span><span class="sxs-lookup"><span data-stu-id="62805-184">Remote IP</span></span>        | <span data-ttu-id="62805-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="62805-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="62805-186">リモート IP プレフィックス</span><span class="sxs-lookup"><span data-stu-id="62805-186">Remote IP Prefix</span></span>    | <span data-ttu-id="62805-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="62805-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="62805-188">Remote Port</span><span class="sxs-lookup"><span data-stu-id="62805-188">Remote Port</span></span>       | <span data-ttu-id="62805-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="62805-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="62805-190">Throttle Rate</span><span class="sxs-lookup"><span data-stu-id="62805-190">Throttle Rate</span></span>      | <span data-ttu-id="62805-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="62805-191">REG_SZ</span></span> |     <span data-ttu-id="62805-192">-1</span><span class="sxs-lookup"><span data-stu-id="62805-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="62805-193">使用しているクライアントのアプリケーション名エントリの値が正しいか確認し、DSCP 値エントリとローカル ポート エントリの両方にグループ ポリシー オブジェクトの設定が反映されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="62805-193">Verify that the value for the Application Name entry is correct for the client you're using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>


## <a name="related-topics"></a><span data-ttu-id="62805-194">関連項目</span><span class="sxs-lookup"><span data-stu-id="62805-194">Related topics</span></span>

[<span data-ttu-id="62805-195">Teams でサービスの品質 (QoS) を実装する</span><span class="sxs-lookup"><span data-stu-id="62805-195">Implement Quality of Service (QoS) in Teams</span></span>](QoS-in-Teams.md)
---
title: サービス品質 (QoS) をクライアントにMicrosoft Teamsする
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: サービス品質 (QoS) を使用して、デスクトップ クライアントのネットワーク トラフィックを最適化Microsoft Teams学習します。
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
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a><span data-ttu-id="1d47b-103">サービス品質 (QoS) をクライアントにMicrosoft Teamsする</span><span class="sxs-lookup"><span data-stu-id="1d47b-103">Implement Quality of Service (QoS) in Microsoft Teams clients</span></span>

<span data-ttu-id="1d47b-104">グループ ポリシー内でポリシー ベースのサービス品質 (QoS) を使用して、クライアント内の定義済み DSCP 値のソース ポート範囲Teamsできます。</span><span class="sxs-lookup"><span data-stu-id="1d47b-104">You can use policy-based Quality of Service (QoS) within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="1d47b-105">次の表に示すポート範囲は、ワークロードごとにポリシーを作成する開始点です。</span><span class="sxs-lookup"><span data-stu-id="1d47b-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="1d47b-106">*表 1.推奨される初期ポート範囲*</span><span class="sxs-lookup"><span data-stu-id="1d47b-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="1d47b-107">メディア トラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="1d47b-107">Media traffic type</span></span>| <span data-ttu-id="1d47b-108">クライアントの送信元ポート範囲</span><span class="sxs-lookup"><span data-stu-id="1d47b-108">Client source port range</span></span> |<span data-ttu-id="1d47b-109">プロトコル</span><span class="sxs-lookup"><span data-stu-id="1d47b-109">Protocol</span></span>|<span data-ttu-id="1d47b-110">DSCP 値</span><span class="sxs-lookup"><span data-stu-id="1d47b-110">DSCP value</span></span>|<span data-ttu-id="1d47b-111">DSCP クラス</span><span class="sxs-lookup"><span data-stu-id="1d47b-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="1d47b-112">オーディオ</span><span class="sxs-lookup"><span data-stu-id="1d47b-112">Audio</span></span>| <span data-ttu-id="1d47b-113">50,000–50,019</span><span class="sxs-lookup"><span data-stu-id="1d47b-113">50,000–50,019</span></span>|<span data-ttu-id="1d47b-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="1d47b-114">TCP/UDP</span></span>|<span data-ttu-id="1d47b-115">46</span><span class="sxs-lookup"><span data-stu-id="1d47b-115">46</span></span>|<span data-ttu-id="1d47b-116">完全優先転送 (EF)</span><span class="sxs-lookup"><span data-stu-id="1d47b-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="1d47b-117">ビデオ</span><span class="sxs-lookup"><span data-stu-id="1d47b-117">Video</span></span>| <span data-ttu-id="1d47b-118">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="1d47b-118">50,020–50,039</span></span>|<span data-ttu-id="1d47b-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="1d47b-119">TCP/UDP</span></span>|<span data-ttu-id="1d47b-120">34</span><span class="sxs-lookup"><span data-stu-id="1d47b-120">34</span></span>|<span data-ttu-id="1d47b-121">相対的優先転送 (AF41)</span><span class="sxs-lookup"><span data-stu-id="1d47b-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="1d47b-122">アプリケーション/画面共有</span><span class="sxs-lookup"><span data-stu-id="1d47b-122">Application/Screen Sharing</span></span>| <span data-ttu-id="1d47b-123">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="1d47b-123">50,040–50,059</span></span>|<span data-ttu-id="1d47b-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="1d47b-124">TCP/UDP</span></span>|<span data-ttu-id="1d47b-125">18</span><span class="sxs-lookup"><span data-stu-id="1d47b-125">18</span></span>|<span data-ttu-id="1d47b-126">相対的優先転送 (AF21)</span><span class="sxs-lookup"><span data-stu-id="1d47b-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="1d47b-127">可能な限り、グループ ポリシー オブジェクト内でポリシー ベースの QoS 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="1d47b-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="1d47b-128">次の手順は[、Skype for Business Server](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)上のクライアントのポート範囲とサービス品質ポリシーの構成に非常に似ています。このポリシーには、必要ない可能性がある追加の詳細がいくつか含まれます。</span><span class="sxs-lookup"><span data-stu-id="1d47b-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="1d47b-129">ドメインに参加しているコンピューターの QoS オーディオ ポリシーを作成Windows 10、最初にグループ ポリシー管理がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1d47b-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="1d47b-130">[グループ ポリシーの管理] を開き ([スタート] をクリックし、[管理ツール] をポイントして、[グループ ポリシー管理] をクリックします)、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1d47b-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="1d47b-131">[グループ ポリシーの管理] で、新しいポリシーを作成するコンテナーを探します。</span><span class="sxs-lookup"><span data-stu-id="1d47b-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="1d47b-132">たとえば、すべてのクライアント コンピューターが **Clients** という名前の OU にある場合、新しいポリシーをクライアント OU に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d47b-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="1d47b-133">適切なコンテナーを右クリックし、[このドメインに GPO を作成する] をクリックし、 **ここにリンクします**。</span><span class="sxs-lookup"><span data-stu-id="1d47b-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="1d47b-134">[新 **しい GPO] ダイアログ** ボックスの [名前] ボックスに新しいグループ ポリシー オブジェクトの名前を入力し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d47b-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="1d47b-135">新しく作成したポリシーを右クリックし、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1d47b-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="1d47b-136">グループ ポリシー管理エディターで、[**コンピューター** の構成] を展開し、[Windows 設定]**を** 展開し、[ポリシー ベース **の QoS]** を右クリックし、[新しいポリシーの作成]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1d47b-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="1d47b-137">[ **ポリシー ベースの QoS]** ダイアログ ボックスの開きページで、[名前] ボックスに新しいポリシーの名前を **入力** します。</span><span class="sxs-lookup"><span data-stu-id="1d47b-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="1d47b-138">[SPECIFY **DSCP Value]を選択し** 、値を **46 に設定します**。</span><span class="sxs-lookup"><span data-stu-id="1d47b-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="1d47b-139">[ **送信スロットル レートの指定] は** オフのままにし、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1d47b-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="1d47b-140">次のページで、[**この** 実行可能ファイル名を持つアプリケーションのみ] を選択し、[次へ]Teams.exeを入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1d47b-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="1d47b-141">この設定は、クライアントからの一致するトラフィックのみを優先順位付けするようにポリシー Teams指示します。</span><span class="sxs-lookup"><span data-stu-id="1d47b-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="1d47b-142">3 番目のページで、[任意の送信元 **IP** アドレス] と [任意の宛先 **IP** アドレス] の両方が選択され、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="1d47b-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="1d47b-143">これら 2 つの設定により、パケットを送信したコンピューター (IP アドレス) とパケットを受信するコンピューター (IP アドレス) に関係なく、パケットが管理されます。</span><span class="sxs-lookup"><span data-stu-id="1d47b-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="1d47b-144">4 ページの [Select **the protocol this QoS policy applies** to](この QoS ポリシーが適用するプロトコルを選択する)ドロップダウン リストから [TCP] と **[UDP]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d47b-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="1d47b-145">TCP (伝送制御プロトコル) と UDP (ユーザー データグラム プロトコル) は、最も一般的に使用される 2 つのネットワーク プロトコルです。</span><span class="sxs-lookup"><span data-stu-id="1d47b-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="1d47b-146">[ソース ポート番号 **の指定] という見出しの下で**、[このソース ポートまたは範囲 **から] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1d47b-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="1d47b-147">付属のテキスト ボックスに、オーディオ転送用に予約されているポート範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="1d47b-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="1d47b-148">たとえば、オーディオ トラフィック用にポート 50000 からポート 50019 を予約した場合は **、50000:50019** という形式でポート範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="1d47b-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="1d47b-149">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d47b-149">Click **Finish**.</span></span>

1. <span data-ttu-id="1d47b-150">手順 6 と 10 で適切な値を置き換え、ビデオとアプリケーション/デスクトップ共有のポリシーを作成するには、手順 5 ~ 10 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1d47b-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="1d47b-151">作成した新しいポリシーは、クライアント コンピューターでグループ ポリシーが更新されるまで有効にされません。</span><span class="sxs-lookup"><span data-stu-id="1d47b-151">The new policies you've created won't take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="1d47b-152">グループ ポリシーは定期的に独自に更新しますが、次の手順に従って、すぐに更新を強制できます。</span><span class="sxs-lookup"><span data-stu-id="1d47b-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="1d47b-153">グループ ポリシーを更新する各コンピューターで、管理者としてコマンド プロンプト (管理者として実行)*を開きます*。</span><span class="sxs-lookup"><span data-stu-id="1d47b-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="1d47b-154">コマンド プロンプトで、「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="1d47b-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="1d47b-155">グループ ポリシー オブジェクトで DSCP マーキングを確認する</span><span class="sxs-lookup"><span data-stu-id="1d47b-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="1d47b-156">グループ ポリシー オブジェクトの値が設定されたと確認するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1d47b-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="1d47b-157">管理者としてコマンド プロンプトを開きます (*管理者として実行)。*</span><span class="sxs-lookup"><span data-stu-id="1d47b-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="1d47b-158">コマンド プロンプトで、「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="1d47b-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="1d47b-159">これにより、適用された GPO のレポートが生成され、 という名前のテキスト *ファイルにgp.txt。*</span><span class="sxs-lookup"><span data-stu-id="1d47b-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="1d47b-160">l という名前の読み取り可能な HTML *gp.htm、* 次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="1d47b-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="1d47b-161">生成されたファイルで、[適用されたグループポリシー オブジェクト] という見出しを探し、先に作成したグループ ポリシー オブジェクトの名前が適用されたポリシーの一覧に含まれています。</span><span class="sxs-lookup"><span data-stu-id="1d47b-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="1d47b-162">レジストリ エディターを開き、</span><span class="sxs-lookup"><span data-stu-id="1d47b-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="1d47b-163">HKEY \_ LOCAL MACHINE Software \_ \\ \\ Policies Microsoft Windows \\ \\ \\ QoS</span><span class="sxs-lookup"><span data-stu-id="1d47b-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="1d47b-164">表 2 に記載されているレジストリ エントリの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="1d47b-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="1d47b-165">*表 2.QoS Windowsレジストリ エントリの値*</span><span class="sxs-lookup"><span data-stu-id="1d47b-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="1d47b-166">名前</span><span class="sxs-lookup"><span data-stu-id="1d47b-166">Name</span></span>          |  <span data-ttu-id="1d47b-167">種類</span><span class="sxs-lookup"><span data-stu-id="1d47b-167">Type</span></span>  |    <span data-ttu-id="1d47b-168">データ</span><span class="sxs-lookup"><span data-stu-id="1d47b-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="1d47b-169">Application Name</span><span class="sxs-lookup"><span data-stu-id="1d47b-169">Application Name</span></span>    | <span data-ttu-id="1d47b-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1d47b-170">REG_SZ</span></span> |  <span data-ttu-id="1d47b-171">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="1d47b-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="1d47b-172">DSCP Value</span><span class="sxs-lookup"><span data-stu-id="1d47b-172">DSCP Value</span></span>       | <span data-ttu-id="1d47b-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1d47b-173">REG_SZ</span></span> |     <span data-ttu-id="1d47b-174">46</span><span class="sxs-lookup"><span data-stu-id="1d47b-174">46</span></span>      |
   |        <span data-ttu-id="1d47b-175">Local IP</span><span class="sxs-lookup"><span data-stu-id="1d47b-175">Local IP</span></span>        | <span data-ttu-id="1d47b-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1d47b-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="1d47b-177">Local IP Prefix Length</span><span class="sxs-lookup"><span data-stu-id="1d47b-177">Local IP Prefix Length</span></span> | <span data-ttu-id="1d47b-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1d47b-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="1d47b-179">Local Port</span><span class="sxs-lookup"><span data-stu-id="1d47b-179">Local Port</span></span>       | <span data-ttu-id="1d47b-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1d47b-180">REG_SZ</span></span> | <span data-ttu-id="1d47b-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="1d47b-181">50000-50019</span></span> |
   |        <span data-ttu-id="1d47b-182">プロトコル</span><span class="sxs-lookup"><span data-stu-id="1d47b-182">Protocol</span></span>        | <span data-ttu-id="1d47b-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1d47b-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="1d47b-184">Remote IP</span><span class="sxs-lookup"><span data-stu-id="1d47b-184">Remote IP</span></span>        | <span data-ttu-id="1d47b-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1d47b-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="1d47b-186">リモート IP プレフィックス</span><span class="sxs-lookup"><span data-stu-id="1d47b-186">Remote IP Prefix</span></span>    | <span data-ttu-id="1d47b-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1d47b-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="1d47b-188">Remote Port</span><span class="sxs-lookup"><span data-stu-id="1d47b-188">Remote Port</span></span>       | <span data-ttu-id="1d47b-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1d47b-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="1d47b-190">Throttle Rate</span><span class="sxs-lookup"><span data-stu-id="1d47b-190">Throttle Rate</span></span>      | <span data-ttu-id="1d47b-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1d47b-191">REG_SZ</span></span> |     <span data-ttu-id="1d47b-192">-1</span><span class="sxs-lookup"><span data-stu-id="1d47b-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="1d47b-193">使用しているクライアントの [アプリケーション名] エントリの値が正しいか確認し、[DSCP 値] エントリと [ローカル ポート] エントリの両方にグループ ポリシー オブジェクトの設定が反映されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1d47b-193">Verify that the value for the Application Name entry is correct for the client you're using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>


## <a name="related-topics"></a><span data-ttu-id="1d47b-194">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1d47b-194">Related topics</span></span>

[<span data-ttu-id="1d47b-195">サービス品質 (QoS) を実装するTeams</span><span class="sxs-lookup"><span data-stu-id="1d47b-195">Implement Quality of Service (QoS) in Teams</span></span>](QoS-in-Teams.md)
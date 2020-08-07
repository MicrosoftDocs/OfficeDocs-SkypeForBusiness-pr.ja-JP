---
title: Microsoft Teams クライアントでサービスの品質 (QoS) を実装する
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Microsoft Teams デスクトップクライアントのネットワークトラフィックを最適化するために、QoS (Quality of Service) を使用する方法について説明します。
ms.custom: seo-marvel-mar2020
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77f1754277cfeacd31de28dcee089a8f97991c87
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583686"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a><span data-ttu-id="cd965-103">Microsoft Teams クライアントでサービスの品質 (QoS) を実装する</span><span class="sxs-lookup"><span data-stu-id="cd965-103">Implement Quality of Service (QoS) in Microsoft Teams clients</span></span>

<span data-ttu-id="cd965-104">グループポリシーでポリシーベースの QoS (Quality of Service) を使用して、Teams クライアントで事前に定義された DSCP 値のソースポート範囲を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="cd965-104">You can use policy-based Quality of Service (QoS) within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="cd965-105">次の表で示されているポート範囲は、各ワークロードのポリシーを作成する開始点です。</span><span class="sxs-lookup"><span data-stu-id="cd965-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="cd965-106">*表1。推奨される初期ポート範囲*</span><span class="sxs-lookup"><span data-stu-id="cd965-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="cd965-107">メディア トラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="cd965-107">Media traffic type</span></span>| <span data-ttu-id="cd965-108">クライアントのソース ポートの範囲</span><span class="sxs-lookup"><span data-stu-id="cd965-108">Client source port range</span></span> |<span data-ttu-id="cd965-109">プロトコル</span><span class="sxs-lookup"><span data-stu-id="cd965-109">Protocol</span></span>|<span data-ttu-id="cd965-110">DSCP 値</span><span class="sxs-lookup"><span data-stu-id="cd965-110">DSCP value</span></span>|<span data-ttu-id="cd965-111">DSCP クラス</span><span class="sxs-lookup"><span data-stu-id="cd965-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="cd965-112">オーディオ</span><span class="sxs-lookup"><span data-stu-id="cd965-112">Audio</span></span>| <span data-ttu-id="cd965-113">50,000–50,019</span><span class="sxs-lookup"><span data-stu-id="cd965-113">50,000–50,019</span></span>|<span data-ttu-id="cd965-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="cd965-114">TCP/UDP</span></span>|<span data-ttu-id="cd965-115">46</span><span class="sxs-lookup"><span data-stu-id="cd965-115">46</span></span>|<span data-ttu-id="cd965-116">完全優先転送 (EF)</span><span class="sxs-lookup"><span data-stu-id="cd965-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="cd965-117">ビデオ</span><span class="sxs-lookup"><span data-stu-id="cd965-117">Video</span></span>| <span data-ttu-id="cd965-118">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="cd965-118">50,020–50,039</span></span>|<span data-ttu-id="cd965-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="cd965-119">TCP/UDP</span></span>|<span data-ttu-id="cd965-120">34</span><span class="sxs-lookup"><span data-stu-id="cd965-120">34</span></span>|<span data-ttu-id="cd965-121">相対的優先転送 (AF41)</span><span class="sxs-lookup"><span data-stu-id="cd965-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="cd965-122">アプリケーション/画面共有</span><span class="sxs-lookup"><span data-stu-id="cd965-122">Application/Screen Sharing</span></span>| <span data-ttu-id="cd965-123">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="cd965-123">50,040–50,059</span></span>|<span data-ttu-id="cd965-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="cd965-124">TCP/UDP</span></span>|<span data-ttu-id="cd965-125">才</span><span class="sxs-lookup"><span data-stu-id="cd965-125">18</span></span>|<span data-ttu-id="cd965-126">相対的優先転送 (AF21)</span><span class="sxs-lookup"><span data-stu-id="cd965-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="cd965-127">可能な限り、グループポリシーオブジェクト内でポリシーベースの QoS 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="cd965-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="cd965-128">次の手順は、 [Skype For Business Server のクライアントに対するサービス品質ポリシーの構成と](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)非常に似ていますが、必要に応じて追加の詳細情報も記載されています。</span><span class="sxs-lookup"><span data-stu-id="cd965-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="cd965-129">ドメインに参加している Windows 10 コンピューターの QoS オーディオポリシーを作成するには、まずグループポリシー管理がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="cd965-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="cd965-130">[グループポリシーの管理] を開き ([スタート] をクリックし、[管理ツール] をポイントして、[グループポリシーの管理] をクリックし)、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cd965-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="cd965-131">[グループポリシーの管理] で、新しいポリシーを作成するコンテナーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="cd965-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="cd965-132">たとえば、クライアントコンピューターが**すべてクライアントという名前**の ou に配置されている場合、新しいポリシーは [クライアント] OU に作成されます。</span><span class="sxs-lookup"><span data-stu-id="cd965-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="cd965-133">適切なコンテナーを右クリックし、[**このドメインに GPO を作成**] をクリックして、ここにリンクを設定します。</span><span class="sxs-lookup"><span data-stu-id="cd965-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="cd965-134">[**新しい GPO** ] ダイアログボックスの [**名前**] ボックスに新しいグループポリシーオブジェクトの名前を入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd965-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="cd965-135">新しく作成したポリシーを右クリックし、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd965-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="cd965-136">グループポリシー管理エディターで、[**コンピューターの構成**]、[ **Windows の設定**] の順に展開し、[**ポリシーベースの QoS**] を右クリックして、[**新しいポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd965-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="cd965-137">[**ポリシーベースの QoS** ] ダイアログボックスの [開く] ページで、[**名前**] ボックスに新しいポリシーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="cd965-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="cd965-138">[ **DSCP 値の指定**] を選択し、値を**46**に設定します。</span><span class="sxs-lookup"><span data-stu-id="cd965-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="cd965-139">[**送信スロットルの比率を指定する**] をオフにして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd965-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="cd965-140">次のページで、[**この実行可能ファイル名のアプリケーションのみ**] を選択して**Teams.exe**名前を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd965-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="cd965-141">この設定では、チームクライアントからの一致トラフィックのみの優先順位付けをポリシーに指示します。</span><span class="sxs-lookup"><span data-stu-id="cd965-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="cd965-142">3番目のページで、[**ソース ip アドレス**] と [**宛先 ip アドレス**] の両方が選択されていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd965-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="cd965-143">この2つの設定では、どのコンピューター (IP アドレス) がパケットを送信したかに関係なく、パケットを管理することができます。どのコンピューター (ip アドレス) がパケットを受信するかは関係ありません。</span><span class="sxs-lookup"><span data-stu-id="cd965-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="cd965-144">4ページ目で、[**この QoS ポリシーが適用されるプロトコルを選択**してください] ドロップダウンリストから [ **TCP および UDP** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd965-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="cd965-145">TCP (伝送制御プロトコル) と UDP (ユーザーデータグラムプロトコル) は、一般的に使用される2つのネットワークプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="cd965-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="cd965-146">見出しの下で、**ソースポート番号を指定**して、[**このソースポートまたは範囲から**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd965-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="cd965-147">[付随するテキスト] ボックスに、オーディオ送信用に予約されているポート範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="cd965-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="cd965-148">たとえば、ポート5万からオーディオトラフィック用にポート50019を予約した場合は、「 **50000:50019**」の形式でポート範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="cd965-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="cd965-149">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd965-149">Click **Finish**.</span></span>

1. <span data-ttu-id="cd965-150">手順5-10 を繰り返して、手順6と10で適切な値に置き換えて、ビデオとアプリケーション/デスクトップ共有のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="cd965-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="cd965-151">作成した新しいポリシーは、クライアントコンピューターのグループポリシーが更新されるまで有効になりません。</span><span class="sxs-lookup"><span data-stu-id="cd965-151">The new policies you've created won't take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="cd965-152">グループポリシーは定期的に更新されますが、次の手順に従って、すぐに更新することができます。</span><span class="sxs-lookup"><span data-stu-id="cd965-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="cd965-153">グループポリシーを更新する各コンピューターで、管理者としてコマンドプロンプトを開きます (*管理者として実行*します)。</span><span class="sxs-lookup"><span data-stu-id="cd965-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="cd965-154">コマンドプロンプトで、</span><span class="sxs-lookup"><span data-stu-id="cd965-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="cd965-155">グループポリシーオブジェクトの DSCP マーキングを確認する</span><span class="sxs-lookup"><span data-stu-id="cd965-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="cd965-156">グループポリシーオブジェクトの値が設定されていることを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cd965-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="cd965-157">管理者としてコマンドプロンプトを開きます (*管理者として実行*します)。</span><span class="sxs-lookup"><span data-stu-id="cd965-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="cd965-158">コマンドプロンプトで、</span><span class="sxs-lookup"><span data-stu-id="cd965-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="cd965-159">これにより、適用された Gpo のレポートが生成され、 *gp.txt*という名前のテキストファイルに送信されます。</span><span class="sxs-lookup"><span data-stu-id="cd965-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="cd965-160">*gp.html*という名前のより読みやすい HTML レポートを作成するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="cd965-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="cd965-161">生成されたファイルで、見出しが適用されている**グループポリシーオブジェクト**を探し、前に作成したグループポリシーオブジェクトの名前が適用されているポリシーの一覧に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cd965-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="cd965-162">レジストリエディターを開き、</span><span class="sxs-lookup"><span data-stu-id="cd965-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="cd965-163">HKEY \_ ローカル \_ コンピューター \\ ソフトウェア \\ ポリシー \\ Microsoft \\ Windows \\ QoS</span><span class="sxs-lookup"><span data-stu-id="cd965-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="cd965-164">表2に示されているレジストリエントリの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="cd965-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="cd965-165">*表2QoS の Windows レジストリエントリの値*</span><span class="sxs-lookup"><span data-stu-id="cd965-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="cd965-166">名前</span><span class="sxs-lookup"><span data-stu-id="cd965-166">Name</span></span>          |  <span data-ttu-id="cd965-167">種類</span><span class="sxs-lookup"><span data-stu-id="cd965-167">Type</span></span>  |    <span data-ttu-id="cd965-168">データ</span><span class="sxs-lookup"><span data-stu-id="cd965-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="cd965-169">Application Name</span><span class="sxs-lookup"><span data-stu-id="cd965-169">Application Name</span></span>    | <span data-ttu-id="cd965-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cd965-170">REG_SZ</span></span> |  <span data-ttu-id="cd965-171">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="cd965-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="cd965-172">DSCP Value</span><span class="sxs-lookup"><span data-stu-id="cd965-172">DSCP Value</span></span>       | <span data-ttu-id="cd965-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cd965-173">REG_SZ</span></span> |     <span data-ttu-id="cd965-174">46</span><span class="sxs-lookup"><span data-stu-id="cd965-174">46</span></span>      |
   |        <span data-ttu-id="cd965-175">Local IP</span><span class="sxs-lookup"><span data-stu-id="cd965-175">Local IP</span></span>        | <span data-ttu-id="cd965-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cd965-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="cd965-177">Local IP Prefix Length</span><span class="sxs-lookup"><span data-stu-id="cd965-177">Local IP Prefix Length</span></span> | <span data-ttu-id="cd965-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cd965-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="cd965-179">Local Port</span><span class="sxs-lookup"><span data-stu-id="cd965-179">Local Port</span></span>       | <span data-ttu-id="cd965-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cd965-180">REG_SZ</span></span> | <span data-ttu-id="cd965-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="cd965-181">50000-50019</span></span> |
   |        <span data-ttu-id="cd965-182">プロトコル</span><span class="sxs-lookup"><span data-stu-id="cd965-182">Protocol</span></span>        | <span data-ttu-id="cd965-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cd965-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="cd965-184">Remote IP</span><span class="sxs-lookup"><span data-stu-id="cd965-184">Remote IP</span></span>        | <span data-ttu-id="cd965-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cd965-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="cd965-186">リモート IP プレフィックス</span><span class="sxs-lookup"><span data-stu-id="cd965-186">Remote IP Prefix</span></span>    | <span data-ttu-id="cd965-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cd965-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="cd965-188">Remote Port</span><span class="sxs-lookup"><span data-stu-id="cd965-188">Remote Port</span></span>       | <span data-ttu-id="cd965-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cd965-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="cd965-190">Throttle Rate</span><span class="sxs-lookup"><span data-stu-id="cd965-190">Throttle Rate</span></span>      | <span data-ttu-id="cd965-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cd965-191">REG_SZ</span></span> |     <span data-ttu-id="cd965-192">-1</span><span class="sxs-lookup"><span data-stu-id="cd965-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="cd965-193">使用しているクライアントに対してアプリケーション名エントリの値が正しいことを確認し、DSCP 値とローカルポートエントリの両方にグループポリシーオブジェクトの設定が反映されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cd965-193">Verify that the value for the Application Name entry is correct for the client you're using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>


## <a name="related-topics"></a><span data-ttu-id="cd965-194">関連トピック</span><span class="sxs-lookup"><span data-stu-id="cd965-194">Related topics</span></span>

[<span data-ttu-id="cd965-195">Teams でサービスの品質 (QoS) を実装する</span><span class="sxs-lookup"><span data-stu-id="cd965-195">Implement Quality of Service (QoS) in Teams</span></span>](QoS-in-Teams.md)
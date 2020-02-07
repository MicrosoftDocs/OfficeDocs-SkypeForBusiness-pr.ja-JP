---
title: Microsoft Teams クライアントでサービスの品質 (QoS) を実施する
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Microsoft Teams クライアントにサービスの品質 (QoS) を実装します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43a4c7ea45fe0feabbe8851cde944a70994829da
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836487"
---
# <a name="set-qos-on-windows-clients"></a><span data-ttu-id="dc75a-103">Windows クライアントで QoS を設定する</span><span class="sxs-lookup"><span data-stu-id="dc75a-103">Set QoS on Windows clients</span></span>

<span data-ttu-id="dc75a-104">グループポリシー内のポリシーベースの QoS を使用して、Teams クライアントで定義済みの DSCP 値のソースポート範囲を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="dc75a-104">You can use policy-based QoS within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="dc75a-105">次の表で示されているポート範囲は、各ワークロードのポリシーを作成する開始点です。</span><span class="sxs-lookup"><span data-stu-id="dc75a-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="dc75a-106">*表1。推奨される初期ポート範囲*</span><span class="sxs-lookup"><span data-stu-id="dc75a-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="dc75a-107">メディア トラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="dc75a-107">Media traffic type</span></span>| <span data-ttu-id="dc75a-108">クライアントのソース ポートの範囲</span><span class="sxs-lookup"><span data-stu-id="dc75a-108">Client source port range</span></span> |<span data-ttu-id="dc75a-109">プロトコル</span><span class="sxs-lookup"><span data-stu-id="dc75a-109">Protocol</span></span>|<span data-ttu-id="dc75a-110">DSCP 値</span><span class="sxs-lookup"><span data-stu-id="dc75a-110">DSCP value</span></span>|<span data-ttu-id="dc75a-111">DSCP クラス</span><span class="sxs-lookup"><span data-stu-id="dc75a-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="dc75a-112">オーディオ</span><span class="sxs-lookup"><span data-stu-id="dc75a-112">Audio</span></span>| <span data-ttu-id="dc75a-113">50,000–50,019</span><span class="sxs-lookup"><span data-stu-id="dc75a-113">50,000–50,019</span></span>|<span data-ttu-id="dc75a-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="dc75a-114">TCP/UDP</span></span>|<span data-ttu-id="dc75a-115">46</span><span class="sxs-lookup"><span data-stu-id="dc75a-115">46</span></span>|<span data-ttu-id="dc75a-116">完全優先転送 (EF)</span><span class="sxs-lookup"><span data-stu-id="dc75a-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="dc75a-117">ビデオ</span><span class="sxs-lookup"><span data-stu-id="dc75a-117">Video</span></span>| <span data-ttu-id="dc75a-118">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="dc75a-118">50,020–50,039</span></span>|<span data-ttu-id="dc75a-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="dc75a-119">TCP/UDP</span></span>|<span data-ttu-id="dc75a-120">34</span><span class="sxs-lookup"><span data-stu-id="dc75a-120">34</span></span>|<span data-ttu-id="dc75a-121">相対的優先転送 (AF41)</span><span class="sxs-lookup"><span data-stu-id="dc75a-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="dc75a-122">アプリケーション/画面共有</span><span class="sxs-lookup"><span data-stu-id="dc75a-122">Application/Screen Sharing</span></span>| <span data-ttu-id="dc75a-123">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="dc75a-123">50,040–50,059</span></span>|<span data-ttu-id="dc75a-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="dc75a-124">TCP/UDP</span></span>|<span data-ttu-id="dc75a-125">才</span><span class="sxs-lookup"><span data-stu-id="dc75a-125">18</span></span>|<span data-ttu-id="dc75a-126">相対的優先転送 (AF21)</span><span class="sxs-lookup"><span data-stu-id="dc75a-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="dc75a-127">可能な限り、グループポリシーオブジェクト内でポリシーベースの QoS 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="dc75a-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="dc75a-128">次の手順は、 [Skype For Business Server のクライアントに対するサービス品質ポリシーの構成と](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)非常に似ていますが、必要に応じて追加の詳細情報も記載されています。</span><span class="sxs-lookup"><span data-stu-id="dc75a-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="dc75a-129">ドメインに参加している Windows 10 コンピューターの QoS オーディオポリシーを作成するには、まずグループポリシー管理がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="dc75a-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="dc75a-130">[グループポリシーの管理] を開き ([スタート] をクリックし、[管理ツール] をポイントして、[グループポリシーの管理] をクリックし)、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dc75a-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="dc75a-131">[グループポリシーの管理] で、新しいポリシーを作成するコンテナーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="dc75a-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="dc75a-132">たとえば、クライアントコンピューターが**すべてクライアントという名前**の ou に配置されている場合、新しいポリシーは [クライアント] OU に作成されます。</span><span class="sxs-lookup"><span data-stu-id="dc75a-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="dc75a-133">適切なコンテナーを右クリックし、[**このドメインに GPO を作成**] をクリックして、ここにリンクを設定します。</span><span class="sxs-lookup"><span data-stu-id="dc75a-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="dc75a-134">[**新しい GPO** ] ダイアログボックスの [**名前**] ボックスに新しいグループポリシーオブジェクトの名前を入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc75a-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="dc75a-135">新しく作成したポリシーを右クリックし、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc75a-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="dc75a-136">グループポリシー管理エディターで、[**コンピューターの構成**]、[ **Windows の設定**] の順に展開し、[**ポリシーベースの QoS**] を右クリックして、[**新しいポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc75a-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="dc75a-137">[**ポリシーベースの QoS** ] ダイアログボックスの [開く] ページで、[**名前**] ボックスに新しいポリシーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="dc75a-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="dc75a-138">[ **DSCP 値の指定**] を選択し、値を**46**に設定します。</span><span class="sxs-lookup"><span data-stu-id="dc75a-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="dc75a-139">[**送信スロットルの比率を指定する**] をオフにして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc75a-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="dc75a-140">次のページで、[**この実行可能ファイル名のアプリケーションのみ**] を選択し、 **Teams**という名前を入力して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc75a-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="dc75a-141">この設定では、チームクライアントからの一致トラフィックのみの優先順位付けをポリシーに指示します。</span><span class="sxs-lookup"><span data-stu-id="dc75a-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="dc75a-142">3番目のページで、[**ソース ip アドレス**] と [**宛先 ip アドレス**] の両方が選択されていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc75a-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="dc75a-143">この2つの設定では、どのコンピューター (IP アドレス) がパケットを送信したかに関係なく、パケットを管理することができます。どのコンピューター (ip アドレス) がパケットを受信するかは関係ありません。</span><span class="sxs-lookup"><span data-stu-id="dc75a-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="dc75a-144">4ページ目で、[**この QoS ポリシーが適用されるプロトコルを選択**してください] ドロップダウンリストから [ **TCP および UDP** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="dc75a-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="dc75a-145">TCP (伝送制御プロトコル) と UDP (ユーザーデータグラムプロトコル) は、一般的に使用される2つのネットワークプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="dc75a-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="dc75a-146">見出しの下で、**ソースポート番号を指定**して、[**このソースポートまたは範囲から**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc75a-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="dc75a-147">[付随するテキスト] ボックスに、オーディオ送信用に予約されているポート範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="dc75a-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="dc75a-148">たとえば、ポート5万からオーディオトラフィック用にポート50019を予約した場合は、「 **50000:50019**」の形式でポート範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="dc75a-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="dc75a-149">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc75a-149">Click **Finish**.</span></span>

1. <span data-ttu-id="dc75a-150">手順5-10 を繰り返して、手順6と10で適切な値に置き換えて、ビデオとアプリケーション/デスクトップ共有のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="dc75a-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="dc75a-151">作成した新しいポリシーは、クライアントコンピューターのグループポリシーが更新されるまで有効になりません。</span><span class="sxs-lookup"><span data-stu-id="dc75a-151">The new policies you’ve created won’t take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="dc75a-152">グループポリシーは定期的に更新されますが、次の手順に従って、すぐに更新することができます。</span><span class="sxs-lookup"><span data-stu-id="dc75a-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="dc75a-153">グループポリシーを更新する各コンピューターで、管理者としてコマンドプロンプトを開きます (*管理者として実行*します)。</span><span class="sxs-lookup"><span data-stu-id="dc75a-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="dc75a-154">コマンドプロンプトで、</span><span class="sxs-lookup"><span data-stu-id="dc75a-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="dc75a-155">グループポリシーオブジェクトの DSCP マーキングを確認する</span><span class="sxs-lookup"><span data-stu-id="dc75a-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="dc75a-156">グループポリシーオブジェクトの値が設定されていることを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dc75a-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="dc75a-157">管理者としてコマンドプロンプトを開きます (*管理者として実行*します)。</span><span class="sxs-lookup"><span data-stu-id="dc75a-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="dc75a-158">コマンドプロンプトで、</span><span class="sxs-lookup"><span data-stu-id="dc75a-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="dc75a-159">これにより、適用された Gpo のレポートが生成され、 *gp*という名前のテキストファイルに送信されます。</span><span class="sxs-lookup"><span data-stu-id="dc75a-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="dc75a-160">" *Gp*" という名前の html レポートを読みやすくするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="dc75a-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="dc75a-161">生成されたファイルで、見出しが適用されている**グループポリシーオブジェクト**を探し、前に作成したグループポリシーオブジェクトの名前が適用されているポリシーの一覧に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dc75a-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="dc75a-162">レジストリエディターを開き、</span><span class="sxs-lookup"><span data-stu-id="dc75a-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="dc75a-163">HKEY\_ローカル\_コンピューター\\ソフトウェア\\ポリシー\\Microsoft\\Windows\\QoS</span><span class="sxs-lookup"><span data-stu-id="dc75a-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="dc75a-164">表2に示されているレジストリエントリの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="dc75a-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="dc75a-165">*表2QoS の Windows レジストリエントリの値*</span><span class="sxs-lookup"><span data-stu-id="dc75a-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="dc75a-166">名前</span><span class="sxs-lookup"><span data-stu-id="dc75a-166">Name</span></span>          |  <span data-ttu-id="dc75a-167">種類</span><span class="sxs-lookup"><span data-stu-id="dc75a-167">Type</span></span>  |    <span data-ttu-id="dc75a-168">データ</span><span class="sxs-lookup"><span data-stu-id="dc75a-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="dc75a-169">Application Name</span><span class="sxs-lookup"><span data-stu-id="dc75a-169">Application Name</span></span>    | <span data-ttu-id="dc75a-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="dc75a-170">REG_SZ</span></span> |  <span data-ttu-id="dc75a-171">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="dc75a-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="dc75a-172">DSCP Value</span><span class="sxs-lookup"><span data-stu-id="dc75a-172">DSCP Value</span></span>       | <span data-ttu-id="dc75a-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="dc75a-173">REG_SZ</span></span> |     <span data-ttu-id="dc75a-174">46</span><span class="sxs-lookup"><span data-stu-id="dc75a-174">46</span></span>      |
   |        <span data-ttu-id="dc75a-175">Local IP</span><span class="sxs-lookup"><span data-stu-id="dc75a-175">Local IP</span></span>        | <span data-ttu-id="dc75a-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="dc75a-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="dc75a-177">Local IP Prefix Length</span><span class="sxs-lookup"><span data-stu-id="dc75a-177">Local IP Prefix Length</span></span> | <span data-ttu-id="dc75a-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="dc75a-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="dc75a-179">Local Port</span><span class="sxs-lookup"><span data-stu-id="dc75a-179">Local Port</span></span>       | <span data-ttu-id="dc75a-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="dc75a-180">REG_SZ</span></span> | <span data-ttu-id="dc75a-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="dc75a-181">50000-50019</span></span> |
   |        <span data-ttu-id="dc75a-182">プロトコル</span><span class="sxs-lookup"><span data-stu-id="dc75a-182">Protocol</span></span>        | <span data-ttu-id="dc75a-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="dc75a-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="dc75a-184">Remote IP</span><span class="sxs-lookup"><span data-stu-id="dc75a-184">Remote IP</span></span>        | <span data-ttu-id="dc75a-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="dc75a-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="dc75a-186">リモート IP プレフィックス</span><span class="sxs-lookup"><span data-stu-id="dc75a-186">Remote IP Prefix</span></span>    | <span data-ttu-id="dc75a-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="dc75a-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="dc75a-188">Remote Port</span><span class="sxs-lookup"><span data-stu-id="dc75a-188">Remote Port</span></span>       | <span data-ttu-id="dc75a-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="dc75a-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="dc75a-190">Throttle Rate</span><span class="sxs-lookup"><span data-stu-id="dc75a-190">Throttle Rate</span></span>      | <span data-ttu-id="dc75a-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="dc75a-191">REG_SZ</span></span> |     <span data-ttu-id="dc75a-192">-1</span><span class="sxs-lookup"><span data-stu-id="dc75a-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="dc75a-193">使用しているクライアントに対してアプリケーション名エントリの値が正しいことを確認し、DSCP 値とローカルポートエントリの両方にグループポリシーオブジェクトの設定が反映されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dc75a-193">Verify that the value for the Application Name entry is correct for the client you’re using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>

---
title: Skype for Business Server の使用停止
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Skype for Business Server を使用停止する手順。
ms.openlocfilehash: 9c6051a07fc05297985b3692351c36791d8842bb
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656693"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="04539-103">オンプレミスの Skype for Business の展開を削除する</span><span class="sxs-lookup"><span data-stu-id="04539-103">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="04539-104">この記事では、オンプレミスの Skype for Business 展開を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="04539-104">This article describes how to remove your on-premises Skype for Business deployment.</span></span> <span data-ttu-id="04539-105">これは、オンプレミス環境を使用停止するための次の手順の手順 4 です。</span><span class="sxs-lookup"><span data-stu-id="04539-105">This is step 4 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="04539-106">手順 1.</span><span class="sxs-lookup"><span data-stu-id="04539-106">Step 1.</span></span> <span data-ttu-id="04539-107">[必要なすべてのユーザーをオンプレミスからオンラインに移動します](decommission-move-on-prem-users.md)。</span><span class="sxs-lookup"><span data-stu-id="04539-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span> 

- <span data-ttu-id="04539-108">手順 2.</span><span class="sxs-lookup"><span data-stu-id="04539-108">Step 2.</span></span> <span data-ttu-id="04539-109">[ハイブリッド構成を無効にします](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="04539-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="04539-110">手順 3.</span><span class="sxs-lookup"><span data-stu-id="04539-110">Step 3.</span></span> [<span data-ttu-id="04539-111">ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移動する</span><span class="sxs-lookup"><span data-stu-id="04539-111">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- <span data-ttu-id="04539-112">**手順 4.オンプレミスの Skype for Business 展開を削除します。**</span><span class="sxs-lookup"><span data-stu-id="04539-112">**Step 4. Remove your on-premises Skype for Business deployment.**</span></span> <span data-ttu-id="04539-113">(この記事)</span><span class="sxs-lookup"><span data-stu-id="04539-113">(This article)</span></span>


> [!IMPORTANT] 
> <span data-ttu-id="04539-114">この記事の手順は、ここで説明するように、ユーザー属性の管理に方法 2 を使用している場合にのみ適用 [されます](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="04539-114">The steps in this article apply only if you are using Method 2 for managing user attributes, as described [here](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span></span> <span data-ttu-id="04539-115">方法 1 を使用している場合は、この記事で説明されている手順を使用して Skype for Business サーバーを削除しません。</span><span class="sxs-lookup"><span data-stu-id="04539-115">If you are using Method 1, do not use the steps described in this article to remove your Skype for Business servers.</span></span> <span data-ttu-id="04539-116">代わりに、サーバーを再イメージできます。</span><span class="sxs-lookup"><span data-stu-id="04539-116">Instead, you can re-image the servers.</span></span>

<span data-ttu-id="04539-117">この記事の手順を完了するには、Schema Admins グループと Enterprise Admin グループの両方に対する特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="04539-117">To complete the steps in this article, you need privileges for both the Schema Admins group and the Enterprise Admin group.</span></span> <span data-ttu-id="04539-118">これらの特権は、Skype for Business Server スキーマを元に戻し、Active Directory ドメイン サービスに対するフォレスト レベルの変更を元に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="04539-118">You will need these privileges to undo the Skype for Business Server schema and forest-level changes to Active Directory Domain Services.</span></span> <span data-ttu-id="04539-119">RTCUniversalServerAdmins グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="04539-119">You will also need to be a member of the RTCUniversalServerAdmins group.</span></span>


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a><span data-ttu-id="04539-120">Skype for Business 展開を削除する準備</span><span class="sxs-lookup"><span data-stu-id="04539-120">Prepare to remove the Skype for Business deployment</span></span>

<span data-ttu-id="04539-121">必要なすべてのユーザー アカウントをクラウドに移動した後も、クリーンアップが必要な連絡先やアプリケーションなどのオンプレミス オブジェクトが残っている場合があります。</span><span class="sxs-lookup"><span data-stu-id="04539-121">After you move all required user accounts to the cloud, there may still be some remaining on-premises objects such as contacts and applications that you will need clean up.</span></span>

<span data-ttu-id="04539-122">以下の手順を使用して、これらのオブジェクトをクリーンアップし、ローカル管理者グループと RTCUniversalServerAdmins グループの両方のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="04539-122">Use the steps below to clean these objects, and make sure you are a member of both the Local Administrator group and the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="04539-123">ExUmContacts と PersistantChatEndPoints は Skype for Business Server 2019 では使用できません。</span><span class="sxs-lookup"><span data-stu-id="04539-123">Note that ExUmContacts and PersistantChatEndPoints are not available in Skype for Business Server 2019.</span></span> <span data-ttu-id="04539-124">Skype for Business Server 2019 を使用している場合は、以下の手順で対応するコマンドレットを省略する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04539-124">If you have Skype for Business Server 2019, the corresponding cmdlets in the steps below should be omitted.</span></span>

1. <span data-ttu-id="04539-125">Skype for Business Server のオンプレミス展開に関連付けられている連絡先またはアプリケーションが何かあるか確認するには、次の Skype for Business Server PowerShell コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="04539-125">To check if there are any contacts or applications associated with the Skype for Business Server on-premises deployment, run the following Skype for Business Server PowerShell cmdlets.</span></span>

   ```PowerShell
   Get-CsMeetingRoom
   Get-CsCommonAreaPhone
   Get-CsAnalogDevice
   Get-CsExUmContact
   Get-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication
   Get-CsPersistentChatEndpoint
   Get-CsAudioTestServiceApplication
   Get-CsCallParkOrbit
   ```
2. <span data-ttu-id="04539-126">手順 1 のコマンドレットからの出力リストを確認します。</span><span class="sxs-lookup"><span data-stu-id="04539-126">Review the output lists from the cmdlets in Step 1.</span></span> <span data-ttu-id="04539-127">次に、オブジェクトを削除できる場合は、次の Skype for Business Server PowerShell コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="04539-127">Then if objects can be removed, run the following Skype for Business Server PowerShell cmdlets:</span></span>

   ```PowerShell
   Get-CsMeetingRoom | Disable-CsMeetingRoom
   Get-CsCommonAreaPhone | Remove-CsCommonAreaPhone 
   Get-CsAnalogDevice | Remove-CsAnalogDevice
   Get-CsExUmContact | Remove-CsExUmContact
   Get-CsDialInConferencingAccessNumber | Remove-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow | Remove-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint | Remove-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication | Remove-CsTrustedApplication -Force
   Get-CsPersistentChatEndpoint |  Remove-CsPersistentChatEndpoint
   Get-CsCallParkOrbit | Remove-CsCallParkOrbit -Force
   Get-CsVoiceRoute | Remove-CsVoiceRoute -Force
   ```
## <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="04539-128">オンプレミスの Skype for Business の展開を削除する</span><span class="sxs-lookup"><span data-stu-id="04539-128">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="04539-129">すべての予備的な手順を完了した後、次の手順に従って Skype for Business の展開を削除できます。</span><span class="sxs-lookup"><span data-stu-id="04539-129">After completing all the preliminary steps, you can remove the Skype for Business deployment by following these steps:</span></span>

1. <span data-ttu-id="04539-130">次のように、1 つのフロントエンドを除き、Skype for Business Server 展開を論理的に削除します。</span><span class="sxs-lookup"><span data-stu-id="04539-130">Logically remove the Skype for Business Server deployment, except for a single front end, as follows:</span></span>

   <span data-ttu-id="04539-131">a.</span><span class="sxs-lookup"><span data-stu-id="04539-131">a.</span></span> <span data-ttu-id="04539-132">Skype for Business Server トポロジを更新して、1 つのフロントエンド プールを使用します。</span><span class="sxs-lookup"><span data-stu-id="04539-132">Update your Skype for Business Server topology to have a single front-end pool:</span></span>

     - <span data-ttu-id="04539-133">トポロジ ビルダーで、新しいコピーをダウンロードし、Frontend プールに移動します。</span><span class="sxs-lookup"><span data-stu-id="04539-133">In Topology Builder, download a new copy and navigate to the Frontend pool.</span></span>
     - <span data-ttu-id="04539-134">プールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04539-134">Right-click the pool, and then click **Edit Properties**.</span></span>
     - <span data-ttu-id="04539-135">[ **関連付け] で**、[ **エッジ プールの関連付け** ] (メディア コンポーネントの場合) のチェックを外し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="04539-135">In **Associations**, uncheck **Associate Edge Pool** (for media components) and click **OK**.</span></span>
     - <span data-ttu-id="04539-136">複数のフロントエンド プールがある場合は、残りのすべてのプールの関連付けを削除します。</span><span class="sxs-lookup"><span data-stu-id="04539-136">If there is more than one Frontend Pool, remove Associations for all remaining pools.</span></span>
     - <span data-ttu-id="04539-137">[アクション **] を選択>展開の削除] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="04539-137">Select **Action > Remove Deployment**.</span></span>
     - <span data-ttu-id="04539-138">[アクション **] を>トポロジの発行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="04539-138">Select **Action > Publish Topology**.</span></span>

    <span data-ttu-id="04539-139">b.</span><span class="sxs-lookup"><span data-stu-id="04539-139">b.</span></span> <span data-ttu-id="04539-140">トポロジを公開したら、ウィザードで説明されている追加の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="04539-140">After publishing the topology, complete the additional steps described in the wizard.</span></span>

2. <span data-ttu-id="04539-141">次の Skype for Business Server PowerShell コマンドレットを実行して、Skype for Business Server 会議ディレクトリを削除します。</span><span class="sxs-lookup"><span data-stu-id="04539-141">Remove Skype for Business Server conference directories by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. <span data-ttu-id="04539-142">次の Skype for Business Server PowerShell コマンドレットを実行して、Skype for Business Server 展開のアンインストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="04539-142">Finalize the uninstall of your Skype for Business Server deployment by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > <span data-ttu-id="04539-143">この手順でエラーが返される場合は、Microsoft サポート チケットを開き、残りの古いオブジェクトの削除に関するヘルプを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="04539-143">If this step returns an error, please open a Microsoft support ticket to get help removing the remaining stale objects.</span></span>

4. <span data-ttu-id="04539-144">次の Skype for Business Server PowerShell コマンドレットを実行して、サーバーの全体管理ストア サービスコントロール ポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="04539-144">Remove Central Management Store Service Control Point by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. <span data-ttu-id="04539-145">次の Skype for Business Server PowerShell コマンドレットを実行して、Skype for Business Server Active Directory ドメインフォレスト レベルの変更を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="04539-145">Undo Skype for Business Server Active Directory Domain forest-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdDomain
   ```
6. <span data-ttu-id="04539-146">次の Skype for Business Server PowerShell コマンドレットを実行して、Skype for Business Server Active Directory ドメイン スキーマの変更を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="04539-146">Undo Skype for Business Server Active Directory Domain schema changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a><span data-ttu-id="04539-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="04539-147">See also</span></span>

- [<span data-ttu-id="04539-148">オンプレミスの Skype for Business 環境を廃止する</span><span class="sxs-lookup"><span data-stu-id="04539-148">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="04539-149">必要なすべてのユーザーをオンプレミスからオンラインに移動する</span><span class="sxs-lookup"><span data-stu-id="04539-149">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="04539-150">ハイブリッド構成を無効にする</span><span class="sxs-lookup"><span data-stu-id="04539-150">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="04539-151">ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移動する</span><span class="sxs-lookup"><span data-stu-id="04539-151">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)












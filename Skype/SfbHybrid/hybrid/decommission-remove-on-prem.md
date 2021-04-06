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
ms.openlocfilehash: 668e3d5ebf5dfa03fcfb883adcc3e08fc5924bae
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593907"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="60563-103">オンプレミスの Skype for Business 展開を削除する</span><span class="sxs-lookup"><span data-stu-id="60563-103">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="60563-104">この記事では、オンプレミスの Skype for Business 展開を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="60563-104">This article describes how to remove your on-premises Skype for Business deployment.</span></span> <span data-ttu-id="60563-105">これは、オンプレミス環境を使用停止するための次の手順の手順 3 です。</span><span class="sxs-lookup"><span data-stu-id="60563-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="60563-106">手順 1.</span><span class="sxs-lookup"><span data-stu-id="60563-106">Step 1.</span></span> <span data-ttu-id="60563-107">[必要なすべてのユーザーとアプリケーション エンドポイントをオンプレミスからオンラインに移動します](decommission-move-on-prem-users.md)。</span><span class="sxs-lookup"><span data-stu-id="60563-107">[Move all required users and application endpoints from on-premises to online](decommission-move-on-prem-users.md).</span></span> 

- <span data-ttu-id="60563-108">手順 2.</span><span class="sxs-lookup"><span data-stu-id="60563-108">Step 2.</span></span> <span data-ttu-id="60563-109">[ハイブリッド構成を無効にします](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="60563-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="60563-110">**手順 3.オンプレミスの Skype for Business 展開を削除します。**</span><span class="sxs-lookup"><span data-stu-id="60563-110">**Step 3. Remove your on-premises Skype for Business deployment.**</span></span> <span data-ttu-id="60563-111">(この記事)</span><span class="sxs-lookup"><span data-stu-id="60563-111">(This article)</span></span>


> [!IMPORTANT] 
> <span data-ttu-id="60563-112">この記事の手順は、ここで説明するように、ユーザー属性の管理に方法 2 を使用している場合にのみ適用 [されます](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="60563-112">The steps in this article apply only if you are using Method 2 for managing user attributes, as described [here](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span></span> <span data-ttu-id="60563-113">方法 1 を使用している場合は、この記事で説明されている手順を使用して Skype for Business サーバーを削除しません。</span><span class="sxs-lookup"><span data-stu-id="60563-113">If you are using Method 1, do not use the steps described in this article to remove your Skype for Business servers.</span></span> <span data-ttu-id="60563-114">代わりに、サーバーを再イメージできます。</span><span class="sxs-lookup"><span data-stu-id="60563-114">Instead, you can re-image the servers.</span></span>

<span data-ttu-id="60563-115">この記事の手順を完了するには、Schema Admins グループと Enterprise Admin グループの両方に対する特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="60563-115">To complete the steps in this article, you need privileges for both the Schema Admins group and the Enterprise Admin group.</span></span> <span data-ttu-id="60563-116">これらの特権は、Skype for Business Server スキーマを元に戻し、Active Directory ドメイン サービスに対するフォレスト レベルの変更を元に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="60563-116">You will need these privileges to undo the Skype for Business Server schema and forest-level changes to Active Directory Domain Services.</span></span> <span data-ttu-id="60563-117">RTCUniversalServerAdmins グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="60563-117">You will also need to be a member of the RTCUniversalServerAdmins group.</span></span>


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a><span data-ttu-id="60563-118">Skype for Business 展開を削除する準備</span><span class="sxs-lookup"><span data-stu-id="60563-118">Prepare to remove the Skype for Business deployment</span></span>

<span data-ttu-id="60563-119">必要なすべてのユーザー アカウントをクラウドに移動した後も、クリーンアップが必要な連絡先やアプリケーションなどのオンプレミス オブジェクトが残っている場合があります。</span><span class="sxs-lookup"><span data-stu-id="60563-119">After you move all required user accounts to the cloud, there may still be some remaining on-premises objects such as contacts and applications that you will need clean up.</span></span>

<span data-ttu-id="60563-120">以下の手順を使用して、これらのオブジェクトをクリーンアップし、ローカル管理者グループと RTCUniversalServerAdmins グループの両方のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="60563-120">Use the steps below to clean these objects, and make sure you are a member of both the Local Administrator group and the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="60563-121">ExUmContacts と PersistantChatEndPoints は Skype for Business Server 2019 では使用できません。</span><span class="sxs-lookup"><span data-stu-id="60563-121">Note that ExUmContacts and PersistantChatEndPoints are not available in Skype for Business Server 2019.</span></span> <span data-ttu-id="60563-122">Skype for Business Server 2019 を使用している場合は、以下の手順で対応するコマンドレットを省略する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60563-122">If you have Skype for Business Server 2019, the corresponding cmdlets in the steps below should be omitted.</span></span>

1. <span data-ttu-id="60563-123">Skype for Business Server のオンプレミス展開に関連付けられている連絡先またはアプリケーションが何かあるか確認するには、次の Skype for Business Server PowerShell コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="60563-123">To check if there are any contacts or applications associated with the Skype for Business Server on-premises deployment, run the following Skype for Business Server PowerShell cmdlets.</span></span>

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
2. <span data-ttu-id="60563-124">手順 1 のコマンドレットからの出力リストを確認します。</span><span class="sxs-lookup"><span data-stu-id="60563-124">Review the output lists from the cmdlets in Step 1.</span></span> <span data-ttu-id="60563-125">次に、オブジェクトを削除できる場合は、次の Skype for Business Server PowerShell コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="60563-125">Then if objects can be removed, run the following Skype for Business Server PowerShell cmdlets:</span></span>

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
## <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="60563-126">オンプレミスの Skype for Business 展開を削除する</span><span class="sxs-lookup"><span data-stu-id="60563-126">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="60563-127">すべての予備的な手順を完了した後、次の手順に従って Skype for Business の展開を削除できます。</span><span class="sxs-lookup"><span data-stu-id="60563-127">After completing all the preliminary steps, you can remove the Skype for Business deployment by following these steps:</span></span>

1. <span data-ttu-id="60563-128">次のように、1 つのフロントエンドを除き、Skype for Business Server 展開を論理的に削除します。</span><span class="sxs-lookup"><span data-stu-id="60563-128">Logically remove the Skype for Business Server deployment, except for a single front end, as follows:</span></span>

   <span data-ttu-id="60563-129">a.</span><span class="sxs-lookup"><span data-stu-id="60563-129">a.</span></span> <span data-ttu-id="60563-130">Skype for Business Server トポロジを更新して、1 つのフロントエンド プールを使用します。</span><span class="sxs-lookup"><span data-stu-id="60563-130">Update your Skype for Business Server topology to have a single front-end pool:</span></span>

     - <span data-ttu-id="60563-131">トポロジ ビルダーで、新しいコピーをダウンロードし、Frontend プールに移動します。</span><span class="sxs-lookup"><span data-stu-id="60563-131">In Topology Builder, download a new copy and navigate to the Frontend pool.</span></span>
     - <span data-ttu-id="60563-132">プールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60563-132">Right-click the pool, and then click **Edit Properties**.</span></span>
     - <span data-ttu-id="60563-133">[ **関連付け] で**、[ **エッジ プールの関連付け** ] (メディア コンポーネントの場合) のチェックを外し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="60563-133">In **Associations**, uncheck **Associate Edge Pool** (for media components) and click **OK**.</span></span>
     - <span data-ttu-id="60563-134">複数のフロントエンド プールがある場合は、残りのすべてのプールの関連付けを削除します。</span><span class="sxs-lookup"><span data-stu-id="60563-134">If there is more than one Frontend Pool, remove Associations for all remaining pools.</span></span>
     - <span data-ttu-id="60563-135">[アクション **] を選択>展開の削除] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="60563-135">Select **Action > Remove Deployment**.</span></span>
     - <span data-ttu-id="60563-136">[アクション **] を>トポロジの発行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="60563-136">Select **Action > Publish Topology**.</span></span>

    <span data-ttu-id="60563-137">b.</span><span class="sxs-lookup"><span data-stu-id="60563-137">b.</span></span> <span data-ttu-id="60563-138">トポロジを公開したら、ウィザードで説明されている追加の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="60563-138">After publishing the topology, complete the additional steps described in the wizard.</span></span>

2. <span data-ttu-id="60563-139">次の Skype for Business Server PowerShell コマンドレットを実行して、Skype for Business Server 会議ディレクトリを削除します。</span><span class="sxs-lookup"><span data-stu-id="60563-139">Remove Skype for Business Server conference directories by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. <span data-ttu-id="60563-140">次の Skype for Business Server PowerShell コマンドレットを実行して、Skype for Business Server 展開のアンインストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="60563-140">Finalize the uninstall of your Skype for Business Server deployment by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > <span data-ttu-id="60563-141">この手順でエラーが返される場合は、Microsoft サポート チケットを開き、残りの古いオブジェクトの削除に関するヘルプを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="60563-141">If this step returns an error, please open a Microsoft support ticket to get help removing the remaining stale objects.</span></span>

4. <span data-ttu-id="60563-142">次の Skype for Business Server PowerShell コマンドレットを実行して、サーバーの全体管理ストア サービスコントロール ポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="60563-142">Remove Central Management Store Service Control Point by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. <span data-ttu-id="60563-143">次の Skype for Business Server PowerShell コマンドレットを実行して、Skype for Business Server Active Directory ドメインフォレスト レベルの変更を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="60563-143">Undo Skype for Business Server Active Directory Domain forest-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdDomain
   ```
6. <span data-ttu-id="60563-144">次の Skype for Business Server PowerShell コマンドレットを実行して、Skype for Business Server Active Directory ドメイン スキーマの変更を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="60563-144">Undo Skype for Business Server Active Directory Domain schema changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a><span data-ttu-id="60563-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="60563-145">See also</span></span>

- [<span data-ttu-id="60563-146">オンプレミスの Skype for Business 環境を使用停止する</span><span class="sxs-lookup"><span data-stu-id="60563-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="60563-147">ユーザーとエンドポイントをクラウドに移動する</span><span class="sxs-lookup"><span data-stu-id="60563-147">Move user and endpoints to the cloud</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="60563-148">ハイブリッド構成を無効にする</span><span class="sxs-lookup"><span data-stu-id="60563-148">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)















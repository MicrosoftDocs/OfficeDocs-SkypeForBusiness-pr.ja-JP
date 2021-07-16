---
title: 使用停止Skype for Business Server
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
description: 使用停止の手順Skype for Business Server。
ms.openlocfilehash: e96c4cd37d09fc62fbfbe34a8b8d61c79ea08289
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454340"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="b5938-103">オンプレミスの Skype for Business の展開を削除する</span><span class="sxs-lookup"><span data-stu-id="b5938-103">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="b5938-104">この記事では、オンプレミスの展開を削除するSkype for Business説明します。</span><span class="sxs-lookup"><span data-stu-id="b5938-104">This article describes how to remove your on-premises Skype for Business deployment.</span></span> <span data-ttu-id="b5938-105">これは、オンプレミス環境を使用停止するための次の手順の手順 4 です。</span><span class="sxs-lookup"><span data-stu-id="b5938-105">This is step 4 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="b5938-106">手順 1.</span><span class="sxs-lookup"><span data-stu-id="b5938-106">Step 1.</span></span> <span data-ttu-id="b5938-107">[必要なすべてのユーザーをオンプレミスからオンラインに移動します](decommission-move-on-prem-users.md)。</span><span class="sxs-lookup"><span data-stu-id="b5938-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span> 

- <span data-ttu-id="b5938-108">手順 2.</span><span class="sxs-lookup"><span data-stu-id="b5938-108">Step 2.</span></span> <span data-ttu-id="b5938-109">[ハイブリッド構成を無効にします](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="b5938-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="b5938-110">手順 3.</span><span class="sxs-lookup"><span data-stu-id="b5938-110">Step 3.</span></span> [<span data-ttu-id="b5938-111">ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移行する</span><span class="sxs-lookup"><span data-stu-id="b5938-111">Migrate hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- <span data-ttu-id="b5938-112">**手順 4.オンプレミスの展開をSkype for Businessします。**</span><span class="sxs-lookup"><span data-stu-id="b5938-112">**Step 4. Remove your on-premises Skype for Business deployment.**</span></span> <span data-ttu-id="b5938-113">(この記事)</span><span class="sxs-lookup"><span data-stu-id="b5938-113">(This article)</span></span>


> [!IMPORTANT] 
> <span data-ttu-id="b5938-114">この記事の手順は、ここで説明するように、ユーザー属性の管理に方法 2 を使用している場合にのみ適用 [されます](cloud-consolidation-managing-attributes.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="b5938-114">The steps in this article apply only if you are using Method 2 for managing user attributes, as described [here](cloud-consolidation-managing-attributes.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span></span> <span data-ttu-id="b5938-115">方法 1 を使用している場合は、この記事で説明されている手順を使用してサーバーを削除Skype for Businessしてください。</span><span class="sxs-lookup"><span data-stu-id="b5938-115">If you are using Method 1, do not use the steps described in this article to remove your Skype for Business servers.</span></span> <span data-ttu-id="b5938-116">代わりに、サーバーを再イメージできます。</span><span class="sxs-lookup"><span data-stu-id="b5938-116">Instead, you can re-image the servers.</span></span>

<span data-ttu-id="b5938-117">この記事の手順を完了するには、スキーマ管理者グループと管理者グループのEnterprise必要です。</span><span class="sxs-lookup"><span data-stu-id="b5938-117">To complete the steps in this article, you need privileges for both the Schema Admins group and the Enterprise Admin group.</span></span> <span data-ttu-id="b5938-118">Active Directory ドメイン サービスに対するスキーマSkype for Business Serverフォレスト レベルの変更を元に戻すには、これらの特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="b5938-118">You will need these privileges to undo the Skype for Business Server schema and forest-level changes to Active Directory Domain Services.</span></span> <span data-ttu-id="b5938-119">RTCUniversalServerAdmins グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5938-119">You will also need to be a member of the RTCUniversalServerAdmins group.</span></span>


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a><span data-ttu-id="b5938-120">展開を削除するSkype for Businessする</span><span class="sxs-lookup"><span data-stu-id="b5938-120">Prepare to remove the Skype for Business deployment</span></span>

<span data-ttu-id="b5938-121">必要なすべてのユーザー アカウントをクラウドに移動した後も、クリーンアップが必要な連絡先やアプリケーションなどのオンプレミス オブジェクトが残っている場合があります。</span><span class="sxs-lookup"><span data-stu-id="b5938-121">After you move all required user accounts to the cloud, there may still be some remaining on-premises objects such as contacts and applications that you will need clean up.</span></span>

<span data-ttu-id="b5938-122">以下の手順を使用して、これらのオブジェクトをクリーンアップし、ローカル管理者グループと RTCUniversalServerAdmins グループの両方のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5938-122">Use the steps below to clean these objects, and make sure you are a member of both the Local Administrator group and the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="b5938-123">ExUmContacts と PersistantChatEndPoints は、2019 年にSkype for Business Serverしてください。</span><span class="sxs-lookup"><span data-stu-id="b5938-123">Note that ExUmContacts and PersistantChatEndPoints are not available in Skype for Business Server 2019.</span></span> <span data-ttu-id="b5938-124">2019 Skype for Business Server場合は、以下の手順で対応するコマンドレットを省略する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5938-124">If you have Skype for Business Server 2019, the corresponding cmdlets in the steps below should be omitted.</span></span>

1. <span data-ttu-id="b5938-125">オンプレミスの展開に関連付けられている連絡先またはアプリケーションSkype for Business Server確認するには、次の PowerShell コマンドレットSkype for Business Server実行します。</span><span class="sxs-lookup"><span data-stu-id="b5938-125">To check if there are any contacts or applications associated with the Skype for Business Server on-premises deployment, run the following Skype for Business Server PowerShell cmdlets.</span></span>

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
2. <span data-ttu-id="b5938-126">手順 1 のコマンドレットからの出力リストを確認します。</span><span class="sxs-lookup"><span data-stu-id="b5938-126">Review the output lists from the cmdlets in Step 1.</span></span> <span data-ttu-id="b5938-127">次に、オブジェクトを削除できる場合は、PowerShell コマンドレットSkype for Business Server実行します。</span><span class="sxs-lookup"><span data-stu-id="b5938-127">Then if objects can be removed, run the following Skype for Business Server PowerShell cmdlets:</span></span>

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
## <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="b5938-128">オンプレミスの Skype for Business の展開を削除する</span><span class="sxs-lookup"><span data-stu-id="b5938-128">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="b5938-129">すべての予備的な手順を完了した後、次の手順に従ってSkype for Business展開を削除できます。</span><span class="sxs-lookup"><span data-stu-id="b5938-129">After completing all the preliminary steps, you can remove the Skype for Business deployment by following these steps:</span></span>

1. <span data-ttu-id="b5938-130">次のように、1 Skype for Business Serverを除き、展開の論理的な削除を行います。</span><span class="sxs-lookup"><span data-stu-id="b5938-130">Logically remove the Skype for Business Server deployment, except for a single front end, as follows:</span></span>

   1. <span data-ttu-id="b5938-131">1 つのフロントエンド Skype for Business Serverを持つトポロジを更新します。</span><span class="sxs-lookup"><span data-stu-id="b5938-131">Update your Skype for Business Server topology to have a single front-end pool:</span></span>

      1. <span data-ttu-id="b5938-132">トポロジ ビルダーで、新しいコピーをダウンロードし、Frontend プールに移動します。</span><span class="sxs-lookup"><span data-stu-id="b5938-132">In Topology Builder, download a new copy and navigate to the Frontend pool.</span></span>
      1. <span data-ttu-id="b5938-133">プールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5938-133">Right-click the pool, and then click **Edit Properties**.</span></span>
      1. <span data-ttu-id="b5938-134">[ **関連付け] で**、[ **エッジ プールの関連付け** ] (メディア コンポーネントの場合) のチェックを外し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b5938-134">In **Associations**, uncheck **Associate Edge Pool** (for media components) and click **OK**.</span></span>
      1. <span data-ttu-id="b5938-135">複数のフロントエンド プールがある場合は、残りのすべてのプールの関連付けを削除します。</span><span class="sxs-lookup"><span data-stu-id="b5938-135">If there is more than one Frontend Pool, remove Associations for all remaining pools.</span></span>
      1. <span data-ttu-id="b5938-136">[アクション **] を選択>展開の削除] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5938-136">Select **Action > Remove Deployment**.</span></span>
      1. <span data-ttu-id="b5938-137">[アクション **] を>トポロジの発行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5938-137">Select **Action > Publish Topology**.</span></span>

    1. <span data-ttu-id="b5938-138">トポロジを公開したら、ウィザードで説明されている追加の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b5938-138">After publishing the topology, complete the additional steps described in the wizard.</span></span>

2. <span data-ttu-id="b5938-139">次Skype for Business Server PowerShell コマンドレットを実行して、会議ディレクトリSkype for Business Server削除します。</span><span class="sxs-lookup"><span data-stu-id="b5938-139">Remove Skype for Business Server conference directories by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. <span data-ttu-id="b5938-140">PowerShell コマンドレットを実行して、Skype for Business Server展開のアンインストールをSkype for Business Serverします。</span><span class="sxs-lookup"><span data-stu-id="b5938-140">Finalize the uninstall of your Skype for Business Server deployment by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > <span data-ttu-id="b5938-141">この手順でエラーが返される場合は、Microsoft サポート チケットを開き、残りの古いオブジェクトの削除に関するヘルプを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b5938-141">If this step returns an error, please open a Microsoft support ticket to get help removing the remaining stale objects.</span></span>

4. <span data-ttu-id="b5938-142">PowerShell コマンドレットで次のコマンドを実行して、サーバーの全体管理ストア サービスSkype for Business Server削除します。</span><span class="sxs-lookup"><span data-stu-id="b5938-142">Remove Central Management Store Service Control Point by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. <span data-ttu-id="b5938-143">次Skype for Business Server PowerShell コマンドレットを実行して、Active Directory ドメイン レベルのSkype for Business Server元に戻します。</span><span class="sxs-lookup"><span data-stu-id="b5938-143">Undo Skype for Business Server Active Directory domain-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdDomain
   ```
6. <span data-ttu-id="b5938-144">次Skype for Business Server PowerShell コマンドレットを実行して、Active Directory フォレスト レベルの変更Skype for Business Server取り消します。</span><span class="sxs-lookup"><span data-stu-id="b5938-144">Undo Skype for Business Server Active Directory forest-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a><span data-ttu-id="b5938-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5938-145">See also</span></span>

- [<span data-ttu-id="b5938-146">オンプレミスの Skype for Business 環境を廃止する</span><span class="sxs-lookup"><span data-stu-id="b5938-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="b5938-147">必要なすべてのユーザーをオンプレミスからオンラインに移動する</span><span class="sxs-lookup"><span data-stu-id="b5938-147">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="b5938-148">ハイブリッド構成を無効にする</span><span class="sxs-lookup"><span data-stu-id="b5938-148">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="b5938-149">ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移動する</span><span class="sxs-lookup"><span data-stu-id="b5938-149">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)


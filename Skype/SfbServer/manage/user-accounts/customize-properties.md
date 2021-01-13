---
title: Skype for Business Server のユーザー アカウント プロパティをカスタマイズする
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: このセクションの手順を使用して、個々のユーザー アカウントのプロパティを変更できます。
ms.openlocfilehash: 6f2c3a76f9047da0a5d78695518cfb8355ab82e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826267"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="23b8f-103">Skype for Business Server のユーザー アカウント プロパティをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="23b8f-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="23b8f-104">このセクションの手順を使用して、個々のユーザー アカウントのプロパティを変更できます。</span><span class="sxs-lookup"><span data-stu-id="23b8f-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="23b8f-105">個々のユーザー レベルで実行できる基本的な操作は 2 種類です。</span><span class="sxs-lookup"><span data-stu-id="23b8f-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="23b8f-106">特定のユーザー アカウントのテレフォニー オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="23b8f-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="23b8f-107">ユーザーを別のプールに移動する</span><span class="sxs-lookup"><span data-stu-id="23b8f-107">Move users to another pool</span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="23b8f-108">特定のユーザー アカウントのテレフォニー オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="23b8f-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="23b8f-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="23b8f-109"><a name="Tel_Op"> </a></span></span>

<span data-ttu-id="23b8f-110">特定のユーザーのテレフォニー設定をカスタマイズできます (個々のユーザーが Skype for Business Server に対して有効で、組織がテレフォニーをサポートしている場合)。</span><span class="sxs-lookup"><span data-stu-id="23b8f-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="23b8f-111">Skype for Business Server のユーザー テレフォニー オプションには、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="23b8f-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="23b8f-112">**オーディオ/ビデオが無効** ユーザーは、音声とビデオを使用して通話を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="23b8f-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="23b8f-113">**PC 間のみ** ユーザーは PC 間の音声通話またはビデオ通話のみを行います。</span><span class="sxs-lookup"><span data-stu-id="23b8f-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="23b8f-114">**エンタープライズ VoIP** ユーザーは、Skype for Business Server インフラストラクチャを使用して、すべての着信および発信通話をルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="23b8f-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="23b8f-115">また、PC 間の通話も可能です。</span><span class="sxs-lookup"><span data-stu-id="23b8f-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="23b8f-116">**リモート通話コントロール** ユーザーは Skype for Business Server を使用してデスクトップ電話を制御し、PC 間呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="23b8f-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="23b8f-117">組織のテレフォニーの構成の詳細については、「展開」のドキュメントの [「Enable users for エンタープライズ VoIP in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and Deploy エンタープライズ VoIP in Skype for Business [Server」](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23b8f-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="23b8f-118">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="23b8f-119">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="23b8f-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="23b8f-120">左側のナビゲーション バーで **[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="23b8f-121">**[ユーザーの検索]** ボックスに、検索するユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全部または最初の一部を入力して、**[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="23b8f-122">表中の変更するユーザー アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="23b8f-123">[**編集**] メニューの [**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="23b8f-124">[**テレフォニー**] で次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="23b8f-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="23b8f-125">ユーザーの音声通話およびビデオ通話を無効にするには、**[音声ビデオを無効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="23b8f-p102">ユーザーの PC 間の音声通信を有効にするが、リモート通話コントロールやエンタープライズ VoIP は有効にしない場合は、[**PC 間のみ**] をクリックします。 ユーザーが PC 間の音声通信に使用する電話の [**回線 URI**] の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="23b8f-p102">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**. Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="23b8f-128">PC 間の音声通信を含むサービス ポリシーのクラスに従って、Skype for Business インフラストラクチャを使用してユーザーの電話をルーティングするには、[エンタープライズ VoIP ] をクリック **します。**</span><span class="sxs-lookup"><span data-stu-id="23b8f-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="23b8f-129">[**回線 URI**] でエンタープライズ VoIP の電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="23b8f-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="23b8f-130">[**ダイヤル プラン ポリシー**] と [**音声ポリシー**] で、ユーザーの適切なポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="23b8f-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="23b8f-131">ユーザーのダイヤルした電話番号を E.164 形式に変換するための正規化ルールを指定するには、[**場所のポリシー**] で適切な場所のプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="23b8f-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="23b8f-132">ユーザーが Skype for Business Server からデスクトップ電話回線を制御して PC 間通話と PC 間通話を行うリモート通話コントロールを有効にするには、[リモート通話コントロール] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="23b8f-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="23b8f-133">[**回線 URI**] でリモート通話コントロールの電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="23b8f-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="23b8f-134">通話ルーティングを行うには、ユーザーがデスクトップ電話と構内交換機 (PBX) を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="23b8f-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="23b8f-135">ユーザーを別のプールに移動する</span><span class="sxs-lookup"><span data-stu-id="23b8f-135">Move users to another pool</span></span>
<span data-ttu-id="23b8f-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="23b8f-136"><a name="Move_Users"> </a></span></span>

<span data-ttu-id="23b8f-137">Skype for Business Server コントロール パネルを使用して、ユーザーを特定のサーバーまたはプールに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="23b8f-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="23b8f-138">Lync Server 2010 以前を実行している送信元プールから複雑な Active Directory 環境内の Skype for Business Server のレプリケーション先プールに既存のすべてのユーザーを移動すると、Active Directory レプリケーションの速度が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="23b8f-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="23b8f-139">これを回避するには、検索フィルターを使用して、Lync Server 2010 以前を実行しているプールからユーザーを個別に移動するか、Skype for Business Server 管理シェルを使用してコマンドレットを使用してユーザーを移動できます。</span><span class="sxs-lookup"><span data-stu-id="23b8f-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="23b8f-140">また、フィルター機能は Skype for Business Server ユーザーと一緒に動作します。</span><span class="sxs-lookup"><span data-stu-id="23b8f-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="23b8f-141">選択したユーザーを別のサーバーまたはプールに移動するには</span><span class="sxs-lookup"><span data-stu-id="23b8f-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="23b8f-142">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="23b8f-143">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="23b8f-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="23b8f-144">左側のナビゲーション バーで **[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="23b8f-145">[**ユーザーの検索**] ボックスに、検索するユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全部または最初の一部を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="23b8f-146">表の一覧で、特定のユーザーまたは複数のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="23b8f-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="23b8f-147">[**アクション**] メニューの [**選択したユーザーをプールに移動する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="23b8f-148">[**ユーザーの移動**] の [**移動先レジストラ プール**] で、ユーザーの移動先のプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="23b8f-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="23b8f-149">(オプション) 移動先のサーバーまたはプールを使用できない場合は、[**強制移動**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="23b8f-p106">[**強制**] を選択すると、ユーザー アカウントは移動しますが、関連付けられているユーザー データ (ユーザーが予約した会議など) がすべて削除されます。選択しない場合は、アカウントも関連付けられているデータも移動します。</span><span class="sxs-lookup"><span data-stu-id="23b8f-p106">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="23b8f-152">サーバー間またはプール間ですべてのユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="23b8f-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="23b8f-153">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="23b8f-154">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="23b8f-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="23b8f-155">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="23b8f-156">[**アクション**] メニューの [**すべてのユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="23b8f-157">[**ユーザーの移動**] の [**移動元レジストラー プール**] で、移動するユーザー アカウントが入っているプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="23b8f-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="23b8f-158">[**移動先レジストラ プール**] で、ユーザーの移動先のプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="23b8f-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="23b8f-159">(オプション) 移動先のサーバーまたはプールを使用できない場合は、[**強制**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="23b8f-p107">[**強制**] を選択すると、ユーザー アカウントは移動しますが、関連付けられているユーザー データ (ユーザーが予約した会議など) がすべて削除されます。選択しない場合は、アカウントも関連付けられているデータも移動します。</span><span class="sxs-lookup"><span data-stu-id="23b8f-p107">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="23b8f-162">フィルターを使用してユーザーをプール間で移動するには</span><span class="sxs-lookup"><span data-stu-id="23b8f-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="23b8f-163">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="23b8f-164">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="23b8f-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="23b8f-165">左側のナビゲーション バーで **[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="23b8f-166">ユーザー **検索で、[** 検索] を **クリックし**、[フィルターの追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="23b8f-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="23b8f-167">検索条件で [**レジストラー プール**] を選択し、[**が次の値に等しい**] を選択して、[**現在のプールの FQDN**] を選択し、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="23b8f-168">[**アクション**] メニューの [**すべてのユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="23b8f-169">既存のユーザー セットに対してフィルターを適用すると、オプション [**すべてのユーザーをプールに移動**] は、可能性のあるユーザーすべてではなく、フィルターされたユーザーのサブセットのコンテキストとなります \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="23b8f-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="23b8f-170">[**ユーザーの移動**] の [**移動元レジストラー プール**] で、移動するユーザー アカウントが入っているプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="23b8f-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="23b8f-171">[**移動先レジストラー プール**] で、ユーザーの移動先のプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="23b8f-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="23b8f-172">(オプション) 移動先のサーバーまたはプールを使用できない場合は、[**強制**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="23b8f-p108">[**強制**] を選択すると、ユーザー アカウントは移動しますが、関連付けられているユーザー データ (ユーザーが予約した会議、連絡先など) がすべて削除されます。選択しない場合は、アカウントも関連付けられているデータも移動します。</span><span class="sxs-lookup"><span data-stu-id="23b8f-p108">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="23b8f-175">Windows Powershell コマンドレットを使用してユーザーをプール間で移動するには</span><span class="sxs-lookup"><span data-stu-id="23b8f-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="23b8f-176">Windows PowerShell コマンドの実行方法 (ローカルまたはリモート) に応じて、次のように正しい Skype for Business Server 管理者の役割のメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="23b8f-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="23b8f-177">a. </span><span class="sxs-lookup"><span data-stu-id="23b8f-177">a.</span></span> <span data-ttu-id="23b8f-178">ローカル コンピューターでコマンドを実行している場合 (たとえば、フロントエンド サーバーに直接ログオンする場合): Skype for Business Server 管理シェルがインストールされているコンピューターに RTCUniversalServerAdmins グループのメンバーとして、またはセットアップのアクセス許可の委任の説明に従って必要なユーザー権限を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="23b8f-179">b.</span><span class="sxs-lookup"><span data-stu-id="23b8f-179">b.</span></span> <span data-ttu-id="23b8f-180">別のコンピューターでリモートでコマンドを実行している場合 (たとえば、コンピューターにログオンし、Standard Edition フロントエンド サーバーでリモートでコマンドを実行する場合): CsUserAdministrator の役割または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="23b8f-181">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23b8f-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="23b8f-182">単一のユーザーを移動するには、Move-CsUser コマンドレットを次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="23b8f-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="23b8f-183">この場合、移動するユーザーは Pilar Ackerman で、現在割り当てられているホーム プールから、プール pool01.contoso.net に移動します。</span><span class="sxs-lookup"><span data-stu-id="23b8f-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="23b8f-184">大量のユーザーを移動するには、フィルターと **Get-CsUser** コマンドレットを使用し、ユーザーの結果セットを **Move-CsUser** に渡します。</span><span class="sxs-lookup"><span data-stu-id="23b8f-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="23b8f-185">**Get-CsUser** と **Move-CsUser** を組み合わせたコマンドを実行すると、たとえば、次のような結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="23b8f-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```



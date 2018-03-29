---
title: ビジネス サーバー 2015 の Skype のユーザー アカウントのプロパティをカスタマイズします。
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: 個々 のユーザー アカウントのプロパティを変更するのには、このセクションの手順を使用できます。
ms.openlocfilehash: fc15dac499fe5d812d5d084a919db10096e6dc56
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="customize-user-account-properties-for-skype-for-business-server-2015"></a><span data-ttu-id="e41f7-103">ビジネス サーバー 2015 の Skype のユーザー アカウントのプロパティをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-103">Customize user account properties for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e41f7-104">個々 のユーザー アカウントのプロパティを変更するのには、このセクションの手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e41f7-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="e41f7-105">個々 のユーザー レベルで実行できる 2 つの基本的な操作があります。</span><span class="sxs-lookup"><span data-stu-id="e41f7-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="e41f7-106">特定のユーザー アカウントのテレフォニー オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="e41f7-107">ユーザーを別のプールに移動します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-107">Move users to another pool </span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="e41f7-108">特定のユーザー アカウントのテレフォニー オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="e41f7-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="e41f7-109"></span></span>

<span data-ttu-id="e41f7-110">(限り、個々 のユーザーが有効になって Skype のビジネス サーバー 2015 と組織がテレフォニーをサポートしています)、特定のユーザーにテレフォニー設定をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="e41f7-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server 2015 and the organization supports telephony).</span></span>
  
<span data-ttu-id="e41f7-111">Skype ビジネス サーバー ユーザーのテレフォニー オプションの次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e41f7-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="e41f7-112">**オーディオとビデオを無効に**ユーザーは、オーディオとビデオでの呼び出しを行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="e41f7-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="e41f7-113">**-PC のみ**ユーザーは、PC のオーディオまたはビデオの呼び出しだけで、ことができます。</span><span class="sxs-lookup"><span data-stu-id="e41f7-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="e41f7-114">**エンタープライズ VoIP**ユーザーは、すべての着信および発信コールをルーティングするのにサーバー 2015 のビジネス ・ インフラストラクチャの Skype を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e41f7-114">**Enterprise Voice** The user can use the Skype for Business Server 2015 infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="e41f7-115">ユーザーは、PC の呼び出しを行うことも。</span><span class="sxs-lookup"><span data-stu-id="e41f7-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="e41f7-116">**リモート通話コントロール**ユーザーは、デスクトップ電話を制御するビジネス サーバー 2015 の Skype を使用することができ、PC の呼び出しを行っても。</span><span class="sxs-lookup"><span data-stu-id="e41f7-116">**Remote call control** The user can use Skype for Business Server 2015 to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="e41f7-117">組織のテレフォニーの構成に関する詳細については、展開に関するドキュメントで[ビジネス サーバー 2015 の Skype でエンタープライズ VoIP のユーザーを有効に](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)し、[ビジネス サーバー 2015 の Skype でのエンタープライズ VoIP の展開](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e41f7-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="e41f7-118">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e41f7-119">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e41f7-120">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="e41f7-121">**ユーザーの検索**] ボックス、すべての種類または、表示名、名、最終名、セキュリティ アカウント マネージャー (SAM) アカウント名、SIP アドレス、または行を選択して、**の検索] をクリックし、ユーザー アカウントの統一リソース識別子 (URI) の最初の部分で**.</span><span class="sxs-lookup"><span data-stu-id="e41f7-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="e41f7-122">テーブルを変更するユーザー アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="e41f7-123">[**編集**] メニューの [**変更**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="e41f7-124">**テレフォニー**では、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e41f7-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="e41f7-125">ユーザーのオーディオおよびビデオの呼び出しを無効にするには、**オーディオとビデオを無効**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="e41f7-126">PC のユーザーが、リモート通話コントロールまたはエンタープライズ VoIP のオーディオの通信を有効にするには、 **- PC のみ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-126">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="e41f7-127">ユーザーは PC の音声通信に使用する電話の**URI の行**の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-127">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="e41f7-128">PC のオーディオの通信を含め、サービスのポリシーのクラスに基づいてビジネス ・ インフラストラクチャの Skype を使用して、ユーザーの電話の通話をルーティングするには、**エンタープライズ VoIP**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="e41f7-129">**回線 URI**では、エンタープライズ VoIP の電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="e41f7-130">**ダイヤル プラン ポリシー**と**ボイス ポリシー**は、ユーザーに対して適切なポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="e41f7-131">E.164 形式にユーザーがダイヤルした電話番号を変換するための正規化の規則を指定するには、**場所のポリシー**で適切な場所のプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="e41f7-132">リモート呼び出しを有効にするのには、PC の呼び出しと PC から電話への呼び出しを作成するのには、ビジネス サーバー 2015 の Skype からには、そのデスクトップの電話回線を制御するユーザーを有効にするコントロールは、**リモート通話コントロール**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server 2015 to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="e41f7-133">**回線 URI**では、リモート通話コントロールの電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="e41f7-134">ユーザーは、デスクトップの電話と通話のルーティングを使用する構内交換 (機 PBX) 接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="e41f7-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="e41f7-135">ユーザーを別のプールに移動します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-135">Move users to another pool</span></span>
<span data-ttu-id="e41f7-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="e41f7-136"></span></span>

<span data-ttu-id="e41f7-137">Skype ビジネス サーバーのコントロール パネルの特定のサーバーまたはプールにユーザーを割り当てるには使用できます。</span><span class="sxs-lookup"><span data-stu-id="e41f7-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="e41f7-138">Lync Server 2010 を実行している移動元のプールから、または、Skype ビジネス サーバー 2015 複雑な Active Directory 環境での移動先のプールの以前のバージョンからすべての既存ユーザーの移動と、Active Directory のレプリケーションが遅くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e41f7-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server 2015 destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="e41f7-139">これを回避するには、Lync Server 2010 を実行しているプールからユーザーを移動する検索フィルターを使用することができますまたは以前のバージョンとは別に、コマンドレットを持つユーザーを移動するビジネス サーバー管理シェルの Skype を使用できますか。</span><span class="sxs-lookup"><span data-stu-id="e41f7-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="e41f7-140">フィルター機能は、Skype で、ビジネス サーバー 2015 のユーザーに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-140">Also, the filter functionality works with Skype for Business Server 2015 users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="e41f7-141">選択したユーザーを別のサーバーまたはプールに移動するには</span><span class="sxs-lookup"><span data-stu-id="e41f7-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="e41f7-142">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e41f7-143">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="e41f7-144">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="e41f7-145">**ユーザーの検索**] ボックス、すべての種類または、表示名、名、最終名、セキュリティ アカウント マネージャー (SAM) アカウント名、SIP アドレス、または行を選択して、**の検索] をクリックし、ユーザー アカウントの統一リソース識別子 (URI) の最初の部分で**.</span><span class="sxs-lookup"><span data-stu-id="e41f7-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="e41f7-146">テーブルで特定のユーザーまたはリスト内のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="e41f7-147">[**操作**] メニューで、**プールを選択したユーザーを移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="e41f7-148">] で、**ユーザーの移動**には、ユーザーの**移動先のレジストラー プール**に移動するプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="e41f7-149">(省略可能)宛先サーバーまたはプールが使用できない場合、[**強制**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="e41f7-150">**荷重**を選択すると、ユーザー アカウントを移動するが、関連付けられたユーザー データが削除される (たとえば、ユーザーがスケジュールされている会議など)。</span><span class="sxs-lookup"><span data-stu-id="e41f7-150">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="e41f7-151">選択しない場合は、アカウントと関連付けられているデータの両方が移動されます。</span><span class="sxs-lookup"><span data-stu-id="e41f7-151">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="e41f7-152">すべてのユーザーを 1 つのサーバーまたはプールから別のサーバーまたはプールに移動するには</span><span class="sxs-lookup"><span data-stu-id="e41f7-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="e41f7-153">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e41f7-154">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="e41f7-155">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="e41f7-156">[**操作**] メニューで、**プールへのすべてのユーザーの移動**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="e41f7-157">] で、**ユーザーの移動****元のレジストラー プール**に移動するユーザー アカウントを含むプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="e41f7-158">**先のレジストラー プール**で、プールにユーザーを移動するを選択します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="e41f7-159">(省略可能)宛先サーバーまたはプールが使用できない場合、[**強制**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="e41f7-160">**荷重**を選択すると、ユーザー アカウントを移動するが、関連付けられたユーザー データが削除される (たとえば、ユーザーがスケジュールされている会議など)。</span><span class="sxs-lookup"><span data-stu-id="e41f7-160">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="e41f7-161">選択しない場合は、アカウントと関連付けられているデータの両方が移動されます。</span><span class="sxs-lookup"><span data-stu-id="e41f7-161">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="e41f7-162">フィルターを使用してユーザーを 1 つのプールから別のプールに移動するには</span><span class="sxs-lookup"><span data-stu-id="e41f7-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="e41f7-163">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e41f7-164">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e41f7-165">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="e41f7-166">**ユーザーの検索**、**検索**] をクリックし、**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="e41f7-167">検索条件に**レジストラー プール**を選択、[**と等しい****現在のプールの FQDN**、し [**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="e41f7-168">[**操作**] メニューで、**プールへのすべてのユーザーの移動**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e41f7-169">フィルターは、既存のセット、ユーザーのいない**すべて**の可能なユーザー、ユーザーのフィルター処理されたサブセットのコンテキストでは、**プールへのすべてのユーザーを移動**するオプションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e41f7-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="e41f7-170">] で、**ユーザーの移動****元のレジストラー プール**に移動するユーザー アカウントを含むプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="e41f7-171">**移動先レジストラー プール**にユーザーを移動先のプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="e41f7-172">(省略可能)宛先サーバーまたはプールが使用できない場合、[**強制**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="e41f7-173">**フォース**を選択した場合は、ユーザー アカウントを移動するは、(ユーザーがスケジュールされている会議や連絡先など) に関連付けられたユーザー データが削除されます。</span><span class="sxs-lookup"><span data-stu-id="e41f7-173">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts).</span></span> <span data-ttu-id="e41f7-174">選択しない場合は、アカウントと関連付けられているデータの両方が移動されます。</span><span class="sxs-lookup"><span data-stu-id="e41f7-174">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="e41f7-175">1 つのプールからユーザーを移動するのには Windows Powershell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="e41f7-176">によってどのように Windows PowerShell コマンドを実行する、(つまり、ローカルまたはリモートで)、次のようにサーバー 2015 のビジネス管理者の役割の正しい Skype のメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e41f7-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server 2015 administrative roles as follows:</span></span>
    
   <span data-ttu-id="e41f7-177">a.</span><span class="sxs-lookup"><span data-stu-id="e41f7-177">a.</span></span> <span data-ttu-id="e41f7-178">(たとえば、ログオンするサーバーをフロント エンド サーバーに直接) ローカル コンピューター上のコマンドを実行している場合: 必要な RTCUniversalServerAdmins グループのメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンユーザー権利**アクセス許可の委任の設定**で説明したようです。</span><span class="sxs-lookup"><span data-stu-id="e41f7-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="e41f7-179">b.</span><span class="sxs-lookup"><span data-stu-id="e41f7-179">b.</span></span> <span data-ttu-id="e41f7-180">かどうかコマンドを実行、リモートで別のコンピューター (たとえば、コンピューターにログオンして標準 Edition フロント エンド サーバー上のコマンドをリモートで実行): CsUserAdministrator の役割や、CsAdministrator に割り当てられているユーザー アカウントからロール、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e41f7-181">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e41f7-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e41f7-182">1 つのユーザーを移動するには、次のように移動 CsUser コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="e41f7-183">移動である久保田千絵、ユーザーと、ユーザーに移動されますが現在割り当てられているホーム プールからプール pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="e41f7-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="e41f7-184">多数のユーザーを移動するには、 **Get CsUser**コマンドレットでフィルターを使用し、 **csuser からの移動**にユーザーの結果セットを渡します。</span><span class="sxs-lookup"><span data-stu-id="e41f7-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="e41f7-185">**Csuser からの取得**と**移動 CsUser**の結合されたコマンドは、この可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e41f7-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```



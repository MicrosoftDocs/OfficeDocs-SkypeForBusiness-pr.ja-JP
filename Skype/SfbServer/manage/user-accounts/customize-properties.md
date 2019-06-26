---
title: Skype for Business Server のユーザーアカウントのプロパティをカスタマイズする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: このセクションの手順を使用して、個々のユーザーアカウントのプロパティを変更することができます。
ms.openlocfilehash: fda11a1b52519f3653c841837af20392383cadd1
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222062"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="0be3c-103">Skype for Business Server のユーザーアカウントのプロパティをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="0be3c-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="0be3c-104">このセクションの手順を使用して、個々のユーザーアカウントのプロパティを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="0be3c-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="0be3c-105">個々のユーザーレベルで実行できる基本的な操作には、次の2つがあります。</span><span class="sxs-lookup"><span data-stu-id="0be3c-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="0be3c-106">特定のユーザーアカウントのテレフォニーオプションを構成する</span><span class="sxs-lookup"><span data-stu-id="0be3c-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="0be3c-107">ユーザーを別のプールに移動する</span><span class="sxs-lookup"><span data-stu-id="0be3c-107">Move users to another pool</span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="0be3c-108">特定のユーザーアカウントのテレフォニーオプションを構成する</span><span class="sxs-lookup"><span data-stu-id="0be3c-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="0be3c-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="0be3c-109"></span></span>

<span data-ttu-id="0be3c-110">特定のユーザーのテレフォニー設定をカスタマイズすることができます (個別のユーザーが Skype for Business Server に対して有効になっており、組織がテレフォニーをサポートしている場合)。</span><span class="sxs-lookup"><span data-stu-id="0be3c-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="0be3c-111">Skype for Business Server のユーザーテレフォニーオプションには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0be3c-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="0be3c-112">**オーディオ/ビデオは無効**ユーザーは、音声とビデオを使って通話を発信することはできません。</span><span class="sxs-lookup"><span data-stu-id="0be3c-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="0be3c-113">**Pc 間のみ**ユーザーは、PC 間の音声通話またはビデオ通話のみを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0be3c-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="0be3c-114">**エンタープライズ voip**ユーザーは、Skype for Business Server インフラストラクチャを使用して、すべての着信通話と発信通話をルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="0be3c-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="0be3c-115">ユーザーは PC 間の通話を発信することもできます。</span><span class="sxs-lookup"><span data-stu-id="0be3c-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="0be3c-116">**リモート通話コントロール**ユーザーは、Skype for Business Server を使用して、デスクトップ電話を制御することができます。また、PC 間通話を発信することもできます。</span><span class="sxs-lookup"><span data-stu-id="0be3c-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="0be3c-117">組織のテレフォニーの構成の詳細については、展開ドキュメントの「skype for business server[でのエンタープライズ voip のユーザーの有効化](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)と[エンタープライズボイスの展開](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0be3c-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="0be3c-118">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0be3c-119">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0be3c-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="0be3c-120">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="0be3c-121">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティアカウントマネージャー (SAM) アカウント名、SIP アドレス、または必要なユーザーアカウントの行の Uniform resource IDENTIFIER (URI) の最初の部分を入力し、[検索] をクリックします。 \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="0be3c-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="0be3c-122">表で、変更するユーザーアカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="0be3c-123">[**編集**] メニューの [**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="0be3c-124">[**テレフォニー**] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0be3c-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="0be3c-125">ユーザーの音声通話とビデオ通話を無効にするには、[**オーディオ/ビデオを無効**にする] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="0be3c-126">ユーザーに対して PC 間音声通信を有効にしますが、リモート通話コントロールまたはエンタープライズボイスでは使用できないようにするには、[ **pc 間のみ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-126">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="0be3c-127">ユーザーが PC 間の音声通信に使用する電話の**ライン URI**の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="0be3c-127">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="0be3c-128">Skype for Business インフラストラクチャを使って、ユーザーの電話をルーティングするには、PC 間の音声通信など、サービスのクラスに応じて、[**エンタープライズ voip**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="0be3c-129">[**行の URI**] で、エンタープライズ voip の電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="0be3c-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="0be3c-130">[**ダイヤルプランポリシー** ] と [**ボイスポリシー**] で、ユーザーに適したポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="0be3c-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="0be3c-131">ユーザーがダイヤルした電話番号を E-164 形式で翻訳するための正規化ルールを指定するには、**場所のポリシー**で適切な場所のプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="0be3c-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="0be3c-132">リモート通話コントロールを有効にして、ユーザーが Skype for Business Server からデスクトップ電話回線を制御できるようにするには、[**リモート通話コントロール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="0be3c-133">[**行の URI**] で、リモート通話コントロール用の電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="0be3c-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="0be3c-134">ユーザーは、通話ルーティング用に、デスクトップ電話と構内交換機 (PBX) 接続を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0be3c-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="0be3c-135">ユーザーを別のプールに移動する</span><span class="sxs-lookup"><span data-stu-id="0be3c-135">Move users to another pool</span></span>
<span data-ttu-id="0be3c-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="0be3c-136"></span></span>

<span data-ttu-id="0be3c-137">Skype for Business Server コントロールパネルを使用して、特定のサーバーまたはプールにユーザーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="0be3c-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="0be3c-138">Lync Server 2010 以前を実行しているソースプールの既存のすべてのユーザーを、複雑な Active Directory 環境の Skype for Business Server の宛先プールに移動すると、Active Directory のレプリケーションが遅くなることがあります。</span><span class="sxs-lookup"><span data-stu-id="0be3c-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="0be3c-139">これを回避するために、検索フィルターを使用して、Lync Server 2010 以前を実行しているプールからユーザーを移動することも、Skype for Business Server 管理シェルを使用してユーザーをコマンドレットで移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="0be3c-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="0be3c-140">また、フィルター機能は、Skype for Business Server ユーザーと連携して動作します。</span><span class="sxs-lookup"><span data-stu-id="0be3c-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="0be3c-141">選択したユーザーを別のサーバーまたはプールに移動するには</span><span class="sxs-lookup"><span data-stu-id="0be3c-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="0be3c-142">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0be3c-143">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0be3c-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="0be3c-144">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="0be3c-145">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティアカウントマネージャー (SAM) アカウント名、SIP アドレス、または必要なユーザーアカウントの行の Uniform resource IDENTIFIER (URI) の最初の部分を入力し、[検索] をクリックします。 \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="0be3c-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="0be3c-146">表で、リスト内の特定のユーザー (複数可) を選びます。</span><span class="sxs-lookup"><span data-stu-id="0be3c-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="0be3c-147">[**操作**] メニューの [**選択したユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="0be3c-148">[**ユーザーの移動**] で、ユーザーを移動**先のレジストラープール**に移動するプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="0be3c-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="0be3c-149">省略移動先のサーバーまたはプールが利用できない場合は、[**強制**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="0be3c-150">[**強制**] を選択すると、ユーザーアカウントは移動されますが、関連付けられているユーザーデータが削除されます (たとえば、ユーザーがスケジュールした会議など)。</span><span class="sxs-lookup"><span data-stu-id="0be3c-150">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="0be3c-151">このチェックボックスをオンにしない場合は、アカウントと関連データの両方が移動されます。</span><span class="sxs-lookup"><span data-stu-id="0be3c-151">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="0be3c-152">1つのサーバーまたはプールから別のサーバーまたはプールにすべてのユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="0be3c-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="0be3c-153">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0be3c-154">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0be3c-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="0be3c-155">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="0be3c-156">[**操作**] メニューの [**すべてのユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="0be3c-157">[**ユーザーの移動**] で、**ソースレジストラープール**内で移動するユーザーアカウントが含まれているプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="0be3c-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="0be3c-158">[**宛先レジスタプール**] で、ユーザーの移動先のプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="0be3c-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="0be3c-159">省略移動先のサーバーまたはプールが利用できない場合は、[**強制**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="0be3c-160">[**強制**] を選択すると、ユーザーアカウントは移動されますが、関連付けられているユーザーデータが削除されます (たとえば、ユーザーがスケジュールした会議など)。</span><span class="sxs-lookup"><span data-stu-id="0be3c-160">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="0be3c-161">このチェックボックスをオンにしない場合は、アカウントと関連データの両方が移動されます。</span><span class="sxs-lookup"><span data-stu-id="0be3c-161">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="0be3c-162">フィルターを使用して1つのプールから別のプールにユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="0be3c-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="0be3c-163">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0be3c-164">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0be3c-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="0be3c-165">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="0be3c-166">[**ユーザー検索**] で [**検索**] をクリックし、[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="0be3c-167">検索条件で、[**レジストラー Pool**]、[指定の**値に等しい**] の順に選択し、[**現在のプールの FQDN**] を選択し、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="0be3c-168">[**操作**] メニューの [**すべてのユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0be3c-169">フィルターが既存のユーザーのセットに適用されている場合、[**すべてのユーザーをプールに移動する**] オプションは、**すべて**のユーザーに対してフィルター処理されたユーザーのサブセットのコンテキストで実行されます。</span><span class="sxs-lookup"><span data-stu-id="0be3c-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="0be3c-170">[**ユーザーの移動**] で、**ソースレジストラープール**内で移動するユーザーアカウントが含まれているプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="0be3c-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="0be3c-171">[**宛先レジストラー pool**] で、ユーザーを移動するプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="0be3c-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="0be3c-172">省略移動先のサーバーまたはプールが利用できない場合は、[**強制**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="0be3c-173">[**強制**] を選択すると、ユーザーアカウントは移動されますが、関連付けられたユーザーデータが削除されます (たとえば、ユーザーがスケジュールした会議や連絡先がある会議など)。</span><span class="sxs-lookup"><span data-stu-id="0be3c-173">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts).</span></span> <span data-ttu-id="0be3c-174">このチェックボックスをオンにしない場合は、アカウントと関連データの両方が移動されます。</span><span class="sxs-lookup"><span data-stu-id="0be3c-174">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="0be3c-175">Windows Powershell コマンドレットを使用してユーザーを別のプールに移動するには</span><span class="sxs-lookup"><span data-stu-id="0be3c-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="0be3c-176">Windows PowerShell コマンドの実行方法 (ローカルまたはリモート) に応じて、次のようにして、正しい Skype for Business Server 管理者ロールのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0be3c-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="0be3c-177">a.</span><span class="sxs-lookup"><span data-stu-id="0be3c-177">a.</span></span> <span data-ttu-id="0be3c-178">ローカルコンピューターでコマンドを実行している場合 (たとえば、フロントエンドサーバーに直接ログオンしている場合) は、Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとしてインストールされているか、または必要な場合は、そのコンピューターにログオンします。「**代理人セットアップの権限**」で説明されているユーザー権限</span><span class="sxs-lookup"><span data-stu-id="0be3c-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="0be3c-179">b.</span><span class="sxs-lookup"><span data-stu-id="0be3c-179">b.</span></span> <span data-ttu-id="0be3c-180">他のコンピューターでリモートでコマンドを実行している場合 (たとえば、コンピューターにログオンして、標準エディションのフロントエンドサーバーでコマンドをリモートで実行している場合) は、CsUserAdministrator ロールまたは CsAdministrator に割り当てられているユーザーアカウントからの操作を行います。[役割] は、社内展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0be3c-181">Skype for Business Server 管理シェルを開始します。 [**スタート**]、[**すべてのプログラム**]、[ **skype For business**]、[ **skype for business server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be3c-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0be3c-182">1人のユーザーを移動するには、次のように移動-CsUser コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="0be3c-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="0be3c-183">ユーザーの移動先がユーザー Pilar Ackerman であり、ユーザーは現在割り当てられているホームプールからプールに移動されます。 pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0be3c-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="0be3c-184">多数のユーザーを移動するには、ユーザーの**アクセス**コマンドレットを使用してフィルターを実行し、その結果セットのユーザーを**移動**するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="0be3c-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="0be3c-185">次のような操作を行うと、ユーザーと**ムーブグループ**のユーザーの組み合わせコマンドが**表示**されます。</span><span class="sxs-lookup"><span data-stu-id="0be3c-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```



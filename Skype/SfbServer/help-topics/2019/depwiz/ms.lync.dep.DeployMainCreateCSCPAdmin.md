---
title: Skype for Business Server コントロール パネル管理者の作成
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: ビジネス サーバー 2015 の Skype へのアクセスを許可するには、次の操作を行います。
ms.openlocfilehash: db781611e2df2abf23c071673d3dfe0570f5700b
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a><span data-ttu-id="6fa10-103">Skype for Business Server コントロール パネル管理者の作成</span><span class="sxs-lookup"><span data-stu-id="6fa10-103">Create Skype for Business Server Control Panel Administrators</span></span>
 
<span data-ttu-id="6fa10-104">ビジネス サーバー 2015 の Skype へのアクセスを許可するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6fa10-104">To grant access to the Skype for Business Server 2015, do the following:</span></span>
  
1. <span data-ttu-id="6fa10-105">Domain Admins グループまたは RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="6fa10-105">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="6fa10-106">[**Active Directory ユーザーとコンピューター**] を開き、ドメインを展開して [**ユーザー**] コンテナーを右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fa10-106">Open **Active Directory Users and Computers**, expand your domain, right-click the **Users** container, and then click **Properties**.</span></span>
    
3. <span data-ttu-id="6fa10-107">[**CSAdministrator のプロパティ**] で、[**メンバー**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fa10-107">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
4. <span data-ttu-id="6fa10-p101">[メンバー] タブで [**追加**] をクリックします。[**ユーザー、連絡先、コンピューター、サービス アカウント、またはグループの選択**] で、[**選択するオブジェクト名を入力してください**] を見つけます。CSAdministrators グループに追加するユーザー名またはグループ名を入力します。[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fa10-p101">On the Members tab, click **Add**. In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**. Type the user name(s) or group name(s) to add to the group CSAdministrators. Click **OK**.</span></span>
    
5. <span data-ttu-id="6fa10-p102">[メンバー] タブで、選択したユーザーまたはグループが表示されていることを確認します。[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fa10-p102">On the Members tab, confirm that the users or groups that you selected are present. Click **OK**.</span></span>
    
> [!TIP]
> <span data-ttu-id="6fa10-114">ビジネス サーバーのコントロール パネルの Skype は、役割ベースのアクセス制御ツールです。</span><span class="sxs-lookup"><span data-stu-id="6fa10-114">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="6fa10-115">CsAdministrator グループのメンバーシップは、利用可能なすべての構成機能のビジネス サーバーのコントロール パネルの [フル コントロールの Skype を使用しているユーザーを与えます。</span><span class="sxs-lookup"><span data-stu-id="6fa10-115">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all the configuration functions available.</span></span> <span data-ttu-id="6fa10-116">特定の機能向けに設計されたその他の役割も使用できます。</span><span class="sxs-lookup"><span data-stu-id="6fa10-116">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="6fa10-117">ユーザーは、管理グループのメンバーになるために Skype ビジネス サーバーに対して有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6fa10-117">Users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
<span data-ttu-id="6fa10-118">他の役割は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6fa10-118">Other roles include:</span></span>
  
- <span data-ttu-id="6fa10-119">**CsArchiving:** このグループのメンバーは、構成、およびアーカイブ サーバーの役割を管理するなど、すべてのアーカイブ機能を実行できます。</span><span class="sxs-lookup"><span data-stu-id="6fa10-119">**CsArchiving:** Members of this group can perform all archiving functions, such as configuring and managing the Archiving Server role.</span></span>
    
- <span data-ttu-id="6fa10-p104">**CsHelpDesk:** このグループのメンバーは、ユーザーのプロパティやポリシーを含む構成と展開を表示できます。またメンバーは、特定のトラブルシューティング タスクも実行できます。</span><span class="sxs-lookup"><span data-stu-id="6fa10-p104">**CsHelpDesk:** Members of this group can view the configuration and deployment, including user properties and policies. Members can also perform specific troubleshooting tasks.</span></span>
    
- <span data-ttu-id="6fa10-p105">**CsLocationAdministrator:** メンバーは、Enhanced 9-1-1 (E9-1-1) の管理と関連付けられた最小限のユーザー権限を持ちます。E9-1-1 の場所およびネットワーク識別子を作成し、展開内でそれらを関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="6fa10-p105">**CsLocationAdministrator:** Members have the lowest level of user rights associated with Enhanced 9-1-1 (E9-1-1) management. They can create E9-1-1 locations and network identifiers and associate those in the deployment.</span></span>
    
- <span data-ttu-id="6fa10-124">**CsResponseGroupAdministrator:** メンバーは、応答グループ サービスを管理および構成できます。</span><span class="sxs-lookup"><span data-stu-id="6fa10-124">**CsResponseGroupAdministrator:** Members can manage and configure the Response Group service.</span></span>
    
- <span data-ttu-id="6fa10-125">**CsServerAdministrator:** メンバーは、管理、監視、およびビジネス サーバーの Skype を実行しているすべてのサーバーのトラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6fa10-125">**CsServerAdministrator:** Members can manage, monitor, and troubleshoot all servers running Skype for Business Server.</span></span>
    
- <span data-ttu-id="6fa10-126">**CsUserAdministrator:** メンバーは、ユーザーの管理、有効化および無効化、ユーザーへの既存ポリシーの割り当てを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6fa10-126">**CsUserAdministrator:** Members can manage, enable and disable users, and assign existing policies to users.</span></span>
    
- <span data-ttu-id="6fa10-127">**CsViewOnlyAdministrator:** メンバーには、展開と構成のサーバーの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="6fa10-127">**CsViewOnlyAdministrator:** Members can view the deployment and configuration of the server information.</span></span> <span data-ttu-id="6fa10-128">このメンバーシップは、ビジネス サーバー 2015 の Skype を実行しているサーバーの稼働状態を監視するにはメンバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="6fa10-128">This membership enables a member to monitor the health of the servers running Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="6fa10-129">**CsVoiceAdministrator:** メンバーは、作成、構成、およびビジネス サーバーの Skype での音声関連の設定を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="6fa10-129">**CsVoiceAdministrator:** Members can create, configure, and manage voice-related settings in Skype for Business Server.</span></span>
    
<span data-ttu-id="6fa10-130">セキュリティとロール ベースのアクセス制御の整合性を確保するため、ユーザーがビジネス サーバー配置の Skype の管理を実行するどのような役割を定義するグループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="6fa10-130">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span>
  


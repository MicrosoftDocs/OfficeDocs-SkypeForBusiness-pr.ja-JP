---
title: 作成会議の Skype ビジネス サーバーの構成設定
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: '概要: 作成する方法を説明する Skype ビジネス サーバーの構成設定に対応します。'
ms.openlocfilehash: c154661e5e8b974e4a475c935b40749776e0499c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222801"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="2a7d4-103">作成会議の Skype ビジネス サーバーの構成設定</span><span class="sxs-lookup"><span data-stu-id="2a7d4-103">Create meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="2a7d4-104">**の概要:** 作成する方法を学習 Skype ビジネス サーバーの構成設定に対応します。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-104">**Summary:** Learn how to create meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="2a7d4-105">作成することができます Skype ビジネス サーバーのコントロール パネルを使用するか、Skype ビジネス サーバー管理シェルを使用して会議の構成設定。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-105">You can create meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="2a7d4-106">作成ビジネス サーバーのコントロール パネルの Skype を使用して、会議の構成設定</span><span class="sxs-lookup"><span data-stu-id="2a7d4-106">Create meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="2a7d4-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="2a7d4-108">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="2a7d4-109">左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="2a7d4-110">[**会議の構成**] ページで、[**新規作成**] をクリックし、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-110">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
    - <span data-ttu-id="2a7d4-p101">サイト レベルのポリシーを作成するには、[**サイト構成**] をクリックします。[**サイトの選択**] 検索フィールドに、会議参加設定を定義するサイトの名前の全体または一部を入力します。サイトの結果一覧で対象のサイトをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-p101">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
    - <span data-ttu-id="2a7d4-p102">プール レベルのポリシーを作成するには、[**プール構成**] をクリックします。[**サービスの選択**] 検索フィールドに、会議参加設定を定義するプール サービスの名前の全体または一部を入力します。サービスの結果一覧で、対象のプールをクリックして [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-p102">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="2a7d4-p103">公衆交換電話網 (PSTN) からダイヤルインする参加者をロビーを介してルーティングするには、[**PSTN 発信者はロビーをバイパスする**] チェック ボックスをオフにします。既定では、PSTN からダイヤルインした参加者は会議に直接移動します。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-p103">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>
    
6. <span data-ttu-id="2a7d4-119">会議の発表者になることができるユーザーを構成するには、[**発表者として指定**] で、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-119">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
   - <span data-ttu-id="2a7d4-120">開催者以外のユーザーが発表者になることを許可しない場合は、[**なし**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-120">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
   - <span data-ttu-id="2a7d4-p104">組織のメンバーになっている参加者にのみ発表者になることを許可する場合は、[**会社**] をクリックします。これは既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-p104">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
   - <span data-ttu-id="2a7d4-123">参加者すべてに発表者になることを許可する場合は、[**全員**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-123">To allow any participants to be a presenter, click **Everyone**.</span></span>
    
7. <span data-ttu-id="2a7d4-p105">開催者が会議のスケジュール時に会議の種類を選択できるようにするには、[**既定で割り当てられた会議の種類**] チェック ボックスをオフにします。既定では、会議の種類が自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-p105">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>
    
8. <span data-ttu-id="2a7d4-p106">匿名 (未認証) ユーザーが自動的に承認されないようにするには、[**既定で匿名ユーザーを承認する**] チェック ボックスをオフにします。既定では、匿名ユーザーは会議に対して自動的に承認されます。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-p106">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>
    
9. <span data-ttu-id="2a7d4-128">参加者に送られる会議の招待をカスタマイズするには、以下を行います。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-128">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="2a7d4-129">URL およびカスタム フッター テキストの長さは最大 1 KB です。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-129">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="2a7d4-130">[**ヘルプ URL**] 以外は、カスタムの値を指定しない場合、会議に含まれません。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-130">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="2a7d4-131">カスタム ヘルプの URL を指定しないと、ビジネスの Skype の既定のヘルプの URL 部分は招待状になります。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-131">If you do not include a custom help URL, the default help URL for Skype for Business will be displayed in the invite.</span></span> 
    
   - <span data-ttu-id="2a7d4-p108">会議の招待に表示されるロゴをカスタマイズするには、[**ロゴ URL**] にロゴの場所を入力します。ロゴは、サイズが 188 x 30 ピクセルの GIF または JPG 画像である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-p108">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo. The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span> 
    
   - <span data-ttu-id="2a7d4-134">会議招待に表示されるヘルプ テキストをカスタマイズするには、[**ヘルプ URL**] にヘルプ テキストの場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-134">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
   - <span data-ttu-id="2a7d4-135">会議の招待に表示される法的情報をカスタマイズするには、[**リーガル テキスト URL**] にリーガル テキストの場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-135">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
   - <span data-ttu-id="2a7d4-136">会議の招待に表示されるカスタム フッター テキストをカスタマイズするには、[**カスタム フッターのテキスト**] にテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-136">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>
    
10. <span data-ttu-id="2a7d4-137">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-137">Click **Commit**.</span></span>
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="2a7d4-138">作成ビジネス サーバー管理シェルの Skype を使用して、会議の構成設定</span><span class="sxs-lookup"><span data-stu-id="2a7d4-138">Create meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="2a7d4-139">会議の構成設定を作成するには、**New-CsMeetingConfiguration** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-139">To create meeting configuration settings, use the **New-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="2a7d4-140">次のコマンドは、Redmond サイト用に会議構成設定の新しいセットを作成しています。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-140">The following command creates a new set of meeting configuration settings for the Redmond site:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="2a7d4-141">上記のコマンドでは必須の Identity パラメーター以外のパラメーターは指定されていないため、新しい会議構成設定はすべてのプロパティについて既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-141">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>
  
<span data-ttu-id="2a7d4-p109">異なるプロパティ値を使用する設定を作成するには、適切なパラメーターとパラメーター値を指定します。たとえば、会議の全員が発表者となることを既定で許可する会議構成設定のセットを作成するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-p109">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="2a7d4-p110">複数のパラメーターを含めることにより複数のプロパティ値を設定できます。たとえば、次のコマンドは、会議の全員が発表者となることを許可し、さらに PSTN ユーザーは会議に対して正式に承認されるまで必ずロビーで待機するように設定しています。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-p110">Multiple property values can be set by including multiple parameters. For example, the following command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

<span data-ttu-id="2a7d4-146">パラメーターの完全な一覧を含む詳細については、[新規 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a7d4-146">For more information, including a complete list of parameters, see [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span></span>
  


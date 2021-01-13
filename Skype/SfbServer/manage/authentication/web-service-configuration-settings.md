---
title: Skype for Business Server での Web サービス構成設定の管理
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
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: '概要: Skype for Business Server で Web サービス構成設定を管理します。'
ms.openlocfilehash: 68abe01614902d5e6f4c58040b30b6afbd475df8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806497"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="6cc20-103">Skype for Business Server での Web サービス構成設定の管理</span><span class="sxs-lookup"><span data-stu-id="6cc20-103">Manage Web Service configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="6cc20-104">**概要:** Skype for Business Server で Web サービス構成設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="6cc20-104">**Summary:** Manage Web Service configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="6cc20-105">[Web サービス] **ページを使用** して、Skype for Business Server 関連の Web サーバーおよび Web サービスにアクセスする認証方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="6cc20-105">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="6cc20-106">以下の手順に従って新しい Web サービス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6cc20-106">Follow these steps to create a new Web Service policy.</span></span>
  
### <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="6cc20-107">新しい Web サービス構成設定を作成するには</span><span class="sxs-lookup"><span data-stu-id="6cc20-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="6cc20-108">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6cc20-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="6cc20-109">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6cc20-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="6cc20-110">左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**Web サービス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cc20-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="6cc20-111">[**Web サービス**] ページで、[**新規作成**] をクリックし、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="6cc20-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="6cc20-p101">サイトの Web サービスを構成するには、[**サイト構成**] をクリックします。 [**サイトの選択**] で、Web サービス ポリシーを適用するサイトをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cc20-p101">To configure the Web Service for a site, click **Site configuration**. In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
   - <span data-ttu-id="6cc20-p102">プールの Web サービスを構成するには、[**プール構成**] をクリックします。 [**サービスの選択**] で、Web サービス ポリシーを適用するサービスをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cc20-p102">To configure the Web Service for a pool, click **Pool configuration**. In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span> 
    
5. <span data-ttu-id="6cc20-116">[**新規 Web サービス設定**] の [**統合 Windows 認証**] で、[**ネゴシエート**]、[**統合 Windows 認証**]、または [**なし**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cc20-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="6cc20-117">クライアントの機能および環境のサポート状況に応じて、次の中から 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="6cc20-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="6cc20-118">[**PIN 認証を有効にする**]。PIN 番号を使用してクライアントが承認されるようにします。</span><span class="sxs-lookup"><span data-stu-id="6cc20-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="6cc20-119">[**証明書認証を有効にする**]。プール内のサーバーは、クライアントに対して証明書を発行します。</span><span class="sxs-lookup"><span data-stu-id="6cc20-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="6cc20-120">[**証明書チェーンのダウンロードを有効にする**]。認証証明書を与えられたサーバーがその証明書の証明書チェーンをダウンロードできるようにします。</span><span class="sxs-lookup"><span data-stu-id="6cc20-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="6cc20-121">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cc20-121">Click **Commit**.</span></span>
    
## <a name="modify-existing-web-service-configuration-settings"></a><span data-ttu-id="6cc20-122">既存の Web サービス構成設定を変更する</span><span class="sxs-lookup"><span data-stu-id="6cc20-122">Modify existing Web Service configuration settings</span></span>

<span data-ttu-id="6cc20-123">[Web サービス] **ページを使用** して、Skype for Business Server 関連の Web サーバーおよび Web サービスにアクセスする認証方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="6cc20-123">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="6cc20-124">既存の Web サービス ポリシーを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6cc20-124">Follow these steps to modify an existing Web Service policy.</span></span>
  
### <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="6cc20-125">既存の Web サービス構成設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="6cc20-125">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="6cc20-126">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6cc20-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="6cc20-127">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6cc20-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="6cc20-128">左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**Web サービス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cc20-128">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="6cc20-129">[**Web サービス**] ページで、構成をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cc20-129">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="6cc20-130">[**Web サービス設定の編集**] の [**Windows 認証**] で、[**ネゴシエート**]、[**統合 Windows 認証**]、または [**なし**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cc20-130">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="6cc20-131">クライアントの機能および環境のサポート状況に応じて、次の中から 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="6cc20-131">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="6cc20-132">[**PIN 認証を有効にする**]。PIN 番号を使用してクライアントが承認されるようにします。</span><span class="sxs-lookup"><span data-stu-id="6cc20-132">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="6cc20-133">[**証明書認証を有効にする**]。プール内のサーバーは、クライアントに対して証明書を発行します。</span><span class="sxs-lookup"><span data-stu-id="6cc20-133">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="6cc20-134">[**証明書チェーンのダウンロードを有効にする**]。認証証明書を与えられたサーバーがその証明書の証明書チェーンをダウンロードできるようにします。</span><span class="sxs-lookup"><span data-stu-id="6cc20-134">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="6cc20-135">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cc20-135">Click **Commit**.</span></span>
    
## <a name="delete-existing-web-service-configuration-settings"></a><span data-ttu-id="6cc20-136">既存の Web サービス構成設定を削除する</span><span class="sxs-lookup"><span data-stu-id="6cc20-136">Delete existing Web Service configuration settings</span></span>

<span data-ttu-id="6cc20-137">Web サービス構成設定を削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6cc20-137">Follow these steps to delete web service configuration settings.</span></span>
  
### <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="6cc20-138">Web サービス構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="6cc20-138">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="6cc20-139">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6cc20-139">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="6cc20-140">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6cc20-140">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="6cc20-141">左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**Web サービス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cc20-141">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="6cc20-142">[**Web サービス**] ページの検索フィールドに、削除するポリシーの名前または名前の一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="6cc20-142">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="6cc20-143">ポリシーのリストで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cc20-143">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="6cc20-144">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cc20-144">Click **OK**.</span></span>
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6cc20-145">コマンドレットを使用した Web サービス構成設定Windows PowerShell削除する</span><span class="sxs-lookup"><span data-stu-id="6cc20-145">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6cc20-146">Web サービス構成設定を削除するには、Windows PowerShell **Remove-CsWebServiceConfiguration コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="6cc20-146">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="6cc20-147">このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="6cc20-147">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6cc20-148">リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cc20-148">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="6cc20-149">このプロセスは、Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="6cc20-149">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="6cc20-150">Web サービス構成設定の特定のコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="6cc20-150">To delete a specific collection of web service configuration settings</span></span>

- <span data-ttu-id="6cc20-151">次のコマンドを実行すると、レドモンド サイトに適用されている Web サービス セキュリティ設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="6cc20-151">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="6cc20-152">サイト スコープに適用されている Web サービス構成設定をすべて削除するには</span><span class="sxs-lookup"><span data-stu-id="6cc20-152">To delete all of the web service configuration settings applied to the site scope</span></span>

<span data-ttu-id="6cc20-153">次のコマンドを実行すると、サービス スコープに適用されているすべての Web サービス セキュリティ設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="6cc20-153">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="6cc20-154">証明書認証を許可する Web サービス構成設定をすべて削除するには</span><span class="sxs-lookup"><span data-stu-id="6cc20-154">To delete all of the web service configuration settings that allow certificate authentication</span></span>

<span data-ttu-id="6cc20-155">次のコマンドを実行すると、証明書認証の使用を許可しているすべての Web サービス セキュリティ設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="6cc20-155">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

<span data-ttu-id="6cc20-156">詳細については [、「Remove-CsWebServiceConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="6cc20-156">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span></span>
  


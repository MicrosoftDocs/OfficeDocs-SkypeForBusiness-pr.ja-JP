---
title: Skype for Business 2015 での Web サービス構成設定の管理
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: '概要: ビジネス サーバー 2015 の Skype での Web サービス構成の設定を管理します。'
ms.openlocfilehash: a0976728ecd09392408fb719861681e0465d7bed
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="14fdb-103">Skype for Business 2015 での Web サービス構成設定の管理</span><span class="sxs-lookup"><span data-stu-id="14fdb-103">Manage Web Service configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="14fdb-104">**の概要:**ビジネス サーバー 2015 の Skype での Web サービス構成の設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="14fdb-104">**Summary:** Manage Web Service configuration settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="14fdb-105">2015 関連の web サーバーと Web サービスの Skype へのアクセスの認証方法を構成するのには、 **Web サービス**のページを使用できます。</span><span class="sxs-lookup"><span data-stu-id="14fdb-105">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server 2015 related web servers and Web Services.</span></span>
  
<span data-ttu-id="14fdb-106">以下の手順に従って新しい Web サービス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="14fdb-106">Follow these steps to create a new Web Service policy.</span></span>
  
### <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="14fdb-107">新しい Web サービス構成設定を作成するには</span><span class="sxs-lookup"><span data-stu-id="14fdb-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="14fdb-108">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは2015。</span><span class="sxs-lookup"><span data-stu-id="14fdb-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="14fdb-109">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="14fdb-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="14fdb-110">左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**Web サービス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14fdb-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="14fdb-111">[**Web サービス**] ページで、[**新規作成**] をクリックし、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="14fdb-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="14fdb-p101">サイトの Web サービスを構成するには、[**サイト構成**] をクリックします。[**サイトの選択**] で、Web サービス ポリシーを適用するサイトをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14fdb-p101">To configure the Web Service for a site, click **Site configuration**. In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
   - <span data-ttu-id="14fdb-p102">プールの Web サービスを構成するには、[**プール構成**] をクリックします。[**サービスの選択**] で、Web サービス ポリシーを適用するサービスをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14fdb-p102">To configure the Web Service for a pool, click **Pool configuration**. In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span> 
    
5. <span data-ttu-id="14fdb-116">[**新規 Web サービス設定**] の [**統合 Windows 認証**] で、[**ネゴシエート**]、[**統合 Windows 認証**]、または [**なし**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14fdb-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="14fdb-117">クライアントの機能および環境のサポート状況に応じて、次の中から 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="14fdb-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="14fdb-118">[**PIN 認証を有効にする**]。PIN 番号を使用してクライアントが承認されるようにします。</span><span class="sxs-lookup"><span data-stu-id="14fdb-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="14fdb-119">[**証明書認証を有効にする**]。プール内のサーバーは、クライアントに対して証明書を発行します。</span><span class="sxs-lookup"><span data-stu-id="14fdb-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="14fdb-120">[**証明書チェーンのダウンロードを有効にする**]。認証証明書を与えられたサーバーがその証明書の証明書チェーンをダウンロードできるようにします。</span><span class="sxs-lookup"><span data-stu-id="14fdb-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="14fdb-121">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14fdb-121">Click **Commit**.</span></span>
    
## <a name="modify-existing-web-service-configuration-settings"></a><span data-ttu-id="14fdb-122">既存の Web サービス構成設定を変更する</span><span class="sxs-lookup"><span data-stu-id="14fdb-122">Modify existing Web Service configuration settings</span></span>

<span data-ttu-id="14fdb-123">2015 関連の web サーバーと Web サービスの Skype へのアクセスの認証方法を構成するのには、 **Web サービス**のページを使用できます。</span><span class="sxs-lookup"><span data-stu-id="14fdb-123">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server 2015 related web servers and Web Services.</span></span>
  
<span data-ttu-id="14fdb-124">既存の Web サービス ポリシーを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="14fdb-124">Follow these steps to modify an existing Web Service policy.</span></span>
  
### <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="14fdb-125">既存の Web サービス構成設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="14fdb-125">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="14fdb-126">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは2015。</span><span class="sxs-lookup"><span data-stu-id="14fdb-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="14fdb-127">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="14fdb-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="14fdb-128">左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**Web サービス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14fdb-128">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="14fdb-129">[**Web サービス**] ページで、構成をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14fdb-129">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="14fdb-130">[**Web サービス設定の編集**] の [**統合 Windows 認証**] で、[**ネゴシエート**]、[**統合 Windows 認証**]、または [**なし**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14fdb-130">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="14fdb-131">クライアントの機能および環境のサポート状況に応じて、次の中から 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="14fdb-131">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="14fdb-132">[**PIN 認証を有効にする**]。PIN 番号を使用してクライアントが承認されるようにします。</span><span class="sxs-lookup"><span data-stu-id="14fdb-132">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="14fdb-133">[**証明書認証を有効にする**]。プール内のサーバーは、クライアントに対して証明書を発行します。</span><span class="sxs-lookup"><span data-stu-id="14fdb-133">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="14fdb-134">[**証明書チェーンのダウンロードを有効にする**]。認証証明書を与えられたサーバーがその証明書の証明書チェーンをダウンロードできるようにします。</span><span class="sxs-lookup"><span data-stu-id="14fdb-134">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="14fdb-135">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14fdb-135">Click **Commit**.</span></span>
    
## <a name="delete-existing-web-service-configuration-settings"></a><span data-ttu-id="14fdb-136">既存の Web サービス構成設定を削除する</span><span class="sxs-lookup"><span data-stu-id="14fdb-136">Delete existing Web Service configuration settings</span></span>

<span data-ttu-id="14fdb-137">Web サービス構成設定を削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="14fdb-137">Follow these steps to delete web service configuration settings.</span></span>
  
### <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="14fdb-138">Web サービス構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="14fdb-138">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="14fdb-139">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは2015。</span><span class="sxs-lookup"><span data-stu-id="14fdb-139">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="14fdb-140">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="14fdb-140">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="14fdb-141">左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**Web サービス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14fdb-141">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="14fdb-142">[**Web サービス**] ページの検索フィールドに、削除するポリシーの名前の全体または一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="14fdb-142">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="14fdb-143">ポリシーのリストで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14fdb-143">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="14fdb-144">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14fdb-144">Click **OK**.</span></span>
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="14fdb-145">Windows PowerShell コマンドレットを使用して Web サービスの構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="14fdb-145">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="14fdb-146">Windows PowerShell と**削除 CsWebServiceConfiguration**コマンドレットを使用して web サービスの構成設定を削除できます。</span><span class="sxs-lookup"><span data-stu-id="14fdb-146">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="14fdb-147">ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="14fdb-147">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="14fdb-148">ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14fdb-148">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="14fdb-149">プロセスは、Skype のビジネス サーバーで同じです。</span><span class="sxs-lookup"><span data-stu-id="14fdb-149">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="14fdb-150">Web サービス構成設定の特定のコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="14fdb-150">To delete a specific collection of web service configuration settings</span></span>

- <span data-ttu-id="14fdb-151">次のコマンドを実行すると、レドモンド サイトに適用されている Web サービス セキュリティ設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="14fdb-151">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="14fdb-152">サイト スコープに適用されているすべての Web サービス構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="14fdb-152">To delete all of the web service configuration settings applied to the site scope</span></span>

<span data-ttu-id="14fdb-153">次のコマンドを実行すると、サービス スコープに適用されているすべての Web サービス セキュリティ設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="14fdb-153">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
  ```
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="14fdb-154">証明書認証を許可しているすべての Web サービス構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="14fdb-154">To delete all of the web service configuration settings that allow certificate authentication</span></span>

<span data-ttu-id="14fdb-155">次のコマンドを実行すると、証明書認証の使用を許可しているすべての Web サービス セキュリティ設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="14fdb-155">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
  ```
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

<span data-ttu-id="14fdb-156">詳細については、[削除 CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14fdb-156">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span></span>
  


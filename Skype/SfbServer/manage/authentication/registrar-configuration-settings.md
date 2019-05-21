---
title: Skype for Business Server でレジストラー構成設定を管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: '概要: Skype for Business Server のレジストラー構成設定を管理します。'
ms.openlocfilehash: 4ad7815da0744a78cd72208ef390362bff26c2ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291173"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="bb1f5-103">Skype for Business Server でレジストラー構成設定を管理する</span><span class="sxs-lookup"><span data-stu-id="bb1f5-103">Manage Registrar configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="bb1f5-104">**概要:** Skype for Business Server のレジストラー構成設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-104">**Summary:** Manage Registrar configuration settings for Skype for Business Server.</span></span>
  
<span data-ttu-id="bb1f5-p101">レジストラーを使用してプロキシ サーバーの認証方式を構成できます。指定する認証プロトコルにより、プール内のサーバーがクライアントに発行するチャレンジの種類が決まります。使用可能なプロトコルは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-p101">You can use the Registrar to configure proxy server authentication methods. The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients. The available protocols are:</span></span>
  
- <span data-ttu-id="bb1f5-108">**Kerberos**これは、クライアントが利用できる最強のパスワードベースの認証スキームですが、通常はエンタープライズクライアントでのみ利用できます。これは、キー配布センター (Kerberos ドメインコントローラー) へのクライアント接続が必要であるためです。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-108">**Kerberos** This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="bb1f5-109">この設定は、サーバーでエンタープライズのクライアントのみを認証する場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-109">This setting is appropriate if the server authenticates only enterprise clients.</span></span>
    
- <span data-ttu-id="bb1f5-110">**NTLM**これはパスワードベースの認証であり、パスワードに関するチャレンジ応答ハッシュスキームを使用するクライアントで利用できます。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-110">**NTLM** This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="bb1f5-111">これは、リモート ユーザーなど、キー配布センター (Kerberos ドメイン コントローラー) に接続できないクライアントの認証で使用できる唯一のクライアント認証方式です。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-111">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="bb1f5-112">サーバーでリモート ユーザーのみの認証処理を行う場合は、NTLM を選択してください。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-112">If a server authenticates only remote users, you should choose NTLM.</span></span>
    
- <span data-ttu-id="bb1f5-113">**証明書の認証**これは、サーバーが Lync Phone Edition クライアント、一般的なエリア電話、Skype for Business、Lync Windows ストアアプリから証明書を取得する必要がある場合の新しい認証方法です。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-113">**Certificate authentication** This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Skype for Business and the Lync Windows Store app.</span></span> <span data-ttu-id="bb1f5-114">Lync Phone Edition クライアントでは、ユーザーがサインインし、暗証番号 (PIN) を指定して認証に成功した後、Skype for Business Server は電話に対して SIP URI をプロビジョニングし、Skype for Business Server を署名します。証明書または Joe (Ex: SN=joe@contoso.com) を電話に識別するユーザー証明書。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-114">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Skype for Business Server then provisions the SIP URI to the phone and provisions a Skype for Business Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="bb1f5-115">この証明書は、レジストラー サービスと Web サービスでの認証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-115">This certificate is used for authenticating with the Registrar and Web Services.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bb1f5-p105">サーバーがリモートとエンタープライズ両方のクライアント認証をサポートする場合は、Kerberos と NTLM の両方を有効にすることをお勧めします。エッジ サーバーと内部サーバーは通信して、NTLM 認証のみがリモート クライアントに提供されるようにします。これらのサーバーで Kerberos のみが有効な場合、リモート ユーザーを認証できません。エンタープライズ ユーザーはサーバーに対しても認証を行い、Kerberos が使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-p105">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="bb1f5-120">Lync Windows ストアアプリクライアントを使用する場合は、証明書の認証を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-120">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>
  
### <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="bb1f5-121">レジストラー構成設定を作成するには</span><span class="sxs-lookup"><span data-stu-id="bb1f5-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="bb1f5-122">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.</span><span class="sxs-lookup"><span data-stu-id="bb1f5-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="bb1f5-123">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="bb1f5-124">左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**レジストラー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-124">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="bb1f5-125">[**レジストラー**] ページで [**新規作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-125">On the **Registrar** page, click **New**</span></span>
    
5. <span data-ttu-id="bb1f5-126">[**サービスの選択**] で、レジストラーを適用するサービスをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-126">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>
    
6. <span data-ttu-id="bb1f5-127">[**新規レジストラー設定**] で、クライアントの機能および環境のサポート状況に応じて、次の中から 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-127">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="bb1f5-128">[**Kerberos 認証を有効にする**]。プール内のサーバーは、Kerberos 認証を使用してチャレンジを発行します。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-128">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="bb1f5-129">[**NTLM 認証を有効にする**]。プール内のサーバーは、NTLM 認証を使用してチャレンジを発行します。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-129">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="bb1f5-130">[**証明書認証を有効にする**]。プール内のサーバーは、クライアントに対して証明書を発行します。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-130">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
7. <span data-ttu-id="bb1f5-131">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-131">Click **Commit**.</span></span>
    
## <a name="modify-existing-registrar-configuration-settings"></a><span data-ttu-id="bb1f5-132">既存のレジストラー構成設定を変更する</span><span class="sxs-lookup"><span data-stu-id="bb1f5-132">Modify existing Registrar configuration settings</span></span>

<span data-ttu-id="bb1f5-133">レジストラーを使用して、プロキシ サーバーの認証プロトコルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-133">You can use the Registrar to configure proxy server authentication protocols.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bb1f5-p106">サーバーがリモートとエンタープライズ両方のクライアント認証をサポートする場合は、Kerberos と NTLM の両方を有効にすることをお勧めします。エッジ サーバーと内部サーバーは通信して、NTLM 認証のみがリモート クライアントに提供されるようにします。これらのサーバーで Kerberos のみが有効な場合、リモート ユーザーを認証できません。エンタープライズ ユーザーはサーバーに対しても認証を行い、Kerberos が使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-p106">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="bb1f5-138">既存のレジストラーを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-138">Follow these steps to modify an existing Registrar.</span></span> 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="bb1f5-139">既存のレジストラー構成設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="bb1f5-139">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="bb1f5-140">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.</span><span class="sxs-lookup"><span data-stu-id="bb1f5-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="bb1f5-141">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="bb1f5-142">左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**レジストラー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-142">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="bb1f5-143">[**レジストラー**] ページでサービスをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-143">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="bb1f5-144">[**レジストラー設定の編集**] で、クライアントの機能や環境内のサポートに合わせて、次のうち 1 つまたは複数を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-144">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="bb1f5-145">[**Kerberos 認証を有効にする**]。プール内のサーバーは、Kerberos 認証を使用してチャレンジを発行します。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-145">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="bb1f5-146">[**NTLM 認証を有効にする**]。プール内のサーバーは、NTLM 認証を使用してチャレンジを発行します。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-146">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="bb1f5-147">[**証明書認証を有効にする**]。プール内のサーバーは、クライアントに対して証明書を発行します。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-147">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
6. <span data-ttu-id="bb1f5-148">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-148">Click **Commit**.</span></span>
    
### <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="bb1f5-149">レジストラー構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="bb1f5-149">To delete Registrar configuration settings</span></span>

1. <span data-ttu-id="bb1f5-150">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.</span><span class="sxs-lookup"><span data-stu-id="bb1f5-150">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="bb1f5-151">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-151">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="bb1f5-152">左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**レジストラー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-152">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="bb1f5-153">[**レジストラー**] ページの検索フィールドに、削除するレジストラーの名前の全体または一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-153">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>
    
5. <span data-ttu-id="bb1f5-154">一覧で、対象のレジストラーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-154">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="bb1f5-155">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-155">Click **OK**.</span></span>
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bb1f5-156">Windows PowerShell コマンドレットを使用してレジストラー構成設定を削除する</span><span class="sxs-lookup"><span data-stu-id="bb1f5-156">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bb1f5-157">レジストラーの構成設定は、Windows PowerShell と**CsProxyConfiguration**コマンドレットを使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-157">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="bb1f5-158">このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-158">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bb1f5-159">リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-159">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="bb1f5-160">このプロセスは、Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-160">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="bb1f5-161">レジストラーのセキュリティ設定の特定のセットを削除するには</span><span class="sxs-lookup"><span data-stu-id="bb1f5-161">To remove a specific set of Registrar security settings</span></span>

- <span data-ttu-id="bb1f5-162">次のコマンドは、エッジ サーバー atl-edge-011.litwareinc.com に適用されるレジストラーのセキュリティ設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-162">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
  ```
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="bb1f5-163">サイト スコープに適用されるレジストラーのセキュリティ設定をすべて削除するには</span><span class="sxs-lookup"><span data-stu-id="bb1f5-163">To remove all of the Registrar security settings applied to the site scope</span></span>

- <span data-ttu-id="bb1f5-164">次のコマンドは、レジストラー サービスに適用されるすべてのレジストラーのセキュリティ設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-164">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
  ```
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="bb1f5-165">NTLM 認証を許可するレジストラーのセキュリティ設定をすべて削除するには</span><span class="sxs-lookup"><span data-stu-id="bb1f5-165">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

- <span data-ttu-id="bb1f5-166">次のコマンドは、クライアント認証に NTLM の使用を許可するレジストラーのセキュリティ設定をすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-166">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
  ```
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

<span data-ttu-id="bb1f5-167">詳しくは、「 [CsProxyConfiguration の削除](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bb1f5-167">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span></span>
  


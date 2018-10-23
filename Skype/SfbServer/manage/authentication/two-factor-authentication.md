---
title: Skype のビジネス サーバーの 2 要素による認証を管理します。
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: '概要: は、Skype のビジネス サーバーの 2 要素による認証を管理します。'
ms.openlocfilehash: a9ebeaa5f8f012d66fb62357e8378010d0a74865
ms.sourcegitcommit: 6251a2c659909c3972ca2ea0a2bcdab4f334df34
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2018
ms.locfileid: "25692741"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="0b828-103">Skype のビジネス サーバーの 2 要素による認証を管理します。</span><span class="sxs-lookup"><span data-stu-id="0b828-103">Manage two-factor authentication in Skype for Business Server</span></span>
 
<span data-ttu-id="0b828-104">**の概要:** Skype のビジネス サーバーの 2 要素による認証を管理します。</span><span class="sxs-lookup"><span data-stu-id="0b828-104">**Summary:** Manage two-factor authentication in Skype for Business Server.</span></span>
  
<span data-ttu-id="0b828-105">2 要素認証では、ユーザーが 2 つの形式の認証情報または識別情報、つまりユーザー名/パスワードの組み合わせと、トークンまたは証明書を提示する必要があるため、セキュリティが強化されます。</span><span class="sxs-lookup"><span data-stu-id="0b828-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="0b828-106">これとも呼ばれるものがある場合、知っていること。</span><span class="sxs-lookup"><span data-stu-id="0b828-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="0b828-p102">証明書を使用した 2 要素認証の一般的な例として、スマート カードの使用があります。スマート カードにはユーザー アカウントに関連付けられている証明書が格納されていて、サーバーに格納されているユーザー情報と証明書情報に対する検証を行うことができます。ユーザー情報 (ユーザー名とパスワード) と提供された証明書を比較することで、サーバーでは資格情報を検証し、ユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="0b828-p102">A typical example of two-factor authentication with a certificate is the use of smart cards. A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server. By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="0b828-110">2 要素認証をサポートするには、ビジネスのサーバー環境に Skype を設定するときは、次の項目を検討してください。</span><span class="sxs-lookup"><span data-stu-id="0b828-110">Consider the following subjects when configuring a Skype for Business Server environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="0b828-111">クライアント サポート</span><span class="sxs-lookup"><span data-stu-id="0b828-111">Client Support</span></span>

<span data-ttu-id="0b828-112">Lync Server 2013 の累積的な更新: 2013年 7 月デスクトップ クライアントおよびビジネス クライアント用の Skype は、2 要素認証がサポートされているクライアントのみです。</span><span class="sxs-lookup"><span data-stu-id="0b828-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="0b828-113">トポロジ要件</span><span class="sxs-lookup"><span data-stu-id="0b828-113">Topology Requirements</span></span>

<span data-ttu-id="0b828-114">お客様は、ビジネスのサーバーのエッジ、ディレクター、およびユーザーのプールと専用の Skype を使用して 2 段階認証を導入するよう強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0b828-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server with Edge, Director, and User Pools.</span></span> <span data-ttu-id="0b828-115">ユーザーに対してパッシブ認証を有効にするには、次に示すように、他の役割およびサービスに対してその他の認証方法を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b828-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="0b828-116">**構成の種類**</span><span class="sxs-lookup"><span data-stu-id="0b828-116">**Configuration Type**</span></span>|<span data-ttu-id="0b828-117">**サービスの種類**</span><span class="sxs-lookup"><span data-stu-id="0b828-117">**Service Type**</span></span>|<span data-ttu-id="0b828-118">**サーバーの役割**</span><span class="sxs-lookup"><span data-stu-id="0b828-118">**Server Role**</span></span>|<span data-ttu-id="0b828-119">**無効にする認証の種類**</span><span class="sxs-lookup"><span data-stu-id="0b828-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0b828-120">Web サービス</span><span class="sxs-lookup"><span data-stu-id="0b828-120">Web Service</span></span>  <br/> |<span data-ttu-id="0b828-121">WebServer</span><span class="sxs-lookup"><span data-stu-id="0b828-121">WebServer</span></span>  <br/> |<span data-ttu-id="0b828-122">ディレクター</span><span class="sxs-lookup"><span data-stu-id="0b828-122">Director</span></span>  <br/> |<span data-ttu-id="0b828-123">Kerberos、NTLM、証明書</span><span class="sxs-lookup"><span data-stu-id="0b828-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="0b828-124">Web サービス</span><span class="sxs-lookup"><span data-stu-id="0b828-124">Web Service</span></span>  <br/> |<span data-ttu-id="0b828-125">WebServer</span><span class="sxs-lookup"><span data-stu-id="0b828-125">WebServer</span></span>  <br/> |<span data-ttu-id="0b828-126">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="0b828-126">Front End</span></span>  <br/> |<span data-ttu-id="0b828-127">Kerberos、NTLM、証明書</span><span class="sxs-lookup"><span data-stu-id="0b828-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="0b828-128">プロキシ</span><span class="sxs-lookup"><span data-stu-id="0b828-128">Proxy</span></span>  <br/> |<span data-ttu-id="0b828-129">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="0b828-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="0b828-130">Edge</span><span class="sxs-lookup"><span data-stu-id="0b828-130">Edge</span></span>  <br/> |<span data-ttu-id="0b828-131">Kerberos および NTLM</span><span class="sxs-lookup"><span data-stu-id="0b828-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="0b828-132">プロキシ</span><span class="sxs-lookup"><span data-stu-id="0b828-132">Proxy</span></span>  <br/> |<span data-ttu-id="0b828-133">レジストラー</span><span class="sxs-lookup"><span data-stu-id="0b828-133">Registrar</span></span>  <br/> |<span data-ttu-id="0b828-134">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="0b828-134">Front End</span></span>  <br/> |<span data-ttu-id="0b828-135">Kerberos および NTLM</span><span class="sxs-lookup"><span data-stu-id="0b828-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="0b828-136">これらの認証の種類がサービス レベルで無効になっていない限り、2 要素認証が展開内で有効になっても、他のすべてのバージョンのクライアントでは正常にサインインできません。</span><span class="sxs-lookup"><span data-stu-id="0b828-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="0b828-137">Skype for Business サービスの検出</span><span class="sxs-lookup"><span data-stu-id="0b828-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="0b828-138">Skype の二要素認証を有効になっていないビジネス サーバーを解決するのには、ビジネス ・ サービスの Skype を検出する内部および外部のクライアントによって使用される DNS レコードを構成してください。</span><span class="sxs-lookup"><span data-stu-id="0b828-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="0b828-139">この構成では、2 要素認証は有効でないビジネス ・ プールの Skype ユーザー必要はありませんビジネス ・ プール 2 要素認証は有効になっている Skype からユーザー間を認証する PIN を入力するのには認証する PIN を入力する必要です。</span><span class="sxs-lookup"><span data-stu-id="0b828-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="0b828-140">Exchange 認証</span><span class="sxs-lookup"><span data-stu-id="0b828-140">Exchange Authentication</span></span>

<span data-ttu-id="0b828-141">Microsoft Exchange 向けの二要素認証を導入しているお客様は、クライアントの特定の機能が使用できないことにあります。</span><span class="sxs-lookup"><span data-stu-id="0b828-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="0b828-142">これは、現在仕様では、ビジネス クライアント用の Skype では Exchange の統合に依存している機能の二要素認証がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0b828-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="0b828-143">連絡先</span><span class="sxs-lookup"><span data-stu-id="0b828-143">Contacts</span></span>

<span data-ttu-id="0b828-144">連絡先が不要になった使用可能な二要素認証を使用してサインインした後に、統合連絡先ストアの機能を活用するように構成されているビジネス ユーザーの Skype が見つかります。</span><span class="sxs-lookup"><span data-stu-id="0b828-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="0b828-145">統合連絡先ストアから既存のユーザーの連絡先を削除し、保存 Skype のビジネス サーバーの 2 要素認証を有効にする前に、**呼び出し CsUcsRollback**コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b828-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="0b828-146">スキル検索</span><span class="sxs-lookup"><span data-stu-id="0b828-146">Skill Search</span></span>

<span data-ttu-id="0b828-147">二要素認証のビジネス用の Skype が有効になっているときに、この機能が動作しないことには、お客様のビジネス環境に、Skype でスキル検索機能を構成しているが見つかります。</span><span class="sxs-lookup"><span data-stu-id="0b828-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="0b828-148">現在、Microsoft SharePoint では 2 要素認証がサポートされていないため、これは仕様です。</span><span class="sxs-lookup"><span data-stu-id="0b828-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="0b828-149">資格情報</span><span class="sxs-lookup"><span data-stu-id="0b828-149">Credentials</span></span>

<span data-ttu-id="0b828-150">2 要素認証を使用するように構成されているユーザーに影響を与えるビジネスの資格情報を保存されている Skype に関連する展開の考慮事項の多くがあります。</span><span class="sxs-lookup"><span data-stu-id="0b828-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="0b828-151">保存された資格情報の削除</span><span class="sxs-lookup"><span data-stu-id="0b828-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="0b828-152">ユーザーが、Skype で**自分のサインイン情報を削除**する] オプションを使用して、ビジネスのクライアントと、SIP プロファイルからフォルダーを削除 %localappdata%\Microsoft\Office\15.0\Skype ビジネスの 2 つの要素を使用して最初にサインインする前にする必要があります。認証します。</span><span class="sxs-lookup"><span data-stu-id="0b828-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="0b828-153">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="0b828-153">DisableNTCredentials</span></span>

<span data-ttu-id="0b828-154">Kerberos または NTLM の認証方法とユーザーの Windows 資格情報を自動的に認証に使用します。</span><span class="sxs-lookup"><span data-stu-id="0b828-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="0b828-155">ビジネス サーバー配置では、Kerberos または NTLM 認証が有効の典型的な Skype、ユーザー必要はありませんにサインインするたびに資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="0b828-155">In a typical Skype for Business Server deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="0b828-156">PIN の入力を求めるメッセージが表示される前に、意図せず資格情報の入力を求められた場合は、クライアント コンピューターで **DisableNTCredentials** レジストリ キーが誤って (おそらくグループ ポリシーを使用して) 構成されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0b828-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="0b828-157">資格情報の追加のプロンプトを避けるためには、ローカル ワークステーションで次のレジストリ エントリを作成または管理用テンプレートをビジネス用の Skype を使用して、グループ ポリシーを使用して特定のプールのすべてのユーザーに適用します。</span><span class="sxs-lookup"><span data-stu-id="0b828-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="0b828-158">SavePassword</span><span class="sxs-lookup"><span data-stu-id="0b828-158">SavePassword</span></span>

<span data-ttu-id="0b828-159">最初に、Skype をビジネスのためにユーザーがサインインすると、ときに、自分のパスワードを保存するのには求められます。</span><span class="sxs-lookup"><span data-stu-id="0b828-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="0b828-160">選択した場合、このオプションでは、ユーザーのクライアントの証明書を個人証明書ストアとローカル コンピューターの資格情報マネージャーに格納するユーザーの Windows の資格情報に格納します。</span><span class="sxs-lookup"><span data-stu-id="0b828-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="0b828-161">2 要素認証をサポートするためにビジネス用の Skype が構成されている場合は、 **SavePassword**レジストリ設定を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b828-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="0b828-162">ユーザーが自分のパスワードを保存することを防ぐ、ローカル ワークステーションで次のレジストリ エントリを変更または管理用テンプレートをビジネス用の Skype を使用して、グループ ポリシーを使用して特定のプールのすべてのユーザーに適用します。</span><span class="sxs-lookup"><span data-stu-id="0b828-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="0b828-163">AD FS 2.0 のトークンのリプレイ</span><span class="sxs-lookup"><span data-stu-id="0b828-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="0b828-p110">AD FS 2.0 には、トークン リプレイ検出と呼ばれる機能が用意されています。この機能によって、同じトークンを使用する複数のトークン要求を検出して破棄できます。この機能が有効な場合は、同じトークンが複数回使用されることがなくなるため、WS-Federation パッシブ プロファイルと SAML WebSSO プロファイルの両方において認証要求の整合性が確保されます。</span><span class="sxs-lookup"><span data-stu-id="0b828-p110">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded. When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="0b828-166">キオスクを使用する場合など、セキュリティが最も重視される状況では、この機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b828-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="0b828-167">トークン リプレイ検出の詳細については、「[Best Practices for Secure Planning and Deployment of AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b828-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="0b828-168">外部ユーザー アクセス</span><span class="sxs-lookup"><span data-stu-id="0b828-168">External User Access</span></span>

<span data-ttu-id="0b828-169">Skype を外部ネットワークからビジネスの 2 要素認証をサポートするには、ad FS プロキシまたはリバース プロキシを構成する」のトピックでは説明しません。</span><span class="sxs-lookup"><span data-stu-id="0b828-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0b828-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b828-170">See also</span></span>

[<span data-ttu-id="0b828-171">Skype のビジネス サーバーの 2 要素認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="0b828-171">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)
  
---
title: Skype for Business Server での 2 要素認証の管理
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
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: '概要: Skype for Business Server で 2 要素認証を管理します。'
ms.openlocfilehash: 8e8f665d824cd5f21cc2ca874668eba90bc97c4b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119546"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="5981a-103">Skype for Business Server での 2 要素認証の管理</span><span class="sxs-lookup"><span data-stu-id="5981a-103">Manage two-factor authentication in Skype for Business Server</span></span>
 
<span data-ttu-id="5981a-104">**概要:** Skype for Business Server で 2 要素認証を管理します。</span><span class="sxs-lookup"><span data-stu-id="5981a-104">**Summary:** Manage two-factor authentication in Skype for Business Server.</span></span>
  
<span data-ttu-id="5981a-105">2 要素認証では、ユーザーに 2 つの形式の認証または ID、ユーザー名/パスワードの組み合わせとトークンまたは証明書を提供する必要が生じ、セキュリティが強化されます。</span><span class="sxs-lookup"><span data-stu-id="5981a-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="5981a-106">これは「持っているもの、知っているもの」とも呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="5981a-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="5981a-107">証明書を使用した 2 要素認証の一般的な例は、スマート カードの使用です。</span><span class="sxs-lookup"><span data-stu-id="5981a-107">A typical example of two-factor authentication with a certificate is the use of smart cards.</span></span> <span data-ttu-id="5981a-108">スマート カードには、ユーザー アカウントに関連付けられた証明書が含まれているので、サーバーに保存されているユーザーと証明書の情報に対して検証できます。</span><span class="sxs-lookup"><span data-stu-id="5981a-108">A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server.</span></span> <span data-ttu-id="5981a-109">ユーザー情報 (ユーザー名とパスワード) と提供された証明書を比較することで、サーバーは資格情報を検証し、ユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="5981a-109">By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="5981a-110">2 要素認証をサポートするために Skype for Business Server 環境を構成する場合は、次のテーマを検討してください。</span><span class="sxs-lookup"><span data-stu-id="5981a-110">Consider the following subjects when configuring a Skype for Business Server environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="5981a-111">クライアント サポート</span><span class="sxs-lookup"><span data-stu-id="5981a-111">Client Support</span></span>

<span data-ttu-id="5981a-112">Lync Server 2013 の累積的な更新プログラム: 2013 年 7 月のデスクトップ クライアントと Skype for Business クライアントは、現在 2 要素認証をサポートしている唯一のクライアントです。</span><span class="sxs-lookup"><span data-stu-id="5981a-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="5981a-113">トポロジ要件</span><span class="sxs-lookup"><span data-stu-id="5981a-113">Topology Requirements</span></span>

<span data-ttu-id="5981a-114">お客様は、エッジ、ディレクター、およびユーザー プールを備える専用の Skype for Business Server を使用して 2 要素認証を展開強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="5981a-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server with Edge, Director, and User Pools.</span></span> <span data-ttu-id="5981a-115">ユーザーのパッシブ認証を有効にするには、次のような他の役割とサービスに対して他の認証方法を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5981a-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="5981a-116">**構成の種類**</span><span class="sxs-lookup"><span data-stu-id="5981a-116">**Configuration Type**</span></span>|<span data-ttu-id="5981a-117">**サービスの種類**</span><span class="sxs-lookup"><span data-stu-id="5981a-117">**Service Type**</span></span>|<span data-ttu-id="5981a-118">**サーバーの役割**</span><span class="sxs-lookup"><span data-stu-id="5981a-118">**Server Role**</span></span>|<span data-ttu-id="5981a-119">**無効にする認証の種類**</span><span class="sxs-lookup"><span data-stu-id="5981a-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5981a-120">(Web) サービス</span><span class="sxs-lookup"><span data-stu-id="5981a-120">Web Service</span></span>  <br/> |<span data-ttu-id="5981a-121">WebServer</span><span class="sxs-lookup"><span data-stu-id="5981a-121">WebServer</span></span>  <br/> |<span data-ttu-id="5981a-122">ディレクター</span><span class="sxs-lookup"><span data-stu-id="5981a-122">Director</span></span>  <br/> |<span data-ttu-id="5981a-123">Kerberos、NTLM、および証明書</span><span class="sxs-lookup"><span data-stu-id="5981a-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="5981a-124">(Web) サービス</span><span class="sxs-lookup"><span data-stu-id="5981a-124">Web Service</span></span>  <br/> |<span data-ttu-id="5981a-125">WebServer</span><span class="sxs-lookup"><span data-stu-id="5981a-125">WebServer</span></span>  <br/> |<span data-ttu-id="5981a-126">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="5981a-126">Front End</span></span>  <br/> |<span data-ttu-id="5981a-127">Kerberos、NTLM、および証明書</span><span class="sxs-lookup"><span data-stu-id="5981a-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="5981a-128">プロキシ</span><span class="sxs-lookup"><span data-stu-id="5981a-128">Proxy</span></span>  <br/> |<span data-ttu-id="5981a-129">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="5981a-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="5981a-130">Edge</span><span class="sxs-lookup"><span data-stu-id="5981a-130">Edge</span></span>  <br/> |<span data-ttu-id="5981a-131">Kerberos と NTLM</span><span class="sxs-lookup"><span data-stu-id="5981a-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="5981a-132">プロキシ</span><span class="sxs-lookup"><span data-stu-id="5981a-132">Proxy</span></span>  <br/> |<span data-ttu-id="5981a-133">レジストラー</span><span class="sxs-lookup"><span data-stu-id="5981a-133">Registrar</span></span>  <br/> |<span data-ttu-id="5981a-134">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="5981a-134">Front End</span></span>  <br/> |<span data-ttu-id="5981a-135">Kerberos と NTLM</span><span class="sxs-lookup"><span data-stu-id="5981a-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="5981a-136">これらの認証の種類がサービス レベルで無効になっていない限り、展開内で 2 要素認証が有効になると、他のすべてのバージョンのクライアントは正常にサインインできません。</span><span class="sxs-lookup"><span data-stu-id="5981a-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="5981a-137">Skype for Business Service Discovery</span><span class="sxs-lookup"><span data-stu-id="5981a-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="5981a-138">Skype for Business サービスを検出するために内部クライアントまたは外部クライアントが使用する DNS レコードは、2 要素認証が有効になっていない Skype for Business サーバーに解決するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5981a-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="5981a-139">この構成では、2 要素認証が有効になっていない Skype for Business プールのユーザーは、認証に PIN を入力する必要はありません。認証には 2 要素認証が有効になっている Skype for Business プールのユーザーが PIN を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5981a-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="5981a-140">Exchange 認証</span><span class="sxs-lookup"><span data-stu-id="5981a-140">Exchange Authentication</span></span>

<span data-ttu-id="5981a-141">Microsoft Exchange 用に 2 要素認証を展開したお客様は、クライアント内の特定の機能が利用できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="5981a-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="5981a-142">これは、Skype for Business クライアントが Exchange 統合に依存する機能に対して 2 要素認証をサポートしていないので、現在は設計されています。</span><span class="sxs-lookup"><span data-stu-id="5981a-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="5981a-143">連絡先</span><span class="sxs-lookup"><span data-stu-id="5981a-143">Contacts</span></span>

<span data-ttu-id="5981a-144">統合連絡先ストア機能を活用するように構成されている Skype for Business ユーザーは、2 要素認証を使用してサインインした後、連絡先が使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="5981a-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="5981a-145">**Invoke-CsUcsRollback** コマンドレットを使用して、2 要素認証を有効にする前に、既存のユーザー連絡先を統合連絡先ストアから削除し、Skype for Business Server に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5981a-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="5981a-146">スキル検索</span><span class="sxs-lookup"><span data-stu-id="5981a-146">Skill Search</span></span>

<span data-ttu-id="5981a-147">Skype for Business 環境でスキル検索機能を構成したお客様は、Skype for Business が 2 要素認証を有効にしている場合、この機能が機能しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="5981a-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="5981a-148">これは、Microsoft SharePoint が現在 2 要素認証をサポートしていないので、設計上です。</span><span class="sxs-lookup"><span data-stu-id="5981a-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="5981a-149">資格情報</span><span class="sxs-lookup"><span data-stu-id="5981a-149">Credentials</span></span>

<span data-ttu-id="5981a-150">保存された Skype for Business 資格情報は、2 要素認証を使用するように構成されているユーザーに影響を与える可能性がある、いくつかの展開に関する考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="5981a-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="5981a-151">保存された資格情報の削除</span><span class="sxs-lookup"><span data-stu-id="5981a-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="5981a-152">ユーザーは、Skype  for Business クライアントの [自分のサインイン情報を削除する] オプションを使用し、2 要素認証を使用して初めてサインインする前に、%localappdata%\Microsoft\Office\15.0\Skype for Business から SIP プロファイル フォルダーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5981a-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="5981a-153">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="5981a-153">DisableNTCredentials</span></span>

<span data-ttu-id="5981a-154">Kerberos または NTLM 認証方法では、ユーザーの Windows 資格情報が認証に自動的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5981a-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="5981a-155">認証に対して Kerberos または NTLM が有効になっている一般的な Skype for Business Server 展開では、ユーザーがサインインする度に資格情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5981a-155">In a typical Skype for Business Server deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="5981a-156">PIN の入力を求めるメッセージが表示される前に、ユーザーが意図せずに資格情報を求めるメッセージが表示された場合は **、DisableNTCredentials** レジストリ キーが、クライアント コンピューター上で意図せずに構成されている可能性があります 。おそらくグループ ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="5981a-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="5981a-157">資格情報の追加のプロンプトが表示されるのを防ぐには、ローカル ワークステーションに次のレジストリ エントリを作成するか、Skype for Business 管理テンプレートを使用して、グループ ポリシーを使用して特定のプールのすべてのユーザーに適用します。</span><span class="sxs-lookup"><span data-stu-id="5981a-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="5981a-158">SavePassword</span><span class="sxs-lookup"><span data-stu-id="5981a-158">SavePassword</span></span>

<span data-ttu-id="5981a-159">ユーザーが初めて Skype for Business にサインインすると、パスワードの保存を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5981a-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="5981a-160">このオプションを選択すると、ユーザーのクライアント証明書を個人用証明書ストアに保存し、ユーザーの Windows 資格情報をローカル コンピューターの Credential Manager に格納できます。</span><span class="sxs-lookup"><span data-stu-id="5981a-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="5981a-161">Skype for Business が 2 要素認証をサポートするように構成されている場合は **、SavePassword** レジストリ設定を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5981a-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="5981a-162">ユーザーがパスワードを保存しなくするには、ローカル ワークステーションで次のレジストリ エントリを変更するか、Skype for Business 管理テンプレートを使用して、グループ ポリシーを使用して特定のプールのすべてのユーザーに適用します。</span><span class="sxs-lookup"><span data-stu-id="5981a-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="5981a-163">AD FS 2.0 トークン再生</span><span class="sxs-lookup"><span data-stu-id="5981a-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="5981a-164">AD FS 2.0 には、同じトークンを使用する複数のトークン要求を検出してから破棄できる、トークン再生検出と呼ばれる機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5981a-164">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded.</span></span> <span data-ttu-id="5981a-165">この機能を有効にすると、トークン再生検出によって、WS-Federation パッシブ プロファイルと SAML WebSSO プロファイルの両方で、同じトークンが 2 回以上使用されないよう、認証要求の整合性が保護されます。</span><span class="sxs-lookup"><span data-stu-id="5981a-165">When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="5981a-166">この機能は、キオスクの使用など、セキュリティが非常に懸念される状況で有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5981a-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="5981a-167">トークン再生の検出の詳細については、「ベスト プラクティス for [Secure Planning and Deployment of AD FS 2.0」を参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ff630160(v=ws.10))。</span><span class="sxs-lookup"><span data-stu-id="5981a-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ff630160(v=ws.10)).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="5981a-168">外部ユーザー アクセス</span><span class="sxs-lookup"><span data-stu-id="5981a-168">External User Access</span></span>

<span data-ttu-id="5981a-169">外部ネットワークからの Skype for Business 2 要素認証をサポートするための ADFS プロキシまたはリバース プロキシの構成については、以下のトピックでは説明されていません。</span><span class="sxs-lookup"><span data-stu-id="5981a-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5981a-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="5981a-170">See also</span></span>

[<span data-ttu-id="5981a-171">Skype for Business Server で 2 要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="5981a-171">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)

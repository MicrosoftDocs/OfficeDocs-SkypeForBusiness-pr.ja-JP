---
title: Skype for Business Server で2要素認証を管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: '概要: Skype for Business Server で2要素認証を管理します。'
ms.openlocfilehash: ccda6795fa5033c792c293701d951e3111666e82
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297562"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="58e5b-103">Skype for Business Server で2要素認証を管理する</span><span class="sxs-lookup"><span data-stu-id="58e5b-103">Manage two-factor authentication in Skype for Business Server</span></span>
 
<span data-ttu-id="58e5b-104">**概要:** Skype for Business Server で2要素認証を管理する。</span><span class="sxs-lookup"><span data-stu-id="58e5b-104">**Summary:** Manage two-factor authentication in Skype for Business Server.</span></span>
  
<span data-ttu-id="58e5b-105">2 要素認証では、ユーザーが 2 つの形式の認証情報または識別情報、つまりユーザー名/パスワードの組み合わせと、トークンまたは証明書を提示する必要があるため、セキュリティが強化されます。</span><span class="sxs-lookup"><span data-stu-id="58e5b-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="58e5b-106">これは、「持っていること、知っていること」とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="58e5b-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="58e5b-p102">証明書を使用した 2 要素認証の一般的な例として、スマート カードの使用があります。スマート カードにはユーザー アカウントに関連付けられている証明書が格納されていて、サーバーに格納されているユーザー情報と証明書情報に対する検証を行うことができます。ユーザー情報 (ユーザー名とパスワード) と提供された証明書を比較することで、サーバーでは資格情報を検証し、ユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="58e5b-p102">A typical example of two-factor authentication with a certificate is the use of smart cards. A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server. By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="58e5b-110">Skype for Business Server 環境を構成して、2段階認証をサポートする場合は、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="58e5b-110">Consider the following subjects when configuring a Skype for Business Server environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="58e5b-111">クライアントのサポート</span><span class="sxs-lookup"><span data-stu-id="58e5b-111">Client Support</span></span>

<span data-ttu-id="58e5b-112">Lync Server 2013 の累積的な更新: 2013 年7月のデスクトップクライアントと Skype for Business クライアントは、現在2要素認証をサポートしている唯一のクライアントです。</span><span class="sxs-lookup"><span data-stu-id="58e5b-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="58e5b-113">トポロジ要件</span><span class="sxs-lookup"><span data-stu-id="58e5b-113">Topology Requirements</span></span>

<span data-ttu-id="58e5b-114">お客様は、エッジ、監督、ユーザープールと共に、専用の Skype for Business Server を使用して2要素認証を展開することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="58e5b-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server with Edge, Director, and User Pools.</span></span> <span data-ttu-id="58e5b-115">ユーザーに対してパッシブ認証を有効にするには、次に示すように、他の役割およびサービスに対してその他の認証方法を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="58e5b-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="58e5b-116">**構成の種類**</span><span class="sxs-lookup"><span data-stu-id="58e5b-116">**Configuration Type**</span></span>|<span data-ttu-id="58e5b-117">**サービスの種類**</span><span class="sxs-lookup"><span data-stu-id="58e5b-117">**Service Type**</span></span>|<span data-ttu-id="58e5b-118">**サーバーの役割**</span><span class="sxs-lookup"><span data-stu-id="58e5b-118">**Server Role**</span></span>|<span data-ttu-id="58e5b-119">**無効にする認証の種類**</span><span class="sxs-lookup"><span data-stu-id="58e5b-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="58e5b-120">Web サービス</span><span class="sxs-lookup"><span data-stu-id="58e5b-120">Web Service</span></span>  <br/> |<span data-ttu-id="58e5b-121">WebServer</span><span class="sxs-lookup"><span data-stu-id="58e5b-121">WebServer</span></span>  <br/> |<span data-ttu-id="58e5b-122">ディレクター</span><span class="sxs-lookup"><span data-stu-id="58e5b-122">Director</span></span>  <br/> |<span data-ttu-id="58e5b-123">Kerberos、NTLM、証明書</span><span class="sxs-lookup"><span data-stu-id="58e5b-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="58e5b-124">Web サービス</span><span class="sxs-lookup"><span data-stu-id="58e5b-124">Web Service</span></span>  <br/> |<span data-ttu-id="58e5b-125">WebServer</span><span class="sxs-lookup"><span data-stu-id="58e5b-125">WebServer</span></span>  <br/> |<span data-ttu-id="58e5b-126">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="58e5b-126">Front End</span></span>  <br/> |<span data-ttu-id="58e5b-127">Kerberos、NTLM、証明書</span><span class="sxs-lookup"><span data-stu-id="58e5b-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="58e5b-128">プロキシ</span><span class="sxs-lookup"><span data-stu-id="58e5b-128">Proxy</span></span>  <br/> |<span data-ttu-id="58e5b-129">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="58e5b-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="58e5b-130">Edge</span><span class="sxs-lookup"><span data-stu-id="58e5b-130">Edge</span></span>  <br/> |<span data-ttu-id="58e5b-131">Kerberos および NTLM</span><span class="sxs-lookup"><span data-stu-id="58e5b-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="58e5b-132">プロキシ</span><span class="sxs-lookup"><span data-stu-id="58e5b-132">Proxy</span></span>  <br/> |<span data-ttu-id="58e5b-133">レジストラー</span><span class="sxs-lookup"><span data-stu-id="58e5b-133">Registrar</span></span>  <br/> |<span data-ttu-id="58e5b-134">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="58e5b-134">Front End</span></span>  <br/> |<span data-ttu-id="58e5b-135">Kerberos および NTLM</span><span class="sxs-lookup"><span data-stu-id="58e5b-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="58e5b-136">これらの認証の種類がサービス レベルで無効になっていない限り、2 要素認証が展開内で有効になっても、他のすべてのバージョンのクライアントでは正常にサインインできません。</span><span class="sxs-lookup"><span data-stu-id="58e5b-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="58e5b-137">Skype for Business サービスの検出</span><span class="sxs-lookup"><span data-stu-id="58e5b-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="58e5b-138">Skype for business サービスを検出するために、内部または外部のクライアントによって使用される DNS レコードは、2要素認証が有効になっていない Skype for Business サーバーに解決するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58e5b-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="58e5b-139">この構成では、2要素認証が有効になっていない Skype for Business プールのユーザーは、認証のために PIN を入力する必要がなく、2要素認証が有効になっている Skype for Business プールのユーザーは実行されません。認証のために PIN を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58e5b-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="58e5b-140">Exchange 認証</span><span class="sxs-lookup"><span data-stu-id="58e5b-140">Exchange Authentication</span></span>

<span data-ttu-id="58e5b-141">Microsoft Exchange の2要素認証を導入しているお客様は、クライアントの一部の機能が利用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="58e5b-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="58e5b-142">現時点では、Skype for Business クライアントは Exchange 統合に依存する機能に対して2要素認証をサポートしていないため、これは現在設計になっています。</span><span class="sxs-lookup"><span data-stu-id="58e5b-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="58e5b-143">連絡先</span><span class="sxs-lookup"><span data-stu-id="58e5b-143">Contacts</span></span>

<span data-ttu-id="58e5b-144">ユニファイド連絡先ストア機能を利用するように構成されている Skype for Business ユーザーは、2要素認証を使用してサインインした後、連絡先を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="58e5b-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="58e5b-145">2要素認証を有効にする前に、 **CsUcsRollback**コマンドレットを使用して、統合された連絡先ストアから既存のユーザーの連絡先を削除し、それらを Skype For business Server に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58e5b-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="58e5b-146">スキル検索</span><span class="sxs-lookup"><span data-stu-id="58e5b-146">Skill Search</span></span>

<span data-ttu-id="58e5b-147">Skype for Business 環境でスキル検索機能を構成している場合は、Skype for Business が2要素認証を有効にしているときに、この機能が機能しないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="58e5b-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="58e5b-148">現在、Microsoft SharePoint では 2 要素認証がサポートされていないため、これは仕様です。</span><span class="sxs-lookup"><span data-stu-id="58e5b-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="58e5b-149">資格情報</span><span class="sxs-lookup"><span data-stu-id="58e5b-149">Credentials</span></span>

<span data-ttu-id="58e5b-150">2要素認証を使用するように構成されているユーザーに影響を与える可能性のある、Skype for Business の資格情報を保存することについて、いくつかの展開の考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="58e5b-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="58e5b-151">保存された資格情報の削除</span><span class="sxs-lookup"><span data-stu-id="58e5b-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="58e5b-152">ユーザーは、Skype for Business クライアントで **[サインイン情報の削除**] オプションを使用し、2つの要素を使用して初めてサインインする前に、%Localappdata%\Microsoft\Office\15.0\Skype for BUSINESS から SIP プロファイルフォルダーを削除する必要があります。認証.</span><span class="sxs-lookup"><span data-stu-id="58e5b-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="58e5b-153">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="58e5b-153">DisableNTCredentials</span></span>

<span data-ttu-id="58e5b-154">Kerberos 認証方法または NTLM 認証方法を使用すると、ユーザーの Windows 資格情報が認証に自動的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="58e5b-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="58e5b-155">Skype for Business Server の一般的な展開では、認証に Kerberos または NTLM が有効になっているため、ユーザーはサインインするたびに資格情報を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="58e5b-155">In a typical Skype for Business Server deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="58e5b-156">PIN の入力を求めるメッセージが表示される前に、意図せず資格情報の入力を求められた場合は、クライアント コンピューターで **DisableNTCredentials** レジストリ キーが誤って (おそらくグループ ポリシーを使用して) 構成されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="58e5b-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="58e5b-157">追加の資格情報の入力を求めるメッセージが表示されないようにするには、ローカルワークステーションで次のレジストリエントリを作成するか、グループポリシーを使って特定のプールのすべてのユーザーに適用する Skype for Business 管理用テンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="58e5b-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="58e5b-158">SavePassword</span><span class="sxs-lookup"><span data-stu-id="58e5b-158">SavePassword</span></span>

<span data-ttu-id="58e5b-159">ユーザーが初めて Skype for Business にサインインしたときに、ユーザーにパスワードの保存を促すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="58e5b-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="58e5b-160">このオプションを選択すると、ユーザーのクライアント証明書が個人証明書ストアに保存され、ユーザーの Windows 資格情報がローカルコンピューターの資格情報マネージャーに格納されるようになります。</span><span class="sxs-lookup"><span data-stu-id="58e5b-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="58e5b-161">Skype for Business が2要素認証をサポートするように構成されている場合は、 **Savepassword**レジストリ設定を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="58e5b-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="58e5b-162">ユーザーがパスワードを保存できないようにするには、ローカルワークステーション上の次のレジストリエントリを変更するか、グループポリシーを使って特定のプールのすべてのユーザーに適用する Skype for Business 管理用テンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="58e5b-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="58e5b-163">AD FS 2.0 のトークンのリプレイ</span><span class="sxs-lookup"><span data-stu-id="58e5b-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="58e5b-p110">AD FS 2.0 には、トークン リプレイ検出と呼ばれる機能が用意されています。この機能によって、同じトークンを使用する複数のトークン要求を検出して破棄できます。この機能が有効な場合は、同じトークンが複数回使用されることがなくなるため、WS-Federation パッシブ プロファイルと SAML WebSSO プロファイルの両方において認証要求の整合性が確保されます。</span><span class="sxs-lookup"><span data-stu-id="58e5b-p110">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded. When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="58e5b-166">キオスクを使用する場合など、セキュリティが最も重視される状況では、この機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="58e5b-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="58e5b-167">トークンの再生検出の詳細については、「 [AD FS 2.0 のセキュリティで保護された計画と展開のためのベストプラクティス](https://go.microsoft.com/fwlink/p/?LinkId=309215)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58e5b-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="58e5b-168">外部ユーザー アクセス</span><span class="sxs-lookup"><span data-stu-id="58e5b-168">External User Access</span></span>

<span data-ttu-id="58e5b-169">外部ネットワークからの Skype for Business の2要素認証をサポートするために ADFS プロキシまたはリバースプロキシを構成する方法については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="58e5b-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="58e5b-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="58e5b-170">See also</span></span>

[<span data-ttu-id="58e5b-171">Skype for Business Server で2要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="58e5b-171">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)
  

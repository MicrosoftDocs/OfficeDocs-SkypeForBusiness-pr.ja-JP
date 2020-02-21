---
title: 'Lync Server 2013: 2 要素認証の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0738cb282ad2f1f375e89526fcdd1569a6707ad0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="b80de-102">Lync Server 2013 での2要素認証の計画</span><span class="sxs-lookup"><span data-stu-id="b80de-102">Planning for two-factor authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b80de-103">_**トピックの最終更新日:** 2015-04-06_</span><span class="sxs-lookup"><span data-stu-id="b80de-103">_**Topic Last Modified:** 2015-04-06_</span></span>

<span data-ttu-id="b80de-104">2要素認証をサポートするように Microsoft Lync Server 2013 環境を構成する場合の展開に関する考慮事項の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b80de-104">The following is a list of deployment considerations when configuring a Microsoft Lync Server 2013 environment to support two-factor authentication.</span></span>

<div>

## <a name="client-support"></a><span data-ttu-id="b80de-105">クライアントサポート</span><span class="sxs-lookup"><span data-stu-id="b80de-105">Client Support</span></span>

<span data-ttu-id="b80de-106">Lync Server 2013 の Lync 2013 の累積的な更新プログラム: 7 月 2013 7 日のデスクトップクライアントとすべてのモバイルクライアントは、現在2要素認証をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b80de-106">The Lync 2013 Cumulative Updates for Lync Server 2013: July 2013 desktop client and all mobile clients currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="b80de-107">トポロジ要件</span><span class="sxs-lookup"><span data-stu-id="b80de-107">Topology Requirements</span></span>

<span data-ttu-id="b80de-108">お客様は、Lync Server 2013 の累積的な更新プログラムと共に、専任の Lync Server 2013 を使用して2要素認証を展開することを強くお勧めします。 7 2013 月のエッジ、ディレクター、およびユーザープール。</span><span class="sxs-lookup"><span data-stu-id="b80de-108">Customers are strongly encouraged to deploy two-factor authentication using dedicated Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Edge, Director, and User Pools.</span></span> <span data-ttu-id="b80de-109">Lync ユーザーのパッシブ認証を有効にするには、他の役割とサービスについて次のような他の認証方法を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b80de-109">To enable passive authentication for Lync users, other authentication methods must be disabled for other roles and services, including the following:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b80de-110">構成の種類</span><span class="sxs-lookup"><span data-stu-id="b80de-110">Configuration Type</span></span></th>
<th><span data-ttu-id="b80de-111">サービス タイプ</span><span class="sxs-lookup"><span data-stu-id="b80de-111">Service Type</span></span></th>
<th><span data-ttu-id="b80de-112">サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="b80de-112">Server Role</span></span></th>
<th><span data-ttu-id="b80de-113">無効にする認証の種類</span><span class="sxs-lookup"><span data-stu-id="b80de-113">Authentication Type to Disable</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b80de-114">(Web) サービス</span><span class="sxs-lookup"><span data-stu-id="b80de-114">Web Service</span></span></p></td>
<td><p><span data-ttu-id="b80de-115">サーバ</span><span class="sxs-lookup"><span data-stu-id="b80de-115">WebServer</span></span></p></td>
<td><p><span data-ttu-id="b80de-116">ディレクター</span><span class="sxs-lookup"><span data-stu-id="b80de-116">Director</span></span></p></td>
<td><p><span data-ttu-id="b80de-117">Kerberos、NTLM、証明書</span><span class="sxs-lookup"><span data-stu-id="b80de-117">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b80de-118">(Web) サービス</span><span class="sxs-lookup"><span data-stu-id="b80de-118">Web Service</span></span></p></td>
<td><p><span data-ttu-id="b80de-119">サーバ</span><span class="sxs-lookup"><span data-stu-id="b80de-119">WebServer</span></span></p></td>
<td><p><span data-ttu-id="b80de-120">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="b80de-120">Front End</span></span></p></td>
<td><p><span data-ttu-id="b80de-121">Kerberos、NTLM、証明書</span><span class="sxs-lookup"><span data-stu-id="b80de-121">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b80de-122">プロキシ</span><span class="sxs-lookup"><span data-stu-id="b80de-122">Proxy</span></span></p></td>
<td><p><span data-ttu-id="b80de-123">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="b80de-123">EdgeServer</span></span></p></td>
<td><p><span data-ttu-id="b80de-124">Edge</span><span class="sxs-lookup"><span data-stu-id="b80de-124">Edge</span></span></p></td>
<td><p><span data-ttu-id="b80de-125">Kerberos および NTLM</span><span class="sxs-lookup"><span data-stu-id="b80de-125">Kerberos and NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b80de-126">プロキシ</span><span class="sxs-lookup"><span data-stu-id="b80de-126">Proxy</span></span></p></td>
<td><p><span data-ttu-id="b80de-127">レジストラー</span><span class="sxs-lookup"><span data-stu-id="b80de-127">Registrar</span></span></p></td>
<td><p><span data-ttu-id="b80de-128">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="b80de-128">Front End</span></span></p></td>
<td><p><span data-ttu-id="b80de-129">Kerberos および NTLM</span><span class="sxs-lookup"><span data-stu-id="b80de-129">Kerberos and NTLM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b80de-130">これらの認証の種類がサービスレベルで無効になっていない場合、展開内で2要素認証が有効になっていると、Lync クライアントの他のすべてのバージョンは正常にサインインできなくなります。</span><span class="sxs-lookup"><span data-stu-id="b80de-130">Unless these authentication types are disabled at the service level, all other versions of the Lync client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>

</div>

<div>

## <a name="lync-service-discovery"></a><span data-ttu-id="b80de-131">Lync Service の検出</span><span class="sxs-lookup"><span data-stu-id="b80de-131">Lync Service Discovery</span></span>

<span data-ttu-id="b80de-132">内部または外部のクライアントが Lync サービスを検出するために使用する DNS レコードは、2要素認証が有効になっていない Lync server に解決するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b80de-132">DNS records used by internal and/or external clients to discover Lync services should be configured to resolve to a Lync server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="b80de-133">この構成では、2要素認証が有効になっていない Lync プールのユーザーは認証のために PIN を入力する必要はありませんが、2要素認証が有効になっている Lync プールのユーザーは PIN を入力する必要があります。対し.</span><span class="sxs-lookup"><span data-stu-id="b80de-133">With this configuration, users from Lync Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Lync Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>

</div>

<div>

## <a name="exchange-authentication"></a><span data-ttu-id="b80de-134">Exchange 認証</span><span class="sxs-lookup"><span data-stu-id="b80de-134">Exchange Authentication</span></span>

<span data-ttu-id="b80de-135">Microsoft Exchange の2要素認証を展開しているお客様は、Lync クライアントの特定の機能が使用できないことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b80de-135">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the Lync client are unavailable.</span></span> <span data-ttu-id="b80de-136">現在、Lync クライアントは、Exchange 統合に依存する機能に対して2要素認証をサポートしていないため、これは現在設計になっています。</span><span class="sxs-lookup"><span data-stu-id="b80de-136">This is currently by design, as the Lync client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>

</div>

<div>

## <a name="lync-contacts"></a><span data-ttu-id="b80de-137">Lync の連絡先</span><span class="sxs-lookup"><span data-stu-id="b80de-137">Lync Contacts</span></span>

<span data-ttu-id="b80de-138">統合連絡先ストア機能を活用するように構成された Lync ユーザーは、2要素認証を使用してサインインした後、連絡先が使用できなくなっていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b80de-138">Lync users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>

<span data-ttu-id="b80de-139">2要素認証を有効にする前に、 **invoke-csucsrollback**コマンドレットを使用して、統合連絡先ストアから既存のユーザー連絡先を削除し、Lync Server 2013 に格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b80de-139">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Lync Server 2013 before enabling two-factor authentication.</span></span>

</div>

<div>

## <a name="skill-search"></a><span data-ttu-id="b80de-140">スキル検索</span><span class="sxs-lookup"><span data-stu-id="b80de-140">Skill Search</span></span>

<span data-ttu-id="b80de-141">Lync 環境でスキル検索機能を構成したお客様は、Lync が2要素認証のために有効になっていると、この機能が機能しないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="b80de-141">Customers who have configured the Skill Search feature in their Lync environment will find that this feature does not work when Lync is enabled for two-factor authentication.</span></span> <span data-ttu-id="b80de-142">Microsoft SharePoint では、現在2要素認証がサポートされていないため、このような設計になっています。</span><span class="sxs-lookup"><span data-stu-id="b80de-142">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="lync-credentials"></a><span data-ttu-id="b80de-143">Lync 資格情報</span><span class="sxs-lookup"><span data-stu-id="b80de-143">Lync Credentials</span></span>

<span data-ttu-id="b80de-144">保存された Lync 資格情報に関しては、2要素認証を使用するように構成されているユーザーに影響を与える可能性がある、いくつかの展開の考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="b80de-144">There are a number of deployment considerations involving saved Lync credentials which may impact users who are configured to use two-factor authentication.</span></span>

<div>

## <a name="deleting-saved-credentials"></a><span data-ttu-id="b80de-145">保存された資格情報の削除</span><span class="sxs-lookup"><span data-stu-id="b80de-145">Deleting Saved Credentials</span></span>

<span data-ttu-id="b80de-146">デスクトップクライアントのユーザーは、Lync クライアントの [**サインイン情報の削除**] オプションを使用して、2要素認証を使用して\\初め\\て\\署名\\する前に、Microsoft Office 15.0 Lync から SIP プロファイルフォルダーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b80de-146">Desktop client users should use the **Delete my sign-in info** option in the Lync client and delete their SIP profile folder from %localappdata%\\Microsoft\\Office\\15.0\\Lync before attempting to sign for the first time using two-factor authentication.</span></span>

</div>

<div>

## <a name="disablentcredentials"></a><span data-ttu-id="b80de-147">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="b80de-147">DisableNTCredentials</span></span>

<span data-ttu-id="b80de-148">Kerberos 認証方法または NTLM 認証方式では、ユーザーの Windows 資格情報が認証に自動的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b80de-148">With the Kerberos or NTLM authentication method, the user’s Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="b80de-149">Kerberos または NTLM 認証が有効になっている典型的な Lync Server 2013 の展開では、ユーザーはサインインするたびに資格情報を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b80de-149">In a typical Lync Server 2013 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>

<span data-ttu-id="b80de-150">PIN の入力を求められる前に、ユーザーが誤って資格情報の入力を求められた場合は、クライアントコンピューターで**Disablentcredentials**レジストリキーが誤って構成されることがあります。グループポリシーを使用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b80de-150">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>

<span data-ttu-id="b80de-151">資格情報の追加を求めるプロンプトを表示しないようにするには、ローカルワークステーションに次のレジストリエントリを作成するか、または Lync 管理用テンプレートを使用して、グループポリシーを使用して特定のプールのすべてのユーザーに適用します。</span><span class="sxs-lookup"><span data-stu-id="b80de-151">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="b80de-152">HKEY\_ローカル\_コンピューター\\ソフトウェア\\ポリシー\\Microsoft\\Office\\15.0\\Lync</span><span class="sxs-lookup"><span data-stu-id="b80de-152">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="b80de-153">REG\_DWORD: DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="b80de-153">REG\_DWORD: DisableNTCredentials</span></span>

<span data-ttu-id="b80de-154">値: 0x0</span><span class="sxs-lookup"><span data-stu-id="b80de-154">Value: 0x0</span></span>

</div>

<div>

## <a name="savepassword"></a><span data-ttu-id="b80de-155">SavePassword</span><span class="sxs-lookup"><span data-stu-id="b80de-155">SavePassword</span></span>

<span data-ttu-id="b80de-156">ユーザーが初めて Lync にサインインすると、ユーザーは自分のパスワードを保存するように求められます。</span><span class="sxs-lookup"><span data-stu-id="b80de-156">When a user signs in to Lync for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="b80de-157">このオプションを選択すると、ユーザーのクライアント証明書を個人証明書ストアに格納し、ユーザーの Windows 資格情報をローカルコンピューターの資格情報マネージャーに保存できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b80de-157">If selected, this option allows the user’s client certificate to be stored in the personal certificate store and the user’s Windows credentials to be stored in the Credential Manager of the local computer.</span></span>

<span data-ttu-id="b80de-158">Lync が2要素認証をサポートするように構成されている場合は、 **Savepassword**レジストリ設定を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b80de-158">The **SavePassword** registry setting should be disabled when Lync is configured to support two-factor authentication.</span></span> <span data-ttu-id="b80de-159">ユーザーがパスワードを保存できないようにするには、ローカルワークステーションの次のレジストリエントリを変更するか、または Lync 管理用テンプレートを使用して、グループポリシーを使用して特定のプールのすべてのユーザーに適用します。</span><span class="sxs-lookup"><span data-stu-id="b80de-159">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="b80de-160">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync</span><span class="sxs-lookup"><span data-stu-id="b80de-160">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="b80de-161">REG\_DWORD: savepassword</span><span class="sxs-lookup"><span data-stu-id="b80de-161">REG\_DWORD: SavePassword</span></span>

<span data-ttu-id="b80de-162">値: 0x0</span><span class="sxs-lookup"><span data-stu-id="b80de-162">Value: 0x0</span></span>

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="b80de-163">AD FS 2.0 トークンの再生</span><span class="sxs-lookup"><span data-stu-id="b80de-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="b80de-164">AD FS 2.0 は、トークン再生検出と呼ばれる機能を提供しており、同じトークンを使用して複数のトークン要求を検出して破棄することができます。</span><span class="sxs-lookup"><span data-stu-id="b80de-164">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded.</span></span> <span data-ttu-id="b80de-165">この機能が有効になっている場合は、同じトークンが一度も使用されないようにすることによって、トークン再生の検出によって、WS-FEDERATION のパッシブプロファイルと SAML WebSSO プロファイルの両方の認証要求の整合性を保護します。</span><span class="sxs-lookup"><span data-stu-id="b80de-165">When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>

<span data-ttu-id="b80de-166">この機能を有効にする必要があるのは、セキュリティがキオスクを使用する場合など、非常に高い問題である場合です。</span><span class="sxs-lookup"><span data-stu-id="b80de-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="b80de-167">トークンリプレイ検出の詳細については、「AD FS 2.0 のセキュリティで保護された[https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215)計画と展開のベストプラクティス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b80de-167">For more information about token replay detection, see Best Practices for Secure Planning and Deployment of AD FS 2.0 at [https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215).</span></span>

</div>

<div>

## <a name="external-user-access"></a><span data-ttu-id="b80de-168">外部ユーザー アクセス</span><span class="sxs-lookup"><span data-stu-id="b80de-168">External User Access</span></span>

<span data-ttu-id="b80de-169">外部ネットワークから Lync の2要素認証をサポートするように AD FS プロキシまたはリバースプロキシを構成する方法については、以下のトピックでは扱いません。</span><span class="sxs-lookup"><span data-stu-id="b80de-169">Configuring an AD FS Proxy or Reverse Proxy to support Lync two-factor authentication from external networks is not covered in these topics.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


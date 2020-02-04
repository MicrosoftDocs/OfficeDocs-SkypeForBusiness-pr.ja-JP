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
ms.openlocfilehash: e610990182e01c0e9e2d7199bd3a34f70fbe3132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="79c99-102">Lync Server 2013 での2要素認証の計画</span><span class="sxs-lookup"><span data-stu-id="79c99-102">Planning for two-factor authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79c99-103">_**最終更新日:** 2015-04-06_</span><span class="sxs-lookup"><span data-stu-id="79c99-103">_**Topic Last Modified:** 2015-04-06_</span></span>

<span data-ttu-id="79c99-104">Microsoft Lync Server 2013 環境を構成して、2段階認証をサポートする場合の展開に関する考慮事項の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="79c99-104">The following is a list of deployment considerations when configuring a Microsoft Lync Server 2013 environment to support two-factor authentication.</span></span>

<div>

## <a name="client-support"></a><span data-ttu-id="79c99-105">クライアントのサポート</span><span class="sxs-lookup"><span data-stu-id="79c99-105">Client Support</span></span>

<span data-ttu-id="79c99-106">Lync 2013 の Lync Server 2013 の累積更新プログラム: 2013 デスクトップクライアントとすべてのモバイルクライアントで現在、2要素認証がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="79c99-106">The Lync 2013 Cumulative Updates for Lync Server 2013: July 2013 desktop client and all mobile clients currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="79c99-107">トポロジ要件</span><span class="sxs-lookup"><span data-stu-id="79c99-107">Topology Requirements</span></span>

<span data-ttu-id="79c99-108">お客様は、lync Server 2013 の累積更新プログラムを使用して、専用の Lync Server 2013 を使って2要素認証を展開することを強くお勧めします。これには、2013年7月のエッジ、監督、ユーザープールがあります。</span><span class="sxs-lookup"><span data-stu-id="79c99-108">Customers are strongly encouraged to deploy two-factor authentication using dedicated Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Edge, Director, and User Pools.</span></span> <span data-ttu-id="79c99-109">Lync ユーザーに対してパッシブ認証を有効にするには、他の役割やサービスについて、次のような他の認証方法を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="79c99-109">To enable passive authentication for Lync users, other authentication methods must be disabled for other roles and services, including the following:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79c99-110">構成の種類</span><span class="sxs-lookup"><span data-stu-id="79c99-110">Configuration Type</span></span></th>
<th><span data-ttu-id="79c99-111">サービスの種類</span><span class="sxs-lookup"><span data-stu-id="79c99-111">Service Type</span></span></th>
<th><span data-ttu-id="79c99-112">サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="79c99-112">Server Role</span></span></th>
<th><span data-ttu-id="79c99-113">無効にする認証の種類</span><span class="sxs-lookup"><span data-stu-id="79c99-113">Authentication Type to Disable</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79c99-114">Web サービス</span><span class="sxs-lookup"><span data-stu-id="79c99-114">Web Service</span></span></p></td>
<td><p><span data-ttu-id="79c99-115">WebServer</span><span class="sxs-lookup"><span data-stu-id="79c99-115">WebServer</span></span></p></td>
<td><p><span data-ttu-id="79c99-116">ディレクター</span><span class="sxs-lookup"><span data-stu-id="79c99-116">Director</span></span></p></td>
<td><p><span data-ttu-id="79c99-117">Kerberos、NTLM、証明書</span><span class="sxs-lookup"><span data-stu-id="79c99-117">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c99-118">Web サービス</span><span class="sxs-lookup"><span data-stu-id="79c99-118">Web Service</span></span></p></td>
<td><p><span data-ttu-id="79c99-119">WebServer</span><span class="sxs-lookup"><span data-stu-id="79c99-119">WebServer</span></span></p></td>
<td><p><span data-ttu-id="79c99-120">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="79c99-120">Front End</span></span></p></td>
<td><p><span data-ttu-id="79c99-121">Kerberos、NTLM、証明書</span><span class="sxs-lookup"><span data-stu-id="79c99-121">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c99-122">プロキシ</span><span class="sxs-lookup"><span data-stu-id="79c99-122">Proxy</span></span></p></td>
<td><p><span data-ttu-id="79c99-123">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="79c99-123">EdgeServer</span></span></p></td>
<td><p><span data-ttu-id="79c99-124">Edge</span><span class="sxs-lookup"><span data-stu-id="79c99-124">Edge</span></span></p></td>
<td><p><span data-ttu-id="79c99-125">Kerberos および NTLM</span><span class="sxs-lookup"><span data-stu-id="79c99-125">Kerberos and NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c99-126">プロキシ</span><span class="sxs-lookup"><span data-stu-id="79c99-126">Proxy</span></span></p></td>
<td><p><span data-ttu-id="79c99-127">レジストラー</span><span class="sxs-lookup"><span data-stu-id="79c99-127">Registrar</span></span></p></td>
<td><p><span data-ttu-id="79c99-128">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="79c99-128">Front End</span></span></p></td>
<td><p><span data-ttu-id="79c99-129">Kerberos および NTLM</span><span class="sxs-lookup"><span data-stu-id="79c99-129">Kerberos and NTLM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="79c99-130">これらの認証の種類がサービスレベルで無効にされていない限り、展開で2要素認証が有効になると、Lync クライアントの他のすべてのバージョンが正常にサインインできなくなります。</span><span class="sxs-lookup"><span data-stu-id="79c99-130">Unless these authentication types are disabled at the service level, all other versions of the Lync client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>

</div>

<div>

## <a name="lync-service-discovery"></a><span data-ttu-id="79c99-131">Lync サービスの検出</span><span class="sxs-lookup"><span data-stu-id="79c99-131">Lync Service Discovery</span></span>

<span data-ttu-id="79c99-132">内部および外部のクライアントによって使用される DNS レコードは、2要素認証が有効になっていない Lync サーバーに解決するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79c99-132">DNS records used by internal and/or external clients to discover Lync services should be configured to resolve to a Lync server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="79c99-133">この構成では、2要素認証が有効になっていない Lync プールのユーザーは、認証のために PIN の入力を求められますが、2要素認証が有効になっている Lync プールのユーザーは PIN を入力する必要があります。相互.</span><span class="sxs-lookup"><span data-stu-id="79c99-133">With this configuration, users from Lync Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Lync Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>

</div>

<div>

## <a name="exchange-authentication"></a><span data-ttu-id="79c99-134">Exchange 認証</span><span class="sxs-lookup"><span data-stu-id="79c99-134">Exchange Authentication</span></span>

<span data-ttu-id="79c99-135">Microsoft Exchange の2要素認証を展開しているお客様は、Lync クライアントの一部の機能が利用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="79c99-135">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the Lync client are unavailable.</span></span> <span data-ttu-id="79c99-136">現時点では、Lync クライアントは Exchange の統合に依存する機能に対して2要素認証をサポートしていないため、現在の設計になっています。</span><span class="sxs-lookup"><span data-stu-id="79c99-136">This is currently by design, as the Lync client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>

</div>

<div>

## <a name="lync-contacts"></a><span data-ttu-id="79c99-137">Lync の連絡先</span><span class="sxs-lookup"><span data-stu-id="79c99-137">Lync Contacts</span></span>

<span data-ttu-id="79c99-138">統合連絡先ストア機能を利用するように構成されている Lync ユーザーは、2要素認証を使用してサインインした後、連絡先が利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="79c99-138">Lync users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>

<span data-ttu-id="79c99-139">2要素認証を有効にする前に、 **CsUcsRollback**コマンドレットを使用して、統合された連絡先ストアから既存のユーザーの連絡先を削除し、それらを Lync Server 2013 に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79c99-139">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Lync Server 2013 before enabling two-factor authentication.</span></span>

</div>

<div>

## <a name="skill-search"></a><span data-ttu-id="79c99-140">スキル検索</span><span class="sxs-lookup"><span data-stu-id="79c99-140">Skill Search</span></span>

<span data-ttu-id="79c99-141">Lync 環境でスキル検索機能を構成している場合は、Lync が2要素認証を有効にしている場合、この機能が機能しないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="79c99-141">Customers who have configured the Skill Search feature in their Lync environment will find that this feature does not work when Lync is enabled for two-factor authentication.</span></span> <span data-ttu-id="79c99-142">現在、Microsoft SharePoint では 2 要素認証がサポートされていないため、これは仕様です。</span><span class="sxs-lookup"><span data-stu-id="79c99-142">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="lync-credentials"></a><span data-ttu-id="79c99-143">Lync の資格情報</span><span class="sxs-lookup"><span data-stu-id="79c99-143">Lync Credentials</span></span>

<span data-ttu-id="79c99-144">2要素認証を使用するように構成されているユーザーに影響を与える可能性のある Lync 資格情報が保存されていることについて、いくつかの展開の考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="79c99-144">There are a number of deployment considerations involving saved Lync credentials which may impact users who are configured to use two-factor authentication.</span></span>

<div>

## <a name="deleting-saved-credentials"></a><span data-ttu-id="79c99-145">保存された資格情報の削除</span><span class="sxs-lookup"><span data-stu-id="79c99-145">Deleting Saved Credentials</span></span>

<span data-ttu-id="79c99-146">デスクトップクライアントユーザーは、Lync クライアントで **[サインイン情報の削除**] オプションを使用し、2段階認証を使用して初めて\\サインイン\\する\\前\\に、% localappdata% Microsoft Office 15.0 Lync から SIP プロファイルフォルダーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79c99-146">Desktop client users should use the **Delete my sign-in info** option in the Lync client and delete their SIP profile folder from %localappdata%\\Microsoft\\Office\\15.0\\Lync before attempting to sign for the first time using two-factor authentication.</span></span>

</div>

<div>

## <a name="disablentcredentials"></a><span data-ttu-id="79c99-147">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="79c99-147">DisableNTCredentials</span></span>

<span data-ttu-id="79c99-148">認証方法が Kerberos または NTLM の場合は、ユーザーの Windows 資格情報が自動的に認証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="79c99-148">With the Kerberos or NTLM authentication method, the user’s Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="79c99-149">認証に Kerberos または NTLM が有効になっている一般的な Lync Server 2013 の展開では、ユーザーがサインインするたびに資格情報を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="79c99-149">In a typical Lync Server 2013 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>

<span data-ttu-id="79c99-150">PIN の入力を求めるメッセージが表示される前に、意図せず資格情報の入力を求められた場合は、クライアント コンピューターで **DisableNTCredentials** レジストリ キーが誤って (おそらくグループ ポリシーを使用して) 構成されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="79c99-150">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>

<span data-ttu-id="79c99-151">追加の資格情報の入力を求めるメッセージが表示されないようにするには、ローカルワークステーションで次のレジストリエントリを作成するか、グループポリシーを使って特定のプールのすべてのユーザーに適用する Lync 管理用テンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="79c99-151">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="79c99-152">HKEY\_ローカル\_コンピューター\\ソフトウェア\\ポリシー\\Microsoft\\Office\\15.0\\Lync</span><span class="sxs-lookup"><span data-stu-id="79c99-152">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="79c99-153">REG\_DWORD: DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="79c99-153">REG\_DWORD: DisableNTCredentials</span></span>

<span data-ttu-id="79c99-154">値: 0x0</span><span class="sxs-lookup"><span data-stu-id="79c99-154">Value: 0x0</span></span>

</div>

<div>

## <a name="savepassword"></a><span data-ttu-id="79c99-155">SavePassword</span><span class="sxs-lookup"><span data-stu-id="79c99-155">SavePassword</span></span>

<span data-ttu-id="79c99-156">ユーザーが初めて Lync にサインインしたときに、ユーザーにパスワードの保存を促すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="79c99-156">When a user signs in to Lync for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="79c99-157">このオプションを選択すると、ユーザーのクライアント証明書を個人証明書ストアに保存したり、ユーザーの Windows 資格情報をローカル コンピューターの資格情報マネージャーに保存したりできます。</span><span class="sxs-lookup"><span data-stu-id="79c99-157">If selected, this option allows the user’s client certificate to be stored in the personal certificate store and the user’s Windows credentials to be stored in the Credential Manager of the local computer.</span></span>

<span data-ttu-id="79c99-158">Lync が2要素認証をサポートするように構成されている場合は、 **Savepassword**レジストリ設定を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="79c99-158">The **SavePassword** registry setting should be disabled when Lync is configured to support two-factor authentication.</span></span> <span data-ttu-id="79c99-159">ユーザーがパスワードを保存できないようにするには、ローカルワークステーションの次のレジストリエントリを変更するか、グループポリシーを使って、特定のプールのすべてのユーザーに適用する Lync 管理用テンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="79c99-159">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="79c99-160">HKEY\_現在\_の\\ユーザー\\ソフトウェア\\Microsoft\\Office\\15.0 Lync</span><span class="sxs-lookup"><span data-stu-id="79c99-160">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="79c99-161">REG\_DWORD: savepassword</span><span class="sxs-lookup"><span data-stu-id="79c99-161">REG\_DWORD: SavePassword</span></span>

<span data-ttu-id="79c99-162">値: 0x0</span><span class="sxs-lookup"><span data-stu-id="79c99-162">Value: 0x0</span></span>

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="79c99-163">AD FS 2.0 のトークンのリプレイ</span><span class="sxs-lookup"><span data-stu-id="79c99-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="79c99-p108">AD FS 2.0 には、トークン リプレイ検出と呼ばれる機能が用意されています。この機能によって、同じトークンを使用する複数のトークン要求を検出して破棄できます。この機能が有効な場合は、同じトークンが複数回使用されることがなくなるため、WS-Federation パッシブ プロファイルと SAML WebSSO プロファイルの両方において認証要求の整合性が確保されます。</span><span class="sxs-lookup"><span data-stu-id="79c99-p108">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded. When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>

<span data-ttu-id="79c99-166">キオスクを使用する場合など、セキュリティが最も重視される状況では、この機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="79c99-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="79c99-167">トークンの再生検出の詳細については、「AD FS 2.0 のセキュリティで保護され[http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215)た計画と展開のためのベストプラクティス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79c99-167">For more information about token replay detection, see Best Practices for Secure Planning and Deployment of AD FS 2.0 at [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215).</span></span>

</div>

<div>

## <a name="external-user-access"></a><span data-ttu-id="79c99-168">外部ユーザー アクセス</span><span class="sxs-lookup"><span data-stu-id="79c99-168">External User Access</span></span>

<span data-ttu-id="79c99-169">外部ネットワークからの Lync の2要素認証をサポートするように AD FS プロキシまたはリバースプロキシを構成する方法については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="79c99-169">Configuring an AD FS Proxy or Reverse Proxy to support Lync two-factor authentication from external networks is not covered in these topics.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


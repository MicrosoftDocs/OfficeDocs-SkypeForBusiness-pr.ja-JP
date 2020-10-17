---
title: 'Lync Server 2013: クライアントブートストラップポリシーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 826f732f25996a9f8fcbd708f7e76157a5753a01
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512774"
---
# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a><span data-ttu-id="aafb0-102">Lync Server 2013 でのクライアントブートストラップポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="aafb0-102">Configuring client bootstrapping policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aafb0-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="aafb0-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="aafb0-104">グループポリシー管理コンソール (GPMC) とグループポリシーオブジェクトエディタは、グループポリシーの管理に使用するツールです。</span><span class="sxs-lookup"><span data-stu-id="aafb0-104">The Group Policy Management Console (GPMC) and the Group Policy Object Editor are tools that you use to manage Group Policy.</span></span> <span data-ttu-id="aafb0-105">Office グループポリシー管理用テンプレートに含まれるのは、ドメイン内のグループポリシーオブジェクトに対して構成するレジストリベースのポリシー設定が含まれている Lync 2013 admx (ADMX) および adml (ADML) 管理用テンプレートです。</span><span class="sxs-lookup"><span data-stu-id="aafb0-105">Included with the Office Group Policy Administrative Template are Lync 2013.admx (ADMX) and .adml (ADML) Administrative Templates, which contain the registry-based policy settings that you configure for Group Policy objects in the domain.</span></span> <span data-ttu-id="aafb0-106">ADML ファイルは、ADMX ファイルに対して言語固有の補完を備えています。</span><span class="sxs-lookup"><span data-stu-id="aafb0-106">ADML files are language-specific complements to ADMX files.</span></span> <span data-ttu-id="aafb0-107">各 ADMX および ADML ファイルには、1つの Office アプリケーションのポリシー設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="aafb0-107">Each ADMX and ADML file contains the policy settings for a single Office application.</span></span> <span data-ttu-id="aafb0-108">詳細については、Office 2013 のドキュメントの「Office 2013 管理用テンプレートファイル (ADMX, ADML)」を参照してください <https://go.microsoft.com/fwlink/p/?linkid=267516> 。</span><span class="sxs-lookup"><span data-stu-id="aafb0-108">For more information, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <https://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<span data-ttu-id="aafb0-109">Lync 2013 では、ユーザーが初めてサーバーにサインインする前に構成を考慮する必要があるクライアントブートストラップポリシーがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="aafb0-109">For Lync 2013, there are several client bootstrapping policies that you should consider configuring before users sign in to the server for the first time.</span></span> <span data-ttu-id="aafb0-110">たとえば、サインインが完了するまでクライアントが使用する既定のサーバーおよびセキュリティモード。</span><span class="sxs-lookup"><span data-stu-id="aafb0-110">For example, the default servers and security mode that the client should use until sign-in is complete.</span></span> <span data-ttu-id="aafb0-111">グループポリシーを使用して、ユーザーのコンピューターのレジストリでこれらの設定を行い、サインインしてから、サーバーからインバンドプロビジョニング設定を受信することができます。</span><span class="sxs-lookup"><span data-stu-id="aafb0-111">You can use Group Policy to establish these settings in users’ computer registries before they sign in and begin receiving in-band provisioning settings from the server.</span></span> <span data-ttu-id="aafb0-112">次の表に、Lync 2013 で使用できるグループポリシー設定を示します。</span><span class="sxs-lookup"><span data-stu-id="aafb0-112">The following table lists the Group Policy settings that are available for Lync 2013.</span></span>

### <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="aafb0-113">Lync 2013 のグループ ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="aafb0-113">Group Policy Settings for Lync 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aafb0-114">グループ ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="aafb0-114">Group Policy setting</span></span></th>
<th><span data-ttu-id="aafb0-115">説明</span><span class="sxs-lookup"><span data-stu-id="aafb0-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aafb0-116">サーバーを指定する</span><span class="sxs-lookup"><span data-stu-id="aafb0-116">Specify Server</span></span><br />
<span data-ttu-id="aafb0-117">ConfigurationMode</span><span class="sxs-lookup"><span data-stu-id="aafb0-117">(ConfigurationMode)</span></span></p></td>
<td><p><span data-ttu-id="aafb0-118">Lync 2013 がサインイン時に使用するトランスポートおよびサーバーを識別する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="aafb0-118">Specifies how Lync 2013 identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="aafb0-119">この設定では、以下のことを指定します。</span><span class="sxs-lookup"><span data-stu-id="aafb0-119">Within this setting, you specify the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="aafb0-120">ServerAddressExternal: 外部ファイアウォールの外側から接続する場合に、クライアントとフェデレーション連絡先が使用するサーバー名または IP アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="aafb0-120">ServerAddressExternal: Specifies the server name or IP address used by clients and federated contacts when connecting from outside the external firewall.</span></span></p></li>
<li><p><span data-ttu-id="aafb0-121">ServerAddressInternal: クライアントが組織のファイアウォールの内側から接続するときに使用されるサーバー名または IP アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="aafb0-121">ServerAddressInternal: Specifies the server name or IP address used when clients connect from inside the organization’s firewall.</span></span></p></li>
<li><p><span data-ttu-id="aafb0-122">Transport: 伝送制御プロトコル (TCP) またはトランスポート層セキュリティ (TLS) のどちらかを指定します。</span><span class="sxs-lookup"><span data-stu-id="aafb0-122">Transport: Specifies either Transmission Control Protocol (TCP) or Transport Layer Security (TLS).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aafb0-123">サポートされているその他のサーバーバージョン</span><span class="sxs-lookup"><span data-stu-id="aafb0-123">Additional server versions supported</span></span><br />
<span data-ttu-id="aafb0-124">(ConfiguredServerCheckValues)</span><span class="sxs-lookup"><span data-stu-id="aafb0-124">(ConfiguredServerCheckValues)</span></span></p></td>
<td><p><span data-ttu-id="aafb0-125">既定でサポートされているサーバーのバージョンに加えて、Lync Server 2013 がログオン先とするサーバーバージョンの名前の一覧をセミコロンで区切って指定します。</span><span class="sxs-lookup"><span data-stu-id="aafb0-125">Specifies a list of server version names separated by semi-colons that Lync Server 2013 will log on to, in addition to the server versions that are supported by default.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aafb0-126">サインイン失敗ログの自動アップロードを無効にする (Disableautomatic Sendtracing)</span><span class="sxs-lookup"><span data-stu-id="aafb0-126">Disable automatic upload of sign-in failure logs (DisableAutomaticSendTracing)</span></span></p></td>
<td><p><span data-ttu-id="aafb0-127">サインインエラーログを分析のために Lync Server に自動的にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="aafb0-127">Automatically uploads sign-in failure logs to Lync Server for analysis.</span></span> <span data-ttu-id="aafb0-128">サインインに成功した場合、ログは自動的にアップロードされません。</span><span class="sxs-lookup"><span data-stu-id="aafb0-128">No logs are automatically uploaded if sign-in is successful.</span></span> <span data-ttu-id="aafb0-129">このポリシーが構成されていない場合、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="aafb0-129">If this policy is not configured, the following happens:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="aafb0-130">Lync Online ユーザーの場合: サインイン失敗ログは自動的にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="aafb0-130">For Lync Online users: Sign-in failure logs are automatically uploaded.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="aafb0-131">Lync オンプレミスユーザーの場合: アップロードする前に、ユーザーに確認のダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="aafb0-131">For Lync on-premises users: A confirmation dialog box is shown to the user before upload.</span></span></p>
</dd>
</dl>
<p><span data-ttu-id="aafb0-132">この設定を無効にすると、lync オンプレミスと Lync Online の両方のユーザーのサインインログが Lync Server に自動的にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="aafb0-132">When this setting is disabled, sign-in logs are automatically uploaded to the Lync Server for both Lync on-premises and Lync Online users.</span></span> <span data-ttu-id="aafb0-133">この設定を有効にした場合、サインインログは自動的にアップロードされることはありません。</span><span class="sxs-lookup"><span data-stu-id="aafb0-133">When this setting is enabled, sign-in logs are never uploaded automatically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aafb0-134">SIP 接続の HTTP フォールバックを無効にする</span><span class="sxs-lookup"><span data-stu-id="aafb0-134">Disable HTTP fallback for SIP connection</span></span><br />
<span data-ttu-id="aafb0-135">(DisableHttpConnect)</span><span class="sxs-lookup"><span data-stu-id="aafb0-135">(DisableHttpConnect)</span></span></p></td>
<td><p><span data-ttu-id="aafb0-136">TLS または TCP が使用できない場合、Lync Server が HTTP を使用してサーバーに接続できないようにします。</span><span class="sxs-lookup"><span data-stu-id="aafb0-136">Prevents Lync Server from trying to connect to the server by using HTTP, if TLS or TCP are unavailable.</span></span> <span data-ttu-id="aafb0-137">既定では、Lync は最初に TLS または TCP を使用してサーバーに接続しようとし、次のどちらのトランスポート方法も成功しないと、Lync は HTTP を使用して接続しようとします。</span><span class="sxs-lookup"><span data-stu-id="aafb0-137">By default, Lync first attempts to connect to the server by using TLS or TCP and, if neither of these transport methods is successful, Lync tries to connect by using HTTP.</span></span> <span data-ttu-id="aafb0-138">このポリシーは、フォールバックの HTTP 接続試行を無効にするために使用します。</span><span class="sxs-lookup"><span data-stu-id="aafb0-138">Use this policy to disable the fallback HTTP connection attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aafb0-139">ログオン資格情報が必要</span><span class="sxs-lookup"><span data-stu-id="aafb0-139">Require logon credentials</span></span><br />
<span data-ttu-id="aafb0-140">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="aafb0-140">(DisableNTCredentials)</span></span></p></td>
<td><p><span data-ttu-id="aafb0-141">ユーザーは、SIP サーバーへのサインイン時に Windows 資格情報を自動的に使用するのではなく、Lync のログオン資格情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aafb0-141">Requires the user to provide logon credentials for Lync rather than automatically using Windows credentials during sign-in to a SIP server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aafb0-142">サーバーバージョンチェックを無効にする</span><span class="sxs-lookup"><span data-stu-id="aafb0-142">Disable server version check</span></span><br />
<span data-ttu-id="aafb0-143">(DisableServerCheck)</span><span class="sxs-lookup"><span data-stu-id="aafb0-143">(DisableServerCheck)</span></span></p></td>
<td><p><span data-ttu-id="aafb0-144">このポリシーを1に設定すると、Lync がサインインする前にサーバー名とバージョンを確認できなくなります。</span><span class="sxs-lookup"><span data-stu-id="aafb0-144">If you set this policy to 1, prevents Lync from checking the server name and version before signing in.</span></span> <span data-ttu-id="aafb0-145">既定では、Lync はサインインする前にこれらのチェックを行います。</span><span class="sxs-lookup"><span data-stu-id="aafb0-145">By default, Lync makes these checks before signing in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aafb0-146">アドレス帳サービスファイルをダウンロードするために BITS を使用できるようにする</span><span class="sxs-lookup"><span data-stu-id="aafb0-146">Enable using BITS to download Address Book Service files</span></span><br />
<span data-ttu-id="aafb0-147">(EnableBitsForGalDownload)</span><span class="sxs-lookup"><span data-stu-id="aafb0-147">(EnableBitsForGalDownload)</span></span></p></td>
<td><p><span data-ttu-id="aafb0-148">Lync でバックグラウンドインテリジェント転送サービス (BITS) を使用して、アドレス帳サービスのファイルをダウンロードできるようにします。</span><span class="sxs-lookup"><span data-stu-id="aafb0-148">Enables Lync to use Background Intelligent Transfer Service (BITS) to download the Address Book Services files.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aafb0-149">SIP セキュリティモードを構成する</span><span class="sxs-lookup"><span data-stu-id="aafb0-149">Configure SIP security mode</span></span><br />
<span data-ttu-id="aafb0-150">(EnableSIPHighSecurityMode)</span><span class="sxs-lookup"><span data-stu-id="aafb0-150">(EnableSIPHighSecurityMode)</span></span></p></td>
<td><p><span data-ttu-id="aafb0-151">Lync は、より安全にインスタントメッセージを送受信することができます。</span><span class="sxs-lookup"><span data-stu-id="aafb0-151">Enables Lync to send and receive instant messages more securely.</span></span> <span data-ttu-id="aafb0-152">このポリシーは、Windows .NET または Microsoft Exchange Server サービスに対して無効です。</span><span class="sxs-lookup"><span data-stu-id="aafb0-152">This policy has no effect on Windows .NET or Microsoft Exchange Server services.</span></span></p>
<p><span data-ttu-id="aafb0-153">このポリシー設定を構成しない場合、Lync は任意のトランスポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="aafb0-153">If you do not configure this policy setting, Lync can use any transport.</span></span> <span data-ttu-id="aafb0-154">ただし、TLS を使用せず、サーバーがユーザーを認証する場合は、Lync で NTLM 認証または Kerberos 認証のいずれかを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aafb0-154">But if it does not use TLS and if the server authenticates users, Lync must use either NTLM or Kerberos authentication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aafb0-155">グローバルアドレス帳のダウンロードの初期遅延</span><span class="sxs-lookup"><span data-stu-id="aafb0-155">Global Address Book Download Initial Delay</span></span><br />
<span data-ttu-id="aafb0-156">(GalDownloadInitialDelay)</span><span class="sxs-lookup"><span data-stu-id="aafb0-156">(GalDownloadInitialDelay)</span></span></p></td>
<td><p><span data-ttu-id="aafb0-157">グローバルアドレス一覧 (GAL) がダウンロードされるまでの期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="aafb0-157">Specifies the time period before a download of the global address list (GAL) occurs.</span></span> <span data-ttu-id="aafb0-158">既定値は60分です。これは、サーバーが0から60分の間のランダムな期間、GAL ファイルのダウンロードを遅延させることを意味します。</span><span class="sxs-lookup"><span data-stu-id="aafb0-158">The default value is 60 minutes, which means the server delays the download of GAL file for a random period of between 0 and 60 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aafb0-159">ユーザーが Microsoft Lync を実行できないようにする</span><span class="sxs-lookup"><span data-stu-id="aafb0-159">Prevent users from running Microsoft Lync</span></span><br />
<span data-ttu-id="aafb0-160">(PreventRun)</span><span class="sxs-lookup"><span data-stu-id="aafb0-160">(PreventRun)</span></span></p></td>
<td><p><span data-ttu-id="aafb0-161">ユーザーが Lync を実行できないようにします。</span><span class="sxs-lookup"><span data-stu-id="aafb0-161">Prevents users from running Lync.</span></span> <span data-ttu-id="aafb0-162">このポリシー設定は、コンピューターの構成とユーザーの構成の両方で構成できますが、コンピューターの構成のポリシー設定が優先されます。</span><span class="sxs-lookup"><span data-stu-id="aafb0-162">You can configure this policy setting under both Computer Configuration and User Configuration, but the policy setting under Computer Configuration takes precedence.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aafb0-163">ユーザーパスワードの保存を許可する</span><span class="sxs-lookup"><span data-stu-id="aafb0-163">Allow storage of user passwords</span></span><br />
<span data-ttu-id="aafb0-164">SavePassword</span><span class="sxs-lookup"><span data-stu-id="aafb0-164">(SavePassword)</span></span></p></td>
<td><p><span data-ttu-id="aafb0-165">Lync がパスワードを保存できるようにします。</span><span class="sxs-lookup"><span data-stu-id="aafb0-165">Enables Lync to store passwords.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aafb0-166">SIP 圧縮モードを構成する</span><span class="sxs-lookup"><span data-stu-id="aafb0-166">Configure SIP compression mode</span></span><br />
<span data-ttu-id="aafb0-167">(SipCompression)</span><span class="sxs-lookup"><span data-stu-id="aafb0-167">(SipCompression)</span></span></p></td>
<td><p><span data-ttu-id="aafb0-168">SIP 圧縮を有効にするタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="aafb0-168">Specifies when to turn on SIP compression.</span></span> <span data-ttu-id="aafb0-169">既定では、SIP 圧縮はアダプターの速度に基づいて有効になっています。</span><span class="sxs-lookup"><span data-stu-id="aafb0-169">By default, SIP compression is enabled based on the adapter speed.</span></span> <span data-ttu-id="aafb0-170">このポリシーを設定すると、サインインの時間が長くなる可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="aafb0-170">Note that setting this policy might cause an increase in sign-in time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aafb0-171">信頼されたドメインの一覧</span><span class="sxs-lookup"><span data-stu-id="aafb0-171">Trusted Domain List</span></span><br />
<span data-ttu-id="aafb0-172">TrustModelData</span><span class="sxs-lookup"><span data-stu-id="aafb0-172">(TrustModelData)</span></span></p></td>
<td><p><span data-ttu-id="aafb0-173">顧客 SIP ドメインのプレフィックスに一致しない信頼されたドメインを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="aafb0-173">Lists the trusted domains that do not match the prefix of the customer SIP domain.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aafb0-p113">サーバー上で構成されたポリシーは、ユーザーによって構成されたグループ ポリシー設定やクライアント オプションよりも優先されます。次の表に、競合が発生した場合の設定の優先順位をまとめます。</span><span class="sxs-lookup"><span data-stu-id="aafb0-p113">Policies configured on the server take precedence over Group Policy settings and client options configured by the user. The following table summarizes the order in which settings take precedence when a conflict occurs.</span></span>

### <a name="group-policy-precedence"></a><span data-ttu-id="aafb0-176">グループ ポリシーの優先順位</span><span class="sxs-lookup"><span data-stu-id="aafb0-176">Group Policy Precedence</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aafb0-177">Precedence</span><span class="sxs-lookup"><span data-stu-id="aafb0-177">Precedence</span></span></th>
<th><span data-ttu-id="aafb0-178">設定の場所と方法</span><span class="sxs-lookup"><span data-stu-id="aafb0-178">Location or Method of Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aafb0-179">1-d</span><span class="sxs-lookup"><span data-stu-id="aafb0-179">1</span></span></p></td>
<td><p><span data-ttu-id="aafb0-180">Lync Server 2013 インバンドプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="aafb0-180">Lync Server 2013 in-band provisioning</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aafb0-181">pbm-2</span><span class="sxs-lookup"><span data-stu-id="aafb0-181">2</span></span></p></td>
<td><p><span data-ttu-id="aafb0-182">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="aafb0-182">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aafb0-183">1/3</span><span class="sxs-lookup"><span data-stu-id="aafb0-183">3</span></span></p></td>
<td><p><span data-ttu-id="aafb0-184">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="aafb0-184">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aafb0-185">4 </span><span class="sxs-lookup"><span data-stu-id="aafb0-185">4</span></span></p></td>
<td><p><span data-ttu-id="aafb0-186">Lync 2013 の [Lync-オプション] ダイアログボックス</span><span class="sxs-lookup"><span data-stu-id="aafb0-186">The Lync - Options dialog box in Lync 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a><span data-ttu-id="aafb0-187">Lync 2013 管理用テンプレートファイルを使用してグループポリシー設定を定義するには</span><span class="sxs-lookup"><span data-stu-id="aafb0-187">To define Group Policy settings by using the Lync 2013 administrative template files</span></span>

1.  <span data-ttu-id="aafb0-188">すべての言語に依存しない ADMX ファイルを含むルートレベルのフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="aafb0-188">Create a root-level folder to contain all language-neutral ADMX files.</span></span> <span data-ttu-id="aafb0-189">たとえば、次の場所で、ドメインコントローラーの中央ストアのルートフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="aafb0-189">For example, create the root folder for the central store on your domain controller at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aafb0-190">この手順では、ドメイン内の複数のコンピューターを管理することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="aafb0-190">This procedure assumes that you want to manage multiple computers in your domain.</span></span> <span data-ttu-id="aafb0-191">この場合は、プライマリドメインコントローラーの Sysvol フォルダーにある中央ストアにテンプレートを格納します。</span><span class="sxs-lookup"><span data-stu-id="aafb0-191">In this case, you store the templates in a central store in the Sysvol folder on the primary domain controller.</span></span> <span data-ttu-id="aafb0-192">これはドメインの管理用テンプレートのためのレプリケートされた集中格納場所となります。</span><span class="sxs-lookup"><span data-stu-id="aafb0-192">This provides a replicated central storage location for domain Administrative Templates.</span></span>

    
    </div>

2.  <span data-ttu-id="aafb0-193">使用する言語ごとにサブフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="aafb0-193">Create a subfolder for each language that you’ll use.</span></span> <span data-ttu-id="aafb0-194">これらのサブフォルダーには、言語固有の ADML リソースファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="aafb0-194">These subfolders will contain the language-specific ADML resource files.</span></span> <span data-ttu-id="aafb0-195">たとえば、次の場所に米国英語 (EN-US) のサブフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="aafb0-195">For example, create a subfolder for United States English (EN-US) at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>


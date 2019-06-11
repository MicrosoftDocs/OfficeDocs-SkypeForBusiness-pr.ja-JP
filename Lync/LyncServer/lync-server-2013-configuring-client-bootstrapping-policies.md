---
title: 'Lync Server 2013: クライアントブートストラップポリシーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06119d5488b47adfe01a934aca9a55581feaf33e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a><span data-ttu-id="6f6bd-102">Lync Server 2013 でクライアントブートストラップポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="6f6bd-102">Configuring client bootstrapping policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f6bd-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="6f6bd-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="6f6bd-104">グループ ポリシー管理コンソール (GPMC) とグループ ポリシー オブジェクト エディターは、グループ ポリシーを管理するために使用するツールです。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-104">The Group Policy Management Console (GPMC) and the Group Policy Object Editor are tools that you use to manage Group Policy.</span></span> <span data-ttu-id="6f6bd-105">Office グループポリシー管理用テンプレートに含まれている Lync 2013 の管理用テンプレートには、ドメインのグループポリシーオブジェクト用に構成したレジストリベースのポリシー設定が含まれています。これには、adml (ADML) 管理用テンプレートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-105">Included with the Office Group Policy Administrative Template are Lync 2013.admx (ADMX) and .adml (ADML) Administrative Templates, which contain the registry-based policy settings that you configure for Group Policy objects in the domain.</span></span> <span data-ttu-id="6f6bd-106">ADML ファイルは、ADMX ファイルに対する言語固有の補完ファイルです。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-106">ADML files are language-specific complements to ADMX files.</span></span> <span data-ttu-id="6f6bd-107">それぞれの ADMX および ADML ファイルには、単一の Office アプリケーションに関するポリシー設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-107">Each ADMX and ADML file contains the policy settings for a single Office application.</span></span> <span data-ttu-id="6f6bd-108">詳細については、Office 2013 ドキュメントの「Office 2013 管理用テンプレートファイル (ADMX、ADML)」 <http://go.microsoft.com/fwlink/p/?linkid=267516>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-108">For more information, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<span data-ttu-id="6f6bd-109">Lync 2013 には、ユーザーが初めてサーバーにサインインする前に構成することを検討する必要がある、いくつかのクライアントブートストラップポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-109">For Lync 2013, there are several client bootstrapping policies that you should consider configuring before users sign in to the server for the first time.</span></span> <span data-ttu-id="6f6bd-110">たとえば、サインインが完了するまでクライアントで使用する既定のサーバーとセキュリティモードなどです。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-110">For example, the default servers and security mode that the client should use until sign-in is complete.</span></span> <span data-ttu-id="6f6bd-111">グループポリシーを使って、ユーザーのコンピューターのレジストリでこれらの設定を行ってから、サインインして、サーバーからインバンドのプロビジョニング設定を受信することができます。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-111">You can use Group Policy to establish these settings in users’ computer registries before they sign in and begin receiving in-band provisioning settings from the server.</span></span> <span data-ttu-id="6f6bd-112">次の表に、Lync 2013 で利用できるグループポリシー設定を示します。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-112">The following table lists the Group Policy settings that are available for Lync 2013.</span></span>

### <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="6f6bd-113">Lync 2013 のグループポリシー設定</span><span class="sxs-lookup"><span data-stu-id="6f6bd-113">Group Policy Settings for Lync 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f6bd-114">グループ ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="6f6bd-114">Group Policy setting</span></span></th>
<th><span data-ttu-id="6f6bd-115">説明</span><span class="sxs-lookup"><span data-stu-id="6f6bd-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f6bd-116">サーバーを指定する</span><span class="sxs-lookup"><span data-stu-id="6f6bd-116">Specify Server</span></span><br />
<span data-ttu-id="6f6bd-117">ConfigurationMode</span><span class="sxs-lookup"><span data-stu-id="6f6bd-117">(ConfigurationMode)</span></span></p></td>
<td><p><span data-ttu-id="6f6bd-118">サインイン時に使用するトランスポートとサーバーの識別2013方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-118">Specifies how Lync 2013 identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="6f6bd-119">この設定では、次の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-119">Within this setting, you specify the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6f6bd-120">ServerAddressExternal: 外部ファイアウォールの外側からの接続時に、フェデレーションからの連絡先とクライアントで使用されるサーバー名または IP アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-120">ServerAddressExternal: Specifies the server name or IP address used by clients and federated contacts when connecting from outside the external firewall.</span></span></p></li>
<li><p><span data-ttu-id="6f6bd-121">ServerAddressInternal: 組織ファイアウォールの内側にあるクライアントからの接続に使用されるサーバー名または IP アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-121">ServerAddressInternal: Specifies the server name or IP address used when clients connect from inside the organization’s firewall.</span></span></p></li>
<li><p><span data-ttu-id="6f6bd-122">Transport: 伝送制御プロトコル (TCP) またはトランスポート層セキュリティ (TLS) のいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-122">Transport: Specifies either Transmission Control Protocol (TCP) or Transport Layer Security (TLS).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f6bd-123">サポートされているその他のサーバーバージョン</span><span class="sxs-lookup"><span data-stu-id="6f6bd-123">Additional server versions supported</span></span><br />
<span data-ttu-id="6f6bd-124">(ConfiguredServerCheckValues)</span><span class="sxs-lookup"><span data-stu-id="6f6bd-124">(ConfiguredServerCheckValues)</span></span></p></td>
<td><p><span data-ttu-id="6f6bd-125">既定でサポートされているサーバーのバージョンに加えて、Lync Server 2013 がログオンするサーバーのバージョン名の一覧をセミコロンで区切って指定します。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-125">Specifies a list of server version names separated by semi-colons that Lync Server 2013 will log on to, in addition to the server versions that are supported by default.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f6bd-126">サインイン失敗ログの自動アップロードを無効にする (DisableAutomaticSendTracing)</span><span class="sxs-lookup"><span data-stu-id="6f6bd-126">Disable automatic upload of sign-in failure logs (DisableAutomaticSendTracing)</span></span></p></td>
<td><p><span data-ttu-id="6f6bd-127">サインインの失敗ログを、分析のために Lync Server に自動的にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-127">Automatically uploads sign-in failure logs to Lync Server for analysis.</span></span> <span data-ttu-id="6f6bd-128">サインインが成功した場合は、ログは自動的にアップロードされません。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-128">No logs are automatically uploaded if sign-in is successful.</span></span> <span data-ttu-id="6f6bd-129">このポリシーが構成されていない場合は、次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-129">If this policy is not configured, the following happens:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="6f6bd-130">Lync Online ユーザーの場合: サインインエラーログは、自動的にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-130">For Lync Online users: Sign-in failure logs are automatically uploaded.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="6f6bd-131">Lync オンプレミスユーザーの場合: アップロードする前に、ユーザーに確認のダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-131">For Lync on-premises users: A confirmation dialog box is shown to the user before upload.</span></span></p>
</dd>
</dl>
<p><span data-ttu-id="6f6bd-132">この設定が無効になっている場合、サインインログは lync オンプレミスと Lync Online の両方のユーザーの Lync サーバーに自動的にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-132">When this setting is disabled, sign-in logs are automatically uploaded to the Lync Server for both Lync on-premises and Lync Online users.</span></span> <span data-ttu-id="6f6bd-133">この設定を有効にすると、サインインログが自動的にアップロードされることはありません。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-133">When this setting is enabled, sign-in logs are never uploaded automatically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f6bd-134">SIP 接続の HTTP フォールバックを無効にする</span><span class="sxs-lookup"><span data-stu-id="6f6bd-134">Disable HTTP fallback for SIP connection</span></span><br />
<span data-ttu-id="6f6bd-135">(DisableHttpConnect)</span><span class="sxs-lookup"><span data-stu-id="6f6bd-135">(DisableHttpConnect)</span></span></p></td>
<td><p><span data-ttu-id="6f6bd-136">TLS または TCP が利用できない場合に、Lync Server が HTTP を使用してサーバーに接続するのを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-136">Prevents Lync Server from trying to connect to the server by using HTTP, if TLS or TCP are unavailable.</span></span> <span data-ttu-id="6f6bd-137">既定では、Lync は最初に TLS または TCP を使用してサーバーに接続しようとし、次のいずれのトランスポート方法も成功しなかった場合、Lync は HTTP を使って接続を試みます。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-137">By default, Lync first attempts to connect to the server by using TLS or TCP and, if neither of these transport methods is successful, Lync tries to connect by using HTTP.</span></span> <span data-ttu-id="6f6bd-138">このポリシーを使用して、フォールバック HTTP 接続の試行を無効にします。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-138">Use this policy to disable the fallback HTTP connection attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f6bd-139">ログオン資格情報を要求する</span><span class="sxs-lookup"><span data-stu-id="6f6bd-139">Require logon credentials</span></span><br />
<span data-ttu-id="6f6bd-140">(DisableNTCredentials)</span><span class="sxs-lookup"><span data-stu-id="6f6bd-140">(DisableNTCredentials)</span></span></p></td>
<td><p><span data-ttu-id="6f6bd-141">SIP サーバーへのサインイン時に、ユーザーが Lync のログオン資格情報を使って、自動的に Windows 資格情報を使用しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-141">Requires the user to provide logon credentials for Lync rather than automatically using Windows credentials during sign-in to a SIP server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f6bd-142">サーバーのバージョンチェックを無効にする</span><span class="sxs-lookup"><span data-stu-id="6f6bd-142">Disable server version check</span></span><br />
<span data-ttu-id="6f6bd-143">(DisableServerCheck)</span><span class="sxs-lookup"><span data-stu-id="6f6bd-143">(DisableServerCheck)</span></span></p></td>
<td><p><span data-ttu-id="6f6bd-144">このポリシーを1に設定すると、Lync がサインイン前にサーバー名とバージョンを確認できなくなります。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-144">If you set this policy to 1, prevents Lync from checking the server name and version before signing in.</span></span> <span data-ttu-id="6f6bd-145">既定では、サインイン前に Lync によってこれらのチェックが行われます。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-145">By default, Lync makes these checks before signing in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f6bd-146">BITS を使用してアドレス帳サービスファイルをダウンロードできるようにする</span><span class="sxs-lookup"><span data-stu-id="6f6bd-146">Enable using BITS to download Address Book Service files</span></span><br />
<span data-ttu-id="6f6bd-147">(EnableBitsForGalDownload)</span><span class="sxs-lookup"><span data-stu-id="6f6bd-147">(EnableBitsForGalDownload)</span></span></p></td>
<td><p><span data-ttu-id="6f6bd-148">Lync がバックグラウンドインテリジェント転送サービス (BITS) を使用して、アドレス帳サービスファイルをダウンロードできるようにします。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-148">Enables Lync to use Background Intelligent Transfer Service (BITS) to download the Address Book Services files.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f6bd-149">SIP セキュリティモードを構成する</span><span class="sxs-lookup"><span data-stu-id="6f6bd-149">Configure SIP security mode</span></span><br />
<span data-ttu-id="6f6bd-150">(EnableSIPHighSecurityMode)</span><span class="sxs-lookup"><span data-stu-id="6f6bd-150">(EnableSIPHighSecurityMode)</span></span></p></td>
<td><p><span data-ttu-id="6f6bd-151">Lync がインスタントメッセージの送受信をより安全に行えるようにします。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-151">Enables Lync to send and receive instant messages more securely.</span></span> <span data-ttu-id="6f6bd-152">このポリシーは、Windows .NET または Microsoft Exchange Server サービスに対して無効です。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-152">This policy has no effect on Windows .NET or Microsoft Exchange Server services.</span></span></p>
<p><span data-ttu-id="6f6bd-153">このポリシー設定を構成しないと、Lync で任意のトランスポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-153">If you do not configure this policy setting, Lync can use any transport.</span></span> <span data-ttu-id="6f6bd-154">ただし、TLS を使っておらず、サーバーがユーザーを認証する場合は、NTLM 認証または Kerberos 認証のいずれかを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-154">But if it does not use TLS and if the server authenticates users, Lync must use either NTLM or Kerberos authentication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f6bd-155">グローバルアドレス帳のダウンロードの最初の遅延</span><span class="sxs-lookup"><span data-stu-id="6f6bd-155">Global Address Book Download Initial Delay</span></span><br />
<span data-ttu-id="6f6bd-156">(GalDownloadInitialDelay)</span><span class="sxs-lookup"><span data-stu-id="6f6bd-156">(GalDownloadInitialDelay)</span></span></p></td>
<td><p><span data-ttu-id="6f6bd-p110">グローバル アドレス一覧 (GAL) のダウンロードが始まるまでの時間を指定します。既定値は 60 分です。つまり、サーバーでは GAL ファイルのダウンロードがランダムに 0 ～ 60 分間延期されます。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-p110">Specifies the time period before a download of the global address list (GAL) occurs. The default value is 60 minutes, which means the server delays the download of GAL file for a random period of between 0 and 60 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f6bd-159">ユーザーが Microsoft Lync を実行できないようにする</span><span class="sxs-lookup"><span data-stu-id="6f6bd-159">Prevent users from running Microsoft Lync</span></span><br />
<span data-ttu-id="6f6bd-160">(PreventRun)</span><span class="sxs-lookup"><span data-stu-id="6f6bd-160">(PreventRun)</span></span></p></td>
<td><p><span data-ttu-id="6f6bd-161">ユーザーが Lync を実行できないようにします。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-161">Prevents users from running Lync.</span></span> <span data-ttu-id="6f6bd-162">このポリシー設定は、コンピューターの構成とユーザーの構成の両方で構成できますが、コンピューターの構成のポリシー設定が優先されます。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-162">You can configure this policy setting under both Computer Configuration and User Configuration, but the policy setting under Computer Configuration takes precedence.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f6bd-163">ユーザーパスワードの保存を許可する</span><span class="sxs-lookup"><span data-stu-id="6f6bd-163">Allow storage of user passwords</span></span><br />
<span data-ttu-id="6f6bd-164">(SavePassword)</span><span class="sxs-lookup"><span data-stu-id="6f6bd-164">(SavePassword)</span></span></p></td>
<td><p><span data-ttu-id="6f6bd-165">Lync でパスワードを保存できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-165">Enables Lync to store passwords.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f6bd-166">SIP 圧縮モードを構成する</span><span class="sxs-lookup"><span data-stu-id="6f6bd-166">Configure SIP compression mode</span></span><br />
<span data-ttu-id="6f6bd-167">(SipCompression)</span><span class="sxs-lookup"><span data-stu-id="6f6bd-167">(SipCompression)</span></span></p></td>
<td><p><span data-ttu-id="6f6bd-p112">SIP 圧縮をオンにするときを定義します。既定では、アダプターのスピードに基づいて SIP 圧縮が有効化されます。このポリシーを設定すると、サインインの時間が長くなる可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-p112">Specifies when to turn on SIP compression. By default, SIP compression is enabled based on the adapter speed. Note that setting this policy might cause an increase in sign-in time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f6bd-171">信頼済みドメインリスト</span><span class="sxs-lookup"><span data-stu-id="6f6bd-171">Trusted Domain List</span></span><br />
<span data-ttu-id="6f6bd-172">TrustModelData</span><span class="sxs-lookup"><span data-stu-id="6f6bd-172">(TrustModelData)</span></span></p></td>
<td><p><span data-ttu-id="6f6bd-173">ユーザーの SIP ドメインのプレフィックスに一致しない信頼されたドメインをリストします。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-173">Lists the trusted domains that do not match the prefix of the customer SIP domain.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6f6bd-p113">サーバー上で構成されたポリシーは、ユーザーによって構成されたグループ ポリシー設定やクライアント オプションよりも優先されます。次の表に、競合が発生した場合の設定の優先順位をまとめます。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-p113">Policies configured on the server take precedence over Group Policy settings and client options configured by the user. The following table summarizes the order in which settings take precedence when a conflict occurs.</span></span>

### <a name="group-policy-precedence"></a><span data-ttu-id="6f6bd-176">グループ ポリシーの優先順位</span><span class="sxs-lookup"><span data-stu-id="6f6bd-176">Group Policy Precedence</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f6bd-177">優先順位</span><span class="sxs-lookup"><span data-stu-id="6f6bd-177">Precedence</span></span></th>
<th><span data-ttu-id="6f6bd-178">設定の場所と方法</span><span class="sxs-lookup"><span data-stu-id="6f6bd-178">Location or Method of Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f6bd-179">1</span><span class="sxs-lookup"><span data-stu-id="6f6bd-179">1</span></span></p></td>
<td><p><span data-ttu-id="6f6bd-180">Lync Server 2013 インバンドプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="6f6bd-180">Lync Server 2013 in-band provisioning</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f6bd-181">2</span><span class="sxs-lookup"><span data-stu-id="6f6bd-181">2</span></span></p></td>
<td><p><span data-ttu-id="6f6bd-182">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="6f6bd-182">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f6bd-183">3</span><span class="sxs-lookup"><span data-stu-id="6f6bd-183">3</span></span></p></td>
<td><p><span data-ttu-id="6f6bd-184">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="6f6bd-184">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f6bd-185">4</span><span class="sxs-lookup"><span data-stu-id="6f6bd-185">4</span></span></p></td>
<td><p><span data-ttu-id="6f6bd-186">Lync 2013 の [Lync-オプション] ダイアログボックス</span><span class="sxs-lookup"><span data-stu-id="6f6bd-186">The Lync - Options dialog box in Lync 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a><span data-ttu-id="6f6bd-187">Lync 2013 管理用テンプレートファイルを使用してグループポリシー設定を定義するには</span><span class="sxs-lookup"><span data-stu-id="6f6bd-187">To define Group Policy settings by using the Lync 2013 administrative template files</span></span>

1.  <span data-ttu-id="6f6bd-p114">言語に依存しないすべての ADMX ファイルを含めるルートレベル フォルダーを作成します。たとえば、ドメイン コントローラーの次の場所で、中央ストア用のルート フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-p114">Create a root-level folder to contain all language-neutral ADMX files. For example, create the root folder for the central store on your domain controller at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6f6bd-p115">この手順では、ドメインで複数のコンピューターを管理することを想定しています。この場合、テンプレートをプライマリ ドメイン コントローラーの Sysvol フォルダーにある中央ストアに保存します。これにより、ドメインの管理用テンプレート用のレプリケートされた中央の保存場所が提供されます。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-p115">This procedure assumes that you want to manage multiple computers in your domain. In this case, you store the templates in a central store in the Sysvol folder on the primary domain controller. This provides a replicated central storage location for domain Administrative Templates.</span></span>

    
    </div>

2.  <span data-ttu-id="6f6bd-p116">使用する言語ごとのサブフォルダーを作成します。これらのサブフォルダーには、言語固有の ADML リソース ファイルが含められます。たとえば、米国英語 (EN-US) 用のサブフォルダーを次の場所で作成します。</span><span class="sxs-lookup"><span data-stu-id="6f6bd-p116">Create a subfolder for each language that you’ll use. These subfolders will contain the language-specific ADML resource files. For example, create a subfolder for United States English (EN-US) at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>


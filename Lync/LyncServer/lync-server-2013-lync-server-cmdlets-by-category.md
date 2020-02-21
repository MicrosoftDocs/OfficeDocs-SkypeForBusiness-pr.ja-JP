---
title: 'Lync Server 2013: Lync Server のコマンドレット (カテゴリ別)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets by category
ms:assetid: 4ce274d7-b0ec-40b8-b85e-9a0613916ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398306(v=OCS.15)
ms:contentKeyID: 48184106
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68764952ebfe2a45895e480d923d76a108fdda8e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-by-category"></a><span data-ttu-id="cb5b2-102">Lync Server 2013 のコマンドレット (カテゴリ別)</span><span class="sxs-lookup"><span data-stu-id="cb5b2-102">Lync Server 2013 cmdlets by category</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb5b2-103">_**トピックの最終更新日:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="cb5b2-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<span data-ttu-id="cb5b2-104">Microsoft Lync Server 2013 には、管理者が Lync Server をコマンドラインから管理できるように特別に設計された、ほぼ550のコマンドレットが付属しています。</span><span class="sxs-lookup"><span data-stu-id="cb5b2-104">Microsoft Lync Server 2013 ships with almost 550 cmdlets specifically designed to allow administrators to manage Lync Server from the command line.</span></span> <span data-ttu-id="cb5b2-105">コマンドレットには、Lync Server 管理シェルからアクセスします。</span><span class="sxs-lookup"><span data-stu-id="cb5b2-105">You access the cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="cb5b2-106">コマンドラインから次のようなコマンドを入力すると、コマンドレットのヘルプを直接取得できます。</span><span class="sxs-lookup"><span data-stu-id="cb5b2-106">You can retrieve help on a cmdlet directly from the command line by typing a command similar to the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="cb5b2-107">上記のコマンドは、 **set-csvoicepolicy**コマンドレットで利用可能なすべてのヘルプを取得します。</span><span class="sxs-lookup"><span data-stu-id="cb5b2-107">The preceding command will retrieve all the help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="cb5b2-108">ヘルプを取得するコマンドレットの名前を使用して、Set-csvoicepolicy への参照を**追加**します。</span><span class="sxs-lookup"><span data-stu-id="cb5b2-108">Substitute the reference to **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>

<span data-ttu-id="cb5b2-109">Microsoft Lync Server 2013 の管理に使用できるコマンドレットの完全な一覧を取得するには、Lync Server 管理シェルコマンドプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="cb5b2-109">To retrieve a full list of cmdlets available for managing Microsoft Lync Server 2013, type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Command * -Module Lync -CommandType cmdlet

<span data-ttu-id="cb5b2-110">必要なコマンドレットがわからない場合は、コマンドレットとヘルプトピックのカテゴリ別の一覧も提供しています。</span><span class="sxs-lookup"><span data-stu-id="cb5b2-110">If you are unsure which cmdlets you need, we have also provided a categorized list of cmdlets and their help topics.</span></span> <span data-ttu-id="cb5b2-111">一部のコマンドレットは複数のカテゴリに表示されることがわかります。これは、製品の複数の領域に適用されるので、意図的に使用されていました。</span><span class="sxs-lookup"><span data-stu-id="cb5b2-111">You will find that some of the cmdlets show up in more than one category, which was intentional as they apply to multiple areas of the product.</span></span> <span data-ttu-id="cb5b2-112">カテゴリの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cb5b2-112">The following is a list of categories:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="cb5b2-113">Skype for Business のコマンドレットリファレンスが docs.microsoft.com に移動されました。</span><span class="sxs-lookup"><span data-stu-id="cb5b2-113">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="cb5b2-114">以下のリンクをクリックすると、新しい docs.microsoft.com ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cb5b2-114">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="cb5b2-115">これで、GitHub を通じてコミュニティの投稿に使用できるようになるコンテンツが公開されました。</span><span class="sxs-lookup"><span data-stu-id="cb5b2-115">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="cb5b2-116">投稿に興味はありますか?</span><span class="sxs-lookup"><span data-stu-id="cb5b2-116">Interested in contributing?</span></span> <span data-ttu-id="cb5b2-117">ここでは、リポジトリ内の README を確認してください。<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="cb5b2-117">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cb5b2-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="cb5b2-118">In This Section</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb5b2-119"><a href="lync-server-2013-user-management-cmdlets.md">Lync Server 2013 でのユーザー管理のコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="cb5b2-119"><a href="lync-server-2013-user-management-cmdlets.md">User management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cb5b2-120"><a href="lync-server-2013-voice-application-cmdlets.md">Lync Server 2013 の音声アプリケーションのコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="cb5b2-120"><a href="lync-server-2013-voice-application-cmdlets.md">Voice application cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb5b2-121"><a href="lync-server-2013-client-management-cmdlets.md">Lync Server 2013 のクライアント管理のコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="cb5b2-121"><a href="lync-server-2013-client-management-cmdlets.md">Client management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cb5b2-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Lync Server 2013 の高度なエンタープライズ Voip のコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="cb5b2-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Advanced Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb5b2-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">Lync Server 2013 の IM およびプレゼンスのコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="cb5b2-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">IM and presence cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cb5b2-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Lync Server 2013 の PSTN 接続のコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="cb5b2-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">PSTN connectivity cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb5b2-125"><a href="lync-server-2013-conferencing-cmdlets.md">Lync Server 2013 での会議のコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="cb5b2-125"><a href="lync-server-2013-conferencing-cmdlets.md">Conferencing cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cb5b2-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Lync Server 2013 の電話およびデバイスのコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="cb5b2-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Phones and devices cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb5b2-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Lync Server 2013 のインフラストラクチャと展開のコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="cb5b2-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Infrastructure and deployment cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cb5b2-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Lync Server 2013 での移行と共存のコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="cb5b2-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Migration and coexistence cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb5b2-129"><a href="lync-server-2013-security-cmdlets.md">Lync Server 2013 のセキュリティコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="cb5b2-129"><a href="lync-server-2013-security-cmdlets.md">Security cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cb5b2-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync server 管理シェルの構成のコマンドレット (Lync Server 2013)</a></span><span class="sxs-lookup"><span data-stu-id="cb5b2-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server Management Shell configuration cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb5b2-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Lync Server 2013 のサーバーの役割およびサービスのコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="cb5b2-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Server roles and services cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cb5b2-132"><a href="lync-server-2013-mobility-cmdlets.md">Lync Server 2013 でのモビリティのコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="cb5b2-132"><a href="lync-server-2013-mobility-cmdlets.md">Mobility cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb5b2-133"><a href="lync-server-2013-application-management-cmdlets.md">Lync Server 2013 のアプリケーション管理のコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="cb5b2-133"><a href="lync-server-2013-application-management-cmdlets.md">Application management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cb5b2-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Lync Server 2013 の常設チャットサーバーのコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="cb5b2-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Persistent Chat Server cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb5b2-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Lync Server 2013 のフェデレーションと外部アクセスのコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="cb5b2-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Federation and external access cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cb5b2-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Lync Server 2013 での集中ログのコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="cb5b2-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Centralized Logging cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb5b2-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Lync Server 2013 のエンタープライズ Voip のコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="cb5b2-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cb5b2-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb5b2-138">See Also</span></span>


[<span data-ttu-id="cb5b2-139">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="cb5b2-139">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


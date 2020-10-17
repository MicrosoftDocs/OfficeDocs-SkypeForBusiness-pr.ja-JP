---
title: 'Lync Server 2013: Lync Server のコマンドレット (カテゴリ別)'
description: 'Lync Server 2013: Lync Server コマンドレット (カテゴリ別)'
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
ms.openlocfilehash: df562bd11d54c9ecda4fe3d6172ed1d8bd2627d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571873"
---
# <a name="lync-server-2013-cmdlets-by-category"></a><span data-ttu-id="2aa8f-103">Lync Server 2013 のコマンドレット (カテゴリ別)</span><span class="sxs-lookup"><span data-stu-id="2aa8f-103">Lync Server 2013 cmdlets by category</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2aa8f-104">_**トピックの最終更新日:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="2aa8f-104">_**Topic Last Modified:** 2017-09-20_</span></span>

<span data-ttu-id="2aa8f-105">Microsoft Lync Server 2013 には、管理者が Lync Server をコマンドラインから管理できるように特別に設計された、ほぼ550のコマンドレットが付属しています。</span><span class="sxs-lookup"><span data-stu-id="2aa8f-105">Microsoft Lync Server 2013 ships with almost 550 cmdlets specifically designed to allow administrators to manage Lync Server from the command line.</span></span> <span data-ttu-id="2aa8f-106">コマンドレットには、Lync Server 管理シェルからアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2aa8f-106">You access the cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="2aa8f-107">コマンドラインから次のようなコマンドを入力すると、コマンドレットのヘルプを直接取得できます。</span><span class="sxs-lookup"><span data-stu-id="2aa8f-107">You can retrieve help on a cmdlet directly from the command line by typing a command similar to the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="2aa8f-108">上記のコマンドは、 **set-csvoicepolicy** コマンドレットで利用可能なすべてのヘルプを取得します。</span><span class="sxs-lookup"><span data-stu-id="2aa8f-108">The preceding command will retrieve all the help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="2aa8f-109">ヘルプを取得するコマンドレットの名前を使用して、Set-csvoicepolicy への参照を **追加** します。</span><span class="sxs-lookup"><span data-stu-id="2aa8f-109">Substitute the reference to **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>

<span data-ttu-id="2aa8f-110">Microsoft Lync Server 2013 の管理に使用できるコマンドレットの完全な一覧を取得するには、Lync Server 管理シェルコマンドプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2aa8f-110">To retrieve a full list of cmdlets available for managing Microsoft Lync Server 2013, type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Command * -Module Lync -CommandType cmdlet

<span data-ttu-id="2aa8f-111">必要なコマンドレットがわからない場合は、コマンドレットとヘルプトピックのカテゴリ別の一覧も提供しています。</span><span class="sxs-lookup"><span data-stu-id="2aa8f-111">If you are unsure which cmdlets you need, we have also provided a categorized list of cmdlets and their help topics.</span></span> <span data-ttu-id="2aa8f-112">一部のコマンドレットは複数のカテゴリに表示されることがわかります。これは、製品の複数の領域に適用されるので、意図的に使用されていました。</span><span class="sxs-lookup"><span data-stu-id="2aa8f-112">You will find that some of the cmdlets show up in more than one category, which was intentional as they apply to multiple areas of the product.</span></span> <span data-ttu-id="2aa8f-113">カテゴリの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2aa8f-113">The following is a list of categories:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="2aa8f-114">Skype for Business のコマンドレットリファレンスが docs.microsoft.com に移動されました。</span><span class="sxs-lookup"><span data-stu-id="2aa8f-114">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="2aa8f-115">以下のリンクをクリックすると、新しい docs.microsoft.com ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="2aa8f-115">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="2aa8f-116">これで、GitHub を通じてコミュニティの投稿に使用できるようになるコンテンツが公開されました。</span><span class="sxs-lookup"><span data-stu-id="2aa8f-116">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="2aa8f-117">投稿に興味はありますか?</span><span class="sxs-lookup"><span data-stu-id="2aa8f-117">Interested in contributing?</span></span> <span data-ttu-id="2aa8f-118">ここでは、リポジトリ内の README を確認してください。 <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="2aa8f-118">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2aa8f-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2aa8f-119">In This Section</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2aa8f-120"><a href="lync-server-2013-user-management-cmdlets.md">Lync Server 2013 でのユーザー管理のコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="2aa8f-120"><a href="lync-server-2013-user-management-cmdlets.md">User management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2aa8f-121"><a href="lync-server-2013-voice-application-cmdlets.md">Lync Server 2013 の音声アプリケーションのコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="2aa8f-121"><a href="lync-server-2013-voice-application-cmdlets.md">Voice application cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2aa8f-122"><a href="lync-server-2013-client-management-cmdlets.md">Lync Server 2013 のクライアント管理のコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="2aa8f-122"><a href="lync-server-2013-client-management-cmdlets.md">Client management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2aa8f-123"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Lync Server 2013 の高度なエンタープライズ Voip のコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="2aa8f-123"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Advanced Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2aa8f-124"><a href="lync-server-2013-im-and-presence-cmdlets.md">Lync Server 2013 の IM およびプレゼンスのコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="2aa8f-124"><a href="lync-server-2013-im-and-presence-cmdlets.md">IM and presence cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2aa8f-125"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Lync Server 2013 の PSTN 接続のコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="2aa8f-125"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">PSTN connectivity cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2aa8f-126"><a href="lync-server-2013-conferencing-cmdlets.md">Lync Server 2013 での会議のコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="2aa8f-126"><a href="lync-server-2013-conferencing-cmdlets.md">Conferencing cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2aa8f-127"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Lync Server 2013 の電話およびデバイスのコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="2aa8f-127"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Phones and devices cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2aa8f-128"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Lync Server 2013 のインフラストラクチャと展開のコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="2aa8f-128"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Infrastructure and deployment cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2aa8f-129"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Lync Server 2013 での移行と共存のコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="2aa8f-129"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Migration and coexistence cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2aa8f-130"><a href="lync-server-2013-security-cmdlets.md">Lync Server 2013 のセキュリティコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="2aa8f-130"><a href="lync-server-2013-security-cmdlets.md">Security cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2aa8f-131"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync server 管理シェルの構成のコマンドレット (Lync Server 2013)</a></span><span class="sxs-lookup"><span data-stu-id="2aa8f-131"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server Management Shell configuration cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2aa8f-132"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Lync Server 2013 のサーバーの役割およびサービスのコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="2aa8f-132"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Server roles and services cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2aa8f-133"><a href="lync-server-2013-mobility-cmdlets.md">Lync Server 2013 でのモビリティのコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="2aa8f-133"><a href="lync-server-2013-mobility-cmdlets.md">Mobility cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2aa8f-134"><a href="lync-server-2013-application-management-cmdlets.md">Lync Server 2013 のアプリケーション管理のコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="2aa8f-134"><a href="lync-server-2013-application-management-cmdlets.md">Application management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2aa8f-135"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Lync Server 2013 の常設チャットサーバーのコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="2aa8f-135"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Persistent Chat Server cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2aa8f-136"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Lync Server 2013 のフェデレーションと外部アクセスのコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="2aa8f-136"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Federation and external access cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2aa8f-137"><a href="lync-server-2013-centralized-logging-cmdlets.md">Lync Server 2013 での集中ログのコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="2aa8f-137"><a href="lync-server-2013-centralized-logging-cmdlets.md">Centralized Logging cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2aa8f-138"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Lync Server 2013 のエンタープライズ Voip のコマンドレット</a></span><span class="sxs-lookup"><span data-stu-id="2aa8f-138"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2aa8f-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="2aa8f-139">See Also</span></span>


[<span data-ttu-id="2aa8f-140">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="2aa8f-140">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


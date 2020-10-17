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
# <a name="lync-server-2013-cmdlets-by-category"></a>Lync Server 2013 のコマンドレット (カテゴリ別)

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2017-09-20_

Microsoft Lync Server 2013 には、管理者が Lync Server をコマンドラインから管理できるように特別に設計された、ほぼ550のコマンドレットが付属しています。 コマンドレットには、Lync Server 管理シェルからアクセスします。 コマンドラインから次のようなコマンドを入力すると、コマンドレットのヘルプを直接取得できます。

    Get-Help New-CsVoicePolicy -Full

上記のコマンドは、 **set-csvoicepolicy** コマンドレットで利用可能なすべてのヘルプを取得します。 ヘルプを取得するコマンドレットの名前を使用して、Set-csvoicepolicy への参照を **追加** します。

Microsoft Lync Server 2013 の管理に使用できるコマンドレットの完全な一覧を取得するには、Lync Server 管理シェルコマンドプロンプトで次のように入力します。

    Get-Command * -Module Lync -CommandType cmdlet

必要なコマンドレットがわからない場合は、コマンドレットとヘルプトピックのカテゴリ別の一覧も提供しています。 一部のコマンドレットは複数のカテゴリに表示されることがわかります。これは、製品の複数の領域に適用されるので、意図的に使用されていました。 カテゴリの一覧を次に示します。

<div>


> [!NOTE]
> Skype for Business のコマンドレットリファレンスが docs.microsoft.com に移動されました。 以下のリンクをクリックすると、新しい docs.microsoft.com ページに移動します。 これで、GitHub を通じてコミュニティの投稿に使用できるようになるコンテンツが公開されました。 投稿に興味はありますか? ここでは、リポジトリ内の README を確認してください。 <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-user-management-cmdlets.md">Lync Server 2013 でのユーザー管理のコマンドレット</a></p></td>
<td><p><a href="lync-server-2013-voice-application-cmdlets.md">Lync Server 2013 の音声アプリケーションのコマンドレット</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-client-management-cmdlets.md">Lync Server 2013 のクライアント管理のコマンドレット</a></p></td>
<td><p><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Lync Server 2013 の高度なエンタープライズ Voip のコマンドレット</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-im-and-presence-cmdlets.md">Lync Server 2013 の IM およびプレゼンスのコマンドレット</a></p></td>
<td><p><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Lync Server 2013 の PSTN 接続のコマンドレット</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencing-cmdlets.md">Lync Server 2013 での会議のコマンドレット</a></p></td>
<td><p><a href="lync-server-2013-phones-and-devices-cmdlets.md">Lync Server 2013 の電話およびデバイスのコマンドレット</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Lync Server 2013 のインフラストラクチャと展開のコマンドレット</a></p></td>
<td><p><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Lync Server 2013 での移行と共存のコマンドレット</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-security-cmdlets.md">Lync Server 2013 のセキュリティコマンドレット</a></p></td>
<td><p><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync server 管理シェルの構成のコマンドレット (Lync Server 2013)</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Lync Server 2013 のサーバーの役割およびサービスのコマンドレット</a></p></td>
<td><p><a href="lync-server-2013-mobility-cmdlets.md">Lync Server 2013 でのモビリティのコマンドレット</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-application-management-cmdlets.md">Lync Server 2013 のアプリケーション管理のコマンドレット</a></p></td>
<td><p><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Lync Server 2013 の常設チャットサーバーのコマンドレット</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Lync Server 2013 のフェデレーションと外部アクセスのコマンドレット</a></p></td>
<td><p><a href="lync-server-2013-centralized-logging-cmdlets.md">Lync Server 2013 での集中ログのコマンドレット</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-enterprise-voice-cmdlets.md">Lync Server 2013 のエンタープライズ Voip のコマンドレット</a></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server PowerShell ブログ](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

